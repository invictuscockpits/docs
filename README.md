# Invictus Cockpits Documentation

Source for [docs.invictuscockpits.com](https://docs.invictuscockpits.com), built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) and deployed to GitHub Pages on every push to `main`.

## Structure

Each product gets a top-level folder under `docs/`, and each doc set (wiki) for that product gets a subfolder:

```
docs/
  cockpit-manager/
    user-guide/        AIM Cockpit Manager user guide
  hotas-configurator/
    user-guide/        HOTAS Configurator (Gen 4) user guide
  joystick-probe/
    user-guide/        AIM Joystick Probe user guide
```

To add a new doc set (for example a developer guide), create a sibling folder like `cockpit-manager/dev-guide/` and add it to the `nav` section of `mkdocs.yml`.

## Editing

Pages are plain Markdown. Images live in an `images/` folder next to the pages that use them. Push to `main` and the site rebuilds automatically.

## Local preview

```
pip install mkdocs-material
mkdocs serve
```

Then open http://127.0.0.1:8000.
