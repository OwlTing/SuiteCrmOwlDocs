# API

## Leads

潛在客戶 / 商業機會
可以是個人或是公司以及小型商業團體

### Create Leads

`POST http://example.com/Api/V8/module`

```json--request

{
    "data": {
        "type": "Leads",
        "attributes": {
            "description": "Description",
            "assigned_user_id": "{{assigned_user_id}}",
            "account_id": "{{account_id}}",
            "salutation": "Mr.",
            "first_name": "Iam",
            "last_name": "Robot4",
            "title": "Mr.",
            "do_not_call": "0",
            "phone_home": "08-88888888",
            "phone_mobile": "0912345678",
            "phone_work": "07-77777777",
            "phone_other": "06-66666666",
            "phone_fax": "1234567890",
            "email1": "mark_huang1@owlting.com",
            "primary_address_street": "primary_address_street",
            "primary_address_street_2": "primary_address_street_2",
            "primary_address_street_3": "primary_address_street_3",
            "primary_address_city": "primary_address_city",
            "primary_address_state": "primary_address_state",
            "primary_address_postalcode": "primary_address_postalcode",
            "primary_address_country": "primary_address_country",
            "converted": "0",
            "refered_by": "汪東城",
            "lead_source": "Web Site",
            "lead_source_description": "lead_source_description",
            "status": "New",
            "status_description": "lead_source_description",
            "birthdate": "2020-10-06",
            "website": "http://example.com",
        }
    }
}

```

Parameter                  | Description              | Value
---------                  | -----------              | -----
description                | 描述                     |
assigned_user_id           | 指派給                   | Experience: 4e640918-9db7-2121-94b5-5eba64642e0c,
account_id                 | 客戶別（這邊帶入事業體） | Experience: dfd71a55-ae2d-1849-b491-5eac392fac52,
salutation                 | 稱呼                     | Mr.,Ms.,Mrs.,Miss,Dr.,Prof.
first_name                 | 名                       |
last_name                  | 姓                       |
title                      | 職稱                     |
do_not_call                | 不接受電訪               | 0,1
phone_home                 | 家庭電話                 | 08-88888888
phone_mobile               | 行動電話                 | 0912345678
phone_work                 | 辦公電話                 | 07-77777777
phone_other                | 傳真電話                 | 06-66666666
phone_fax                  | 傳真                     | 1234567890
email1                     | 主要聯絡                 |
email2                     | 次要聯絡                 |
invalid_email              | 無效郵件地址             | 0,1
email_opt_out              | 棄用                     | 0,1
lawful_basis               | 合法基礎                 | consent, contract, legal_obligation, protection_of_interest, public_interest, legitimate_interest, withdrawn
lawful_basis_source        | 合法基礎來源             | website, phone, given_to_user, email, third_party
date_reviewed              | 合法基礎之審核日期       |
primary_address_street     | 主要地址1                |
primary_address_street_2   | 主要地址2                |
primary_address_street_3   | 主要地址2                |
primary_address_city       | 主要城市                 |
primary_address_state      | 主要州或省               |
primary_address_postalcode | 郵地區碼                 |
primary_address_country    | 國家                     |
converted                  | 已轉換                   | 0,1
refered_by                 | 推薦人                   |
lead_source                | 潛在客戶來源             | Cold Call, Existing Customer, Self Generated, Employee, Partner, Public Relations, Direct Mail, Conference, Trade Show, Web Site, Word of mouth, Email, Campaign, Other
lead_source_description    | 潛在客戶來源說明         | lead_source_description
status                     | 狀態                     | New, Assigned, In Process, Converted, Recycled, Dead
status_description         | 狀態描述                 |
birthdate                  | 生日                     |
website                    | 網址                     |

