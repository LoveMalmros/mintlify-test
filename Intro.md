## What is this API for?
This API is for integrating Homepals service mainly through <iframes /> in internal tools.
The API will always fetch data from a specified Company Group (specified with company_group_id).

## How does it work?
The API is centered around the /third-party/dashboards endpoint. With this endpoint you fetch all the 
dashboards that the Company Group has access to. From this you get a `url` that references a html-page
that you can insert into an iframe in the page you are fetching from.

## Query params
From the /third-party/dashboards you also get the following field `meta.available_query_params`. These are the 
query params that you can use to send into the embedded dashboards. For an example ?filter=true adds a filter to
the embedded page.

## Preview widgets
Some dashboards will have widgets that you can embedd separately. These also