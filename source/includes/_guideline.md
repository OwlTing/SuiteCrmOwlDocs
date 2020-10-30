# GuideLine

## 建立潛在客戶

會員留下任意聯絡資訊的時候視為潛在客戶

### 1 建立 潛在客戶 (Leads)

`POST http://example.com/Api/V8/module`

```json--request

HTTP/1.1 201

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
            "phone_home": "+886 8-88888888",
            "phone_mobile": "+886 912345678",
            "phone_work": "+886 7-77777777",
            "phone_other": "+886 6-66666666",
            "phone_fax": "+886 1234567890",
            "email1": "mark_huang1@owlting.com",
            "primary_address_street": "primary_address_street",
            "primary_address_street_2": "primary_address_street_2",
            "primary_address_street_3": "primary_address_street_3",
            "primary_address_city": "primary_address_city",
            "primary_address_state": "primary_address_state",
            "primary_address_postalcode": "primary_address_postalcode",
            "primary_address_country": "primary_address_country",
            "lawful_basis": "Consent",
            "lawful_basis_source": "Website",
            "date_reviewed": "2020-10-06",
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

<aside class="warning"><strong>Important</strong>: 保留 Lead id 以便後續可以轉換為真實客戶</aside>


```json--response

HTTP/1.1 200
{
    "data": {
        "type": "Lead",
        "id": "c5b0c6b8-dbcd-ac19-b0bf-5f7a92d51a15",
        "attributes": {
          ...
        },
        "relationships": {
          ...
        }
    }
}

```


## 潛在客戶轉換成真實客戶

當使用者成功購買產品時

### 1. 檢查潛在客戶是否曾經被轉換為真實客戶

<aside class="warning"><strong>Information</strong>: 如果建立潛在客戶時選擇不保存 lead_id 則在查詢真實客戶時，務必小心使用 filter 的過濾功能，以免真實客戶被重複建立</aside>

`GET http://example.com/Api/V8/module/Contacts?filter[email1][eq]=example@example.com`

<aside class="info"><strong>Information</strong>: 成功建立過聯絡人則不再建立一次聯絡人</aside>

```json--response

HTTP/1.1 200
{
    "data": [
        {
            "type": "Contact",
            "id": "914afaa0-022a-8bce-36de-5ea15dd6868d",
            "attributes": {
                ...
                "email1": "example@example.com",
                ...
            },
            "relationships": {
                ...
            }
        }
    ]
}

HTTP/1.1 200
{
    "meta": {
        "message": "Request was successful, but there is no result"
    },
    "data": []
}

```


### 2. 若無真實客戶則需建立真實客戶

* 建立聯絡人

`POST http://example.com/Api/V8/module`

<aside class="warning"><strong>Important</strong>: 保留 contact id 為後續建立關聯的活動紀錄</aside>

```json--request

HTTP/1.1 201
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
            "phone_home": "+886 8-88888888",
            "phone_mobile": "+886 912345678",
            "phone_work": "+886 7-77777777",
            "phone_other": "+886 6-66666666",
            "phone_fax": "+886 1234567890",
            "email1": "mark_huang1@owlting.com",
            "primary_address_street": "primary_address_street",
            "primary_address_street_2": "primary_address_street_2",
            "primary_address_street_3": "primary_address_street_3",
            "primary_address_city": "primary_address_city",
            "primary_address_state": "primary_address_state",
            "primary_address_postalcode": "primary_address_postalcode",
            "primary_address_country": "primary_address_country",
            "lawful_basis": "Consent",
            "lawful_basis_source": "Website",
            "date_reviewed": "2020-10-06",
            "birthdate": "2020-10-06",
            "birth_of_day_c": "birth_of_day_c",
            "birth_of_year_c": "birth_of_year_c",
            "birth_of_month_c": "birth_of_month_c"
        }
    }
}

```

```json--response

{
    "data": {
        "type": "Contact",
        "id": "ed9a0c87-aa99-83bc-2268-5f7a9afefd5f",
        "attributes": {
          ...
        },
        "relationships": {
          ...
        }
    }
}

```

### 3. 完成真實客戶建立後需與潛在客戶建立關聯

需將 Leads 與 Contacts 建立關聯

* Create relationship

`POST http://example.com/Api/V8/module/Leads/{{lead_id}}/relationships`

```json--request

HTTP/1.1 201
{
  "data": {
    "type": "Contacts",
    "id": "{{contact_id}}"
  }
}

```

```json--response

{
    "meta": {
        "message": "Contact with id ed9a0c87-aa99-83bc-2268-5f7a9afefd5f has been added to Lead with id c5b0c6b8-dbcd-ac19-b0bf-5f7a92d51a15"
    },
    "data": []
}

```

### 4. 關聯潛在客戶及真實客戶後將 Leads 標為已經 轉換過

更新 Leads 的狀態


`PATCH http://example.com/Api/V8/module`

```
HTTP/1.1 201

{
  "data": {
    "type": "Lead",
    "id": "{{lead_id}}",
    "attributes": {
      "converted": "1",
      "status": "Converted"
    }
  }
}

```