```json--response

HTTP/1.1 201

{
    "data": {
        "type": "Lead",
        "id": "4668a815-e946-dd50-7ac8-5f9927fbfd11",
        "attributes": {
            "name": "Iam Robot4",
            "date_entered": "2020-10-28T08:12:00+08:00",
            "date_modified": "2020-10-28T08:12:00+08:00",
            "modified_user_id": "1",
            "modified_by_name": "Administrator",
            "created_by": "1",
            "created_by_name": "Administrator",
            "description": "Description",
            "deleted": "0",
            "created_by_link": "",
            "modified_user_link": "",
            "assigned_user_id": "",
            "assigned_user_name": "",
            "assigned_user_link": "",
            "SecurityGroups": "",
            "salutation": "Mr.",
            "first_name": "Iam",
            "last_name": "Robot4",
            "full_name": "Iam Robot4",
            "title": "Mr.",
            "photo": "",
            "department": "",
            "do_not_call": "0",
            "phone_home": "08-88888888",
            "email": "",
            "phone_mobile": "0912345678",
            "phone_work": "07-77777777",
            "phone_other": "06-66666666",
            "phone_fax": "1234567890",
            "email1": "mark_huang1@owlting.com",
            "email2": "mark_huang2@owlting.com",
            "invalid_email": "0",
            "email_opt_out": "0",
            "lawful_basis": "lawful_basis",
            "date_reviewed": "",
            "lawful_basis_source": "lawful_basis_source",
            "primary_address_street": "primary_address_street\nprimary_address_street_2\nprimary_address_street_3",
            "primary_address_street_2": "",
            "primary_address_street_3": "",
            "primary_address_city": "primary_address_city",
            "primary_address_state": "primary_address_state",
            "primary_address_postalcode": "primary_address_post",
            "primary_address_country": "primary_address_country",
            "alt_address_street": "alt_address_street\nalt_address_street_2\nalt_address_street_3",
            "alt_address_street_2": "",
            "alt_address_street_3": "",
            "alt_address_city": "alt_address_city",
            "alt_address_state": "alt_address_state",
            "alt_address_postalcode": "alt_address_postalco",
            "alt_address_country": "alt_address_country",
            "assistant": "assistant",
            "assistant_phone": "assistant_phone",
            "email_addresses_primary": "",
            "email_addresses": "",
            "email_addresses_non_primary": "",
            "converted": "0",
            "refered_by": "汪東城",
            "lead_source": "Web Site",
            "lead_source_description": "lead_source_description",
            "status": "New",
            "status_description": "lead_source_description",
            "reports_to_id": "reports_to_id",
            "report_to_name": "",
            "reports_to_link": "",
            "reportees": "",
            "contacts": "",
            "account_name": "",
            "accounts": "",
            "account_description": "",
            "contact_id": "",
            "contact": "",
            "account_id": "",
            "opportunity_id": "",
            "opportunity": "",
            "opportunity_name": "",
            "opportunity_amount": "",
            "campaign_id": "",
            "campaign_name": "",
            "campaign_leads": {},
            "c_accept_status_fields": "",
            "m_accept_status_fields": "",
            "accept_status_id": "",
            "accept_status_name": "",
            "webtolead_email1": "",
            "webtolead_email2": "",
            "webtolead_email_opt_out": "",
            "webtolead_invalid_email": "",
            "birthdate": "2020-10-06",
            "portal_name": "portal_name",
            "portal_app": "portal_app",
            "website": "http://example.com",
            "tasks": "",
            "notes": "",
            "meetings": "",
            "calls": "",
            "oldmeetings": "",
            "oldcalls": "",
            "emails": "",
            "campaigns": "",
            "prospect_lists": "",
            "fp_events_leads_1": "",
            "e_invite_status_fields": "",
            "event_status_name": "",
            "event_invite_id": "",
            "e_accept_status_fields": "",
            "event_accept_status": "",
            "event_status_id": "",
            "jjwg_maps_lat_c": "0.00000000",
            "jjwg_maps_lng_c": "0.00000000",
            "jjwg_maps_geocode_status_c": "jjwg_maps_geocode_status_c",
            "jjwg_maps_address_c": "jjwg_maps_geocode_status_c"
        },
        "relationships": {
            "CampaignLog": {
                "links": {
                    "related": "V8/module/4668a815-e946-dd50-7ac8-5f9927fbfd11/relationships/campaigns"
                }
            },
            "Contacts": {
                "links": {
                    "related": "V8/module/4668a815-e946-dd50-7ac8-5f9927fbfd11/relationships/contacts"
                }
            },
            "EmailAddress": {
                "links": {
                    "related": "V8/module/4668a815-e946-dd50-7ac8-5f9927fbfd11/relationships/email_addresses"
                }
            },
            "ProspectLists": {
                "links": {
                    "related": "V8/module/4668a815-e946-dd50-7ac8-5f9927fbfd11/relationships/prospect_lists"
                }
            },
            "SecurityGroups": {
                "links": {
                    "related": "V8/module/4668a815-e946-dd50-7ac8-5f9927fbfd11/relationships/SecurityGroups"
                }
            },
            "Users": {
                "links": {
                    "related": "V8/module/4668a815-e946-dd50-7ac8-5f9927fbfd11/relationships/created_by_link"
                }
            }
        }
    }
}

```
### Update Leads

## Contacts

聯絡人 / 真實客戶

### Create Contacts

`POST http://example.com/Api/V8/module`

```json--request

{
    "data": {
        "type": "Contacts",
        "attributes": {
            "description": "Description",
            "assigned_user_id": "{{assigned_user_id}}",
            "account_id": "{{account_id}}",
            "salutation": "Mr.",
            "first_name": "Iam",
            "last_name": "Robot5",
            "title": "Mr.",
            "do_not_call": "0",
            "phone_home": "08-88888888",
            "phone_mobile": "0912345678",
            "phone_work": "07-77777777",
            "phone_other": "06-66666666",
            "phone_fax": "1234567890",
            "email1": "mark_huang1@owlting.com",
            "primary_address_street": "primary_address_street",
            "primary_address_street_2": "primary_address_street_2",
            "primary_address_street_3": "primary_address_street_3",
            "primary_address_city": "primary_address_city",
            "primary_address_state": "primary_address_state",
            "primary_address_postalcode": "primary_address_postalcode",
            "primary_address_country": "primary_address_country",
            "birthdate": "2020-10-06",
            "birth_of_day_c": "birth_of_day_c",
            "birth_of_year_c": "birth_of_year_c",
            "birth_of_month_c": "birth_of_month_c"
        }
    }
}

```

