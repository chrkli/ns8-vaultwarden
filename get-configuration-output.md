# Configure Vaultwarden Schema

```txt
http://schema.nethserver.org/vaultwarden/get-configuration-output.json
```

Configure Vaultwarden

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                        |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [get-configuration-output.json](vaultwarden/get-configuration-output.json "open original schema") |

## Configure Vaultwarden Type

`object` ([Configure Vaultwarden](get-configuration-output.md))

## Configure Vaultwarden Examples

```json
{
  "domain": "vaultwarden.example.com",
  "path": "/webvault",
  "orgname": "NS8 Vaultwarden",
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

# Configure Vaultwarden Properties

| Property                            | Type      | Required | Nullable       | Defined by                                                                                                                                                                                   |
| :---------------------------------- | :-------- | :------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [domain](#domain)                   | `string`  | Required | can be null    | [Configure Vaultwarden](get-configuration-output-properties-fully-qualified-domain-name.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/domain")      |
| [path](#path)                       | `string`  | Optional | can be null    | [Configure Vaultwarden](get-configuration-output-properties-webvault-url-path.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/path")                  |
| [orgname](#orgname)                 | `string`  | Required | can be null    | [Configure Vaultwarden](get-configuration-output-properties-e-mail-display-name.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/orgname")             |
| [invitations](#invitations)         | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toggle-invitations.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/invitations")          |
| [webvault](#webvault)               | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toggle-webvault.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/webvault")                |
| [websocket](#websocket)             | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toggle-websocket-support.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/websocket")      |
| [sends](#sends)                     | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toogle-sends.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/sends")                      |
| [emergencyaccess](#emergencyaccess) | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toggle-emergency-access.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/emergencyaccess") |
| [icondownload](#icondownload)       | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toggle-icon-download.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/icondownload")       |
| [signups](#signups)                 | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-toggle-signups.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/signups")                  |
| [lets\_encrypt](#lets_encrypt)      | `boolean` | Optional | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-lets-encrypt-certificate.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/lets_encrypt")   |
| [http2https](#http2https)           | `boolean` | Required | cannot be null | [Configure Vaultwarden](get-configuration-output-properties-http-to-https.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/http2https")                |

## domain

Vaultwarden needs to know the FQDN for e.g. FIDO2 WebAuthn.

`domain`

*   is required

*   Type: `string` ([Fully Qualified Domain Name](get-configuration-output-properties-fully-qualified-domain-name.md))

*   can be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-fully-qualified-domain-name.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/domain")

### domain Type

`string` ([Fully Qualified Domain Name](get-configuration-output-properties-fully-qualified-domain-name.md))

## path

URL for webapplication, may also be '/' (but not empty).

`path`

*   is optional

*   Type: `string` ([Webvault URL path](get-configuration-output-properties-webvault-url-path.md))

*   can be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-webvault-url-path.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/path")

### path Type

`string` ([Webvault URL path](get-configuration-output-properties-webvault-url-path.md))

## orgname

Used for send emails - e.g. invitations to create an account.

`orgname`

*   is required

*   Type: `string` ([E-Mail display name](get-configuration-output-properties-e-mail-display-name.md))

*   can be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-e-mail-display-name.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/orgname")

### orgname Type

`string` ([E-Mail display name](get-configuration-output-properties-e-mail-display-name.md))

## invitations

Global preference for sending invitations.

`invitations`

*   is optional

*   Type: `boolean` ([Toggle invitations](get-configuration-output-properties-toggle-invitations.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toggle-invitations.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/invitations")

### invitations Type

`boolean` ([Toggle invitations](get-configuration-output-properties-toggle-invitations.md))

## webvault

Wheather or not the integrated webUI can be used.

`webvault`

*   is optional

*   Type: `boolean` ([Toggle webvault](get-configuration-output-properties-toggle-webvault.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toggle-webvault.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/webvault")

### webvault Type

`boolean` ([Toggle webvault](get-configuration-output-properties-toggle-webvault.md))

## websocket

Enable to automatically inform desktop & browser clients on changes.

`websocket`

*   is optional

*   Type: `boolean` ([Toggle websocket support](get-configuration-output-properties-toggle-websocket-support.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toggle-websocket-support.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/websocket")

### websocket Type

`boolean` ([Toggle websocket support](get-configuration-output-properties-toggle-websocket-support.md))

## sends

Wheater or not to use Bitwarden's secure sharing system.

`sends`

*   is optional

*   Type: `boolean` ([Toogle sends](get-configuration-output-properties-toogle-sends.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toogle-sends.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/sends")

### sends Type

`boolean` ([Toogle sends](get-configuration-output-properties-toogle-sends.md))

## emergencyaccess

Wheater or not an users may enable emergency acces functionality.

`emergencyaccess`

*   is optional

*   Type: `boolean` ([Toggle emergency access](get-configuration-output-properties-toggle-emergency-access.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toggle-emergency-access.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/emergencyaccess")

### emergencyaccess Type

`boolean` ([Toggle emergency access](get-configuration-output-properties-toggle-emergency-access.md))

## icondownload

Wheather or not favicons for entries are fetched.

`icondownload`

*   is optional

*   Type: `boolean` ([Toggle icon download](get-configuration-output-properties-toggle-icon-download.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toggle-icon-download.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/icondownload")

### icondownload Type

`boolean` ([Toggle icon download](get-configuration-output-properties-toggle-icon-download.md))

## signups

Wheather or not new accounts can be created.

`signups`

*   is optional

*   Type: `boolean` ([Toggle signups](get-configuration-output-properties-toggle-signups.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-toggle-signups.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/signups")

### signups Type

`boolean` ([Toggle signups](get-configuration-output-properties-toggle-signups.md))

## lets\_encrypt

Request a TLS certificate from Let's Encrypt.

`lets_encrypt`

*   is optional

*   Type: `boolean` ([Let's Encrypt certificate](get-configuration-output-properties-lets-encrypt-certificate.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-lets-encrypt-certificate.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/lets_encrypt")

### lets\_encrypt Type

`boolean` ([Let's Encrypt certificate](get-configuration-output-properties-lets-encrypt-certificate.md))

## http2https

Redirect plain web requests to TLS enabled port.

`http2https`

*   is required

*   Type: `boolean` ([HTTP to HTTPS](get-configuration-output-properties-http-to-https.md))

*   cannot be null

*   defined in: [Configure Vaultwarden](get-configuration-output-properties-http-to-https.md "http://schema.nethserver.org/vaultwarden/get-configuration-output.json#/properties/http2https")

### http2https Type

`boolean` ([HTTP to HTTPS](get-configuration-output-properties-http-to-https.md))
