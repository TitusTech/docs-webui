---
title: Production Planning Config
permalink: /docs/configurations/Production-Planning-Config/
---

### Config File

`src/data/ProductionPlanning/settings.json`


### Example
```
    {"settings":
        [
            {"type": "employeeHasMissingSkill", 
            "config": {
                "color": "#FF69B4", "label": "Employee skill missing"
            }
            },
            {"type": "multiple", 
            "config": {
                "color": "#FF0000", "label": "Multiple"
            }
            },
            {"type": "finished", 
            "config": {
                "color": "#D3D3D3", "label": "Finished"
            }
            }
        ]
    }
```

### Steps config

Config for displaying p-steps in item details

| Field | Type | Meaning |
| ------------- | ------------- | ------------- |
| `type`| `string` | Hard constraint name and/or Status ID |
| `color `| `string` | Color of the task box |
| `label` | `string` | Hard constraint name and/or Status Description |
