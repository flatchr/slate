--- 

title: Flatchr API Documentation 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

This is a sample example of API documentation. 

**Version:** 1.8.2 

# /CANDIDATE/CHECK
## ***GET*** 

**Summary:** Check

**Description:** Check email to see if candidate email exist

### HTTP Request 
`***GET*** /candidate/check` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| email | query |  | Yes | string |
| key | query |  | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /CANDIDATE/{CANDIDATE}
## ***GET*** 

**Summary:** Consent

**Description:** Consent candidate information

### HTTP Request 
`***GET*** /candidate/{candidate}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| candidate | path |  | Yes | string |
| key | query |  | Yes | string |
| consent | query |  | Yes | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /COMPANY/{COMPANY}/SUBSCRIPTIONS
## ***GET*** 

**Summary:** Collection

**Description:** Get all subscriptions from a company

### HTTP Request 
`***GET*** /company/{company}/subscriptions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| company | path |  | Yes | string |
| fields | query |  | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /CANDIDATE
## ***POST*** 

**Summary:** Create Candidate

**Description:** create new candidate

### HTTP Request 
`***POST*** /candidate` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /COMPANY/{COMPANY}/SUBSCRIPTION
## ***POST*** 

**Summary:** Create

**Description:** Create a subscription

### HTTP Request 
`***POST*** /company/{company}/subscription` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| company | path |  | Yes | string |
| archive | query |  | No | boolean |
| iban | query |  | No | boolean |
| body | body |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /VACANCY/{VACANCY}/CANDIDATE
## ***POST*** 

**Summary:** Create Candidate

**Description:** create new candidate

### HTTP Request 
`***POST*** /vacancy/{vacancy}/candidate` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| vacancy | path |  | Yes | string |
| body | body |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /CANDIDATE/APPLICANT/{APPLICANT}
## ***DELETE*** 

**Summary:** Delete

**Description:** Delete candidate information

### HTTP Request 
`***DELETE*** /candidate/applicant/{applicant}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| applicant | path |  | Yes | string |
| key | query |  | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

# /COMPANY/{COMPANY}/APPLICANT/{APPLICANT}
## ***DELETE*** 

**Summary:** Delete

**Description:** Delete candidate information for a company

### HTTP Request 
`***DELETE*** /company/{company}/applicant/{applicant}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| company | path |  | Yes | string |
| applicant | path |  | Yes | string |
| fields | query |  | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| default | Successful |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
