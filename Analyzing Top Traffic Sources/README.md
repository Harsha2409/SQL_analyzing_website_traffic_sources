--- sql
SELECT
	ws.utm_content,
    COUNT(DISTINCT ws.website_session_id) AS sessions,
    COUNT(DISTINCT o.order_id) AS orders,
    100*COUNT(DISTINCT o.order_id)/COUNT(DISTINCT ws.website_session_id) AS session_to_order_conv_rt
FROM website_sessions AS ws
	LEFT JOIN orders AS o
		ON o.website_session_id = ws.website_session_id
GROUP BY 1
ORDER BY 4 DESC;
---

![](https://github.com/Harsha2409/SQL_analyzing_website_traffic_sources/blob/main/Analyzing%20Top%20Traffic%20Sources/result.PNG)
