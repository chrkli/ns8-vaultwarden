# Untitled string in configure vaultwarden Schema

```txt
http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/path
```

url path for web application, like '/vaultwarden'

| Abstract            | Extensible | Status         | Identifiable            | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                      |
| :------------------ | :--------- | :------------- | :---------------------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | Unknown identifiability | Forbidden         | Allowed               | none                | [configure-module-input.json\*](vaultwarden/configure-module-input.json "open original schema") |

## path Type

`string`

## path Constraints

**pattern**: the string must match the following regular expression:&#x20;

```regexp
^/[a-zA-Z0-9]*
```

[try pattern](https://regexr.com/?expression=%5E%2F%5Ba-zA-Z0-9%5D* "try regular expression with regexr.com")
