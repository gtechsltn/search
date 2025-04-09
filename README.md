# Google Search + AI Search

## Google Search: To get articles from the 5 days ago

**To get articles from the last 5 days ago (meaning articles created exactly 5 days ago)**

Set:

From: April 4, 2025

To: April 8, 2025

```
site:genk.vn after:2025-04-04 before:2025-04-08
```


## T-SQL: This will return articles created exactly 5 days ago
```
SELECT *
FROM Articles
WHERE CAST(CreatedDate AS DATE) = CAST(DATEADD(DAY, -5, GETDATE()) AS DATE)
```

## T-SQL: This will return articles from now to the last 5 days ago
```
SELECT *
FROM Articles
WHERE CreatedDate >= DATEADD(DAY, -5, GETDATE())
```

## T-SQL: articles created between 5 and 4 days ago (strict 5th day)
```
SELECT *
FROM Articles
WHERE CreatedDate >= DATEADD(DAY, -5, CAST(GETDATE() AS DATE))
  AND CreatedDate < DATEADD(DAY, -4, CAST(GETDATE() AS DATE))
```
