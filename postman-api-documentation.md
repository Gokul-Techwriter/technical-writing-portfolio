# Postman API Documentation

---

| **FIELD** | **DETAILS** |
|-----------|-------------|
| API Name  | Postman     |
| Version   | 12.8.4      |
| Base URL  | `https://api.getpostman.com` |
| Author    | Gokul S Anand |
| Last Updated | May 6, 2026  |

---

## Overview

Postman is a tool designed for testing and interacting with APIs. It enables users to send requests and view responses, supporting REST, GraphQL, WebSocket, and gRPC methods. This guide outlines the API endpoints for developers creating Postman integrations, specifically targeting those who are familiar with REST APIs but new to Postman.

---

## Base URL

`https://api.getpostman.com`

All endpoints are relative to this base URL.

---

## Authentication

To get an API Key:

1. Log in to `postman.com`

2. Go to **Settings** → **API Keys**

3. Click **Generate API Key**

> 📝 **Note:** Copy and store it securely; it won't be shown again.

Format of the API Key: `PMAK-xxxxxx`

Authorization: `X-API-Key` `PMAK-xxxxx`

> ⚠️ **Warning:** Never share your API key publicly.
> Keep it secure at all times.

---

## Rate Limiting

Postman's API has rate limits for each user during specific time periods. When you use a key, you're limited to 300 requests per minute. Every API response includes headers showing your usage.

---

## Headers

| **METHOD** | **HEADERS** |
|------------|-------------|
| GET        | `X-Api-Key` |
| POST       | `X-Api-Key`, `Content-Type: application/json` |
| PUT        | `X-Api-Key`, `Content-Type: application/json` |
| DELETE     | `X-Api-Key` |
 
---

## Response Format

All responses return JSON:

```json

{
    "workspaces": [
        {
            "id": "34ea80af-261d-4655-a9af-e56406de04e4",
            "name": "Personal Workspace",
            "type": "team",
            "visibility": "public",
            "createdBy": "53663724",
            "about": "This is your personal, private workspace to play around in.",
            "createdAt": "2026-04-01T05:26:12.000Z",
            "updatedAt": "2026-05-01T17:58:46.000Z"
        },
        {
            "id": "c13d343c-fbd2-4562-83d7-4c0c06240cca",
            "name": "Gokul S Ananad's Workspace",
            "type": "team",
            "visibility": "team",
            "createdBy": "53663724",
            "about": "",
            "createdAt": "2026-04-06T18:00:26.000Z",
            "updatedAt": "2026-04-07T10:02:55.000Z"
        },
        {
            "id": "c7cbd19a-7d42-4ede-a6db-d3007616590b",
            "name": "Notion Api Testing",
            "type": "team",
            "visibility": "team",
            "createdBy": "53663724",
            "about": "This workspace helps our team maintain a high quality bar for our APIs.",
            "createdAt": "2026-04-11T09:23:43.000Z",
            "updatedAt": "2026-04-11T09:23:45.000Z"
        }
    ]
}

```
---

## Endpoints

### 1. Fetch User Info

Returns details about the user info your API key is linked with.

#### Endpoint:

`GET /me`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "user": {
        "id": 53663724,
        "sub": "03fe0ae0-4b59-4239-9889-329ecdcc9057",
        "username": "gokul-s-anand",
        "email": "twrgokul02@gmail.com",
        "fullName": "Gokul S Ananad",
        "avatar": "https://res.cloudinary.com/postman/image/upload/t_user_profile_300/v1775021368359/user/2df13d22e41cc6c44b2a565493fd9d37",
        "isPublic": true,
        "emailVerified": true,
        "teamId": 14837945,
        "teamName": "Gokul S Ananad's Team",
        "teamDomain": "gold-trinity-1068502",
        "roles": [
            "admin",
            "billing",
            "user"
        ]
    },
    "operations": [
        {
            "name": "file_storage_limit",
            "limit": 100,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "flow_count",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "internal_specifications",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "performance_test_limit",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "test_data_retrieval",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "test_data_storage",
            "limit": 8.88,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "ai_millicredits",
            "limit": 50,
            "usage": 23,
            "overage": 0
        },
        {
            "name": "collection_run_limit",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "mock_usage",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "monitor_request_runs",
            "limit": 1000,
            "usage": 3,
            "overage": 0
        },
        {
            "name": "api_usage",
            "limit": 10000,
            "usage": 50,
            "overage": 0
        },
        {
            "name": "flow_requests",
            "limit": 25,
            "usage": 0,
            "overage": 0
        },
        {
            "name": "flows_local_runs",
            "limit": 99999999,
            "usage": 0,
            "overage": 0
        }
    ]
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `user`    | object   | User details    |
| `id`      | integer  | Unique identifier of the user |
| `sub`     | string   | Unique subject identifier of the user |
| `username` | string  | Username of the user |
| `email`   | string   | Email address of the user |
| `fullName` | string  | Full name of the user |
| `avatar`  | string   | URL of the user's profile image |
| `isPublic` | boolean | Indicates whether the user profile is public |
| `emailVerified` | boolean | Indicates whether the email is verified |
| `teamId`  | integer  | Identifier of the user's team |
| `teamName` | string  | Name of the user's team |
| `teamDomain` | string | Domain of the user's team |
| `roles`    | array   | List of roles assigned to the user |
| `roles[]`  | string  | Individual role assigned to the user |
| `operations` | array | List of operational limits and usage |
| `operations[]` | object | Individual operation object |
| `name`     | string  | Name of the operation |
| `limit`    | number  | Maximum allowed limit for the operation |
| `usage`    | number  | Current usage of the operation |
| `overage`  | number  | Amount exceeded beyond the limit |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | User info fetched successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 2. Get all Workspaces

Returns back all the workspaces that are linked to your API key.

#### Endpoint:

`GET /workspaces`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "workspaces": [
        {
            "id": "34ea80af-261d-4655-a9af-e56406de04e4",
            "name": "Personal Workspace",
            "type": "team",
            "visibility": "team",
            "createdBy": "53663724",
            "about": "This is your personal, private workspace to play around in.",
            "createdAt": "2026-04-01T05:26:12.000Z",
            "updatedAt": "2026-05-02T12:15:23.000Z"
        },
        {
            "id": "c13d343c-fbd2-4562-83d7-4c0c06240cca",
            "name": "Gokul S Ananad's Workspace",
            "type": "team",
            "visibility": "team",
            "createdBy": "53663724",
            "about": "",
            "createdAt": "2026-04-06T18:00:26.000Z",
            "updatedAt": "2026-04-07T10:02:55.000Z"
        },
        {
            "id": "c7cbd19a-7d42-4ede-a6db-d3007616590b",
            "name": "Notion Api Testing",
            "type": "team",
            "visibility": "team",
            "createdBy": "53663724",
            "about": "This workspace helps our team maintain a high quality bar for our APIs.",
            "createdAt": "2026-04-11T09:23:43.000Z",
            "updatedAt": "2026-04-11T09:23:45.000Z"
        },
        {
            "id": "67e2ac91-8342-4703-8d06-2b0eb0d34332",
            "name": "New Personal Workspace",
            "type": "team",
            "visibility": "personal",
            "createdBy": "53663724",
            "about": "",
            "createdAt": "2026-05-02T05:44:40.000Z",
            "updatedAt": "2026-05-02T05:44:40.000Z"
        },
        {
            "id": "2fb9a1bc-4b71-4d85-a8d2-2fb878507819",
            "name": "3esxfdvg",
            "type": "team",
            "visibility": "team",
            "createdBy": "53663724",
            "about": "This workspace helps our team maintain a high quality bar for our APIs.",
            "createdAt": "2026-05-02T06:12:23.000Z",
            "updatedAt": "2026-05-02T06:12:26.000Z"
        },
        {
            "id": "0bff42e2-a3b3-4531-bbca-64e03d42449e",
            "name": "user guide",
            "type": "team",
            "visibility": "public",
            "createdBy": "53663724",
            "about": "Public workspace.",
            "createdAt": "2026-05-02T12:06:13.000Z",
            "updatedAt": "2026-05-02T12:06:13.000Z"
        },
        {
            "id": "64fd966e-c700-4e3c-9d8f-a93edb7abfd6",
            "name": "po api",
            "type": "team",
            "visibility": "public",
            "createdBy": "53663724",
            "about": "Public workspace.",
            "createdAt": "2026-05-05T13:55:07.000Z",
            "updatedAt": "2026-05-05T13:55:07.000Z"
        }
    ]
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `workspaces` | array | List of workspace objects |
| `workspaces[]` | object | Individual workspace object |
| `id`      | string   | Unique identifier of the workspace |
| `name`    | string   | Name of the workspace |
| `type`    | string   | Type of the workspace (e.g., team) |
| `visibility` | string | Visibility level of the workspace (e.g., team, personal, public) |
| `createdBy` | string | Identifier of the user who created the workspace |
| `about`   | string   | Description of the workspace |
| `createdAt` | string | Timestamp when the workspace was created (ISO 8601) |
| `updatedAt` | string | Timestamp of the last update (ISO 8601) |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Collected all workspaces successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 3. Fetch a Specific Workspace

Returns details of a particular workspace.

#### Endpoint:

`GET /workspaces/{workspaceId}`

#### Path parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `workspaceID` | string | Yes      | Unique ID of the workspace |

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "workspace": {
        "id": "34ea80af-261d-4655-a9af-e56406de04e4",
        "name": "Personal Workspace",
        "type": "team",
        "description": null,
        "visibility": "team",
        "createdBy": "53663724",
        "updatedBy": "53663724",
        "createdAt": "2026-04-01T05:26:12.000Z",
        "updatedAt": "2026-05-02T12:15:23.000Z",
        "about": "This is your personal, private workspace to play around in.",
        "collections": [
            {
                "id": "db289dc7-d0f9-45f7-94ae-5c366c69f095",
                "name": "POSTMAN",
                "uid": "53663724-db289dc7-d0f9-45f7-94ae-5c366c69f095"
            },
            {
                "id": "15e3671f-9f6f-485c-89d6-9a32536f4d22",
                "name": "ANTHROPIC",
                "uid": "53663724-15e3671f-9f6f-485c-89d6-9a32536f4d22"
            },
            {
                "id": "c18dd000-f7ce-482a-847e-7e26a19fb71b",
                "name": "NOTION",
                "uid": "53663724-c18dd000-f7ce-482a-847e-7e26a19fb71b"
            },
            {
                "id": "e7ecb82e-f372-4353-805d-a0db8166176b",
                "name": "postman api doc",
                "uid": "53663724-e7ecb82e-f372-4353-805d-a0db8166176b"
            }
        ],
        "environments": [
            {
                "id": "9396fef2-ffc4-4f94-9ae1-04a1cf77bc18",
                "name": "GOKUL",
                "uid": "53663724-9396fef2-ffc4-4f94-9ae1-04a1cf77bc18"
            }
        ],
        "monitors": [
            {
                "id": "1f146c43-5f8a-4ce0-abe0-49ae56173d06",
                "name": "ANTHROPIC",
                "uid": "53663724-1f146c43-5f8a-4ce0-abe0-49ae56173d06",
                "deactivated": false
            }
        ]
    }
}

```
#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `workspace` | object | Workspace details |
| `id`      | string   | Unique identifier of the workspace |
| `name`    | string   | Name of the workspace |
| `type`    | string   | Type of the workspace (e.g., team) |
| `description` | null/string | Description of the workspace (null if not set) |
| `visibility` | string | Visibility level of the workspace |
| `createdBy` | string | Identifier of the user who created the workspace |
| `updatedBy` | string | Identifier of the user who last updated the workspace |
| `createdAt` | string | Timestamp when the workspace was created (ISO 8601) |
| `updatedAt` | string | Timestamp of the last update (ISO 8601) |
| `about`     | string | Additional information about the 
workspace |
| `collections` | array | List of collection objects |
| `collections[]` | object | Individual collection object |
| `id`      | string   | Unique identifier of the collection |
| `name`    | string | Name of the collection |
| `uid`     | string | Unique user-specific identifier of the collection  |
| `environments` | array | List of environment objects |
| `environments[]` | object | Individual environment object |
| `id`      | string | Unique identifier of the environment |
| `name`    | string | Name of the environment |
| `uid`     | string | Unique user-specific identifier of the environment |
| `monitors` | array | List of monitor objects |
| `monitors[]` | object | Individual monitor object |
| `id`      | string | Unique identifier of the monitor |
| `name`    | string | Name of the monitor |
| `uid`     | string | Unique user-specific identifier of the monitor |
| `deactivated` | boolean | Indicates whether the monitor is deactivated |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Specific workspace fetched successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 4. Create a Workspace

Creates a new workspace.

#### Endpoint:

`POST /workspaces`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |
| Content-Type | `application/json` |

#### Request:

```json

{
    "workspace": {
        "name": "user guide",
        "type": "public",
        "description": "This is a public workspace.",
        "about": "Public workspace."
    }
}

```
#### Request Fields

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `workspace` | object | Contains workspace creation details |
| `name`    | string   | Name of the workspace |
| `type`    | string   | Type/visibility of the workspace (e.g., public, team, private) |
| `description` | string | Short description of the workspace |
| `about`   | string   | Additional details or purpose of the workspace |

#### Response:

```json

