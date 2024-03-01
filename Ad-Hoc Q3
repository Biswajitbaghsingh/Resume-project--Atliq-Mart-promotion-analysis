WITH PRE_PROMO_REVENUE AS ( 
SELECT
    dc.campaign_name, 
    ROUND(SUM(f.base_price * f.quantity_sold_before_promo) / 1000000,2) AS total_revenue_before_promo 
FROM
    dim_campaigns dc
LEFT JOIN
    fact_events f ON dc.campaign_id = f.campaign_id
 GROUP BY 
    dc.campaign_name
),
POST_PROMO_REVENUE AS (
 SELECT 
     dc.campaign_name,
     SUM(
     CASE 
         WHEN promo_type = '50% OFF' THEN base_price * 0.5 * f.quantity_sold_after_promo
         WHEN promo_type = '25% OFF' THEN base_price * 0.75 * f.quantity_sold_after_promo
		 WHEN promo_type = '33% OFF' THEN base_price * 0.67 * f.quantity_sold_after_promo
         WHEN promo_type = 'BOGOF' THEN base_price * f.quantity_sold_after_promo 
         WHEN promo_type = '500 Cashback' THEN (base_price - 500) * f.quantity_sold_after_promo
         ELSE base_price * f.quantity_sold_after_promo
	 END
	)/1000000 AS total_revenue_after_promo
    FROM 
        fact_events f
    LEFT JOIN 
		dim_campaigns dc ON f.campaign_id = dc.campaign_id
	GROUP BY 
        dc.campaign_name
)
SELECT pre.campaign_name,
       pre.total_revenue_before_promo,
       post.total_revenue_after_promo
FROM PRE_PROMO_REVENUE pre
JOIN POST_PROMO_REVENUE post ON pre.campaign_name = post.campaign_name; 