Parameter                  | Description              | Value
---------                  | -----------              | -----
description                | 描述                     | Description
assigned_user_id           | 指派給                   | Experience: 4e640918-9db7-2121-94b5-5eba64642e0c
account_id                 | 客戶別（這邊帶入事業體） | Experience: dfd71a55-ae2d-1849-b491-5eac392fac52
salutation                 | 稱呼                     | Mr.,Ms.,Mrs.,Miss,Dr.,Prof.
first_name                 | 名                       |
last_name                  | 姓                       |
title                      | 職稱                     |
do_not_call                | 不接受電訪               | 0,1
phone_home                 | 家庭電話                 | 08-88888888
phone_mobile               | 行動電話                 | 0912345678
phone_work                 | 辦公電話                 | 07-77777777
phone_other                | 傳真電話                 | 06-66666666
phone_fax                  | 傳真                     | 1234567890
email1                     | 主要聯絡                 |
email2                     | 次要聯絡                 |
invalid_email              | 無效郵件地址             | 0,1
email_opt_out              | 棄用                     | 0,1
lawful_basis               | 合法基礎                 | consent, contract, legal_obligation, protection_of_interest, public_interest, legitimate_interest, withdrawn
lawful_basis_source        | 合法基礎來源             | website, phone, given_to_user, email, third_party
date_reviewed              | 合法基礎之審核日期       |
primary_address_street     | 主要地址1                |
primary_address_street_2   | 主要地址2                |
primary_address_street_3   | 主要地址3                |
primary_address_city       | 主要城市                 |
primary_address_state      | 主要州或省               |
primary_address_postalcode | 郵地區碼                 |
primary_address_country    | 國家                     |
lead_source                | 潛在客戶來源             | Cold Call, Existing Customer, Self Generated, Employee, Partner, Public Relations, Direct Mail, Conference, Trade Show, Web Site, Word of mouth, Email, Campaign, Other
lead_source_description    | 潛在客戶來源說明         | lead_source_description
birthdate                  | 生日                     |
birth_of_day_c             | 日                       |
birth_of_year_c            | 年                       |
birth_of_month_c           | 月                       |


```json--response

HTTP/1.1 201

{
    "data": {
        "type": "Contact",
        "id": "1e3924cd-4833-dfa4-b43a-5f9a336972d9",
        "attributes": {
            "name": "Iam Robot5",
            "date_entered": "2020-10-29T03:13:00+08:00",
            "date_modified": "2020-10-29T03:13:00+08:00",
            "modified_user_id": "1",
            "modified_by_name": "Administrator",
            "created_by": "1",
            "created_by_name": "Administrator",
            "description": "Description",
            "deleted": "0",
            "created_by_link": "",
            "modified_user_link": "",
            "assigned_user_id": "",
            "assigned_user_name": "",
            "assigned_user_link": "",
            "SecurityGroups": "",
            "salutation": "Mr.",
            "first_name": "Iam",
            "last_name": "Robot5",
            "full_name": "Iam Robot5",
            "title": "Mr.",
            "photo": "",
            "department": "",
            "do_not_call": "0",
            "phone_home": "08-88888888",
            "email": "",
            "phone_mobile": "0912345678",
            "phone_work": "07-77777777",
            "phone_other": "06-66666666",
            "phone_fax": "1234567890",
            "email1": "mark_huang1@owlting.com",
            "email2": "mark_huang2@owlting.com",
            "invalid_email": "0",
            "email_opt_out": "0",
            "lawful_basis": "lawful_basis",
            "date_reviewed": "",
            "lawful_basis_source": "lawful_basis_source",
            "primary_address_street": "primary_address_street\nprimary_address_street_2\nprimary_address_street_3",
            "primary_address_street_2": "",
            "primary_address_street_3": "",
            "primary_address_city": "primary_address_city",
            "primary_address_state": "primary_address_state",
            "primary_address_postalcode": "primary_address_post",
            "primary_address_country": "primary_address_country",
            "alt_address_street": "",
            "alt_address_street_2": "",
            "alt_address_street_3": "",
            "alt_address_city": "",
            "alt_address_state": "",
            "alt_address_postalcode": "",
            "alt_address_country": "",
            "assistant": "",
            "assistant_phone": "",
            "email_addresses_primary": "",
            "email_addresses": "",
            "email_addresses_non_primary": "",
            "email_and_name1": "",
            "lead_source": "",
            "account_name": "",
            "account_id": "",
            "opportunity_role_fields": "",
            "opportunity_role_id": "",
            "opportunity_role": "",
            "reports_to_id": "",
            "report_to_name": "",
            "birthdate": "2020-10-06",
            "accounts": "",
            "reports_to_link": {},
            "opportunities": "",
            "bugs": "",
            "calls": "",
            "cases": "",
            "direct_reports": "",
            "emails": "",
            "documents": "",
            "leads": "",
            "meetings": "",
            "notes": "",
            "project": "",
            "project_resource": "",
            "am_projecttemplates_resources": "",
            "am_projecttemplates_contacts_1": "",
            "tasks": "",
            "tasks_parent": "",
            "notes_parent": "",
            "user_sync": {},
            "campaign_id": "",
            "campaign_name": "",
            "campaigns": "",
            "campaign_contacts": {},
            "c_accept_status_fields": "",
            "m_accept_status_fields": "",
            "accept_status_id": "",
            "accept_status_name": "",
            "prospect_lists": "",
            "sync_contact": "",
            "fp_events_contacts": "",
            "aos_quotes": "",
            "aos_invoices": "",
            "aos_contracts": "",
            "e_invite_status_fields": "",
            "event_status_name": "",
            "event_invite_id": "",
            "e_accept_status_fields": "",
            "event_accept_status": "",
            "event_status_id": "",
            "project_contacts_1": "",
            "aop_case_updates": "",
            "joomla_account_id": "",
            "portal_account_disabled": false,
            "joomla_account_access": "",
            "portal_user_type": "Single",
            "jjwg_maps_lat_c": "0.00000000",
            "gender_c": "",
            "birth_of_day_c": "birth_of_day_c",
            "birth_of_year_c": "birth_of_year_c",
            "jjwg_maps_lng_c": "0.00000000",
            "jjwg_maps_geocode_status_c": "",
            "jjwg_maps_address_c": "",
            "birth_of_month_c": "birth_of_month_c"
        },
        "relationships": {
            "AM_ProjectTemplates": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/am_projecttemplates_contacts_1"
                }
            },
            "AOS_Contracts": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/aos_contracts"
                }
            },
            "AOS_Invoices": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/aos_invoices"
                }
            },
            "AOS_Quotes": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/aos_quotes"
                }
            },
            "CampaignLog": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/campaigns"
                }
            },
            "EmailAddress": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/email_addresses"
                }
            },
            "Opportunities": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/opportunities"
                }
            },
            "Project": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/project_contacts_1"
                }
            },
            "ProspectLists": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/prospect_lists"
                }
            },
            "SecurityGroups": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/SecurityGroups"
                }
            },
            "Users": {
                "links": {
                    "related": "V8/module/1e3924cd-4833-dfa4-b43a-5f9a336972d9/relationships/created_by_link"
                }
            }
        }
    }
}

```

