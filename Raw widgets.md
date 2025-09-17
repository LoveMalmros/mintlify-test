From the preview_widgets field from /third-party/dashboards you have the possibility to
fetch the widgets "raw" response. This means that you get a JSON-response that you can render 
in the way you prefer in your App. 

## Where?
From the dashboards endpoint use the url in `preview_widgets.raw.url` and the headers from
`preview_widgets.raw.headers`.

## Documentation
You find the documentation for the endpoint under the Widgets section.

## Important 
Since the widgets can have multiple settings the results from the widgets can vary a little bit.
Here we cover some of the cases, that you should take into consideration.

### Status
If `status.broken=true`. Then data will return null.

### The data response
The data response is returned in a list in the field `data`. This consists of items which have labels or data.
The first segment is always the segment (unless it is a KEY_FIGURE widget). The data field in each of these items
consists of labels or data. If we peak in the first item, we can for an example have data like this:
```json
"title": "Real estate",
"data": [
    "Real estate 1",
    "Real estate 2",
    "Real estate 3"
]
```
And then in the second item we might have
```json
"title": "Reported errands"
"data": [
    200,
    302,
    123
]
```
This would correspond to Real estate 1 having 200 reported errands and Real estate 2 having 302, etc.

We also get a `data_type`-field for seing if we are getting a number or string in the data field.

### Comparative data
The widgets can also return comparative data. This is if the widget has a setting that the values in the time period should be compared to another time period.
The data is seen in the field `comparative_data`, here it is ordered in the same way as data in the section above. The field `comparative_display_type` specifies if the
values in `comparative_data` is the actual values from the comparative period or the percentage difference from that period. This field is an enum and can be VALUE or PERCENTAGE.


### meta.type
This field says what type of widget is being returned. When `type` = KEY_FIGURE, then the response will vary 
slightly. This response will only return one item in the `data`-field and in the `data[0].data`-field. This
is the case when the widget is only showing a single value and in turn that value can be reached in `data[0].data[0]`.
All other types return the response in the same way.