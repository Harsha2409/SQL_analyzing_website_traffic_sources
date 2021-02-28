``` sql
SELECT
	utm_source,
    utm_campaign,
    http_referer,
    COUNT(DISTINCT website_session_id) AS number_of_sessions
FROM website_sessions
WHERE created_at < '2012-04-12'
GROUP BY
	utm_source,
    utm_campaign,
    http_referer
ORDER BY number_of_sessions DESC

```

![](https://github.com/Harsha2409/SQL_analyzing_website_traffic_sources/blob/main/Finding%20Top%20Traffic%20Sources/result.PNG)
