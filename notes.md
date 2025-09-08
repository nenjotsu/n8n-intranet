```bash
docker run -d \
  --name langflow \
  --restart unless-stopped \
  -p 7860:7860 \
  --volume langflow-data:/app/langflow \
  langflowai/langflow:latest

docker run -d \
  --name langflow \
  --restart always \
  --network n8n-intranet_n8n-ollama-network \
  -p 7860:7860 \
  --env-file .env \
  --volume langflow-data:/app/langflow \
  langflowai/langflow:latest
```