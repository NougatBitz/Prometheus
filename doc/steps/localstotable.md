---
description: >-
  This Step will wrap all Locals in each scope into a table. (Not recommended
  due to memory issues)
---

# LocalsToTable

### Settings

| Name         | type    | description                                                                                                            |
| ------------ | ------- | ---------------------------------------------------------------------------------------------------------------------- |
| Treshold     | number  | The relative amount of scopes that will be affected                                                                    |
| RemapIndices | boolean | When this option is set to true, new table indices will be generated instead of using the id's generated by the parser |

### Example

{% code title="in.lua" %}
```lua
local a, b, c = 1, 2, 3
print(a + b + c)
```
{% endcode %}

{% code title="out.lua" %}
```lua
-- Treshold = 1
-- RemapIndices = true
local G = {}
G[3], G[1], G[2] = 1, 2, 3
print(G[3] + (G[1] + G[2]))
```
{% endcode %}