{
    "workspace": {
        "id": "76de7912-a4ff-48d7-9d85-bdfa3de594e8",
        "name": "techTWR"
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `workspace` | object | Workspace details |
| `id`      | string   | Unique identifier of the workspace |
| `name`    | string   | Name of the workspace |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Create new workspace successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 5. Get all Collections

Returns back all the collections linked to your API key.

#### Endpoint:

`GET /collections`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response: 

```json

{
    "collections": [
        {
            "id": "15e3671f-9f6f-485c-89d6-9a32536f4d22",
            "name": "ANTHROPIC",
            "owner": "53663724",
            "createdAt": "2026-04-29T13:48:15.000Z",
            "updatedAt": "2026-04-29T13:50:17.000Z",
            "uid": "53663724-15e3671f-9f6f-485c-89d6-9a32536f4d22",
            "isPublic": false
        },
        {
            "id": "5409d1ac-77cf-4872-90ee-71e2afe4879a",
            "name": "API Portfolio",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:05:27.000Z",
            "updatedAt": "2026-05-02T06:05:28.000Z",
            "uid": "53663724-5409d1ac-77cf-4872-90ee-71e2afe4879a",
            "isPublic": false
        },
        {
            "id": "7de2c98e-79ba-46fb-b4b3-d6db57b1982b",
            "name": "Contract Testing",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:12:26.000Z",
            "updatedAt": "2026-05-02T06:12:27.000Z",
            "uid": "53663724-7de2c98e-79ba-46fb-b4b3-d6db57b1982b",
            "isPublic": false
        },
        {
            "id": "cdf10ded-f909-4ebc-bc29-1d04c42ba35c",
            "name": "Integration Testing",
            "owner": "53663724",
            "createdAt": "2026-04-11T09:23:46.000Z",
            "updatedAt": "2026-04-11T09:23:47.000Z",
            "uid": "53663724-cdf10ded-f909-4ebc-bc29-1d04c42ba35c",
            "isPublic": false
        },
        {
            "id": "d66d5052-2423-491d-aaf4-949ba7dbc0ae",
            "name": "Integration Testing",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:12:28.000Z",
            "updatedAt": "2026-05-02T06:12:29.000Z",
            "uid": "53663724-d66d5052-2423-491d-aaf4-949ba7dbc0ae",
            "isPublic": false
        },
        {
            "id": "67452ee7-f1ce-4d26-b54b-97b90080db30",
            "name": "Intro to Writing Tests",
            "owner": "53663724",
            "createdAt": "2026-04-11T09:23:46.000Z",
            "updatedAt": "2026-04-11T09:23:47.000Z",
            "uid": "53663724-67452ee7-f1ce-4d26-b54b-97b90080db30",
            "isPublic": false
        },
        {
            "id": "86ba07af-1747-47b2-99b2-6e2c4d723182",
            "name": "Intro to Writing Tests",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:12:28.000Z",
            "updatedAt": "2026-05-02T06:12:29.000Z",
            "uid": "53663724-86ba07af-1747-47b2-99b2-6e2c4d723182",
            "isPublic": false
        },
        {
            "id": "77c175aa-e8f6-48b0-aef5-db096157dec1",
            "name": "Mock Data Generation",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:12:28.000Z",
            "updatedAt": "2026-05-02T06:12:28.000Z",
            "uid": "53663724-77c175aa-e8f6-48b0-aef5-db096157dec1",
            "isPublic": false
        },
        {
            "id": "d76fdcb5-d0d4-4868-9ca0-94f7c6421f0e",
            "name": "Mock Data Generation",
            "owner": "53663724",
            "createdAt": "2026-04-11T09:23:46.000Z",
            "updatedAt": "2026-04-11T09:23:46.000Z",
            "uid": "53663724-d76fdcb5-d0d4-4868-9ca0-94f7c6421f0e",
            "isPublic": false
        },
        {
            "id": "c18dd000-f7ce-482a-847e-7e26a19fb71b",
            "name": "NOTION",
            "owner": "53663724",
            "createdAt": "2026-04-11T09:26:26.000Z",
            "updatedAt": "2026-05-01T11:04:17.000Z",
            "uid": "53663724-c18dd000-f7ce-482a-847e-7e26a19fb71b",
            "isPublic": false
        },
        {
            "id": "db289dc7-d0f9-45f7-94ae-5c366c69f095",
            "name": "POSTMAN",
            "owner": "53663724",
            "createdAt": "2026-05-01T18:28:10.000Z",
            "updatedAt": "2026-05-05T14:14:35.000Z",
            "uid": "53663724-db289dc7-d0f9-45f7-94ae-5c366c69f095",
            "isPublic": false
        },
        {
            "id": "6b5e29e5-920b-4423-be7c-b004fd2dab0c",
            "name": "Performance Testing",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:12:27.000Z",
            "updatedAt": "2026-05-02T06:12:28.000Z",
            "uid": "53663724-6b5e29e5-920b-4423-be7c-b004fd2dab0c",
            "isPublic": false
        },
        {
            "id": "248de445-d718-4004-ae0c-36d605d40472",
            "name": "Performance Testing",
            "owner": "53663724",
            "createdAt": "2026-04-11T09:23:46.000Z",
            "updatedAt": "2026-04-11T09:23:46.000Z",
            "uid": "53663724-248de445-d718-4004-ae0c-36d605d40472",
            "isPublic": false
        },
        {
            "id": "bc713bf6-d29d-48f3-b019-544085035094",
            "name": "Postman Portfolio",
            "owner": "53663724",
            "createdAt": "2026-05-05T14:12:05.000Z",
            "updatedAt": "2026-05-05T14:12:06.000Z",
            "uid": "53663724-bc713bf6-d29d-48f3-b019-544085035094",
            "isPublic": false
        },
        {
            "id": "0b19365d-9b6b-4891-8499-8198e11b9ba6",
            "name": "Postman Portfolio",
            "owner": "53663724",
            "createdAt": "2026-05-02T05:44:41.000Z",
            "updatedAt": "2026-05-02T05:44:41.000Z",
            "uid": "53663724-0b19365d-9b6b-4891-8499-8198e11b9ba6",
            "isPublic": false
        },
        {
            "id": "1d57910a-ced2-4320-9119-aae8a19c4522",
            "name": "Regression Testing",
            "owner": "53663724",
            "createdAt": "2026-04-11T09:23:45.000Z",
            "updatedAt": "2026-04-11T09:23:46.000Z",
            "uid": "53663724-1d57910a-ced2-4320-9119-aae8a19c4522",
            "isPublic": false
        },
        {
            "id": "3b9d9173-d0e8-4db2-919f-cf236565b1c2",
            "name": "Regression Testing",
            "owner": "53663724",
            "createdAt": "2026-05-02T06:12:27.000Z",
            "updatedAt": "2026-05-02T06:12:27.000Z",
            "uid": "53663724-3b9d9173-d0e8-4db2-919f-cf236565b1c2",
            "isPublic": false
        },
        {
            "id": "e7ecb82e-f372-4353-805d-a0db8166176b",
            "name": "postman api doc",
            "owner": "53663724",
            "createdAt": "2026-04-07T10:06:46.000Z",
            "updatedAt": "2026-05-05T14:10:15.000Z",
            "uid": "53663724-e7ecb82e-f372-4353-805d-a0db8166176b",
            "isPublic": false
        }
    ]
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `collections` | array | List of collection objects |
| `collections[]` | object | Individual collection object |
| `id`      | string | Unique identifier of the collection |
| `name`    | string | Name of the collection |
| `owner`   | string | Identifier of the collection owner |
| `createdAt` | string | Timestamp when the collection was created (ISO 8601) |
| `updatedAt` | string | Timestamp of the last update (ISO 8601) |
| `uid`     | string | Unique user-specific identifier of the collection |
| `isPublic` | boolean | Indicates whether the collection is 
public |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | All collections fetched successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 6. Fetch a Specific Collection

Returns details of a specific collection.

#### Endpoint:

`GET /collections/{collectionId}`

#### Path Parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `collectionID` | string | Yes | Unique ID of the collection |

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response: 

```json

{
    "collection": {
        "info": {
            "_postman_id": "c18dd000-f7ce-482a-847e-7e26a19fb71b",
            "name": "NOTION",
            "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
            "createdAt": "2026-04-11T09:26:26.000Z",
            "updatedAt": "2026-05-01T11:04:16.000Z",
            "lastUpdatedBy": "53663724",
            "uid": "53663724-c18dd000-f7ce-482a-847e-7e26a19fb71b"
        },
        "item": [
            {
                "name": "create a new page",
                "id": "9dd184e1-f275-4f63-b3a7-8880a4ea76a8",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "POST",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        },
                        {
                            "key": "Authorization",
                            "value": "Bearer_ntn_218336376358nHTIC0hAPiQMmZkKxFf17rCr8GcSdiGdwT",
                            "type": "text"
                        }
                    ],
                    "body": {
                        "mode": "raw",
                        "raw": "{\n  \"parent\": {\n    \"page_id\": \"34051562df03806ab9d7cd40439aef35\"\n  },\n  \"properties\": {\n    \"title\": {\n      \"title\": [{ \"text\": { \"content\": \"new notion\" } }]\n    }\n  }\n}"
                    },
                    "url": {
                        "raw": "https://api.notion.com/v1/pages",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "pages"
                        ]
                    }
                },
                "response": [
                    {
                        "id": "783ff102-c5bf-46e1-a137-979a3ac64720",
                        "name": "create a new page",
                        "originalRequest": {
                            "method": "POST",
                            "header": [
                                {
                                    "key": "Content-Type",
                                    "value": "application/json"
                                },
                                {
                                    "key": "Notion-Version",
                                    "value": "2022-06-28",
                                    "type": "text"
                                },
                                {
                                    "key": "Authorization",
                                    "value": "Bearer_ntn_218336376358nHTIC0hAPiQMmZkKxFf17rCr8GcSdiGdwT",
                                    "type": "text"
                                }
                            ],
                            "body": {
                                "mode": "raw",
                                "raw": "{\n  \"parent\": {\n    \"page_id\": \"34051562df03806ab9d7cd40439aef35\"\n  },\n  \"properties\": {\n    \"title\": {\n      \"title\": [{ \"text\": { \"content\": \"new notion\" } }]\n    }\n  }\n}"
                            },
                            "url": {
                                "raw": "https://api.notion.com/v1/pages",
                                "protocol": "https",
                                "host": [
                                    "api",
                                    "notion",
                                    "com"
                                ],
                                "path": [
                                    "v1",
                                    "pages"
                                ]
                            }
                        },
                        "status": "OK",
                        "code": 200,
                        "_postman_previewlanguage": "Text",
                        "header": [
                            {
                                "key": ":status",
                                "value": 200
                            },
                            {
                                "key": "date",
                                "value": "Mon, 13 Apr 2026 08:28:16 GMT"
                            },
                            {
                                "key": "content-type",
                                "value": "application/json; charset=utf-8"
                            },
                            {
                                "key": "cf-ray",
                                "value": "9eb918a71bf57f5f-MAA"
                            },
                            {
                                "key": "cf-cache-status",
                                "value": "DYNAMIC"
                            },
                            {
                                "key": "etag",
                                "value": "W/\"3d3-H9CaqJ36zbTMPM+agtvy/vH0IpY\""
                            },
                            {
                                "key": "server",
                                "value": "cloudflare"
                            },
                            {
                                "key": "strict-transport-security",
                                "value": "max-age=31536000; includeSubDomains; preload"
                            },
                            {
                                "key": "vary",
                                "value": "Accept-Encoding"
                            },
                            {
                                "key": "content-security-policy",
                                "value": "default-src 'none'"
                            },
                            {
                                "key": "referrer-policy",
                                "value": "strict-origin-when-cross-origin"
                            },
                            {
                                "key": "x-content-type-options",
                                "value": "nosniff"
                            },
                            {
                                "key": "x-dns-prefetch-control",
                                "value": "off"
                            },
                            {
                                "key": "x-download-options",
                                "value": "noopen"
                            },
                            {
                                "key": "x-frame-options",
                                "value": "SAMEORIGIN"
                            },
                            {
                                "key": "x-notion-request-id",
                                "value": "6648a0a9-e6fd-4443-8dc1-5f1886147ec1"
                            },
                            {
                                "key": "x-permitted-cross-domain-policies",
                                "value": "none"
                            },
                            {
                                "key": "x-xss-protection",
                                "value": "0"
                            },
                            {
                                "key": "content-encoding",
                                "value": "gzip"
                            },
                            {
                                "key": "alt-svc",
                                "value": "h3=\":443\"; ma=86400"
                            }
                        ],
                        "cookie": [],
                        "responseTime": null,
                        "body": "{\n    \"object\": \"page\",\n    \"id\": \"34151562-df03-81a6-a2c3-c82b3003edd8\",\n    \"created_time\": \"2026-04-13T08:28:00.000Z\",\n    \"last_edited_time\": \"2026-04-13T08:28:00.000Z\",\n    \"created_by\": {\n        \"object\": \"user\",\n        \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n    },\n    \"last_edited_by\": {\n        \"object\": \"user\",\n        \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n    },\n    \"cover\": null,\n    \"icon\": null,\n    \"parent\": {\n        \"type\": \"page_id\",\n        \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n    },\n    \"in_trash\": false,\n    \"is_archived\": false,\n    \"is_locked\": false,\n    \"properties\": {\n        \"title\": {\n            \"id\": \"title\",\n            \"type\": \"title\",\n            \"title\": [\n                {\n                    \"type\": \"text\",\n                    \"text\": {\n                        \"content\": \"new notion\",\n                        \"link\": null\n                    },\n                    \"annotations\": {\n                        \"bold\": false,\n                        \"italic\": false,\n                        \"strikethrough\": false,\n                        \"underline\": false,\n                        \"code\": false,\n                        \"color\": \"default\"\n                    },\n                    \"plain_text\": \"new notion\",\n                    \"href\": null\n                }\n            ]\n        }\n    },\n    \"url\": \"https://www.notion.so/new-notion-34151562df0381a6a2c3c82b3003edd8\",\n    \"public_url\": null,\n    \"archived\": false,\n    \"developer_survey\": \"https://notionup.typeform.com/to/bllBsoI4?utm_source=postman\",\n    \"request_id\": \"6648a0a9-e6fd-4443-8dc1-5f1886147ec1\"\n}",
                        "createdAt": "2026-04-13T09:47:51.000Z",
                        "updatedAt": "2026-04-13T09:47:51.000Z",
                        "uid": "53663724-783ff102-c5bf-46e1-a137-979a3ac64720"
                    }
                ],
                "createdAt": "2026-04-11T09:27:37.000Z",
                "updatedAt": "2026-04-13T11:12:31.000Z",
                "uid": "53663724-9dd184e1-f275-4f63-b3a7-8880a4ea76a8"
            },
            {
                "name": "fetch a page by id",
                "id": "9ebaa941-cbfc-4f9c-b047-c284283cd124",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "GET",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json",
                            "type": "text"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        }
                    ],
                    "url": {
                        "raw": "https://api.notion.com/v1/pages/34051562df03806ab9d7cd40439aef35",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "pages",
                            "34051562df03806ab9d7cd40439aef35"
                        ]
                    }
                },
                "response": [
                    {
                        "id": "02478d6c-0193-4327-89d1-e0c86d06c2f4",
                        "name": "fetch a page by id",
                        "originalRequest": {
                            "method": "GET",
                            "header": [
                                {
                                    "key": "Content-Type",
                                    "value": "application/json",
                                    "type": "text"
                                },
                                {
                                    "key": "Notion-Version",
                                    "value": "2022-06-28",
                                    "type": "text"
                                },
                                {
                                    "key": "Authorization",
                                    "value": "{{vault:bearer-token}}",
                                    "type": "text"
                                }
                            ],
                            "url": {
                                "raw": "https://api.notion.com/v1/pages/34051562df03806ab9d7cd40439aef35",
                                "protocol": "https",
                                "host": [
                                    "api",
                                    "notion",
                                    "com"
                                ],
                                "path": [
                                    "v1",
                                    "pages",
                                    "34051562df03806ab9d7cd40439aef35"
                                ]
                            }
                        },
                        "status": "OK",
                        "code": 200,
                        "_postman_previewlanguage": "Text",
                        "header": [
                            {
                                "key": ":status",
                                "value": 200
                            },
                            {
                                "key": "date",
                                "value": "Mon, 13 Apr 2026 08:27:32 GMT"
                            },
                            {
                                "key": "content-type",
                                "value": "application/json; charset=utf-8"
                            },
                            {
                                "key": "cf-ray",
                                "value": "9eb9178ecfc17f5f-MAA"
                            },
                            {
                                "key": "cf-cache-status",
                                "value": "DYNAMIC"
                            },
                            {
                                "key": "content-encoding",
                                "value": "gzip"
                            },
                            {
                                "key": "etag",
                                "value": "W/\"42d-PtfoTrA7xVIcGAVgpDnDPjyjazE\""
                            },
                            {
                                "key": "server",
                                "value": "cloudflare"
                            },
                            {
                                "key": "strict-transport-security",
                                "value": "max-age=31536000; includeSubDomains; preload"
                            },
                            {
                                "key": "vary",
                                "value": "Accept-Encoding"
                            },
                            {
                                "key": "content-security-policy",
                                "value": "default-src 'none'"
                            },
                            {
                                "key": "referrer-policy",
                                "value": "strict-origin-when-cross-origin"
                            },
                            {
                                "key": "x-content-type-options",
                                "value": "nosniff"
                            },
                            {
                                "key": "x-dns-prefetch-control",
                                "value": "off"
                            },
                            {
                                "key": "x-download-options",
                                "value": "noopen"
                            },
                            {
                                "key": "x-frame-options",
                                "value": "SAMEORIGIN"
                            },
                            {
                                "key": "x-notion-request-id",
                                "value": "f2a7d57a-09bd-465b-8bbd-732b8ef9ed1a"
                            },
                            {
                                "key": "x-permitted-cross-domain-policies",
                                "value": "none"
                            },
                            {
                                "key": "x-xss-protection",
                                "value": "0"
                            },
                            {
                                "key": "alt-svc",
                                "value": "h3=\":443\"; ma=86400"
                            }
                        ],
                        "cookie": [],
                        "responseTime": null,
                        "body": "{\n    \"object\": \"page\",\n    \"id\": \"34051562-df03-806a-b9d7-cd40439aef35\",\n    \"created_time\": \"2026-04-12T11:55:00.000Z\",\n    \"last_edited_time\": \"2026-04-13T07:16:00.000Z\",\n    \"created_by\": {\n        \"object\": \"user\",\n        \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n    },\n    \"last_edited_by\": {\n        \"object\": \"user\",\n        \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n    },\n    \"cover\": {\n        \"type\": \"external\",\n        \"external\": {\n            \"url\": \"https://www.notion.so/images/page-cover/nationalMuseumOfAsianArt_landscapeWithGibbonsAndCranes.jpg\"\n        }\n    },\n    \"icon\": null,\n    \"parent\": {\n        \"type\": \"workspace\",\n        \"workspace\": true\n    },\n    \"in_trash\": false,\n    \"is_archived\": false,\n    \"is_locked\": false,\n    \"properties\": {\n        \"title\": {\n            \"id\": \"title\",\n            \"type\": \"title\",\n            \"title\": [\n                {\n                    \"type\": \"text\",\n                    \"text\": {\n                        \"content\": \"gokul\",\n                        \"link\": null\n                    },\n                    \"annotations\": {\n                        \"bold\": false,\n                        \"italic\": false,\n                        \"strikethrough\": false,\n                        \"underline\": false,\n                        \"code\": false,\n                        \"color\": \"default\"\n                    },\n                    \"plain_text\": \"gokul\",\n                    \"href\": null\n                }\n            ]\n        }\n    },\n    \"url\": \"https://www.notion.so/gokul-34051562df03806ab9d7cd40439aef35\",\n    \"public_url\": null,\n    \"archived\": false,\n    \"developer_survey\": \"https://notionup.typeform.com/to/bllBsoI4?utm_source=postman\",\n    \"request_id\": \"f2a7d57a-09bd-465b-8bbd-732b8ef9ed1a\"\n}",
                        "createdAt": "2026-04-13T09:47:59.000Z",
                        "updatedAt": "2026-04-13T09:47:59.000Z",
                        "uid": "53663724-02478d6c-0193-4327-89d1-e0c86d06c2f4"
                    }
                ],
                "createdAt": "2026-04-13T06:07:21.000Z",
                "updatedAt": "2026-04-13T09:47:59.000Z",
                "uid": "53663724-9ebaa941-cbfc-4f9c-b047-c284283cd124"
            },
            {
                "name": "update page",
                "id": "5e23b692-3cd0-4607-8e42-e7adc8789dfd",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "PATCH",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json",
                            "type": "text"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        }
                    ],
                    "body": {
                        "mode": "raw",
                        "raw": "{\r\n  \"properties\": {\r\n    \"title\": {\r\n      \"title\": [{ \"text\": { \"content\": \"gokul\" } }]\r\n    }\r\n  }\r\n}",
                        "options": {
                            "raw": {
                                "language": "json"
                            }
                        }
                    },
                    "url": {
                        "raw": "https://api.notion.com/v1/pages/34051562df03806ab9d7cd40439aef35",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "pages",
                            "34051562df03806ab9d7cd40439aef35"
                        ]
                    }
                },
                "response": [],
                "createdAt": "2026-04-13T07:23:58.000Z",
                "updatedAt": "2026-04-13T07:23:58.000Z",
                "uid": "53663724-5e23b692-3cd0-4607-8e42-e7adc8789dfd"
            },
            {
                "name": "retreive base schema",
                "id": "9f3dfaa8-cf15-436c-9faf-e5647d46f27f",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "GET",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json",
                            "type": "text"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        }
                    ],
                    "url": {
                        "raw": "https://api.notion.com/v1/databases/34151562df0380c3a20bfed75ebccced",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "databases",
                            "34151562df0380c3a20bfed75ebccced"
                        ]
                    }
                },
                "response": [],
                "createdAt": "2026-04-13T18:20:09.000Z",
                "updatedAt": "2026-04-13T18:20:09.000Z",
                "uid": "53663724-9f3dfaa8-cf15-436c-9faf-e5647d46f27f"
            },
            {
                "name": "retreive child blocks",
                "id": "d4984a2f-98fa-438e-9399-2318387fc419",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "GET",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json",
                            "type": "text"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        }
                    ],
                    "url": {
                        "raw": "https://api.notion.com/v1/blocks/34051562df03806ab9d7cd40439aef35/children",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "blocks",
                            "34051562df03806ab9d7cd40439aef35",
                            "children"
                        ]
                    }
                },
                "response": [
                    {
                        "id": "4730c0e7-2f42-447b-9909-16da0f19162a",
                        "name": "retreive child blocks",
                        "originalRequest": {
                            "method": "GET",
                            "header": [
                                {
                                    "key": "Content-Type",
                                    "value": "application/json",
                                    "type": "text"
                                },
                                {
                                    "key": "Notion-Version",
                                    "value": "2022-06-28",
                                    "type": "text"
                                }
                            ],
                            "url": {
                                "raw": "https://api.notion.com/v1/blocks/34051562df03806ab9d7cd40439aef35/children",
                                "protocol": "https",
                                "host": [
                                    "api",
                                    "notion",
                                    "com"
                                ],
                                "path": [
                                    "v1",
                                    "blocks",
                                    "34051562df03806ab9d7cd40439aef35",
                                    "children"
                                ]
                            }
                        },
                        "status": "OK",
                        "code": 200,
                        "_postman_previewlanguage": "Text",
                        "header": [
                            {
                                "key": ":status",
                                "value": 200
                            },
                            {
                                "key": "date",
                                "value": "Mon, 13 Apr 2026 18:24:47 GMT"
                            },
                            {
                                "key": "content-type",
                                "value": "application/json; charset=utf-8"
                            },
                            {
                                "key": "cf-ray",
                                "value": "9ebc8272fbd92c07-MAA"
                            },
                            {
                                "key": "cf-cache-status",
                                "value": "DYNAMIC"
                            },
                            {
                                "key": "content-encoding",
                                "value": "gzip"
                            },
                            {
                                "key": "etag",
                                "value": "W/\"1277-D5cH6dWWdEsiV6J/wPnOdVgUHHA\""
                            },
                            {
                                "key": "server",
                                "value": "cloudflare"
                            },
                            {
                                "key": "strict-transport-security",
                                "value": "max-age=31536000; includeSubDomains; preload"
                            },
                            {
                                "key": "vary",
                                "value": "Accept-Encoding"
                            },
                            {
                                "key": "content-security-policy",
                                "value": "default-src 'none'"
                            },
                            {
                                "key": "referrer-policy",
                                "value": "strict-origin-when-cross-origin"
                            },
                            {
                                "key": "x-content-type-options",
                                "value": "nosniff"
                            },
                            {
                                "key": "x-dns-prefetch-control",
                                "value": "off"
                            },
                            {
                                "key": "x-download-options",
                                "value": "noopen"
                            },
                            {
                                "key": "x-frame-options",
                                "value": "SAMEORIGIN"
                            },
                            {
                                "key": "x-notion-request-id",
                                "value": "7e27e82d-c1dc-4ff2-9ed3-522e363bc650"
                            },
                            {
                                "key": "x-permitted-cross-domain-policies",
                                "value": "none"
                            },
                            {
                                "key": "x-xss-protection",
                                "value": "0"
                            },
                            {
                                "key": "alt-svc",
                                "value": "h3=\":443\"; ma=86400"
                            }
                        ],
                        "cookie": [],
                        "responseTime": null,
                        "body": "{\n    \"object\": \"list\",\n    \"results\": [\n        {\n            \"object\": \"block\",\n            \"id\": \"34051562-df03-80c0-bc43-fce363bee5bf\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-12T11:56:00.000Z\",\n            \"last_edited_time\": \"2026-04-12T11:59:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"paragraph\",\n            \"paragraph\": {\n                \"rich_text\": [\n                    {\n                        \"type\": \"text\",\n                        \"text\": {\n                            \"content\": \"Notion is used by 30 million people globally for documentation, project management, and knowledge bases. We expose a public API allowing developers to build integrations — automating page creation, database queries, and content updates. Our current API docs are written by engineers and lack clarity for developers new to our platform. We need a Technical Writer to rebuild the core API reference.\",\n                            \"link\": null\n                        },\n                        \"annotations\": {\n                            \"bold\": false,\n                            \"italic\": false,\n                            \"strikethrough\": false,\n                            \"underline\": false,\n                            \"code\": false,\n                            \"color\": \"default\"\n                        },\n                        \"plain_text\": \"Notion is used by 30 million people globally for documentation, project management, and knowledge bases. We expose a public API allowing developers to build integrations — automating page creation, database queries, and content updates. Our current API docs are written by engineers and lack clarity for developers new to our platform. We need a Technical Writer to rebuild the core API reference.\",\n                        \"href\": null\n                    }\n                ],\n                \"icon\": null,\n                \"color\": \"default\"\n            },\n            \"archived\": false\n        },\n        {\n            \"object\": \"block\",\n            \"id\": \"34051562-df03-81d0-b27f-e1622a0bf74f\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-12T12:36:00.000Z\",\n            \"last_edited_time\": \"2026-04-13T18:19:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"child_page\",\n            \"child_page\": {\n                \"title\": \"Brand\"\n            },\n            \"archived\": false\n        },\n        {\n            \"object\": \"block\",\n            \"id\": \"34151562-df03-80f6-a134-d0225736708b\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-13T10:55:00.000Z\",\n            \"last_edited_time\": \"2026-04-13T10:55:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"paragraph\",\n            \"paragraph\": {\n                \"rich_text\": [],\n                \"icon\": null,\n                \"color\": \"default\"\n            },\n            \"archived\": false\n        },\n        {\n            \"object\": \"block\",\n            \"id\": \"34151562-df03-8146-92d4-cf446fbd43a5\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-13T06:05:00.000Z\",\n            \"last_edited_time\": \"2026-04-13T06:05:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"child_page\",\n            \"child_page\": {\n                \"title\": \"new notion\"\n            },\n            \"archived\": false\n        },\n        {\n            \"object\": \"block\",\n            \"id\": \"34151562-df03-8157-ac8f-dd6065bdb7a6\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-13T08:28:00.000Z\",\n            \"last_edited_time\": \"2026-04-13T08:28:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"child_page\",\n            \"child_page\": {\n                \"title\": \"new notion\"\n            },\n            \"archived\": false\n        },\n        {\n            \"object\": \"block\",\n            \"id\": \"34151562-df03-81a6-a2c3-c82b3003edd8\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-13T08:28:00.000Z\",\n            \"last_edited_time\": \"2026-04-13T08:28:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"child_page\",\n            \"child_page\": {\n                \"title\": \"new notion\"\n            },\n            \"archived\": false\n        },\n        {\n            \"object\": \"block\",\n            \"id\": \"34151562-df03-8006-bebe-e7407547a187\",\n            \"parent\": {\n                \"type\": \"page_id\",\n                \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n            },\n            \"created_time\": \"2026-04-13T10:56:00.000Z\",\n            \"last_edited_time\": \"2026-04-13T10:56:00.000Z\",\n            \"created_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"last_edited_by\": {\n                \"object\": \"user\",\n                \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n            },\n            \"has_children\": false,\n            \"in_trash\": false,\n            \"type\": \"paragraph\",\n            \"paragraph\": {\n                \"rich_text\": [],\n                \"icon\": null,\n                \"color\": \"default\"\n            },\n            \"archived\": false\n        }\n    ],\n    \"next_cursor\": null,\n    \"has_more\": false,\n    \"type\": \"block\",\n    \"block\": {},\n    \"developer_survey\": \"https://notionup.typeform.com/to/bllBsoI4?utm_source=postman\",\n    \"request_id\": \"7e27e82d-c1dc-4ff2-9ed3-522e363bc650\"\n}",
                        "createdAt": "2026-04-13T18:29:47.000Z",
                        "updatedAt": "2026-04-13T18:29:47.000Z",
                        "uid": "53663724-4730c0e7-2f42-447b-9909-16da0f19162a"
                    }
                ],
                "createdAt": "2026-04-13T18:29:42.000Z",
                "updatedAt": "2026-04-13T18:29:47.000Z",
                "uid": "53663724-d4984a2f-98fa-438e-9399-2318387fc419"
            },
            {
                "name": "update block",
                "id": "b5b41fc1-4a5f-45bb-8745-ca3bb5b2ba47",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "PATCH",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json",
                            "type": "text"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        }
                    ],
                    "body": {
                        "mode": "raw",
                        "raw": "{\r\n  \"paragraph\": {\r\n    \"rich_text\": [{ \"text\": { \"content\": \"make the title full bold\" } }]\r\n  }\r\n}",
                        "options": {
                            "raw": {
                                "language": "json"
                            }
                        }
                    },
                    "url": {
                        "raw": "https://api.notion.com/v1/blocks/34051562-df03-80c0-bc43-fce363bee5bf",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "blocks",
                            "34051562-df03-80c0-bc43-fce363bee5bf"
                        ]
                    }
                },
                "response": [
                    {
                        "id": "a1933e93-459c-461f-a1c6-74a15421af77",
                        "name": "update block",
                        "originalRequest": {
                            "method": "PATCH",
                            "header": [
                                {
                                    "key": "Content-Type",
                                    "value": "application/json",
                                    "type": "text"
                                },
                                {
                                    "key": "Notion-Version",
                                    "value": "2022-06-28",
                                    "type": "text"
                                }
                            ],
                            "body": {
                                "mode": "raw",
                                "raw": "{\r\n  \"paragraph\": {\r\n    \"rich_text\": [{ \"text\": { \"content\": \"make the title full bold\" } }]\r\n  }\r\n}",
                                "options": {
                                    "raw": {
                                        "language": "json"
                                    }
                                }
                            },
                            "url": {
                                "raw": "https://api.notion.com/v1/blocks/34051562-df03-80c0-bc43-fce363bee5bf",
                                "protocol": "https",
                                "host": [
                                    "api",
                                    "notion",
                                    "com"
                                ],
                                "path": [
                                    "v1",
                                    "blocks",
                                    "34051562-df03-80c0-bc43-fce363bee5bf"
                                ]
                            }
                        },
                        "status": "OK",
                        "code": 200,
                        "_postman_previewlanguage": "Text",
                        "header": [
                            {
                                "key": ":status",
                                "value": 200
                            },
                            {
                                "key": "date",
                                "value": "Mon, 13 Apr 2026 18:56:13 GMT"
                            },
                            {
                                "key": "content-type",
                                "value": "application/json; charset=utf-8"
                            },
                            {
                                "key": "cf-ray",
                                "value": "9ebcb0839bb1c784-MAA"
                            },
                            {
                                "key": "cf-cache-status",
                                "value": "DYNAMIC"
                            },
                            {
                                "key": "etag",
                                "value": "W/\"378-iNWVvNmsyfdViAsNxh6pZzrbzws\""
                            },
                            {
                                "key": "server",
                                "value": "cloudflare"
                            },
                            {
                                "key": "strict-transport-security",
                                "value": "max-age=31536000; includeSubDomains; preload"
                            },
                            {
                                "key": "vary",
                                "value": "Accept-Encoding"
                            },
                            {
                                "key": "content-security-policy",
                                "value": "default-src 'none'"
                            },
                            {
                                "key": "referrer-policy",
                                "value": "strict-origin-when-cross-origin"
                            },
                            {
                                "key": "x-content-type-options",
                                "value": "nosniff"
                            },
                            {
                                "key": "x-dns-prefetch-control",
                                "value": "off"
                            },
                            {
                                "key": "x-download-options",
                                "value": "noopen"
                            },
                            {
                                "key": "x-frame-options",
                                "value": "SAMEORIGIN"
                            },
                            {
                                "key": "x-notion-request-id",
                                "value": "d3d94088-d43e-414d-8a19-9e6dd1622b3b"
                            },
                            {
                                "key": "x-permitted-cross-domain-policies",
                                "value": "none"
                            },
                            {
                                "key": "x-xss-protection",
                                "value": "0"
                            },
                            {
                                "key": "content-encoding",
                                "value": "gzip"
                            },
                            {
                                "key": "alt-svc",
                                "value": "h3=\":443\"; ma=86400"
                            }
                        ],
                        "cookie": [],
                        "responseTime": null,
                        "body": "{\n    \"object\": \"block\",\n    \"id\": \"34051562-df03-80c0-bc43-fce363bee5bf\",\n    \"parent\": {\n        \"type\": \"page_id\",\n        \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n    },\n    \"created_time\": \"2026-04-12T11:56:00.000Z\",\n    \"last_edited_time\": \"2026-04-13T18:56:00.000Z\",\n    \"created_by\": {\n        \"object\": \"user\",\n        \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n    },\n    \"last_edited_by\": {\n        \"object\": \"user\",\n        \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n    },\n    \"has_children\": false,\n    \"in_trash\": false,\n    \"type\": \"paragraph\",\n    \"paragraph\": {\n        \"rich_text\": [\n            {\n                \"type\": \"text\",\n                \"text\": {\n                    \"content\": \"make the title full bold\",\n                    \"link\": null\n                },\n                \"annotations\": {\n                    \"bold\": false,\n                    \"italic\": false,\n                    \"strikethrough\": false,\n                    \"underline\": false,\n                    \"code\": false,\n                    \"color\": \"default\"\n                },\n                \"plain_text\": \"make the title full bold\",\n                \"href\": null\n            }\n        ],\n        \"icon\": null,\n        \"color\": \"default\"\n    },\n    \"archived\": false,\n    \"developer_survey\": \"https://notionup.typeform.com/to/bllBsoI4?utm_source=postman\",\n    \"request_id\": \"d3d94088-d43e-414d-8a19-9e6dd1622b3b\"\n}",
                        "createdAt": "2026-04-13T18:57:10.000Z",
                        "updatedAt": "2026-04-13T18:57:10.000Z",
                        "uid": "53663724-a1933e93-459c-461f-a1c6-74a15421af77"
                    }
                ],
                "createdAt": "2026-04-13T18:57:03.000Z",
                "updatedAt": "2026-04-13T18:57:10.000Z",
                "uid": "53663724-b5b41fc1-4a5f-45bb-8745-ca3bb5b2ba47"
            },
            {
                "name": "delete a block",
                "id": "834d41f3-5881-4cfe-b784-d16fa60da804",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "bearer",
                        "bearer": [
                            {
                                "key": "token",
                                "value": "{{vault:authorization-secret}}",
                                "type": "string"
                            }
                        ]
                    },
                    "method": "DELETE",
                    "header": [
                        {
                            "key": "Content-Type",
                            "value": "application/json",
                            "type": "text"
                        },
                        {
                            "key": "Notion-Version",
                            "value": "2022-06-28",
                            "type": "text"
                        }
                    ],
                    "url": {
                        "raw": "https://api.notion.com/v1/blocks/34051562-df03-80c0-bc43-fce363bee5bf",
                        "protocol": "https",
                        "host": [
                            "api",
                            "notion",
                            "com"
                        ],
                        "path": [
                            "v1",
                            "blocks",
                            "34051562-df03-80c0-bc43-fce363bee5bf"
                        ]
                    }
                },
                "response": [
                    {
                        "id": "aef43eb3-5d52-4ab6-818a-1ac7fed26595",
                        "name": "delete a block",
                        "originalRequest": {
                            "method": "DELETE",
                            "header": [
                                {
                                    "key": "Content-Type",
                                    "value": "application/json",
                                    "type": "text"
                                },
                                {
                                    "key": "Notion-Version",
                                    "value": "2022-06-28",
                                    "type": "text"
                                }
                            ],
                            "url": {
                                "raw": "https://api.notion.com/v1/blocks/34051562-df03-80c0-bc43-fce363bee5bf",
                                "protocol": "https",
                                "host": [
                                    "api",
                                    "notion",
                                    "com"
                                ],
                                "path": [
                                    "v1",
                                    "blocks",
                                    "34051562-df03-80c0-bc43-fce363bee5bf"
                                ]
                            }
                        },
                        "status": "OK",
                        "code": 200,
                        "_postman_previewlanguage": "Text",
                        "header": [
                            {
                                "key": ":status",
                                "value": 200
                            },
                            {
                                "key": "date",
                                "value": "Tue, 14 Apr 2026 06:32:23 GMT"
                            },
                            {
                                "key": "content-type",
                                "value": "application/json; charset=utf-8"
                            },
                            {
                                "key": "cf-ray",
                                "value": "9ec0ac401957c87a-MAA"
                            },
                            {
                                "key": "cf-cache-status",
                                "value": "DYNAMIC"
                            },
                            {
                                "key": "etag",
                                "value": "W/\"376-rmK7mcirsliEclRQTeR4EPr7asY\""
                            },
                            {
                                "key": "server",
                                "value": "cloudflare"
                            },
                            {
                                "key": "strict-transport-security",
                                "value": "max-age=31536000; includeSubDomains; preload"
                            },
                            {
                                "key": "vary",
                                "value": "Accept-Encoding"
                            },
                            {
                                "key": "content-security-policy",
                                "value": "default-src 'none'"
                            },
                            {
                                "key": "referrer-policy",
                                "value": "strict-origin-when-cross-origin"
                            },
                            {
                                "key": "x-content-type-options",
                                "value": "nosniff"
                            },
                            {
                                "key": "x-dns-prefetch-control",
                                "value": "off"
                            },
                            {
                                "key": "x-download-options",
                                "value": "noopen"
                            },
                            {
                                "key": "x-frame-options",
                                "value": "SAMEORIGIN"
                            },
                            {
                                "key": "x-notion-request-id",
                                "value": "6e691175-31ac-47f3-92bf-860f415b5b54"
                            },
                            {
                                "key": "x-permitted-cross-domain-policies",
                                "value": "none"
                            },
                            {
                                "key": "x-xss-protection",
                                "value": "0"
                            },
                            {
                                "key": "set-cookie",
                                "value": "__cf_bm=yXhovuB9QPPQ5OGpYSCclc9Ivk8ucGpp08XdEFoE21o-1776148341.7732544-1.0.1.1-Cs08uYMJXuXaiArbHSdiiX9ZEucAiX4Iq0Y8ysZSOGRrRfxkHegizooPozDWIi3fr6iOpTYH5SijQsYENEF.iWWzPmfG.OspXFoxFsyLKLe_ml4bFQy84xsuHC.NQmcL; HttpOnly; Secure; Path=/; Domain=notion.com; Expires=Tue, 14 Apr 2026 07:02:23 GMT"
                            },
                            {
                                "key": "content-encoding",
                                "value": "gzip"
                            },
                            {
                                "key": "alt-svc",
                                "value": "h3=\":443\"; ma=86400"
                            }
                        ],
                        "cookie": [],
                        "responseTime": null,
                        "body": "{\n    \"object\": \"block\",\n    \"id\": \"34051562-df03-80c0-bc43-fce363bee5bf\",\n    \"parent\": {\n        \"type\": \"page_id\",\n        \"page_id\": \"34051562-df03-806a-b9d7-cd40439aef35\"\n    },\n    \"created_time\": \"2026-04-12T11:56:00.000Z\",\n    \"last_edited_time\": \"2026-04-14T06:32:00.000Z\",\n    \"created_by\": {\n        \"object\": \"user\",\n        \"id\": \"33ed872b-594c-81ef-a03c-00026e2d4efd\"\n    },\n    \"last_edited_by\": {\n        \"object\": \"user\",\n        \"id\": \"33f51562-df03-81b1-bc3a-0027d86fa2da\"\n    },\n    \"has_children\": false,\n    \"in_trash\": true,\n    \"type\": \"paragraph\",\n    \"paragraph\": {\n        \"rich_text\": [\n            {\n                \"type\": \"text\",\n                \"text\": {\n                    \"content\": \"make the title full bold\",\n                    \"link\": null\n                },\n                \"annotations\": {\n                    \"bold\": false,\n                    \"italic\": false,\n                    \"strikethrough\": false,\n                    \"underline\": false,\n                    \"code\": false,\n                    \"color\": \"default\"\n                },\n                \"plain_text\": \"make the title full bold\",\n                \"href\": null\n            }\n        ],\n        \"icon\": null,\n        \"color\": \"default\"\n    },\n    \"archived\": true,\n    \"developer_survey\": \"https://notionup.typeform.com/to/bllBsoI4?utm_source=postman\",\n    \"request_id\": \"6e691175-31ac-47f3-92bf-860f415b5b54\"\n}",
                        "createdAt": "2026-04-14T06:36:10.000Z",
                        "updatedAt": "2026-04-14T06:36:10.000Z",
                        "uid": "53663724-aef43eb3-5d52-4ab6-818a-1ac7fed26595"
                    }
                ],
                "createdAt": "2026-04-14T06:36:04.000Z",
                "updatedAt": "2026-04-14T06:36:10.000Z",
                "uid": "53663724-834d41f3-5881-4cfe-b784-d16fa60da804"
            }
        ]
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `object`  | string   | Type of object returned (e.g., page, block, list) |
| `id`      | string   | Unique identifier of the resource |
| `created_time` | string | Timestamp when the resource was created (ISO 8601) |
| `last_edited_time`   | string | Timestamp of the last update (ISO 8601) |
| `created_by` | object | Details of the user who created the resource |
| `object`  | string   | Type of user object |
| `id`      | string   | Unique identifier of the user |
| `last_edited_by` | object | Details of the user who last edited the resource |
| `object`  | string   | Type of user object |
| `id`      | string   | Unique identifier of the user |
| `parent`  | object   | Parent reference of the resource |
| `type`    | string   | Type of parent reference |
| `page_id` | string   | Identifier of the parent page (if applicable) |
| `workspace` | boolean | Indicates if the parent is a workspace |
| `has_children` | boolean | Indicates whether the block has child elements |
| `in_trash` | boolean | Indicates whether the resource is in trash |
| `archived` | boolean | Indicates whether the resource is archived |
| `type`    | string   | Type of block (e.g., paragraph, child_page) |
| `paragraph` | object | Paragraph block content |
| `rich_text` | array | List of rich text objects |
| `rich_text[]` | object | Individual rich text object |
| `type`    | string   | Type of rich text content |
| `text`    | object   | Text content details |
| `content` | string   | Actual text content |
| `link`    | null/object | Link associated with the text |
| `annotations` | object | Text styling information |
| `bold`    | boolean  | Indicates bold formatting |
| `italic`  | boolean  | Indicates italic formatting |
| `strikethrough` | boolean | Indicates strikethrough formatting |
| `underline` | boolean | Indicates underline formatting |
| `code`    | boolean  | Indicates code formatting |
| `color`   | string   | Text color |
| `plain_text` | string | Plain text version of content |
| `href`    | null/string | URL reference if available |
| `child_page` | object | Child page details |
| `title`   | string   | Title of the child page |
| `results` | array    | List of block objects (for list responses) |
| `results[]` | object | Individual block object |
| `next_cursor` | null/string | Cursor for pagination |
| `has_more` | boolean | Indicates if more results are available |
| `url`     | string   | URL of the page |
| `public_url` | null/string | Public shareable URL |
| `developer_survey` | string | Developer feedback URL |
| `request_id` | string | Unique request identifier |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Fetched specific collection successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 7. Create a collection

