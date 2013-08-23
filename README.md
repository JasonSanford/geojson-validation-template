## GeoJSON Validation Template

Use this template to add validation, via http://geojsonlint.com, to your repo.

### Running the script

There is a `validate_geojson` script in the root of the repo. Run it.

    $ ./validate_geojson 
    Testing ./a_directory/a_nested_directory/this_is_invalid.geojson
        Invalid GeoJSON
    Testing ./a_directory/a_nested_directory/this_is_valid.geojson
        Valid GeoJSON
    Testing ./a_directory/this_is_invalid.geojson
        Invalid GeoJSON
    Testing ./a_directory/this_is_valid.geojson
        Valid GeoJSON
    Testing ./this_is_valid.geojson
        Valid GeoJSON
    5 files checked. 2 failures.

This script crawls the repo's directory structure looking for `*.geojson` files and validates them via a `POST` to `http://geojsonlint.com/validate`. Upon completion, the failure count is printed.

### Continuous Integration

To help with continuous integration things like [Travis CI](https://travis-ci.org/), the process exits with a status of `0` if all items are valid and `1` if one or more items aren't, triggering a fail or pass of your build.
