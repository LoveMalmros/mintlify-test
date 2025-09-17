## Query Parameters
From `/third-party/dashboards`, you receive the field `meta.available_query_params`.  

This field lists the query parameters you can pass into embedded dashboards.  
For example:  

```
?filter=true
```

adds a filter to the embedded page.

---

## Preview Widgets
Some dashboards include widgets that can be embedded individually via the `url` field.  

- Use the `url`-field in your `<iframe />`
- These widgets can also return their raw data more on this in [Raw widgets](/Raw%20widgets).

---

## Custom Fields
Dashboards may also have **custom fields**, which can be used for special integrations.  

For example, if you want dashboards to appear in a specific order, you can add a custom field like `sorting_index` to each dashboard. Then, you can sort them programmatically according to that index.  

These custom fields are set and managed by the Homepal administrator.

---

## Link Validity
Dashboard links are valid for **3600 seconds** (1 hour).
