# Smart Factory Anomaly Explainer

Minimal config to run the project.

---

## 1. Environment Variables

### Core

- `HYDRAULIC_DATA_DIR`  
  Path to the folder containing the hydraulic dataset `.txt` files, e.g.:

  ```bash
  HYDRAULIC_DATA_DIR=/path/to/data/condition+monitoring+of+hydraulic+systems


This folder should contain:

* `PS1.txt`, `PS2.txt`, `PS3.txt`, `PS4.txt`, `PS5.txt`, `PS6.txt`
* `EPS1.txt`, `FS1.txt`, `FS2.txt`
* `TS1.txt`, `TS2.txt`, `TS3.txt`, `TS4.txt`
* `VS1.txt`, `CE.txt`, `CP.txt`, `SE.txt`
* `profile.txt`

If not set, the code defaults to:

```text
<project_root>/data/condition+monitoring+of+hydraulic+systems
```

* `OLLAMA_HOST`
  URL of the Ollama server.

  ```bash
  # default if not set
  OLLAMA_HOST=http://localhost:11434
  ```

* `OLLAMA_MODEL`
  Name of the Ollama model to use, e.g.:

  ```bash
  # example
  OLLAMA_MODEL=llama3
  ```

---

## 2. Local Run

```bash
# example (PowerShell)
set HYDRAULIC_DATA_DIR=C:\path\to\data\condition+monitoring+of+hydraulic+systems
set OLLAMA_HOST=http://localhost:11434
set OLLAMA_MODEL=llama3

python smart_factory_anomaly_explainer.py
```

---

## 3. Docker

### Build

```bash
docker build -t smart-factory-anomaly-explainer .
```

### Run (Docker Desktop on Windows/macOS)

```bash
docker run --rm ^
  -e HYDRAULIC_DATA_DIR=/app/data/condition+monitoring+of+hydraulic+systems ^
  -e OLLAMA_HOST=http://host.docker.internal:11434 ^
  -e OLLAMA_MODEL=llama3 ^
  smart-factory-anomaly-explainer
```

### Run (Linux, host network)

```bash
docker run --rm \
  --network=host \
  -e HYDRAULIC_DATA_DIR=/app/data/condition+monitoring+of+hydraulic+systems \
  -e OLLAMA_HOST=http://localhost:11434 \
  -e OLLAMA_MODEL=llama3 \
  smart-factory-anomaly-explainer
```

```
::contentReference[oaicite:0]{index=0}
```
