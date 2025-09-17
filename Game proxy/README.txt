# Game Proxy - Quickstart for Railway

ENV VARIABLES (set in Railway):
- PROXY_TARGET (required) : full URL of the backend you want proxied, e.g. https://example-game-server.com
- MOUNT_PATH (optional) : path where proxy is mounted. default '/proxy'
- PROXY_ALL (optional) : 'true' to proxy all incoming routes to target (use carefully)
- PROXY_PREFIX (optional) : prefix to strip from proxied path (default '/')
- ENABLE_BASIC_AUTH (optional) : 'true' to force basic auth
- BASIC_USER / BASIC_PASS (optional) : credentials if basic auth is enabled
- CACHE_MAX_AGE (optional) : static asset cache seconds, default 300
- RATE_MAX (optional) : requests per rate window (default 200)
- SERVE_STATIC (optional) : 'true' to serve ./public/index.html at root

Deploy:
1. Push this repo to GitHub.
2. In Railway, create a new project, connect your GitHub repo, and set the above env vars.
3. Railway will detect Node, run `npm install` and launch using the Procfile.
4. Test: visit your Railway domain and call the mount path:
   https://your-railway-app.up.railway.app/proxy/path/to/resource
