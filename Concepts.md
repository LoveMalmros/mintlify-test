## Query params
From the /third-party/dashboards you also get the following field `meta.available_query_params`. These are the 
query params that you can use to send into the embedded dashboards. For an example ?filter=true adds a filter to
the embedded page.

## Preview widgets
Some dashboards will have widgets that you can embedd separately via the `url` field. 
The data from these widgets can also be fetched in its raw format if you want to create your own UI for
the widget. More on this in the next section.

## Custom fields
The dashboard might have custom fields, these can be used for custom integrations. Lets say you need a
sorting return then you can add the custom field sorting_index to all the dashboards and then sort the 
dashboards in the order you would like. These fields are set by the administrator in Homepal.

## Validity
Links are valid in 3600s.