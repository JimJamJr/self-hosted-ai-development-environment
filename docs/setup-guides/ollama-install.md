# Ollama Installation

1. Open CasaOs
2. Go to App Store
3. Find Ollama
4. Install applicable Ollama container
5. Verify

Go to:
```bash
# if using server ip
http://<server-ip>:11434

# if using tailscale
http://100.x.x.x:11434
```
Expected return
```bash
Ollama is running
```
6. Pull models
```bash
docker exec -it ollama ollama pull qwen2.5-coder
docker exec -it ollama ollama pull llama3.2
```
