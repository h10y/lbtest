# Load balancing test app: R

Run the app interactively:

```bash
# Change directory
cd r-shiny

# Install dependencies
R -q -e "install.packages('deps');deps::install(ask=FALSE)"

# Run the app, visit http://localhost:8080
R -q -e "shiny::runApp('app', port=8080)"
```

Pull and run Docker image:

```bash
docker pull ghcr.io/h10y/lbtest/r-shiny:latest
docker run --rm -p 8080:3838 ghcr.io/h10y/lbtest/r-shiny:latest
```

Containerized version:

```bash
# Change directory
cd r-shiny

# If on MacOS X, set this
export DOCKER_DEFAULT_PLATFORM=linux/amd64

# Specify tag
export TAG=lbtest/r-shiny:latest

# Build image
docker build -t $TAG .

# Run image, visit http://localhost:8080
docker run --rm -p 8080:3838 $TAG
```
