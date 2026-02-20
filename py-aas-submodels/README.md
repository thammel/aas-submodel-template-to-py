# py-aas-submodels - Submodels Repository

**py-aas-submodels** is a collection of submodel templates based python classes, which were generated automatically
using the **aas-sm-to-py** tool.
## Regenerating published submodels

Use the repository script below to regenerate all submodels from the
`published` directory of
[`admin-shell-io/submodel-templates`](https://github.com/admin-shell-io/submodel-templates):

```bash
python py-aas-submodels/regenerate_submodels.py
```

The script:
- Collects every `.json` template below `published/**`.
- Generates Python classes via `aas-sm-to-py`.
- Applies file-name normalization/replacement for generated Python modules.
- Logs any conversion failures to `py-aas-submodels/generation_failures.log`.

A GitHub Actions workflow (`.github/workflows/regenerate-submodels.yml`) runs this
automatically whenever files under `aas-sm-to-py/**` change on `main`, and daily
(on schedule) to pick up newly published submodels.
