SELECT DISTINCT product_name, base_price
FROM fact_events
JOIN dim_products ON dim_products.product_code = fact_events.product_code
WHERE base_price > 500 AND promo_type= "BOGOF";
