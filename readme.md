
# Sabomoney

Describing APIs in accounts.py File



# app.py
#### /domain-verification verification
methods: GET
#### input
#### output Hello World

#### /support support
methods: POST
#### input: {"name":"Your Name", "email":"your@email.com ", "message":"Your Message"}
#### output:
{
    "success": "Support Request Received."
}

#### /link/<link_id> linkroute
methods: GET
#### input: link_id
#### output: redirect to associated promo link

#### /<path:path> all_routes
methods:GET
#### input:path:path
#### output: redirects to matching paths API link


#### / 
methods: GET
#### output renders template index.html

# domains.py

### /domain-verification domain_verification
methods: GET
#### input: host
#### output: verifies itself
{"success":"Domain http://localhost:5000/ has been successfully validated."}

### /verify_domain/<id> verify_domain
methods: GET
#### input: id
#### output: 
{
    "success": "Domain http://localhost:5000 has been successfully validated."
}

### /account/domain domain
methods: POST
#### input={"domain_url":"http://localhost:5000"}
#### output:
{
    "success": "Domain Created Successfully."
}

### /account/domains get_domains
method: GET
#### input:
#### output: 
{
    "domains": [
        {
            "created_by_id": 1,
            "default_domain": 1,
            "domain_url": "https://sabomoney.com",
            "id": 1,
            "verified": 1
        },
        {
            "created_by_id": 1,
            "default_domain": 1,
            "domain_url": "http://localhost:5000",
            "id": 2,
            "verified": 1
        }
    ],
    "success": "Successfully retrieved Domains"
}


# promos.py

### /promos get_promos
#### input: token
#### output:
{
    "promos_assigned": [
        {
            "assigned_to": [
                {
                    "assigned_links": [
                        "https://sabomoney.com/mXhlIqG",
                        "https://sabomoney.com/GLzelw0",
                        "https://sabomoney.com/5q8acEp",
                        "https://sabomoney.com/kEuv0Mr",
                        "https://sabomoney.com/YoIbVnW",
                        "https://sabomoney.com/laUwnu1",
                        "https://sabomoney.com/Bq6X6a1",
                        "https://sabomoney.com/NpsidzA",
                        "https://sabomoney.com/9Gi2NjP",
                        "https://sabomoney.com/qolEUi0",
                        "https://sabomoney.com/m7b0DL1",
                        "https://sabomoney.com/12wF4hR",
                        "https://sabomoney.com/K00yM0E",
                        "https://sabomoney.com/zK8ngSq",
                        "https://sabomoney.com/wJRnaGM",
                        "https://sabomoney.com/f2jDyf2",
                        "https://sabomoney.com/iqziwVQ",
                        "https://sabomoney.com/WripYDI",
                        "https://sabomoney.com/0Y28o4e",
                        "https://sabomoney.com/cVYB4lY",
                        "https://sabomoney.com/76c33JG"
                    ],
                    "email": "diveej1@gmail.com",
                    "id": 1,
                    "promo_id": 1,
                    "source_link": "",
                    "spc": 515,
                    "status": "Terminated"
                }
            ],
            "cost_limit": null,
            "created_at": "2022-09-29T12:21:03",
            "created_by_id": 5,
            "default_spc": 515,
            "description": "rick roll people",
            "destination_link": "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
            "id": 1,
            "invite_id": "iumrP0CUI1Y1JXwn8ixr",
            "last_modified": "2022-09-29T12:42:58",
            "name": "rickroll people",
            "promo_type": 7,
            "selected_domain": 1,
            "status": "Active",
            "termination_datetime": null,
            "type": "other"
        },
        ...
    ],
    "promos_owned": [],
    "success": "Promos successfully retrieved."
}

