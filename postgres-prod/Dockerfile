FROM postgres:16.2-bullseye

# Update apt and install PostGIS (will install PostgreSQL as a dependency)
RUN apt-get update \
    && apt-get install -y postgis \
    && apt-get autoremove --purge -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