## Currencies

貨幣

<aside class="info"><strong>Important</strong>: 預設幣別(TWD) 無法透過api 查詢 直接帶入-99</aside>

Parameter       | Description | Value
---------       | ----------- | -----
name            | 貨幣名稱    | EUR
symbol          | 貨幣符號    |
iso4217         | ISO4217編碼 | https://www.iso.org/iso-4217-currency-codes.html
conversion_rate | 匯率        | 跟預設幣別 (TWD) 的比率
status          | 狀態        | Active, Inactive

`GET http://example.com/Api/V8/module/Currencies?page[size]=10&page[number]=1`

```json--response
{
    "meta": {
        "total-pages": 1,
        "records-on-this-page": 1
    },
    "data": [
        {
            "type": "Currency",
            "id": "6ccfc88a-598b-898a-91f5-5f7ed4511cc2",
            "attributes": {
                "name": "EUR",
                "symbol": "EUR",
                "iso4217": "",
                "conversion_rate": "1.2",
                "status": "Active",
                "deleted": "0",
                "date_entered": "2020-10-08T08:58:00+08:00",
                "date_modified": "2020-10-08T08:58:00+08:00",
                "created_by": "1",
                "hide": "",
                "unhide": ""
            },
            "relationships": []
        }
    ],
    "links": {
        "first": null,
        "prev": null,
        "next": null,
        "last": null
    }
}
```

## Products

產品

### Create Products

Parameter               | Description      | Value
---------               | -----------      | -----
name                    | 產品名稱         |
description             | 描述             |
assigned_user_id        | 負責人           |
part_number             | 部件編碼         | M01040500000282
type                    | 產品類型         | Good,Service
cost                    | 成本             |
cost_usdollar           | 成本（預設貨幣） |
currency_id             | 貨幣             |
price                   | 價格             |
price_usdollar          | 價格（預設貨幣） |
url                     | 超連結           |
contact_id              | 聯絡人           |
aos_product_category_id | 產品類別         |

`POST http://example.com/Api/V8/module`

```json--request
{
    "data": {
        "type": "AOS_Products",
        "attributes": {
            "name": "MIS 【預購商品 佑爾康金貝親 HappyFamily有機蔬果牙餅 蘋果口味】用最天",
            "description": "MIS 【預購商品 佑爾康金貝親 HappyFamily有機蔬果牙餅 蘋果口味】用最天",
            "part_number": "MISM01040500000282",
            "type": "Good",
            "cost": "180.000000",
            "cost_usdollar": "180.000000",
            "currency_id": "{{currency_id}}",
            "price": "180.000000",
            "price_usdollar": "180.00",
            "url": "",
            "contact_id": "",
            "aos_product_category_id": "{{product_category_id}}"
        }
    }
}

```

## Products Categories

### 產品類別

Parameter          | Description | Value
---------          | ----------- | -----
name               | 名稱        |
description        | 描述        |
assigned_user_id   | 負責人      | 1
is_parent          | 是父類別    | 0,1
parent_category_id | 父類別      |

```json--response
{
    "data": [
        {
            "type": "AOS_Product_Categories",
            "id": "173f2e49-ebc0-ac85-f383-5f7d82c7b1fb",
            "attributes": {
                "name": "E",
                "date_entered": "2020-10-07T08:54:00+08:00",
                "date_modified": "2020-10-07T08:54:00+08:00",
                "modified_user_id": "4e640918-9db7-2121-94b5-5eba64642e0c",
                "modified_by_name": "Experience",
                "created_by": "4e640918-9db7-2121-94b5-5eba64642e0c",
                "created_by_name": "Experience",
                "description": "Experiences體驗大類",
                "deleted": "0",
                "created_by_link": "",
                "modified_user_link": "",
                "assigned_user_id": "1",
                "assigned_user_name": "Administrator",
                "assigned_user_link": "",
                "SecurityGroups": "",
                "is_parent": "1",
                "aos_products": "",
                "sub_categories": "",
                "parent_category": {},
                "parent_category_name": "",
                "parent_category_id": ""
            },
            "relationships": {
                "AOS_Product_Categories": {
                    "links": {
                        "related": "V8/module/AOS_Product_Categories/173f2e49-ebc0-ac85-f383-5f7d82c7b1fb/relationships/parent_category"
                    }
                },
                "SecurityGroups": {
                    "links": {
                        "related": "V8/module/AOS_Product_Categories/173f2e49-ebc0-ac85-f383-5f7d82c7b1fb/relationships/SecurityGroups"
                    }
                },
                "Users": {
                    "links": {
                        "related": "V8/module/AOS_Product_Categories/173f2e49-ebc0-ac85-f383-5f7d82c7b1fb/relationships/created_by_link"
                    }
                }
            }
        }
    ],
}
```

