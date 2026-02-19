# OpenWebUI
## Maintenance

To Update:
```
docker pull ghcr.io/open-webui/open-webui:cuda
```
```
docker rm -f open-webui
```
```
docker run -d -p 3000:8080 \
  --device nvidia.com/gpu=all \
  --add-host=host.docker.internal:host-gateway \
  -e SCARF_NO_ANALYTICS=True \
  -e DO_NOT_TRACK=True \
  -e OLLAMA_MAX_LOADED_MODELS=1 \
  -v open-webui:/app/backend/data \
  --name open-webui \
  --restart always \
  ghcr.io/open-webui/open-webui:cuda
```