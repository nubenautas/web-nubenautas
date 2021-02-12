# JWT API

## URL Base: `https://cloud.nubenautas.com/api`

## Autenticación:

__POST__ `/sign_in`
* **Request:**
*Required URL Params:*
  `email=[string]`
  `password=[string]`
`
* **Response:**
*Code:* 200
*Headers:*
`Authorization=[authorization_code]`

__POST__ `/sign_out`
* **Request:**
*Headers:*
`Authorization=[authorization_code]`
* **Response:**
*Code:* 200

***Nota:*** El header de toda request deberá contener `Authorization` excepto `sign_in`.
## DNS:
__GET__ `/dns/[domain_name]/records`

* **Response:**
*Code:* 200
*Content example:*
```json
[
  {
    "id": 20142611,
    "content": "127.0.0.1",
    "created_at": "2020-10-25T22:23:09Z",
    "domain_id": ".sentidocomun.ninja",
    "name": "",
    "prio": null,
    "ttl": 3600,
    "type": "A"
  },
  {
    "id": 22545628,
    "content": "127.0.0.1",
    "created_at": "2020-10-25T22:23:14Z",
    "domain_id": "sentidocomun.ninja",
    "name": "www",
    "prio": null,
    "ttl": 3600,
    "type": "A"
  }
]
```

__POST__ `/dns/[domain_name]/records/`
* **Request:**
*Required URL Params:*
  `type=[string]`
  `name=[string]`
  `content=[string]`
*Optional URL Params:*
  `ttl=[string]`
  `prio=[string]`


* **Response:**
*Code:* 200
*Content example:*
```json
{
  "id": 20245620,
  "content": "127.0.0.1",
  "created_at": "2020-10-25T22:23:14Z",
  "domain_id": "sentidocomun.ninja",
  "name": "test",
  "prio": null,
  "ttl": 3600,
  "type": "A"
}
```

__PUT__ `/dns/[domain_name]/records/[record_id]`

*Required URL Params:*
  `type=[string]`
  `name=[string]`
  `content=[string]`
*Optional URL Params:*
  `ttl=[string]`
  `prio=[string]`
* **Response:**
*Code:* 200
*Content example:*
```json
{
  "id": 20245620,
  "content": "127.0.0.1",
  "created_at": "2020-10-25T22:23:14Z",
  "domain_id": "sentidocomun.ninja",
  "name": "test",
  "prio": null,
  "ttl": 3600,
  "type": "A"
}
```

__DEL__ `/dns/[domain_name]/records/[record_id]`
* **Response:**
*Code:* 200

## Obtén tu IPv4 pública actual:

__GET__ `http://ip.nubenautas.net/`
