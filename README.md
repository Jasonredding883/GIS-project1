# GIS-project1

This repository is set up for GIS + data analytics work in Python. The recommended way to install the heavy GIS dependencies is via conda-forge (conda or mamba). If you prefer a virtualenv/pip approach, instructions are below — but note some packages may require system libraries and may fail to build without conda.

## Clone the repo
git clone https://github.com/Jasonredding883/GIS-project1
cd GIS-project1

## Recommended: Create environment with conda (conda-forge)
1. Install mamba (fast conda replacement) if you don't have it:
   - conda install -n base -c conda-forge mamba
2. Create the environment from environment.yml:
   - mamba env create -f environment.yml
3. Activate:
   - conda activate gis-project1

This will install geopandas, rasterio, fiona, pyproj and their binary dependencies from conda-forge.

## Alternative: Use virtualenv + pip
1. python -m venv venv
2. source venv/bin/activate   # or venv\Scripts\activate on Windows
3. pip install --upgrade pip setuptools wheel
4. pip install -r requirements.txt

Warning: geopandas, rasterio, fiona, and some other spatial libs often fail to build from source on many systems. If pip fails, use conda-forge.

## Optional: Docker (reproducible container)
You can build an image with conda-forge installed packages. Example Dockerfile snippet is in Dockerfile.sample.

Build:
docker build -t gis-project1 .
Run (Jupyter example):
docker run -p 8888:8888 gis-project1

## Notes
- Use conda-forge for the smoothest install of GIS packages (GDAL, GEOS, PROJ, etc.).
- If you need GPU-enabled packages or specialized versions, let me know and I’ll tailor the environment.
- Tell me if you want any additional packages (e.g., geoplot, keplergl, pydeck, snowflake connector, bigquery, etc.)
