# Untitled string in configure vaultwarden Schema

```txt
http://schema.nethserver.org/vaultwarden/configure-module-input.json#/properties/orgname
```

name to be displayes whithin notifications, e.g. 'ns8-Vaultwarden'

| Abstract            | Extensible | Status         | Identifiable            | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                      |
| :------------------ | :--------- | :------------- | :---------------------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | Unknown identifiability | Forbidden         | Allowed               | none                | [configure-module-input.json\*](vaultwarden/configure-module-input.json "open original schema") |

## orgname Type

`string`

## orgname Constraints

**pattern**: the string must match the following regular expression:&#x20;

```regexp
^[a-zA-Z0-9.-]+
```

[try pattern](https://regexr.com/?expression=%5E%5Ba-zA-Z0-9.-%5D%2B "try regular expression with regexr.com")