## Invoice

發票(收據) / 銷售紀錄

Parameter                    | Description              | Value
---------                    | -----------              | -----
name                         | 職稱                     |
description                  | 描述                     |
assigned_user_id             | 負責人                   |
billing_account_id           | 客戶                     |
billing_contact_id           | 聯絡人                   |
billing_address_street       | 街道                     |
billing_address_city         | 城市                     |
billing_address_state        | 州或省                   |
billing_address_country      | 國家                     |
shipping_address_street      | 街道                     |
shipping_address_city        | 城市                     |
shipping_address_state       | 州或省                   |
shipping_address_postalcode  | 郵遞區號                 |
shipping_address_country     | 國家                     |
total_amt                    | 訂單總計                 | 6971 (item_groups 的 amount)
total_amt_usdollar           | 訂單總計（預設貨幣）     | 6971
subtotal_amount              | 訂單小計                 | 6891 ( total_amt - discount_amount )
subtotal_amount_usdollar     | 訂單小計（預設貨幣）     | 6891
discount_amount              | 訂單折扣總計             | -80
discount_amount_usdollar     | 訂單折扣總計（預設貨幣） | -80
tax_amount                   | 訂單稅金總計 (訂單貨幣)  | 349.55 ( item_groups 的tax_amount + shipping_tax_amt )
tax_amount_usdollar          | 訂單稅金總計（預設貨幣） | 349.55
shipping_amount              | 訂單貨運                 | 100
shipping_amount_usdollar     | 訂單貨運（預設貨幣）     | 100
shipping_tax                 | 訂單貨運稅 (百分之幾)    | 5.0
shipping_tax_amt             | 訂單貨運稅               | 5 ( shipping_tax_amt * shipping_tax / 100 )
shipping_tax_amt_usdollar    | 訂單貨運稅（預設貨幣）   | 5
total_amount                 | 訂單含稅總計             | 7340.55 ( subtotal_amount + tax_amount + shipping_amount)
total_amount_usdollar        | 訂單含稅總計（預設貨幣） | 7340.55
currency_id                  | 訂單貨幣                 | -99
quote_number                 | 報價編號                 |
quote_date                   | 報價日期                 |
invoice_date                 | 發票日期                 |
due_date                     | 到期時間                 |
status                       | 狀態                     | Paid,Canceled,Not Paid,Return
subtotal_tax_amount          | 小計＋稅金               | 0
subtotal_tax_amount_usdollar | 小計＋稅金（預設貨幣）   | 0
billing_address_postalcode   | 郵遞區號                 |

```json--request
{
    "data": {
        "type": "AOS_Invoices",
        "attributes": {
            "name": "MIS004",
            "description": "",
            "deleted": "0",
            "billing_account_id": "670f411d-7f4f-abc5-d253-5eac39e93e09",
            "billing_account": "EC_Market",
            "billing_contact_id": "",
            "billing_contact": "",
            "billing_address_street": "",
            "billing_address_city": "",
            "billing_address_state": "",
            "billing_address_postalcode": "",
            "billing_address_country": "",
            "shipping_address_street": "",
            "shipping_address_city": "",
            "shipping_address_state": "",
            "shipping_address_postalcode": "",
            "shipping_address_country": "",
            "number": "",
            "total_amt": "399.000000",
            "total_amt_usdollar": "399.000000",
            "subtotal_amount": "378.000000",
            "subtotal_amount_usdollar": "378.000000",
            "discount_amount": "-21.000000",
            "discount_amount_usdollar": "-21.000000",
            "tax_amount": "0.000000",
            "tax_amount_usdollar": "0.000000",
            "shipping_amount": "0.000000",
            "shipping_amount_usdollar": "0.000000",
            "shipping_tax": "0",
            "shipping_tax_amt": "0.000000",
            "shipping_tax_amt_usdollar": "0.000000",
            "total_amount": "378.000000",
            "total_amount_usdollar": "378.000000",
            "currency_id": "47009c9c-6151-33e1-49a1-5ea287700de2",
            "quote_number": "",
            "quote_date": "",
            "invoice_date": "202-02-03",
            "due_date": "",
            "status": "Paid",
            "template_ddown_c": "",
            "subtotal_tax_amount": "",
            "subtotal_tax_amount_usdollar": "0.000000"
        }
    }
}
```

