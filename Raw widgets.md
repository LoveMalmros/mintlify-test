Preview widget don't have to be rendered in an `<iframe />`. From the `preview_widgets`-field from /third-party/dashboards you have the possibility to
fetch the widgets "raw" response. This means that you get a JSON-response that you can render 
in the way you prefer in your App. 

## How?
After fetching from the /third-party/dashboards endpoint you can get a url that is
for fetching a widgets "raw" data.
You get the url in `preview_widgets.raw.url` and then you need to authorize yourself with the headers from
`preview_widgets.raw.headers`. [API-reference](/api-reference/fetches-one-raw-api-access-widget)


## Widget Data Responses

Widgets can have multiple settings, which means their results may vary depending on configuration. Below are key scenarios and fields you should be aware of.

---

### Status Handling
If `status.broken = true`, the response will return `null`.

---

### Data Response Structure
The main response is returned in the `data` field, which is a list of items. Each item has a `title` and a `data` array.  

- The **first item** in the list is always the *segment* (except for `KEY_FIGURE` widgets).  
- Each `data` entry can contain either strings (labels) or numbers (values).  

**Example 1:**
```json
"title": "Real estate",
"data": [
  "Real estate 1",
  "Real estate 2",
  "Real estate 3"
]
```

**Example 2:**
```json
"title": "Reported errands",
"data": [
  200,
  302,
  123
]
```

This means:
- **Real estate 1** → 200 reported errands  
- **Real estate 2** → 302 reported errands, etc.  

Each item also includes a `data_type` field, indicating whether the values are strings or numbers.

---

### Comparative Data
If the widget compares values across different time periods, comparative results appear in the `comparative_data` field.  

- The structure matches the `data` field.  
- The `comparative_display_type` field defines how values are displayed:  
  - `VALUE`: raw values from the comparative period  
  - `PERCENTAGE`: percentage differences relative to that period  

---

### Widget Type (`meta.type`)
The `meta.type` field specifies the type of widget returned.  

- For **`KEY_FIGURE` widgets**:  
  - The response includes only one item in the `data` list.  
  - That item’s value can be accessed directly at `data[0].data[0]`.  

- For **all other widgets**:  
  - The structure follows the standard `data` and `comparative_data` format described above.  
