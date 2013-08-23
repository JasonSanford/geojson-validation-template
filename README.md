## GeoJSON Validation Template

Use this template to add validation, via http://geojsonlint.com, to your repo.

### Running the script

There is a `test_geojson` script in the root of the repo. Run it.

    ./test_geojson

This script crawls the repo's directory structure looking for `*.geojson` files and validates them via a `POST` to `http://geojsonlint.com/validate`. Upon completion the failure count is printed. Also, to help with continuous deployment things like [Travis CI](https://travis-ci.org/), the process exits with a status of `0` if all items are valid and `1` if one or more items aren't.