```json--response
{
    "data": {
        "type": "AOS_Invoices",
        "id": "b4534cda-6fe8-2926-47b4-5fa3d3146c98",
        "attributes": {
            "name": "MIS004",
            "date_entered": "2020-11-05T10:26:00+08:00",
            "date_modified": "2020-11-05T10:26:00+08:00",
            "modified_user_id": "1",
            "modified_by_name": "Administrator",
            "created_by": "1",
            "created_by_name": "Administrator",
            "description": "",
            "deleted": "0",
            "created_by_link": "",
            "modified_user_link": "",
            "assigned_user_id": "",
            "assigned_user_name": "",
            "assigned_user_link": "",
            "SecurityGroups": "",
            "billing_account_id": "670f411d-7f4f-abc5-d253-5eac39e93e09",
            "billing_account": "EC_Market",
            "billing_contact_id": "",
            "billing_contact": "",
            "billing_address_street": "",
            "billing_address_city": "",
            "billing_address_state": "",
            "billing_address_postalcode": "",
            "billing_address_country": "",
            "shipping_address_street": "",
            "shipping_address_city": "",
            "shipping_address_state": "",
            "shipping_address_postalcode": "",
            "shipping_address_country": "",
            "number": "18985",
            "line_items": "",
            "total_amt": "399.000000",
            "total_amt_usdollar": "399.000000",
            "subtotal_amount": "378.000000",
            "subtotal_amount_usdollar": "378.000000",
            "discount_amount": "-21.000000",
            "discount_amount_usdollar": "-21.000000",
            "tax_amount": "0.000000",
            "tax_amount_usdollar": "0.000000",
            "shipping_amount": "0.000000",
            "shipping_amount_usdollar": "0.000000",
            "shipping_tax": "0",
            "shipping_tax_amt": "0.000000",
            "shipping_tax_amt_usdollar": "0.000000",
            "total_amount": "378.000000",
            "total_amount_usdollar": "378.000000",
            "currency_id": "47009c9c-6151-33e1-49a1-5ea287700de2",
            "quote_number": "0",
            "quote_date": "",
            "invoice_date": "",
            "due_date": "",
            "status": "Paid",
            "template_ddown_c": "",
            "subtotal_tax_amount": "0.000000",
            "subtotal_tax_amount_usdollar": "0.000000",
            "accounts": "",
            "contacts": "",
            "aos_quotes_aos_invoices": "",
            "aos_products_quotes": "",
            "aos_line_item_groups": "",
            "aos_invoices_aos_invoices_1": "",
            "invoice_datetime_c": ""
        },
        "relationships": {
            "AOS_Invoices": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/aos_invoices_aos_invoices_1"
                }
            },
            "AOS_Line_Item_Groups": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/aos_line_item_groups"
                }
            },
            "AOS_Products_Quotes": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/aos_products_quotes"
                }
            },
            "AOS_Quotes": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/aos_quotes_aos_invoices"
                }
            },
            "Accounts": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/accounts"
                }
            },
            "Contacts": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/contacts"
                }
            },
            "SecurityGroups": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/SecurityGroups"
                }
            },
            "Users": {
                "links": {
                    "related": "V8/module/b4534cda-6fe8-2926-47b4-5fa3d3146c98/relationships/created_by_link"
                }
            }
        }
    }
}
```

## Item Groups

小計群組

Parameter                    | Description          | Value | Example
---------                    | -----------          | ----- | -------
name                         | 名稱                 |       |
description                  | 描述                 |       |
assigned_user_id             | 負責人               |       |
total_amt                    | 總計                 |       | 5971
total_amt_usdollar           | 總計（預設貨幣）     |       | 5971
discount_amount              | 折扣總計             |       | -30
discount_amount_usdollar     | 折扣總計（預設貨幣） |       | -30
subtotal_amount              | 小計總計             |       | total_amt - discount_amount = 5941
subtotal_amount_usdollar     | 小計總計             |       | 5941
tax_amount                   | 稅額                 |       | total_amt * 0.05 = 297.05
tax_amount_usdollar          | 稅額                 |       | 297.05
subtotal_tax_amount          | 小計                 |       | 0.000000
subtotal_tax_amount_usdollar | 小計（預設貨幣）     |       | 0.000000
total_amount                 | 總計                 |       | 6238.05
total_amount_usdollar        | 總計（預設貨幣）     |       | 6238.05
parent_type                  | 類型                 |       | AOS_Invoices


```json--request
{
    "data": {
        "type": "AOS_Line_Item_Groups",
        "attributes": {
            "name": "name",
            "description": "description",
            "total_amt": "180.000000",
            "total_amt_usdollar": "180.000000",
            "discount_amount": "0.000000",
            "discount_amount_usdollar": "0.000000",
            "subtotal_amount": "180.000000",
            "subtotal_amount_usdollar": "180.000000",
            "tax_amount": "0.000000",
            "tax_amount_usdollar": "0.000000",
            "subtotal_tax_amount": "0.000000",
            "subtotal_tax_amount_usdollar": "0.000000",
            "total_amount": "180.000000",
            "total_amount_usdollar": "180.000000",
            "parent_type": "AOS_Invoices",
            "parent_id": "{{invoice_id}}",
            "number": "1",
            "currency_id": "47009c9c-6151-33e1-49a1-5ea287700de2"
        }
    }
}
```

