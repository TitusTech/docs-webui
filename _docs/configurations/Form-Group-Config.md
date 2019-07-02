---
title: Form-Group-Config
permalink: /docs/configurations/Form-Group-Config/
---

### Description
Overrides the `webui-lib` form groups css. It can also be used to configure the css of individual form groups.

# Config File
`src/data/${ItemType}/formGroup.json`

# Example
```{
"Group": [{
    "Group-2": [{
      "label": {
        "position": "relative",
        "bottom": "3em",
        "color": "red"
      },
      "container": {
        "border-style": "solid !important",
        "border-radius": "5px",
        "border-top": "2em solid",
        "border-bottom": "1px",
        "border-left": "1px",
        "border-right": "1px",
        "border-color": "#7BA22F !important",
        "padding": "1em !important",
        "box-shadow": "0px 0px 0.5px 0.5px #C9C9C9 !important",
        "display": "block !important"
      }
    }],
    "default": [{
      "label": {
        "position": "relative",
        "bottom": "3em",
        "color": "white"
      },
      "container": {
        "border-style": "solid !important",
        "border-radius": "5px",
        "border-top": "2em solid",
        "border-bottom": "1px",
        "border-left": "1px",
        "border-right": "1px",
        "border-color": "#2399e5 !important",
        "padding": "1em !important",
        "box-shadow": "0px 0px 0.5px 0.5px #C9C9C9 !important",
        "display": "block !important"
      }
   }]
}]
}
```

# Form Group Configurations

| Configuration | Meaning |
| ------------- | ------------- |
| `Group-n` | Where `n` is a the position/index of the group. Specifies the form group that have the configuration |
| `default` | The default configuration or the fallback configuration for unconfigured groups. If not defined, the `webui-lib` css will be used for the form groups |
| `label` | The css configuration for the label of the form group |
| `container` | The css configuration for the container of the form group |