Creates a new collection. 

#### Endpoint:

`POST /collections`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |
| Content-Type | `application/json` |

#### Request:

```json

{
    "collection": {
        "info": {
            "name": "Postman Portfolio",
            "description": "This is a test.",
            "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
        },
        "variable": [
            {
                "key": "userId",
                "value": 12345678,
                "disabled": true,
                "description": "The user's ID."
            }
        ],
        "auth": {
            "type": "apikey",
            "apikey": [
                {
                    "key": "value",
                    "value": "{{apiKey}}"
                },
                {
                    "key": "key",
                    "value": "api-key"
                },
                {
                    "key": "in",
                    "value": "header"
                }
            ]
        },
        "item": [
            {
                "name": "Users",
                "item": [
                    {
                        "name": "Update User",
                        "item": [
                            {
                                "name": "Update user",
                                "protocolProfileBehavior": {
                                    "disableBodyPruning": true
                                },
                                "request": {
                                    "method": "PATCH",
                                    "header": [],
                                    "body": {
                                        "mode": "raw",
                                        "raw": "{\n    \"name\": \"{{name}}\",\n    \"email\": \"{{emailAddress}}\",\n    \"roles\": [\n        \"{{role}}\"\n    ]\n}",
                                        "options": {
                                            "raw": {
                                                "language": "json"
                                            }
                                        }
                                    },
                                    "url": {
                                        "raw": "https://postman-echo.com/users/:userId",
                                        "protocol": "https",
                                        "host": [
                                            "postman-echo",
                                            "com"
                                        ],
                                        "path": [
                                            "users",
                                            ":userId"
                                        ],
                                        "variable": [
                                            {
                                                "key": "userId",
                                                "value": "{{userId}}",
                                                "description": "The user's ID."
                                            }
                                        ]
                                    },
                                    "description": "This is an example GET request."
                                },
                                "response": [
                                    {
                                        "name": "Successful Response",
                                        "originalRequest": {
                                            "method": "GET",
                                            "header": [
                                                {
                                                    "key": "Content-Type",
                                                    "value": "application/json",
                                                    "type": "text"
                                                }
                                            ],
                                            "body": {
                                                "mode": "raw",
                                                "raw": "{\n    \"name\": \"Taylor Lee\",\n    \"email\": \"taylor.lee@example.com\",\n    \"roles\": [\n        \"user\",\n        \"admin\"\n    ]\n}",
                                                "options": {
                                                    "raw": {
                                                        "language": "json"
                                                    }
                                                }
                                            },
                                            "url": {
                                                "raw": "https://postman-echo.com/users/:userId",
                                                "protocol": "https",
                                                "host": [
                                                    "postman-echo",
                                                    "com"
                                                ],
                                                "path": [
                                                    "users",
                                                    ":userId"
                                                ],
                                                "variable": [
                                                    {
                                                        "key": "userId",
                                                        "value": "12345678"
                                                    }
                                                ]
                                            }
                                        },
                                        "status": "OK",
                                        "code": 200,
                                        "_postman_previewlanguage": "json",
                                        "header": [
                                            {
                                                "key": "Content-Type",
                                                "value": "application/json",
                                                "description": "",
                                                "type": "text",
                                                "enabled": true
                                            }
                                        ],
                                        "cookie": [],
                                        "responseTime": null,
                                        "body": "{\n    \"id\": \"12345678\",\n    \"name\": \"Taylor Lee\",\n    \"username\": \"taylor-lee\",\n    \"email\": \"taylor.lee@example.com\",\n    \"roles\": [\n        \"user\",\n        \"admin\"\n    ]\n}"
                                    }
                                ]
                            }
                        ],
                        "event": [
                            {
                                "listen": "prerequest",
                                "script": {
                                    "type": "text/javascript",
                                    "exec": [
                                        "pm.sendRequest(\"https://postman-echo.com/get\", function (err, response) {",
                                        "    console.log(response.json());",
                                        "});"
                                    ]
                                }
                            },
                            {
                                "listen": "test",
                                "script": {
                                    "type": "text/javascript",
                                    "exec": [
                                        "pm.test(\"Status code is 200\", function () {",
                                        "    pm.response.to.have.status(200);",
                                        "});"
                                    ]
                                }
                            }
                        ]
                    },
                    {
                        "name": "Get user",
                        "event": [
                            {
                                "listen": "prerequest",
                                "script": {
                                    "exec": [
                                        "pm.sendRequest(\"https://postman-echo.com/get\", function (err, response) {",
                                        "    console.log(response.json());",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            },
                            {
                                "listen": "test",
                                "script": {
                                    "exec": [
                                        "pm.test(\"Status code is 200\", function () {",
                                        "    pm.response.to.have.status(200);",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            }
                        ],
                        "protocolProfileBehavior": {
                            "disableBodyPruning": true
                        },
                        "request": {
                            "method": "GET",
                            "header": [],
                            "url": {
                                "raw": "https://postman-echo.com/users?id={{userId}}",
                                "protocol": "https",
                                "host": [
                                    "postman-echo",
                                    "com"
                                ],
                                "path": [
                                    "users"
                                ],
                                "query": [
                                    {
                                        "key": "id",
                                        "value": "{{userId}}",
                                        "description": "The user's ID."
                                    }
                                ]
                            },
                            "description": "This is an example GET request."
                        },
                        "response": [
                            {
                                "name": "Successful Response",
                                "originalRequest": {
                                    "method": "GET",
                                    "header": [
                                        {
                                            "key": "Content-Type",
                                            "value": "application/json",
                                            "type": "text"
                                        }
                                    ],
                                    "url": {
                                        "raw": "https://postman-echo.com/get?id=12345678",
                                        "protocol": "https",
                                        "host": [
                                            "postman-echo",
                                            "com"
                                        ],
                                        "path": [
                                            "get"
                                        ],
                                        "query": [
                                            {
                                                "key": "id",
                                                "value": "12345678"
                                            }
                                        ]
                                    }
                                },
                                "status": "OK",
                                "code": 200,
                                "_postman_previewlanguage": "json",
                                "header": [
                                    {
                                        "key": "Content-Type",
                                        "value": "application/json",
                                        "description": "",
                                        "type": "text",
                                        "enabled": true
                                    }
                                ],
                                "cookie": [],
                                "responseTime": null,
                                "body": "{\n    \"id\": \"12345678\",\n    \"name\": \"Taylor Lee\",\n    \"username\": \"taylor-lee\",\n    \"email\": \"taylor.lee@example.com\",\n    \"roles\": [\n        \"user\",\n        \"admin\"\n    ],\n    \"joinedAt\": \"2022-11-23T14:38:25.000Z\"\n}"
                            }
                        ]
                    },
                    {
                        "name": "Get all users",
                        "event": [
                            {
                                "listen": "test",
                                "script": {
                                    "exec": [
                                        "pm.test(\"Status code is 200\", function () {",
                                        "    pm.response.to.have.status(200);",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            },
                            {
                                "listen": "prerequest",
                                "script": {
                                    "exec": [
                                        "pm.sendRequest(\"https://postman-echo.com/get\", function (err, response) {",
                                        "    console.log(response.json());",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            }
                        ],
                        "protocolProfileBehavior": {
                            "disableBodyPruning": true
                        },
                        "request": {
                            "method": "GET",
                            "header": [],
                            "body": {
                                "mode": "raw",
                                "raw": "",
                                "options": {
                                    "raw": {
                                        "language": "json"
                                    }
                                }
                            },
                            "url": {
                                "raw": "https://postman-echo.com/users",
                                "protocol": "https",
                                "host": [
                                    "postman-echo",
                                    "com"
                                ],
                                "path": [
                                    "users"
                                ],
                                "query": [
                                    {
                                        "key": "groupId",
                                        "value": "{{groupId}}",
                                        "description": "The user group's ID.",
                                        "disabled": true
                                    }
                                ]
                            },
                            "description": "This is a test API."
                        },
                        "response": [
                            {
                                "name": "Successful Response",
                                "originalRequest": {
                                    "method": "POST",
                                    "header": [
                                        {
                                            "key": "Host",
                                            "value": "postman-echo.com"
                                        },
                                        {
                                            "key": "user-agent",
                                            "value": "curl/7.88.1"
                                        },
                                        {
                                            "key": "accept",
                                            "value": "*/*"
                                        },
                                        {
                                            "key": "content-type",
                                            "value": "application/json"
                                        },
                                        {
                                            "key": "content-length",
                                            "value": "22"
                                        }
                                    ],
                                    "body": {
                                        "mode": "raw",
                                        "raw": "{\n  \"field\": \"Value\"\n}",
                                        "options": {
                                            "raw": {
                                                "language": "json"
                                            }
                                        }
                                    },
                                    "url": {
                                        "raw": "https://postman-echo.com/post",
                                        "protocol": "https",
                                        "host": [
                                            "postman-echo",
                                            "com"
                                        ],
                                        "path": [
                                            "post"
                                        ]
                                    }
                                },
                                "status": "OK",
                                "code": 200,
                                "_postman_previewlanguage": "json",
                                "header": [
                                    {
                                        "key": "date",
                                        "value": "Thu, 07 Sep 2023 12:41:59 GMT",
                                        "enabled": true
                                    },
                                    {
                                        "key": "content-type",
                                        "value": "application/json; charset=utf-8",
                                        "enabled": true
                                    },
                                    {
                                        "key": "content-length",
                                        "value": "468",
                                        "enabled": true
                                    },
                                    {
                                        "key": "etag",
                                        "value": "W/\"1d4-JuAIw8ssoFCtGzk/UwITxaiSbrc\"",
                                        "enabled": true
                                    },
                                    {
                                        "key": "set-cookie",
                                        "value": "sails.sid=s%3A6p_NXpI3OZeGE35bI6i5Uq3XgHHxcsdJ.dQVpBE%2BJ9wHWainkqe6F6dkdv7UKoshSZY7sdZ5sbzo; Path=/ HttpOnly",
                                        "enabled": true
                                    }
                                ],
                                "cookie": [],
                                "responseTime": null,
                                "body": "{\n    \"data\": [\n        {\n            \"id\": \"12345678\",\n            \"name\": \"Taylor Lee\",\n            \"username\": \"taylor-lee\",\n            \"email\": \"taylor.lee@example.com\",\n            \"roles\": [\n                \"admin\",\n                \"user\"\n            ],\n            \"joinedAt\": \"2022-11-23T14:38:25.000Z\"\n        },\n        {\n            \"id\": \"87654321\",\n            \"name\": \"Alex Cruz\",\n            \"username\": \"alex-cruz\",\n            \"email\": \"alex.cruz@example.com\",\n            \"roles\": [\n                \"user\"\n            ],\n            \"joinedAt\": \"2022-11-24T10:18:11.000Z\"\n        }\n    ]\n}"
                            },
                            {
                                "name": "No Group Found",
                                "originalRequest": {
                                    "method": "GET",
                                    "header": [
                                        {
                                            "key": "Accept",
                                            "value": "application/vnd.example.v1+json",
                                            "type": "text"
                                        }
                                    ],
                                    "body": {
                                        "mode": "raw",
                                        "raw": "",
                                        "options": {
                                            "raw": {
                                                "language": "json"
                                            }
                                        }
                                    },
                                    "url": {
                                        "raw": "http://api.getpostman.com/v1/request?groupId=123",
                                        "protocol": "http",
                                        "host": [
                                            "api",
                                            "getpostman",
                                            "com"
                                        ],
                                        "path": [
                                            "v1",
                                            "request"
                                        ],
                                        "query": [
                                            {
                                                "key": "groupId",
                                                "value": "123"
                                            }
                                        ]
                                    }
                                },
                                "status": "OK",
                                "code": 200,
                                "_postman_previewlanguage": "json",
                                "header": [
                                    {
                                        "key": "Content-Type",
                                        "value": "application/json",
                                        "description": "",
                                        "type": "text",
                                        "enabled": true
                                    }
                                ],
                                "cookie": [],
                                "responseTime": null,
                                "body": "{\n    \"data\": []\n}"
                            }
                        ]
                    }
                ],
                "description": "This is a test folder.",
                "event": [
                    {
                        "listen": "prerequest",
                        "script": {
                            "type": "text/javascript",
                            "exec": [
                                "pm.variables.get(\"variable_key\");"
                            ]
                        }
                    },
                    {
                        "listen": "test",
                        "script": {
                            "type": "text/javascript",
                            "exec": [
                                "pm.test(\"Status code is 200\", function () {",
                                "    pm.response.to.have.status(200);",
                                "});"
                            ]
                        }
                    }
                ]
            }
        ]
    }
}

```