```json--response
{
    "data": {
        "type": "AOS_Line_Item_Groups",
        "id": "1f58e96f-f3aa-0937-f19d-5fa3d39107ce",
        "attributes": {
            "name": "name",
            "date_entered": "2020-11-05T10:27:00+08:00",
            "date_modified": "2020-11-05T10:27:00+08:00",
            "modified_user_id": "1",
            "modified_by_name": "Administrator",
            "created_by": "1",
            "created_by_name": "Administrator",
            "description": "description",
            "deleted": "0",
            "created_by_link": "",
            "modified_user_link": "",
            "assigned_user_id": "c56be602-4a6b-269c-e734-5eaeb97af366",
            "assigned_user_name": "ec_market",
            "assigned_user_link": "",
            "total_amt": "180.000000",
            "total_amt_usdollar": "180.000000",
            "discount_amount": "0.000000",
            "discount_amount_usdollar": "0.000000",
            "subtotal_amount": "180.000000",
            "subtotal_amount_usdollar": "180.000000",
            "tax_amount": "0.000000",
            "tax_amount_usdollar": "0.000000",
            "subtotal_tax_amount": "0.000000",
            "subtotal_tax_amount_usdollar": "0.000000",
            "total_amount": "180.000000",
            "total_amount_usdollar": "180.000000",
            "parent_name": "MIS004",
            "parent_type": "AOS_Invoices",
            "parent_id": "b4534cda-6fe8-2926-47b4-5fa3d3146c98",
            "number": "1",
            "currency_id": "47009c9c-6151-33e1-49a1-5ea287700de2",
            "aos_products_quotes": ""
        },
        "relationships": {
            "AOS_Products_Quotes": {
                "links": {
                    "related": "V8/module/1f58e96f-f3aa-0937-f19d-5fa3d39107ce/relationships/aos_products_quotes"
                }
            },
            "Users": {
                "links": {
                    "related": "V8/module/1f58e96f-f3aa-0937-f19d-5fa3d39107ce/relationships/created_by_link"
                }
            }
        }
    }
}
```

## Items

小計群組裡面的商品

