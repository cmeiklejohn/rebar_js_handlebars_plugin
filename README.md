# Rebar JS Handlebars Plugin

Handlebars support during rebar compilation.

## Installation

Specify ```rebar_js_handlebars_plugin``` as a dependency in your ```rebar.config```.

```erlang
{deps, [
       {rebar_js_handlebars_plugin, ".*",
        {git, "git://github.com/cmeiklejohn/rebar_js_handlebars_plugin.git", {branch, "master"}}}
]}.
```

Then, configure as a plugin in your ```rebar.config```.

```erlang
{plugins, [rebar_js_handlebars_plugin]}.
```

## Configuration

Example usage:

```erlang
{js_minispade, [
    {doc_root,   "priv/assets/javascripts"},
    {out_dir,    "priv/www/javascripts"},
    {target,     "Ember.TEMPLATES"},
    {compiler,   "Ember.Handlebars.compile"},
    {templates,  [{"templates", ["models"]}]}
]}.
```

Produces the following for each input, in one concatenated javascript file called templates.js.

```javascript
Ember.TEMPLATES['models'] = Ember.Handlebars.compile('<h1>models</h1>').
```
