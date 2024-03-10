# configure vaultwarden Schema

```txt
http://schema.nethserver.org/vaultwarden/configure-module-input.json
```

Configure vaultwarden

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                    |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [configure-module-input.json](vaultwarden/configure-module-input.json "open original schema") |

## configure vaultwarden Type

`object` ([configure vaultwarden](configure-module-input.md))

## configure vaultwarden Examples

```json
{
  "domain": "vaultwarden.example.org",
  "path": "/webvault",
  "orgname": "ns8-Vaultwarden",
  "invitations": true,
  "webvault": true,
  "websocket": false,
  "sends": true,
  "emergencyaccess": true,
  "icondownload": true,
  "signups": true,
  "lets_encrypt": false,
  "http2https": true
}
```

# configure vaultwarden Properties

| Property                       | Type      | Required | Nullable       | Defined by                                                                                                                                                                              |
| :----------------------------- | :-------- | :------- | :------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [domain](#domain)              | `string`  | Required | cannot be null | [configure vaultwarden](configure-module-input-properties-domain.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/domain")                          |
| [path](#path)                  | `string`  | Required | cannot be null | [configure vaultwarden](configure-module-input-properties-path.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/path")                              |
| [orgname](#orgname)            | `string`  | Required | cannot be null | [configure vaultwarden](configure-module-input-properties-orgname.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/orgname")                        |
| [lets\_encrypt](#lets_encrypt) | `boolean` | Required | cannot be null | [configure vaultwarden](configure-module-input-properties-lets-encrypt-certificatae.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/lets_encrypt") |
| [http2https](#http2https)      | `boolean` | Required | cannot be null | [configure vaultwarden](configure-module-input-properties-http-to-https-redirection.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/http2https")   |

## domain

fully-qualified hostname needed for WebAuthn to work, e.g. vault.example.org

`domain`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [configure vaultwarden](configure-module-input-properties-domain.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/domain")

### domain Type

`string`

### domain Constraints

**(international) hostname**: the string must be an (IDN) hostname, according to [RFC 5890, section 2.3.2.3](https://tools.ietf.org/html/rfc5890 "check the specification")

## path

url path for web application, like '/vaultwarden'

`path`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [configure vaultwarden](configure-module-input-properties-path.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/path")

### path Type

`string`

### path Constraints

**pattern**: the string must match the following regular expression:&#x20;

```regexp
^/[a-zA-Z0-9]*
```

[try pattern](https://regexr.com/?expression=%5E%2F%5Ba-zA-Z0-9%5D* "try regular expression with regexr.com")

## orgname

name to be displayes whithin notifications, e.g. 'ns8-Vaultwarden'

`orgname`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [configure vaultwarden](configure-module-input-properties-orgname.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/orgname")

### orgname Type

`string`

### orgname Constraints

**pattern**: the string must match the following regular expression:&#x20;

```regexp
^[a-zA-Z0-9.-]+
```

[try pattern](https://regexr.com/?expression=%5E%5Ba-zA-Z0-9.-%5D%2B "try regular expression with regexr.com")

## lets\_encrypt

Request a valid Let's Encrypt certificate.

`lets_encrypt`

*   is required

*   Type: `boolean` ([Let's Encrypt certificatae](configure-module-input-properties-lets-encrypt-certificatae.md))

*   cannot be null

*   defined in: [configure vaultwarden](configure-module-input-properties-lets-encrypt-certificatae.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/lets_encrypt")

### lets\_encrypt Type

`boolean` ([Let's Encrypt certificatae](configure-module-input-properties-lets-encrypt-certificatae.md))

## http2https

Redirect all HTTP requests to HTTPS

`http2https`

*   is required

*   Type: `boolean` ([HTTP to HTTPS redirection](configure-module-input-properties-http-to-https-redirection.md))

*   cannot be null

*   defined in: [configure vaultwarden](configure-module-input-properties-http-to-https-redirection.md "http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/http2https")

### http2https Type

`boolean` ([HTTP to HTTPS redirection](configure-module-input-properties-http-to-https-redirection.md))