Parameter                        | Description             | Value             | Example
---------                        | -----------             | -----             | -------
name                             | 名稱                    |                   |
description                      | 描述                    |                   |
assigned_user_id                 | 負責人                  |                   |
currency_id                      | 幣別                    | 預設貨幣(-99)     | -99
part_number                      | 部件編號                |                   | J_725_3314
item_description                 | 商品描述                |                   | ""
number                           | 順序                    |                   | 1
product_qty                      | 商品數量                |                   | 2
product_cost_price               | 商品成本                |                   | 2700
product_cost_price_usdollar      | 商品成本 (預設幣別)     |                   | 2700
product_list_price               | 商品價格                |                   | 2700
product_list_price_usdollar      | 商品價格 (預設幣別)     |                   | 2700
product_discount                 | 折扣                    |                   | 10
product_discount_usdollar        | 折扣 (預設幣別)         |                   | 10
product_discount_amount          | 折扣總計                |                   | ""
product_discount_amount_usdollar | 折扣總計 (預設幣別)     |                   | ""
discount                         | 折扣類型                | Amount, Percetage | Amount
product_unit_price               | 產品單位價格            |                   | 2690
product_unit_price_usdollar      | 產品單位價格 (預設幣別) |                   | 2690
vat_amt                          | 含稅價                  |                   | 269
vat_amt_usdollar                 | 含稅價 (預設幣別)       |                   | 269
product_total_price              | 商品含稅總額            |                   | 5380
product_total_price_usdollar     | 商品含稅總額 (預設幣別) |                   | 5380
vat                              | 稅率                    |                   | 5.0
parent_id                        | 發票編號                |                   | {{invoice_id}}
product_id                       | 產品編號                |                   | {{product_id}}
group_id                         | 小計編號（產品組）      |                   | {{item_group_id}

```json--request
{
    "data": {
        "type": "AOS_Products_Quotes",
        "attributes": {
            "name": "name",
            "description": "description",
            "deleted": "0",
            "assigned_user_id": "c56be602-4a6b-269c-e734-5eaeb97af366",
            "currency_id": "47009c9c-6151-33e1-49a1-5ea287700de2",
            "part_number": "M01990100000001",
            "item_description": "",
            "number": "1",
            "product_qty": "1.0000",
            "product_cost_price": "180.000000",
            "product_cost_price_usdollar": "180.000000",
            "product_list_price": "180.000000",
            "product_list_price_usdollar": "180.000000",
            "product_discount": "0.000000",
            "product_discount_usdollar": "0.000000",
            "product_discount_amount": "",
            "product_discount_amount_usdollar": "",
            "discount": "Percentage",
            "product_unit_price": "0.000000",
            "product_unit_price_usdollar": "0.000000",
            "vat_amt": "0.000000",
            "vat_amt_usdollar": "0.000000",
            "product_total_price": "180.000000",
            "product_total_price_usdollar": "180.000000",
            "vat": "0",
            "parent_name": "OD2020040900050",
            "parent_type": "AOS_Invoices",
            "parent_id": "{{invoice_id}}",
            "product_id": "{{product_id}}",
            "group_id": "{{item_group_id}}"
        }
    }
}
```

```json--response
{
    "data": {
        "type": "AOS_Products_Quotes",
        "attributes": {
            "name": "name",
            "description": "description",
            "deleted": "0",
            "assigned_user_id": "c56be602-4a6b-269c-e734-5eaeb97af366",
            "currency_id": "47009c9c-6151-33e1-49a1-5ea287700de2",
            "part_number": "M01990100000001",
            "item_description": "",
            "number": "1",
            "product_qty": "1.0000",
            "product_cost_price": "180.000000",
            "product_cost_price_usdollar": "180.000000",
            "product_list_price": "180.000000",
            "product_list_price_usdollar": "180.000000",
            "product_discount": "0.000000",
            "product_discount_usdollar": "0.000000",
            "product_discount_amount": "",
            "product_discount_amount_usdollar": "",
            "discount": "Percentage",
            "product_unit_price": "0.000000",
            "product_unit_price_usdollar": "0.000000",
            "vat_amt": "0.000000",
            "vat_amt_usdollar": "0.000000",
            "product_total_price": "180.000000",
            "product_total_price_usdollar": "180.000000",
            "vat": "0",
            "parent_name": "OD2020040900050",
            "parent_type": "AOS_Invoices",
            "parent_id": "{{invoice_id}}",
            "product_id": "{{product_id}}",
            "group_id": "{{item_group_id}}"
        }
    }
}
```

## Promotions

促銷相關訊息

Parameter        | Description  | Value | Example
---------        | -----------  | ----- | -------
name             | 促銷名稱     |       |
description      | 描述         |       |
assigned_user_id | 負責人       |       |
code             | 促銷編碼     |       |
priority         | 優先權       |       |
exclusive        | 獨一         | 0,1   |
usage_limit      | 使用次數限制 |       |
used             | 使用中       | 0,1   |
coupon_based     | 需配合折扣碼 | 0,1   |
date_start       | 開始日期     |       |
date_end         | 結束日期     |       |

Experiece Premium:34371b7d-6437-ca5c-a772-5facafb3942f

`GET http://example.com/Api/V8/module/OWL_Promotions?page[size]=10&page[number]=1&sort=name`

```json--response
{
    "meta": {
        "total-pages": 1,
        "records-on-this-page": 2
    },
    "data": [
        {
            "type": "OWL_Promotions",
            "id": "95ccec35-d944-3df1-edd1-5faba28ab21f",
            "attributes": {
                "name": "Market Premium 500",
                "date_entered": "2020-11-11T08:35:00+00:00",
                "date_modified": "2020-11-11T09:52:00+00:00",
                "modified_user_id": "1",
                "modified_by_name": "Administrator",
                "created_by": "1",
                "created_by_name": "Administrator",
                "description": "單筆消費折扣後滿 500 元即享免運費",
                "deleted": "0",
                "created_by_link": "",
                "modified_user_link": "",
                "assigned_user_id": "1",
                "assigned_user_name": "Administrator",
                "assigned_user_link": "",
                "SecurityGroups": "",
                "code": "Market Premium 500",
                "priority": "0",
                "exclusive": "0",
                "usage_limit": "0",
                "used": "0",
                "coupon_based": "0",
                "date_start": "2020-11-11T04:00:00+00:00",
                "date_end": "2020-11-11T05:00:00+00:00",
                "owl_promotionactions_owl_promotions": "",
                "owl_promotioncoupons_owl_promotions": "",
                "owl_promotionrules_owl_promotions": ""
            },
            "relationships": {
                "OWL_PromotionActions": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/95ccec35-d944-3df1-edd1-5faba28ab21f/relationships/owl_promotionactions_owl_promotions"
                    }
                },
                "OWL_PromotionCoupons": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/95ccec35-d944-3df1-edd1-5faba28ab21f/relationships/owl_promotioncoupons_owl_promotions"
                    }
                },
                "OWL_PromotionRules": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/95ccec35-d944-3df1-edd1-5faba28ab21f/relationships/owl_promotionrules_owl_promotions"
                    }
                },
                "SecurityGroups": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/95ccec35-d944-3df1-edd1-5faba28ab21f/relationships/SecurityGroups"
                    }
                },
                "Users": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/95ccec35-d944-3df1-edd1-5faba28ab21f/relationships/created_by_link"
                    }
                }
            }
        },
        {
            "type": "OWL_Promotions",
            "id": "cbfd0ade-3c89-5737-0933-5faba09842b2",
            "attributes": {
                "name": "Market Premium 9 percetage discount",
                "date_entered": "2020-11-11T08:27:00+00:00",
                "date_modified": "2020-11-11T08:33:00+00:00",
                "modified_user_id": "1",
                "modified_by_name": "Administrator",
                "created_by": "1",
                "created_by_name": "Administrator",
                "description": "",
                "deleted": "0",
                "created_by_link": "",
                "modified_user_link": "",
                "assigned_user_id": "1",
                "assigned_user_name": "Administrator",
                "assigned_user_link": "",
                "SecurityGroups": "",
                "code": "Market Premium",
                "priority": "0",
                "exclusive": "0",
                "usage_limit": "0",
                "used": "0",
                "coupon_based": "0",
                "date_start": "2020-11-11T04:00:00+00:00",
                "date_end": "2020-11-11T05:00:00+00:00",
                "owl_promotionactions_owl_promotions": "",
                "owl_promotioncoupons_owl_promotions": "",
                "owl_promotionrules_owl_promotions": ""
            },
            "relationships": {
                "OWL_PromotionActions": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/cbfd0ade-3c89-5737-0933-5faba09842b2/relationships/owl_promotionactions_owl_promotions"
                    }
                },
                "OWL_PromotionCoupons": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/cbfd0ade-3c89-5737-0933-5faba09842b2/relationships/owl_promotioncoupons_owl_promotions"
                    }
                },
                "OWL_PromotionRules": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/cbfd0ade-3c89-5737-0933-5faba09842b2/relationships/owl_promotionrules_owl_promotions"
                    }
                },
                "SecurityGroups": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/cbfd0ade-3c89-5737-0933-5faba09842b2/relationships/SecurityGroups"
                    }
                },
                "Users": {
                    "links": {
                        "related": "V8/module/OWL_Promotions/cbfd0ade-3c89-5737-0933-5faba09842b2/relationships/created_by_link"
                    }
                }
            }
        }
    ],
    "links": {
        "first": null,
        "prev": null,
        "next": null,
        "last": null
    }
}
```

## SecurityGroups

群組權限

Parameter        | Description  | Value | Example
---------        | -----------  | ----- | -------
name             | 群組名稱     |       |
description      | 描述         |       |

Experiece: 2
