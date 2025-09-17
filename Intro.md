## Purpose of This API
This API is designed for integrating Homepal’s services into internal tools, primarily through the use of `<iframe />` embeds.  

- All data is fetched for a specific **Company Group**, identified by `company_group_id`.  
- This ensures that the data and dashboards displayed are scoped correctly to the given group.  

---

## How It Works
The API is centered around the `/third-party/dashboards` endpoint.  

1. Call this endpoint to fetch all dashboards available to the specified Company Group.  
2. The response includes multiple `url` fields, each pointing to an HTML page.  
3. These URLs can then be embedded directly into your application via an `<iframe />`.  

This approach makes it simple to integrate dashboards into internal tools without needing to manually rebuild or replicate the UI.
