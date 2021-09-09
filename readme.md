# NVP Website

This is the source code for the website of the Dutch psychonomic society, or the Nederlandse Vereniging voor Psychonomie (NVP).


## Requirements

This site is built with [Pelican](https://docs.getpelican.com/en/latest/), currently using 4.6.0.


## Build instructions

In the `src` folder, run the following.


First recreate the output folders and copy static resources to the output.

```
rm -Rf output/*
mkdir output
cp -R static/* output
rm -Rf img
mkdir img
```

Build the menu from `sitemap.yaml` (if changed).

```
python build-menu.py
```

Build for local test:

```
pelican -s pelicanconf.py --fatal errors
cp output/index/index.html output/index.html
cp -R img output/
```

Build for upload:

```
pelican -s publishconf.py
cp output/index/index.html output/index.html
cp -R img output/
```

Start a local webserver for testing:

```
cd output
python -m http.server
cd ..
```