#### Request Field

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `data`    | array    | List of user objects |
| `data[]`  | object   | Individual user object |
| `id`      | string   | Unique identifier of the user |
| `name`    | string   | Full name of the user |
| `username` | string  | Username of the user |
| `email`   | string   | Email address of the user |
| `roles`   | array    | List of roles assigned to the user |
| `roles[]` | string   | Individual role assigned to the user |
| `joinedAt` | string  | Timestamp when the user joined the system (ISO 8601) |

#### Response:

```json

{
    "collection": {
        "id": "e7ecb82e-f372-4353-805d-a0db8166176b",
        "name": "postman api doc",
        "uid": "53663724-e7ecb82e-f372-4353-805d-a0db8166176b"
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `collection` | object | Collection details |
| `id`      | string   | Unique identifier of the collection |
| `name`    | string   | Name of the collection |
| `uid`     | string   | Unique user-specific identifier of the collection |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | New collection created successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 8. Update a collection

Updates a specific collection.

#### Endpoint:

`PUT /collections/{collectionId}`

#### Path Parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `collectionId` | string |	Yes	| Unique ID of the collection |

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |
| Content-Type | `application/json` |

#### Request:

```json

{
    "collection": {
        "info": {
            "name": "Postman Portfolio",
            "description": "This is a test.",
            "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
        },
        "variable": [
            {
                "key": "userId",
                "value": 12345678,
                "disabled": true,
                "description": "The user's ID."
            }
        ],
        "auth": {
            "type": "apikey",
            "apikey": [
                {
                    "key": "value",
                    "value": "{{apiKey}}"
                },
                {
                    "key": "key",
                    "value": "api-key"
                },
                {
                    "key": "in",
                    "value": "header"
                }
            ]
        },
        "item": [
            {
                "name": "Users",
                "item": [
                    {
                        "name": "Update User",
                        "item": [
                            {
                                "name": "Update user",
                                "protocolProfileBehavior": {
                                    "disableBodyPruning": true
                                },
                                "request": {
                                    "method": "PATCH",
                                    "header": [],
                                    "body": {
                                        "mode": "raw",
                                        "raw": "{\n    \"name\": \"{{name}}\",\n    \"email\": \"{{emailAddress}}\",\n    \"roles\": [\n        \"{{role}}\"\n    ]\n}",
                                        "options": {
                                            "raw": {
                                                "language": "json"
                                            }
                                        }
                                    },
                                    "url": {
                                        "raw": "https://postman-echo.com/users/:userId",
                                        "protocol": "https",
                                        "host": [
                                            "postman-echo",
                                            "com"
                                        ],
                                        "path": [
                                            "users",
                                            ":userId"
                                        ],
                                        "variable": [
                                            {
                                                "key": "userId",
                                                "value": "{{userId}}",
                                                "description": "The user's ID."
                                            }
                                        ]
                                    },
                                    "description": "This is an example GET request."
                                },
                                "response": [
                                    {
                                        "name": "Successful Response",
                                        "originalRequest": {
                                            "method": "GET",
                                            "header": [
                                                {
                                                    "key": "Content-Type",
                                                    "value": "application/json",
                                                    "type": "text"
                                                }
                                            ],
                                            "body": {
                                                "mode": "raw",
                                                "raw": "{\n    \"name\": \"Taylor Lee\",\n    \"email\": \"taylor.lee@example.com\",\n    \"roles\": [\n        \"user\",\n        \"admin\"\n    ]\n}",
                                                "options": {
                                                    "raw": {
                                                        "language": "json"
                                                    }
                                                }
                                            },
                                            "url": {
                                                "raw": "https://postman-echo.com/users/:userId",
                                                "protocol": "https",
                                                "host": [
                                                    "postman-echo",
                                                    "com"
                                                ],
                                                "path": [
                                                    "users",
                                                    ":userId"
                                                ],
                                                "variable": [
                                                    {
                                                        "key": "userId",
                                                        "value": "12345678"
                                                    }
                                                ]
                                            }
                                        },
                                        "status": "OK",
                                        "code": 200,
                                        "_postman_previewlanguage": "json",
                                        "header": [
                                            {
                                                "key": "Content-Type",
                                                "value": "application/json",
                                                "description": "",
                                                "type": "text",
                                                "enabled": true
                                            }
                                        ],
                                        "cookie": [],
                                        "responseTime": null,
                                        "body": "{\n    \"id\": \"12345678\",\n    \"name\": \"Taylor Lee\",\n    \"username\": \"taylor-lee\",\n    \"email\": \"taylor.lee@example.com\",\n    \"roles\": [\n        \"user\",\n        \"admin\"\n    ]\n}"
                                    }
                                ]
                            }
                        ],
                        "event": [
                            {
                                "listen": "prerequest",
                                "script": {
                                    "type": "text/javascript",
                                    "exec": [
                                        "pm.sendRequest(\"https://postman-echo.com/get\", function (err, response) {",
                                        "    console.log(response.json());",
                                        "});"
                                    ]
                                }
                            },
                            {
                                "listen": "test",
                                "script": {
                                    "type": "text/javascript",
                                    "exec": [
                                        "pm.test(\"Status code is 200\", function () {",
                                        "    pm.response.to.have.status(200);",
                                        "});"
                                    ]
                                }
                            }
                        ]
                    },
                    {
                        "name": "Get user",
                        "event": [
                            {
                                "listen": "prerequest",
                                "script": {
                                    "exec": [
                                        "pm.sendRequest(\"https://postman-echo.com/get\", function (err, response) {",
                                        "    console.log(response.json());",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            },
                            {
                                "listen": "test",
                                "script": {
                                    "exec": [
                                        "pm.test(\"Status code is 200\", function () {",
                                        "    pm.response.to.have.status(200);",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            }
                        ],
                        "protocolProfileBehavior": {
                            "disableBodyPruning": true
                        },
                        "request": {
                            "method": "GET",
                            "header": [],
                            "url": {
                                "raw": "https://postman-echo.com/users?id={{userId}}",
                                "protocol": "https",
                                "host": [
                                    "postman-echo",
                                    "com"
                                ],
                                "path": [
                                    "users"
                                ],
                                "query": [
                                    {
                                        "key": "id",
                                        "value": "{{userId}}",
                                        "description": "The user's ID."
                                    }
                                ]
                            },
                            "description": "This is an example GET request."
                        },
                        "response": [
                            {
                                "name": "Successful Response",
                                "originalRequest": {
                                    "method": "GET",
                                    "header": [
                                        {
                                            "key": "Content-Type",
                                            "value": "application/json",
                                            "type": "text"
                                        }
                                    ],
                                    "url": {
                                        "raw": "https://postman-echo.com/get?id=12345678",
                                        "protocol": "https",
                                        "host": [
                                            "postman-echo",
                                            "com"
                                        ],
                                        "path": [
                                            "get"
                                        ],
                                        "query": [
                                            {
                                                "key": "id",
                                                "value": "12345678"
                                            }
                                        ]
                                    }
                                },
                                "status": "OK",
                                "code": 200,
                                "_postman_previewlanguage": "json",
                                "header": [
                                    {
                                        "key": "Content-Type",
                                        "value": "application/json",
                                        "description": "",
                                        "type": "text",
                                        "enabled": true
                                    }
                                ],
                                "cookie": [],
                                "responseTime": null,
                                "body": "{\n    \"id\": \"12345678\",\n    \"name\": \"Taylor Lee\",\n    \"username\": \"taylor-lee\",\n    \"email\": \"taylor.lee@example.com\",\n    \"roles\": [\n        \"user\",\n        \"admin\"\n    ],\n    \"joinedAt\": \"2022-11-23T14:38:25.000Z\"\n}"
                            }
                        ]
                    },
                    {
                        "name": "Get all users",
                        "event": [
                            {
                                "listen": "test",
                                "script": {
                                    "exec": [
                                        "pm.test(\"Status code is 200\", function () {",
                                        "    pm.response.to.have.status(200);",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            },
                            {
                                "listen": "prerequest",
                                "script": {
                                    "exec": [
                                        "pm.sendRequest(\"https://postman-echo.com/get\", function (err, response) {",
                                        "    console.log(response.json());",
                                        "});"
                                    ],
                                    "type": "text/javascript",
                                    "packages": {}
                                }
                            }
                        ],
                        "protocolProfileBehavior": {
                            "disableBodyPruning": true
                        },
                        "request": {
                            "method": "GET",
                            "header": [],
                            "body": {
                                "mode": "raw",
                                "raw": "",
                                "options": {
                                    "raw": {
                                        "language": "json"
                                    }
                                }
                            },
                            "url": {
                                "raw": "https://postman-echo.com/users",
                                "protocol": "https",
                                "host": [
                                    "postman-echo",
                                    "com"
                                ],
                                "path": [
                                    "users"
                                ],
                                "query": [
                                    {
                                        "key": "groupId",
                                        "value": "{{groupId}}",
                                        "description": "The user group's ID.",
                                        "disabled": true
                                    }
                                ]
                            },
                            "description": "This is a test API."
                        },
                        "response": [
                            {
                                "name": "Successful Response",
                                "originalRequest": {
                                    "method": "POST",
                                    "header": [
                                        {
                                            "key": "Host",
                                            "value": "postman-echo.com"
                                        },
                                        {
                                            "key": "user-agent",
                                            "value": "curl/7.88.1"
                                        },
                                        {
                                            "key": "accept",
                                            "value": "*/*"
                                        },
                                        {
                                            "key": "content-type",
                                            "value": "application/json"
                                        },
                                        {
                                            "key": "content-length",
                                            "value": "22"
                                        }
                                    ],
                                    "body": {
                                        "mode": "raw",
                                        "raw": "{\n  \"field\": \"Value\"\n}",
                                        "options": {
                                            "raw": {
                                                "language": "json"
                                            }
                                        }
                                    },
                                    "url": {
                                        "raw": "https://postman-echo.com/post",
                                        "protocol": "https",
                                        "host": [
                                            "postman-echo",
                                            "com"
                                        ],
                                        "path": [
                                            "post"
                                        ]
                                    }
                                },
                                "status": "OK",
                                "code": 200,
                                "_postman_previewlanguage": "json",
                                "header": [
                                    {
                                        "key": "date",
                                        "value": "Thu, 07 Sep 2023 12:41:59 GMT",
                                        "enabled": true
                                    },
                                    {
                                        "key": "content-type",
                                        "value": "application/json; charset=utf-8",
                                        "enabled": true
                                    },
                                    {
                                        "key": "content-length",
                                        "value": "468",
                                        "enabled": true
                                    },
                                    {
                                        "key": "etag",
                                        "value": "W/\"1d4-JuAIw8ssoFCtGzk/UwITxaiSbrc\"",
                                        "enabled": true
                                    },
                                    {
                                        "key": "set-cookie",
                                        "value": "sails.sid=s%3A6p_NXpI3OZeGE35bI6i5Uq3XgHHxcsdJ.dQVpBE%2BJ9wHWainkqe6F6dkdv7UKoshSZY7sdZ5sbzo; Path=/ HttpOnly",
                                        "enabled": true
                                    }
                                ],
                                "cookie": [],
                                "responseTime": null,
                                "body": "{\n    \"data\": [\n        {\n            \"id\": \"12345678\",\n            \"name\": \"Taylor Lee\",\n            \"username\": \"taylor-lee\",\n            \"email\": \"taylor.lee@example.com\",\n            \"roles\": [\n                \"admin\",\n                \"user\"\n            ],\n            \"joinedAt\": \"2022-11-23T14:38:25.000Z\"\n        },\n        {\n            \"id\": \"87654321\",\n            \"name\": \"Alex Cruz\",\n            \"username\": \"alex-cruz\",\n            \"email\": \"alex.cruz@example.com\",\n            \"roles\": [\n                \"user\"\n            ],\n            \"joinedAt\": \"2022-11-24T10:18:11.000Z\"\n        }\n    ]\n}"
                            },
                            {
                                "name": "No Group Found",
                                "originalRequest": {
                                    "method": "GET",
                                    "header": [
                                        {
                                            "key": "Accept",
                                            "value": "application/vnd.example.v1+json",
                                            "type": "text"
                                        }
                                    ],
                                    "body": {
                                        "mode": "raw",
                                        "raw": "",
                                        "options": {
                                            "raw": {
                                                "language": "json"
                                            }
                                        }
                                    },
                                    "url": {
                                        "raw": "http://api.getpostman.com/v1/request?groupId=123",
                                        "protocol": "http",
                                        "host": [
                                            "api",
                                            "getpostman",
                                            "com"
                                        ],
                                        "path": [
                                            "v1",
                                            "request"
                                        ],
                                        "query": [
                                            {
                                                "key": "groupId",
                                                "value": "123"
                                            }
                                        ]
                                    }
                                },
                                "status": "OK",
                                "code": 200,
                                "_postman_previewlanguage": "json",
                                "header": [
                                    {
                                        "key": "Content-Type",
                                        "value": "application/json",
                                        "description": "",
                                        "type": "text",
                                        "enabled": true
                                    }
                                ],
                                "cookie": [],
                                "responseTime": null,
                                "body": "{\n    \"data\": []\n}"
                            }
                        ]
                    }
                ],
                "description": "This is a test folder.",
                "event": [
                    {
                        "listen": "prerequest",
                        "script": {
                            "type": "text/javascript",
                            "exec": [
                                "pm.variables.get(\"variable_key\");"
                            ]
                        }
                    },
                    {
                        "listen": "test",
                        "script": {
                            "type": "text/javascript",
                            "exec": [
                                "pm.test(\"Status code is 200\", function () {",
                                "    pm.response.to.have.status(200);",
                                "});"
                            ]
                        }
                    }
                ]
            }
        ]
    }
}

```

#### Request Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `user` | object | Yes   | Contains the authenticated user's details |
| `user.id` | integer | Yes | Unique numeric identifier of the 
user |
| `user.sub` | string | Yes | Universally unique identifier (UUID) of the user |
| `user.username` | string | Yes | Postman username of the   account |
| `user.email` | string | Yes | Email address associated with the account |
| `user.fullName` | string | Yes | Full name of the account   holder |
| `user.avatar` | string | No | URL of the user's profile avatar image |
| `user.isPublic` | boolean | Yes | Whether the user profile is publicly visible |
| `user.emailVerified` | boolean | Yes | Whether the email address is verified |
| `user.teamId` | integer | Yes | Unique identifier of the user's team |
| `user.teamName` | string | Yes | Name of the user's team |
| `user.teamDomain` | string | Yes | Unique domain identifier of the team |
| `user.roles` | array | Yes | List of roles assigned to the user |
| `operations` | array | Yes | List of feature usage and limits for the account |
| `operations[].name` | string | Yes | Name of the operation or feature |
| `operations[].limit` | number | Yes | Maximum allowed usage for the operation |
| `operations[].usage` | number | Yes | Current usage count for the operation |
| `operations[].overage` | number | Yes | Usage exceeding the allowed limit |

#### Response:

```json

{
    "collection": {
        "id": "e7ecb82e-f372-4353-805d-a0db8166176b",
        "name": "postman api doc",
        "uid": "53663724-e7ecb82e-f372-4353-805d-a0db8166176b"
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `collection` | object | Collection details |
| `id`      | string   | Unique identifier of the collection |
| `name`    | string   | Name of the collection |
| `uid`     | string   | Unique user-specific identifier of the collection |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Specific collection fetched successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 9. Delete a Collection

Deletes a specific collection.

#### Endpoint:

`DELETE /collections/{collectionId}`

#### Path Parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `collectionId` | string |	Yes	| Unique ID of the collection |

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "collection": {
        "id": "15e3671f-9f6f-485c-89d6-9a32536f4d22",
        "uid": "53663724-15e3671f-9f6f-485c-89d6-9a32536f4d22"
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `collection` | object | Collection details |
| `id`      | string   | Unique identifier of the collection |
| `uid`     | string   | Unique user-specific identifier of the collection |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Particular collection deleted successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 10. List all Environment

Returns back all the environments linked to your API key.

#### Endpoint:

`GET /environments`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "environments": [
        {
            "id": "59befd1f-06e9-4f2c-af91-9d811bfcf4b0",
            "name": "{{postman api testing}}",
            "createdAt": "2026-05-02T06:28:12.000Z",
            "updatedAt": "2026-05-02T06:28:13.000Z",
            "owner": "53663724",
            "uid": "53663724-59befd1f-06e9-4f2c-af91-9d811bfcf4b0",
            "isPublic": false
        },
        {
            "id": "8a6593fa-dae2-4f71-b166-68db0eb7dfdc",
            "name": "{{postman api testing}}",
            "createdAt": "2026-05-05T14:13:17.000Z",
            "updatedAt": "2026-05-05T14:13:17.000Z",
            "owner": "53663724",
            "uid": "53663724-8a6593fa-dae2-4f71-b166-68db0eb7dfdc",
            "isPublic": false
        },
        {
            "id": "9396fef2-ffc4-4f94-9ae1-04a1cf77bc18",
            "name": "GOKUL",
            "createdAt": "2026-05-02T06:48:01.000Z",
            "updatedAt": "2026-05-05T14:14:23.000Z",
            "owner": "53663724",
            "uid": "53663724-9396fef2-ffc4-4f94-9ae1-04a1cf77bc18",
            "isPublic": false
        }
    ]
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `environments` | array | List of environment objects |
| `environments[]` | object | Individual environment object |
| `id`      | string   | Unique identifier of the environment |
| `name`    | string   | Name of the environment |
| `createdAt` | string | Timestamp when the environment was created (ISO 8601) |
| `updatedAt` | string | Timestamp of the last update (ISO 8601) |
| `owner`   | string   | Identifier of the environment owner |
| `uid`     | string   | Unique user-specific identifier of the environment |
| `isPublic` | boolean | Indicates whether the environment is public |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | All environments collected successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 11. Fetch a Specific Environment

Returns details of a specific environment.

#### Endpoint:

`GET /environments/{environmentId}`

#### Path Parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `environmentId` | string |	Yes	| Unique ID of the environment|

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "environment": {
        "id": "9396fef2-ffc4-4f94-9ae1-04a1cf77bc18",
        "name": "GOKUL",
        "owner": "53663724",
        "createdAt": "2026-05-02T06:48:01.000Z",
        "updatedAt": "2026-05-05T14:14:23.000Z",
        "values": [
            {
                "key": "collectionId",
                "value": "12345678-12ece9e1-2abf-4edc-8e34-de66e74114d2",
                "type": "default",
                "enabled": true,
                "description": "The collection's ID."
            }
        ],
        "uid": "53663724-9396fef2-ffc4-4f94-9ae1-04a1cf77bc18",
        "isPublic": false
    }
}

```

#### Response Fields

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `environment` | object | Environment details |
| `id`      | string   | Unique identifier of the environment |
| `name`    | string   | Name of the environment |
| `owner`   | string   | Identifier of the environment owner |
| `createdAt` | string | Timestamp when the environment was created (ISO 8601)  |
| `updatedAt` | string | Timestamp of the last update (ISO 8601) |
| `values`  | array    | List of environment variables |
| `values[]` | object  | Individual environment variable |
| `key`     | string   | Name of the variable |
| `value`   | string   | Value assigned to the variable |
| `type`    | string   | Type of the variable |
| `enabled` | boolean  | Indicates whether the variable is 
enabled |
| `description` | string | Description of the variable |
| `uid`     | string   | Unique user-specific identifier of the environment |
| `isPublic` | boolean | Indicates whether the environment is public |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Specific environment fetched successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 12. Create Environments

CreateS a new environment on the workspace.

#### Endpoint:

`POST /environments`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |
| Content-Type | `application/json` |

#### Request:

```json

{
    "environment": {
        "name": "{{postman api testing}}",
        "values": [
            {
                "key": "{{environmentVariableName}}",
                "value": "{{environmentVariableValue}}",
                "enabled": true,
                "type": "{{environmentVariableType}}",
                "description": "{{environmentVariableDescription}}"
            }
        ]
    }
}

```

#### Request Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `environment` | object | Environment details |
| `name`    | string   | Name of the environment |
| `values`  | array    | List of environment variables |
| `values[]` | object  | Individual environment variable |
| `key`     | string   | Name of the variable |
| `value`   | string   | Value assigned to the variable |
| `enabled` | boolean  | Indicates whether the variable is 
enabled |
| `type`    | string   | Type of the variable |
| `description` | string | Description of the variable |

#### Response:

```json

{
    "environment": {
        "id": "8a6593fa-dae2-4f71-b166-68db0eb7dfdc",
        "name": "{{postman api testing}}",
        "uid": "53663724-8a6593fa-dae2-4f71-b166-68db0eb7dfdc"
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `environment` | object | Contains the details of the created environment |
| `id`      | string   | Unique identifier of the created environment |
| `name`    | string   | Name of the created environment |
| `uid`     | string   | Unique identifier combining user ID and environment ID |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | New environment created successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

### 13. Update an environment

Updates an environment.

#### Endpoint:

`PUT /environments/{environmentId}`

#### Path Parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `environmentId` | string |	Yes	| Unique ID of the environment|

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |
| Content-Type | `application/json` |

#### Request: 

```json

{
    "environment": {
        "name": "GOKUL",
        "values": [
            {
                "key": "collectionId",
                "value": "12345678-12ece9e1-2abf-4edc-8e34-de66e74114d2",
                "type": "default",
                "enabled": true,
                "description": "The collection's ID."
            }
        ]
    }
}

```

#### Request Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `environment` | object | Environment details |
| `name`    | string   | Name of the environment |
| `values`  | array    | List of environment variables |
| `values[]` | object  | Individual environment variable |
| `key`     | string   | Name of the variable |
| `value`   | string   | Value assigned to the variable |
| `type`    | string   | Type of the variable |
| `enabled` | boolean  | Indicates whether the variable is 
enabled |
| `description` | string | Description of the variable |

#### Response:

```json

{
    "environment": {
        "id": "9396fef2-ffc4-4f94-9ae1-04a1cf77bc18",
        "name": "GOKUL",
        "uid": "53663724-9396fef2-ffc4-4f94-9ae1-04a1cf77bc18"
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `environment` | object | Environment details |
| `id`      | string   | Unique identifier of the environment |
| `name`    | string   | Name of the environment |
| `uid`     | string   | Unique user-specific identifier of the environment |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Environment updated successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 14. Get all Monitors

Returns details of all monitors 

#### Endpoint:

`GET /monitors`

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "monitors": [
        {
            "id": "1f148ace-d8b4-4c20-aa19-11b9135fd5a7",
            "name": "NOTION",
            "active": true,
            "uid": "53663724-1f148ace-d8b4-4c20-aa19-11b9135fd5a7",
            "owner": 53663724,
            "collectionUid": "53663724-c18dd000-f7ce-482a-847e-7e26a19fb71b",
            "environmentUid": ""
        },
        {
            "id": "1f148ace-8719-4a50-a883-cde6f9e0b019",
            "name": "NOTION",
            "active": true,
            "uid": "53663724-1f148ace-8719-4a50-a883-cde6f9e0b019",
            "owner": 53663724,
            "collectionUid": "53663724-c18dd000-f7ce-482a-847e-7e26a19fb71b",
            "environmentUid": ""
        }
    ],
    "meta": {
        "nextCursor": "",
        "limit": 25
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `monitors` | array   | List of monitor objects |
| `monitors[]` | object | Individual monitor object |
| `id`      | string   | Unique identifier of the monitor |
| `name`    | string   | Name of the monitor |
| `active`  | boolean  | Indicates whether the monitor is active |
| `uid`     | string   | Unique user-specific identifier of the monitor |
| `owner`   | integer  | Identifier of the monitor owner |
| `collectionUid` | string | Identifier of the associated collection |
| `environmentUid` | string | Identifier of the associated environment (empty if not set) |
| `meta`    | object   | Pagination metadata |
| `nextCursor` | string | Cursor for retrieving the next page of results |
| `limit`   | integer  | Maximum number of monitors returned per page |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Fetched all monitors successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

### 15. Get Specific Monitor

Returns details of a specific monitor.

#### Endpoint:

`GET /monitors/{monitorId}`

#### Path Parameters:

|**PARAMETER**|**TYPE**|**REQUIRED**|**DESCRIPTION**|
|-------------|--------|------------|---------------|
| `monitorID` | string | Yes | Unique ID of the monitor |

#### Headers:

| **HEADER** | **VALUE** |
|------------|-----------|
| Authorization | `X-Api-Key` `PMAK-XXXX` |

#### Response:

```json

{
    "monitor": {
        "id": "1f148ace-d8b4-4c20-aa19-11b9135fd5a7",
        "name": "NOTION",
        "uid": "53663724-1f148ace-d8b4-4c20-aa19-11b9135fd5a7",
        "owner": 53663724,
        "active": true,
        "notificationLimit": 3,
        "collectionUid": "53663724-c18dd000-f7ce-482a-847e-7e26a19fb71b",
        "options": {
            "strictSSL": true,
            "followRedirects": true,
            "requestTimeout": null,
            "requestDelay": 0
        },
        "notifications": {
            "onError": [
                {
                    "email": "twrgokul02@gmail.com"
                }
            ],
            "onFailure": [
                {
                    "email": "twrgokul02@gmail.com"
                }
            ]
        },
        "distribution": [],
        "schedule": {
            "cron": "0 0 0 * * *",
            "timezone": "Asia/Calcutta",
            "nextRun": "2026-05-05T18:30:00.000Z"
        },
        "lastRun": {
            "status": "success",
            "startedAt": "2026-05-05T18:05:08.379Z",
            "finishedAt": "2026-05-05T18:06:11.185Z",
            "jobId": "1f148acf-366c-4750-9741-357bb2e0f49f",
            "stats": {
                "assertions": {
                    "total": 0,
                    "failed": 0
                },
                "requests": {
                    "total": 7
                },
                "runCount": 1,
                "errorCount": 0,
                "abortedCount": 0,
                "responseLatency": 51500,
                "responseSize": 973
            }
        }
    }
}

```

#### Response Fields:

| **FIELD** | **TYPE** | **DESCRIPTION** |
|-----------|----------|-----------------|
| `monitor` | object   | Monitor details |
| `id`      | string   | Unique identifier of the monitor |
| `name`    | string   | Name of the monitor |
| `uid`     | string   | Unique user-specific identifier of the monitor |
| `owner`   | integer  | Identifier of the monitor owner |
| `active`  | boolean  | Indicates whether the monitor is active |
| `notificationLimit` | integer | Maximum number of notifications allowed |
| `collectionUid` | string | Identifier of the associated collection |
| `options` | object   | Configuration options for the monitor |
| `strictSSL` | boolean | Indicates whether SSL verification is enforced |
| `followRedirects` | boolean | Indicates whether redirects are followed |
| `requestTimeout` | null/integer | Timeout for requests (null if not set) |
| `requestDelay` | integer | Delay between requests in milliseconds |
| `notifications` | object | Notification settings |
| `onError` | array    | Notifications triggered on error |
| `onError[]` | object | Individual error notification |
| `email`   | string   | Email address for notifications |
| `onFailure` | array  | Notifications triggered on failure |
| `onFailure[]` | object | Individual failure notification |
| `distribution` | array | Distribution list for monitor (empty if not set) |
| `schedule` | object  | Scheduling details for the monitor |
| `cron`    | string   | Cron expression defining execution schedule |
| `timezone` | string  | Timezone for the schedule |
| `nextRun` | string   | Timestamp of the next scheduled run (ISO 8601) |
| `lastRun` | object   | Details of the last execution |
| `status`  | string   | Status of the last run |
| `startedAt` | string | Timestamp when the run started (ISO 8601) |
| `finishedAt` | string | Timestamp when the run finished (ISO 8601) |
| `jobId`   | string   | Identifier of the execution job |
| `stats`   | object   | Execution statistics |
| `assertions` | object | Assertion results |
| `total`   | integer  | Total number of assertions |
| `failed`  | integer  | Number of failed assertions |
| `requests` | object  | Request execution details |
| `total`   | integer  | Total number of requests executed |
| `runCount` | integer | Number of times the monitor has run |
| `errorCount` | integer | Number of errors encountered |
| `abortedCount` | integer | Number of aborted executions |
| `responseLatency` | integer | Total response time in milliseconds |
| `responseSize` | integer | Total size of responses in bytes |

#### Status Codes:

| **CODE** | **MEANING** |
|----------|-------------|
| `200`    | Specific monitor fetched successfully |
| `400`    | Bad request — missing or invalid fields |
| `401`    | Unauthorized — invalid or missing token |
| `404`    | Not found - The requested resource does not exist|
| `500`    | Internal server error |

---

## Error Reference

|**CODE**|**ERROR**|**CAUSE**|
|--------|---------|---------|
| `400`  | Bad Request | Malformed JSON or missing required 
fields | 
| `401`  | Unauthorized | API key missing or invalid | 
| `403`  | Forbidden | Valid key but no permission for this resource |
| `404`  | Not Found | Collection/environment ID doesn't exist |
| `409`  | Conflict | Duplicate name or resource already exists |
| `429`  | Too Many Requests | Rate limit of 60 req/min exceeded |
| `500`  | Internal Server Error | Postman server-side issue | 

---

## Code Examples Appendix

### 1. GET /me - Fetch User Info

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/me", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/me"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 2. GET /workspaces — Get all Workspaces

**JavaScript:**

```javascript
const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/workspaces", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/workspaces"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 3. GET /workspaces/{workspaceId} - Fetch a Specific Workspace

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/workspaces/{workspaceId}", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/workspaces/{workspaceId}"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 4. POST /workspaces — Create a Workspace

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const raw = JSON.stringify({
  "workspace": {
    "name": "My Workspace",
    "type": "personal",
    "description": "A new workspace"
  }
});

const requestOptions = {
  method: "POST",
  headers: myHeaders,
  body: raw,
  redirect: "follow"
};

fetch("https://api.getpostman.com/workspaces", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests
import json

url = "https://api.getpostman.com/workspaces"
headers = {
  'Content-Type': 'application/json',
  'X-Api-Key': 'YOUR_API_KEY'
}
payload = json.dumps({
  "workspace": {
    "name": "My Workspace",
    "type": "personal",
    "description": "A new workspace"
  }
})

response = requests.request("POST", url, headers=headers, data=payload)
print(response.text)

```

### 5. GET /collections — Get all Collections

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/collections", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/collections"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 6. GET /collections/{collectionId} — Fetch a Specific Collection

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/collections/{collectionId}", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/collections/{collectionId}"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 7. POST /collections — Create a collection

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const raw = JSON.stringify({
  "collection": {
    "info": {
      "name": "My Collection",
      "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
    },
    "item": []
  }
});

const requestOptions = {
  method: "POST",
  headers: myHeaders,
  body: raw,
  redirect: "follow"
};

fetch("https://api.getpostman.com/collections", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests
import json

url = "https://api.getpostman.com/collections"
headers = {
  'Content-Type': 'application/json',
  'X-Api-Key': 'YOUR_API_KEY'
}
payload = json.dumps({
  "collection": {
    "info": {
      "name": "My Collection",
      "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
    },
    "item": []
  }
})

response = requests.request("POST", url, headers=headers, data=payload)
print(response.text)

```

### 8. PUT /collections/{collectionId} — Update a collection

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const raw = JSON.stringify({
  "collection": {
    "info": {
      "name": "Updated Collection Name",
      "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
    },
    "item": []
  }
});

const requestOptions = {
  method: "PUT",
  headers: myHeaders,
  body: raw,
  redirect: "follow"
};

fetch("https://api.getpostman.com/collections/{collectionId}", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests
import json

url = "https://api.getpostman.com/collections/{collectionId}"
headers = {
  'Content-Type': 'application/json',
  'X-Api-Key': 'YOUR_API_KEY'
}
payload = json.dumps({
  "collection": {
    "info": {
      "name": "Updated Collection Name",
      "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
    },
    "item": []
  }
})

response = requests.request("PUT", url, headers=headers, data=payload)
print(response.text)

```
### 9. DELETE /collections/{collectionId} - Delete a Collection

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "DELETE",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/collections/{collectionId}", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/collections/{collectionId}"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("DELETE", url, headers=headers)
print(response.text)

```

### 10. GET /environments - List all Environment

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/environments", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/environments"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 11. GET /environments/{environmentId} - Fetch a Specific Environment

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/environments/{environmentId}", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/environments/{environmentId}"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 12. POST /environments - Create Environments

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const raw = JSON.stringify({
  "environment": {
    "name": "My Environment",
    "values": [
      {
        "key": "baseUrl",
        "value": "https://api.example.com",
        "type": "default",
        "enabled": true
      }
    ]
  }
});

const requestOptions = {
  method: "POST",
  headers: myHeaders,
  body: raw,
  redirect: "follow"
};

fetch("https://api.getpostman.com/environments", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests
import json

url = "https://api.getpostman.com/environments"
headers = {
  'Content-Type': 'application/json',
  'X-Api-Key': 'YOUR_API_KEY'
}
payload = json.dumps({
  "environment": {
    "name": "My Environment",
    "values": [
      {
        "key": "baseUrl",
        "value": "https://api.example.com",
        "type": "default",
        "enabled": True
      }
    ]
  }
})

response = requests.request("POST", url, headers=headers, data=payload)
print(response.text)

```

### 13. PUT /environments/{environmentId} - Update Environments

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("Authorization", "YOUR_API_KEY");
myHeaders.append("Content-Type", "application/json");

const raw = JSON.stringify({
  "environment": {
    "name": "GOKUL",
    "values": [
      {
        "key": "collectionId",
        "value": "12345678-12ece9e1-2abf-4edc-8e34-de66e74114d2",
        "type": "default",
        "enabled": true,
        "description": "The collection's ID."
      }
    ]
  }
});

const requestOptions = {
  method: "PUT",
  headers: myHeaders,
  body: raw,
  redirect: "follow"
};

fetch("https://api.getpostman.com/environments/53663724-9396fef2-ffc4-4f94-9ae1-04a1cf77bc18", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests
import json

url = "https://api.getpostman.com/environments/53663724-9396fef2-ffc4-4f94-9ae1-04a1cf77bc18"

payload = json.dumps({
  "environment": {
    "name": "GOKUL",
    "values": [
      {
        "key": "collectionId",
        "value": "12345678-12ece9e1-2abf-4edc-8e34-de66e74114d2",
        "type": "default",
        "enabled": True,
        "description": "The collection's ID."
      }
    ]
  }
})
headers = {
  'Authorization': 'YOUR_API_KEY',
  'Content-Type': 'application/json'
}

response = requests.request("PUT", url, headers=headers, data=payload)

print(response.text)

```

### 14. GET /monitors - Get all monitors

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/monitors", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/monitors"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

### 15. GET/monitors/{monitorId} - Get a specific monitor

**JavaScript:**

```javascript

const myHeaders = new Headers();
myHeaders.append("X-Api-Key", "YOUR_API_KEY");

const requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow"
};

fetch("https://api.getpostman.com/monitors/{monitorId}", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

```

**Python:**

```python

import requests

url = "https://api.getpostman.com/monitors/{monitorId}"
headers = {
  'X-Api-Key': 'YOUR_API_KEY'
}

response = requests.request("GET", url, headers=headers)
print(response.text)

```

---

## Change log

|**VERSION**|**DATE**|**CHANGES**|
|-----------|--------|-----------|
| 1.0       | May 6, 2026 | Initial release |

## Support & Contact

|**CHANNEL**|**DETAILS**|
|-----------|-----------|
| Official Docs | https://learning.postman.com/docs/introduction/overview |
| Community | https://community.postman.com/ |
| Status Page | https://status.postman.com/ |

## License & Compliance

Postman is proprietary software owned by Postman, Inc., governed by its Terms of Service and Privacy Policy. The free plan requires no license; paid plans (Basic, Professional, Enterprise) require a license agreement. Postman complies with SOC 2 Type II, GDPR, and CCPA standards. It uses open-source libraries listed in its attribution documentation. Exported collections and schemas remain the intellectual property of the respective API owner. Enterprise users should verify data residency options before handling sensitive data.

---

*Document Version: 1.0 | Last Reviewed: May 6, 2026* 

---