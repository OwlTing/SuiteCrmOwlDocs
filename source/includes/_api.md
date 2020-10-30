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
lawful_basis               | 合法基礎                 | Consent, Contract, Legal obligation, Protection of interest, Public interest, Legitimate interest, Withdrawn
lawful_basis_source        | 合法基礎來源             | Website, Phone, Given to user, Email, Third Party
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
lawful_basis               | 合法基礎                 | Consent, Contract, Legal obligation, Protection of interest, Public interest, Legitimate interest, Withdrawn
lawful_basis_source        | 合法基礎來源             | Website, Phone, Given to user, Email, Third Party
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
