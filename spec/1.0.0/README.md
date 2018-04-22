# Greenlight Config Spec

## Data Structure & File Format

Config files are required to be saved in `UTF-8` encoding, other encodings are forbidden. Allowed formats are limited to [`JSON`][json] & [`YAML`][yaml].

### File Naming

Acceptable file name must match the following pattern:

```regex
^\.?greenlight\.(json|ya?ml|rc){1}$
```

###### Example

- [`.greenlight.json`](#json-example)
- [`.greenlight.yml`](#yaml-example)

---

### `greenlight.json`

```json
{
  "version": "1.0.0",
  "plugins": {}
}
```

name        | type     | required | default | description                                      
----------- | -------- | -------- | ------- | -------------------------------------------------
**version** | `String` | 🗸        | `-`     | Spec version. Format must follow [semver][]      
**plugins** | `Object` | 🗸        | `-`     | List of [Plugins](#plugins) to enable / configure

### `plugins`

```json
{
  "plugins": {
    "foo": true,
    "eslint": {
      "enabled": true,
      "paths": "!node_modules/**",
      "settings": {
        "foo": "bar"
      }
    },
    "csslint": {
      "enabled": true,
      "paths": [
        "!test/**",
        "!node_modules/**"
      ]
    }
  }
}
```

> Plugins are declared as key/value pairs, where `value` can either be a `boolean` (enable / disable), or an `object` allowing for further configuration:

name         | type           | required | default | description                         
------------ | -------------- | -------- | ------- | ------------------------------------
**enabled**  | `Boolean`      | ✗        | `true`  | Flag to enable/disable the plugin   
**paths**    | `String or Array` | ✗        | `-`     | Path(s) to include / exclude in scan
**settings** | `Object`       | ✗        | `-`     | Plugin specific settings            

---

###### JSON Example

> ```json
> {
>   "version": "1.1.0",
>   "plugins": {
>     "foo": {
>       "enabled": true,
>       "paths": "!node_modules",
>       "settings": {
>         "foo": "bar"
>       }
>     },
>     "bar": {
>       "enabled": true,
>       "paths": ["!node_modules"],
>       "settings": {
>         "foo": "bar"
>       }
>     },
>     "baz": true
>   }
> }
> ```

###### YAML Example

> ```yml
> version: 1.1.0
>
> plugins:
>   foo:
>     enabled: true
>     paths: !node_modules
>     settings:
>       foo: "bar"
>
>   bar:
>     enabled: true
>     paths:
>       - !node_modules
>     settings:
>       foo: bar
>
>   baz: true
> ```

[json]: https://www.json.org/

[semver]: https://semver.org

[yaml]: http://www.yaml.org/
