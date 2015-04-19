---
layout: page
title: Settings

sidebar_link: true
---

Machiavelli defines settings using [RailsConfig](https://github.com/railsconfig/rails_config). Settings can be pulled from [various places](https://github.com/railsconfig/rails_config#common-config-file) in the `config/` structure, allowing differentiation between environments in a clear, concise format. 

Backends
--------

Machiavelli supports one or more backends `origins` defined in an array with the following format: 

 * `(id)` - the id used to uniquely identify the origin (for Vaultaire, this **must** be the origin_id
 * `title` - The name used in graphs to prefix the metric name
 * `source` - the name of the source library. If none, specify the parent library `Source`
 * `store` - the name of the source library. 
 * `store_settings` - a hash of settings, as defined by each store library. Check class documentation, or the `initialize` method for `(mandatory|optional)_param` calls. 


**Sample Settings**

```
origins:
        "Simple": {
                store: "Simple",
                source: "Source",
                title: "Simple",
                store_settings: {
                        url: "http://localhost:4567",
                }
        }
```

Redis Cache
-------------

Machiavelli automatically assumes redis host, port, and a key-space to use. These can be overwritten in the settings file. 

 * `metrics_key` - the namespace for which all keys will be generated. default: "Machiavelli.Metrics"
 * `redis_host` - hostname for the redis instance. default: "127.0.0.1"
 * `redis_port` - port for the redis instance. default: "6379"


Other settings
----------------

Machiavelli has a bunch of settings that can be overridden by setting preferred values in the settings file

 * `autoplay` - When `stop=now`, every `step` seconds, call for an updated metric window. Allows for live graph updates. default: true. 
 * `disable_tooltips` - Disables helper tool-tips (note, some tool-tips mandatory, and will not be removed when this is set). default: false/undefined
 * `horizon_color` - hex colour for Horizon graphs. default: "#006d2c"
 

