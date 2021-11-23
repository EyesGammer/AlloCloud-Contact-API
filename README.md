# AlloCloud API - Contacts - Octup!
- [AlloCloud API](#allocloud-api---Contacts---octup!)
	- [0. Descriptor](#0-descriptor)
	- [1. Connection](#1-connection)
	- [2. Add Contact](#2-add-contact)
	- [3. Update Contact](#3-update-contact)
	- [4. Delete Contact](#4-delete-contact)
> `used_account` is the account username

## 0. Descriptor
| Method | URL                                                      |
| ------ | -------------------------------------------------------- |
| PUT    | `https://{used_account}.allocloud.com/v3.0/auth/account` |
| PUT    | `https://{used_account}.allocloud.com/v3.0/directories`  |
| POST   | `https://{used_account}.allocloud.com/v3.0/directories`  |
| DELETE | `https://{used_account}.allocloud.com/v3.0/directories`  |

## 1. Connection
```json
{
	"data": {
		"api_key": "ACCOUNT_API_KEY"
	}
}
```
> `ACCOUNT_API_KEY` is the key from *Config>Advanced>Account Details>Credentials*<br>Return: `auth_token`

## 2. Add Contact
```json
{
    "data": {
        "contacts": [{
            "details": {
                "names": {
                    "first": "FIRST_NAME",
                    "last": "LAST_NAME"
                },
                "company": {
                    "name": "COMPANY_NAME"
                },
                "phone_numbers": {
                    "land_lines": ["LAND_LINE"],
                    "mobiles": ["MOBILE_LINE"],
                    "faxes": [""]
                }
            },
            "phonebook": "global"
        }],
        "phonebook": "global"
    }
}
```
> Warning: `COMPANY_NAME` need to contain only alphanumeric characters<br>Return: `computer-id` (Contact ID)

## 3. Update Contact
```json
{
    "data": {
        "contacts": [{
            "details": {
                "names": {
                    "first": "FIRST_NAME",
                    "last": "LAST_NAME"
                },
                "company": {
                    "name": "COMPANY_NAME"
                },
                "phone_numbers": {
                    "land_lines": ["LAND_LINE"],
                    "mobiles": ["MOBILE_LINE"],
                    "faxes": [""]
                }
            },
            "phonebook": "global",
            "id": computer-id
        }],
        "phonebook": "global"
    }
}
```
> Warning: `COMPANY_NAME` need to contain only alphanumeric characters

## 4. Delete Contact
URL Parameter: `computer_id (int)` is the contact ID
