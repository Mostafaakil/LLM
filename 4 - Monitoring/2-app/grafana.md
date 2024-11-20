SELECT
  relevance,
  COUNT(*) as count
FROM conversations
WHERE timestamp BETWEEN $__timeFrom()  AND  $__timeTo()
GROUP BY relevance
ORDER BY count DESC 

SELECT SUM(openai_cost)
FROM conversations

SELECT
  model_used,
  COUNT(*) as count
FROM conversations
GROUP BY model_used

SELECT
  timestamp AS time,
  response_time
FROM conversations
ORDER BY timestamp

SELECT
  timestamp AS time,
  question,
  answer,
  relevance
FROM conversations
ORDER BY timestamp DESC
LIMIT 8