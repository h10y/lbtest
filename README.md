# Load Balancing Shiny App

Original source: <https://github.com/rstudio/py-shiny/blob/7ba8f90a44ee25f41aa8c258eceeba6807e0017a/examples/load_balance/app.py>

Examples explained: <https://github.com/analythium/shiny-load-balancing>

## For R

1. Install libraries with `R -q -e "install.packages('deps');deps::install()"` in the r folder
2. Run the app with `R -q -e "shiny::runApp(port=8080)"`

## For Python

1. Install libraries with `pip install -r requirements.txt` in the python folder
2. Run the app with `shiny run --reload --port 8080`

## Shinylive

Create Python shinylive version following <https://github.com/posit-dev/py-shinylive>:

```bash
cd shiny-apps/hello-shiny
# cd shiny-apps/load-balancing
# cd shiny-apps/bananas
shinylive export python py-shinylive
python3 -m http.server --directory py-shinylive 8008
```

Create R shinylive version following <https://posit-dev.github.io/r-shinylive/>:

```bash
cd shiny-apps/hello-shiny
# cd shiny-apps/load-balancing
# cd shiny-apps/bananas
R -q -e 'shinylive::export("r", "r-shinylive")'
R -q -e 'httpuv::runStaticServer("r-shinylive", port=8008)'
```
