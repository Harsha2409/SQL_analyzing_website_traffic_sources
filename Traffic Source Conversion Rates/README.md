``` sql

SELECT
	COUNT(DISTINCT ws.website_session_id) AS sessions,
    COUNT(DISTINCT o.order_id) AS orders,
    100*COUNT(DISTINCT o.order_id)/COUNT(DISTINCT ws.website_session_id) AS session_to_order_convr_rt
FROM website_sessions AS ws
	LEFT JOIN orders AS o
		ON o.website_session_id = ws.website_session_id
WHERE ws.created_at < '2012-04-12'
	AND utm_source = 'gsearch'
    AND utm_campaign = 'nonbrand'

```

![](https://github.com/Harsha2409/SQL_analyzing_website_traffic_sources/blob/main/Traffic%20Source%20Conversion%20Rates/result.PNG)
