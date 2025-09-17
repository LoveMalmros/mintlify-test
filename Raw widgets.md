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
If `status.broken`=true. Then data will return null.

### meta.type
This field says what type of widget is being returned. When `type` = KEY_FIGURE, then the response will vary 
slightly. This response will only return one item in the `data`-field and in the `data[0].data`.field. This
is the case when the widget is only showing a single value and in turn that value can be reached in `data[0].data[0]`.
All other types return the response in the same way.