### /promo/<promo_id> individual_promo
#### input: token, promo_id
#### output:
{
    "promo_assigned": {
        "assigned_to": [
            {
                "assigned_links": [
                    "https://sabomoney.com/FkwiXJm",
                    "https://sabomoney.com/9O5ZXYL",
                    "https://sabomoney.com/UDvzxuz",
                    "https://sabomoney.com/85ToxFI",
                    "https://sabomoney.com/TT6IHQd",
                    "https://sabomoney.com/ev7hZik",
                    "https://sabomoney.com/xSuUcYp",
                    "https://sabomoney.com/DNs4Zk7",
                    "https://sabomoney.com/g516mcJ",
                    "https://sabomoney.com/K0GUulU",
                    "https://sabomoney.com/UnkqUFo",
                    "https://sabomoney.com/F7MSHzg",
                    "https://sabomoney.com/G9gQq3v",
                    "https://sabomoney.com/w2FUC3c",
                    "https://sabomoney.com/xm1aFR6",
                    "https://sabomoney.com/Ie9ft37",
                    "https://sabomoney.com/YzTPfSd",
                    "https://sabomoney.com/peuWyMK",
                    "https://sabomoney.com/TJCAWke",
                    "https://sabomoney.com/NkDuSpE",
                    "https://sabomoney.com/mOjEC6Y"
                ],
                "email": "diveej1@gmail.com",
                "id": 2,
                "promo_id": 2,
                "source_link": "",
                "spc": 1291,
                "status": "Active"
            }
        ],
        "cost_limit": null,
        "created_at": "2022-09-29T13:49:27",
        "created_by_id": 5,
        "default_spc": 1291,
        "description": "Barrel Roll",
        "destination_link": "https://www.google.com/search?q=do+a+barrel+roll",
        "id": 2,
        "invite_id": "EsEmcSe8st5BPVxLP8n5",
        "last_modified": "2022-09-29T13:51:19",
        "name": "New Promo",
        "promo_type": 7,
        "selected_domain": 1,
        "status": "Active",
        "termination_datetime": null,
        "type": "other"
    },
    "success": "Promo Successfully Retrieved"
}

### /promo/terminate/<promo_id> terminate_promo
#### input:promo_id, token
#### output:
{
    "success": "Your involvement in this promo has been terminated."
}

### /promo create_promo
method: POST
#### input: token, {"name":"Promo name", "type":"other", "default_spc":512, "destination_link":"www.google.com"}
#### output:{
    "success":"Promo Successfully created"
}

### /promo/accept accept_promo
method:POST
#### input: {"promo_id":5}
#### output: {
    "success":"Promo Accepted"
}

### /affiliate invite_affiliate
method: POST
#### input:token, {"affiliate_email":"diveej1@gmail.com", "promo_id":"3", "spc":512}
#### output:
{
    "success":"Affiliate Invited Successfully."

}

### /affiliate/terminate terminate_affiliate
method:POST
#### input: {"promo_id":4, "affiliate_email":"diveej1@gmail.com"}
#### output:{
    "success":"Affiliate Terminated."
}


### registration.py /register
method: POST
#### input: {"user_email":"your@email.com", "user_password","qwerty123",
                         "first_name":"yourfirstname", "last_name":"yourlastname", "role":"affiliate"}
#### output:{
    "success": "Account Successfully Created"
}

### /verify verify
methods: GET POST
GET: 
Input-> {"verification_token":"d65903e9f328800b9586b51a1fc75b8ec7161717fa9d887846a824a330db4572"}
#### output-> {"success": "Success - You have been successfully verified."}

POST:
#### input->{"user_email":"your@gmail.com"}
#### output->{"success": "A verification link has been emailed to you."}

### /emails/is_available/<email>
#### input: email
#### output: {"success": "Email Is Available."}


# payment.py

### /btcpayserve btcpayserver
Methods: POST
#### input: {"type":"InvoiceReceivedPayment","invoiceId":"dfgdfdfoaidsfmeptyk", "payment":{"id":"bjdgfbdof","value":43.12}}
#### output:

### /account/invoice/<fulfillmentAmount> add_funds
methods: POST
#### input: fulfillmentAmount, Token {"return_path":"path"}
#### output: {
    "invoice": {}
    "success":"Invoice Created."
}


#logger.py

### /emails log_email
method: POST 
#### input: {"user_email":"log@gmail.com"}
#### output:{"success": "Email Logged."}
