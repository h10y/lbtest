# Load Balancing Shiny App

Original source: <https://github.com/rstudio/py-shiny/blob/7ba8f90a44ee25f41aa8c258eceeba6807e0017a/examples/load_balance/app.py>

Examples explained: <https://github.com/analythium/shiny-load-balancing>

- [Load Balancing Shiny App](#load-balancing-shiny-app)
  - [Python](#python)
  - [R](#r)
  - [Python Shinylive](#python-shinylive)
  - [R Shinylive](#r-shinylive)
  - [Serving Shinylive on GitHub Pages](#serving-shinylive-on-github-pages)

## Python

See the [`py-shiny`](./py-shiny/) folder.

## R

See the [`r-shiny`](./r-shiny/) folder.

## Python Shinylive

Create Python Shinylive version following <https://github.com/posit-dev/py-shinylive>:

```bash
# Export static files
shinylive export py-shiny/app py-shinylive

# Serve contents, visit http://localhost:8080
python3 -m http.server --directory py-shinylive 8080
```

## R Shinylive

Create R Shinylive version following <https://posit-dev.github.io/r-shinylive/>:

```bash
# Export static files
R -q -e "shinylive::export('r-shiny/app', 'r-shinylive')"

# Serve contents, visit http://localhost:8080
R -q -e "httpuv::runStaticServer('r-shinylive', port=8080)"
```

## Serving Shinylive on GitHub Pages

Serving Shinylive apps on GitHub Pages (from `docs` folder on the `main` branch).

```bash
# Cleanup
rm -rf docs/py-shinylive docs/r-shinylive

# Copy files
cp -r r-shinylive docs/ && cp -r py-shinylive docs/

# Render HTML from markdown
pandoc -s -f markdown -t html5 -o "docs/index.html" "index.md"
```
