SELECT dp.product_name, dp.category,
(SUM(fe.quantity_sold_after_promo * fe.base_price) - SUM(fe.quantity_sold_before_promo* fe.base_price)) / SUM(fe.quantity_sold_after_promo * fe.base_price) *100 AS IR_percentage
FROM dim_products dp
JOIN fact_events fe ON dp.product_code = fe.product_code
GROUP BY dp.product_name, dp.category
ORDER BY IR_percentage DESC
LIMIT 5;
