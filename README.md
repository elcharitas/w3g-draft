# W3g Draft
> Here lies the remains of the docs for w3g rest api

# How to Use?

The table below gives an insight to how to use the endpoints. 

| endpoint       | method |  request payload           |            response payload      |
|----------------|:------:|----------------------------|----------------------------------|
| */connect*     |  GET   |                            | `{ message, url, is_connected, is_metamask, is_registered }`               |
| */user/me*     |  GET   |                            | `{ user: { email, address }, message, is_registered, is_connected }`   |
| */user/me*     |  POST  | `{ email, name, image* }`  | `{ user: { email, address, image* } }`   |
|*/user/accounts*|  GET   |                            | `{ accounts: string[] }`         |
| */upload* (deprecated)     | POST   | `{ file }`                  | `{ upload: { _id } }`            |
| */uploads*     | GET    | `{ id, width+, height+ }`  | `upload data/blob`               |
| */upload/:id*     | GET    | `{ width+, height+ }`  | `upload data/blob`               |
| */mint*        | POST   | `{ metadata: {image+*, video+* audio+*, name, desc }, amount, price }` | `{message, response: {community, address}}`|
| */communities* | GET | `{page+, limit+}` | `{result: [{ address, creator, metadata, path }], page: {next, previous} }`|
|*/community/:contractAddress/*| GET | | `{address, creator, metadata, path}` |
|*/community/:contractAddress/posts*| GET | `{limit}` | `{result: [{content, user, community}]}` |
| */search*      | GET | `{keywords}`| `{communities: [], message}` |
|*/signMessage*  | GET | `{message}` | `{status, message, url}` |

**NOTES**
- payload keys marked `*` are ids retrieved by uploading the data to `/upload` endpoint
- payload keys marked `+` are optional entries
- all fields in payload are strings unless indicated with a `:` 
