## What is this API for?
This API is for integrating Homepals service mainly through `<iframes />` in internal tools.
The API will always fetch data from a specified Company Group (specified with company_group_id).

---

## How does it work?
The API is centered around the /third-party/dashboards endpoint. With this endpoint you fetch all the 
dashboards that the Company Group has access to. From this you get mutliple `url`s that references html-pages
that you can insert into an iframe in the page you are fetching from.
