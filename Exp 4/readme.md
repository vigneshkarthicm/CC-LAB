# Experiment 4 – GAE Launcher: Launch Web Applications

## Title
Use GAE Launcher to Launch Web Applications

## Aim
To use the GAE launcher to configure and launch web applications on Google App Engine.

---

## Requirements
| Item | Details |
|------|---------|
| Cloud Platform | Google App Engine (GAE) |
| SDK | Google Cloud SDK / GAE SDK |
| Configuration | app.yaml |
| Runtime | python27 (static file serving) |
| Files | index.html, style.css |

---

## Introduction
**Google App Engine (GAE)** provides a platform to host and serve web applications in the cloud. The **GAE SDK** includes a local development server (`dev_appserver.py`) and a launcher to test apps locally before deploying. The `app.yaml` file is the core configuration file that defines the runtime, URL handlers, and static file mappings.

---

## Project Structure
```
Exp 4/
├── app.yaml           ← App Engine configuration
├── deploy.txt         ← Deployment commands
└── www/
    ├── index.html     ← Main web page
    └── css/
        └── style.css  ← Stylesheet
```

---

## Configuration – app.yaml

The `app.yaml` file:
- Specifies `runtime: python27` for a Python 2.7 static app.
- Maps `/` to `www/index.html`.
- Maps all other URLs to files under `www/`.

```yaml
runtime: python27
api_version: 1
threadsafe: true

handlers:
- url: /
  static_files: www/index.html
  upload: www/index.html

- url: /(.*)
  static_files: www/\1
  upload: www/(.*)
```

---

## Web Page – www/index.html

A simple static HTML page:
```html
<html>
<head>
    <title>Hello, world!</title>
    <link rel="stylesheet" type="text/css" href="/css/style.css">
</head>
<body>
    <h1>Hello, world!</h1>
    <p>This is a simple static HTML file served from Google App Engine.</p>
</body>
</html>
```

---

## Launching Locally

```bash
dev_appserver.py app.yaml
```

Access at: `http://localhost:8080/`

---

## Deployment to Google App Engine

```bash
gcloud app deploy
gcloud app browse
```

See `deploy.txt` for full deployment steps.

---

## Expected Output
When the app is running (locally or deployed):

```
Hello, world!

This is a simple static HTML file that will be served from Google App Engine.
```

---

## Files
| File | Description |
|------|-------------|
| `app.yaml` | App Engine application configuration |
| `deploy.txt` | Cloud SDK deployment commands |
| `www/index.html` | Static web page served by GAE |
| `www/css/style.css` | Stylesheet for the web page |
| `output.txt` | Simulated deployment and browser output |

---

## Result
The web application was successfully configured using `app.yaml` and launched using the GAE workflow. The application serves a static HTML page accessible via the browser.
