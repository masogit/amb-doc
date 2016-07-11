# AM Browser Document Online Help

Build AM Browser document by mkdocs

### Prerequisite

- Install git
- Install mkdocs from `http://www.mkdocs.org/`

### Build

Mkdocs can generate static html pages in `site` folder: 

```
mkdocs build
```
Or overwrite existing `site` folder
```
mkdocs build --clean
```

### Test

Mkdocs support start local web server to preview document pages:

```
mkdocs serve
```