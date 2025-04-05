Get Domains
Endpoint: api/domains/{apiKey}/{type}

Method: GET

Parameters:

apiKey - Your API key.
type - Type of domains to fetch (free, premium, all).
Example Request:

GET api/domains/your-api-key/all
Example Response:

{
    "status": true,
    "data": {
        "domains": [
            {
                "domain": "free.com",
                "type": "Free"
            },
            {
                "domain": "lobage.com",
                "type": "Free"
            },
            {
                "domain": "premium.com",
                "type": "Premium"
            }
        ]
    }
}
