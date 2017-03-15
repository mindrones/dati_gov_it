# GET endpoints (incomplete)

I'm doing a first round of endpoints testing to get acquainted with the CKAN API.

I'm using correct parameters (if they're needed) where possible, but where I can't find suitable values (maybe because I can't find any example in data files I downloaded previously) I just test the endpoint without parameters, because if the endpoint exists we get a `400: Bad Request`, otherwise we get a `404: Not Found`.

## Response examples

### Working endpoint (Response code: `200: OK`)

```
$ wget http://www.dati.gov.it/api/3/action/group_package_show?id=ufficio-statistica
--2017-03-14 17:41:43--  http://www.dati.gov.it/api/3/action/group_package_show?id=ufficio-statistica
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [application/json]
Saving to: ‘group_package_show?id=ufficio-statistica’

group_package_show?id=ufficio-statistica        [   <=>   ]  64.82K  --.-KB/s    in 0.04s
```

### Missing endpoint (Response code: `404: Not Found`)

```
$ wget http://www.dati.gov.it/api/3/action/member_list?id=comune-siena        
--2017-03-14 16:42:17--  http://www.dati.gov.it/api/3/action/member_list?id=comune-siena
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 16:42:18 ERROR 404: Not Found.
```

### Working endpoint, bad request (Response code: `400: Bad Request`)

```
$ wget http://www.dati.gov.it/api/3/action/group_package_show
--2017-03-14 17:39:40--  http://www.dati.gov.it/api/3/action/group_package_show
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 400 Bad Request
2017-03-14 17:39:41 ERROR 400: Bad Request.
```

## Endpoints responses

If an endpoint has no notes, it works.

- [site_read](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.site_read)
- [package_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_list)
- [current_package_list_with_resources](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.current_package_list_with_resources)
- [revision_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.revision_list)
- [package_revision_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_revision_list)
- [member_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.member_list)

```
$ wget http://www.dati.gov.it/api/3/action/member_list?id=comune-siena        
--2017-03-14 16:42:17--  http://www.dati.gov.it/api/3/action/member_list?id=comune-siena
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 16:42:18 ERROR 404: Not Found.
```

- [group_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_list)
- [organization_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_list)

```
$ wget http://www.dati.gov.it/api/3/action/organization_list
--2017-03-14 15:24:10--  http://www.dati.gov.it/api/3/action/organization_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 15:24:11 ERROR 404: Not Found.
```

- [group_list_authz](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_list_authz)

(about user auth, can't test it + it doesn't matter from an external user perspective)

- [organization_list_for_user](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_list_for_user)

(about user auth, can't test it + it doesn't matter from an external user perspective)

- [group_revision_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_revision_list)

```
$ wget http://www.dati.gov.it/api/3/action/group_revision_list?id=ufficio-statistica
--2017-03-14 15:28:36--  http://www.dati.gov.it/api/3/action/group_revision_list?id=ufficio-statistica
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 15:28:37 ERROR 404: Not Found.
```
- [organization_revision_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_revision_list)

```
$ wget http://www.dati.gov.it/api/3/action/organization_revision_list?id=a6bc8e36-122e-4577-820a-cb6a13313b5b
--2017-03-14 17:01:24--  http://www.dati.gov.it/api/3/action/organization_revision_list?id=a6bc8e36-122e-4577-820a-cb6a13313b5b
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:01:25 ERROR 404: Not Found.
```

- [license_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.license_list)

```
$ wget http://www.dati.gov.it/api/3/action/license_list
--2017-03-14 17:03:21--  http://www.dati.gov.it/api/3/action/license_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:03:21 ERROR 404: Not Found.
```

- [tag_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.tag_list)

```
$ wget http://www.dati.gov.it/api/3/action/tag_list
--2017-03-09 13:21:44--  http://www.dati.gov.it/api/3/action/tag_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-09 13:21:44 ERROR 404: Not Found.
```

- [user_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_list)

```
$ wget http://www.dati.gov.it/api/3/action/user_list
--2017-03-14 17:08:19--  http://www.dati.gov.it/api/3/action/user_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:08:19 ERROR 404: Not Found.
```

- [package_relationships_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_relationships_list)

```
$ wget http://www.dati.gov.it/api/3/action/package_relationships_list
--2017-03-14 18:19:40--  http://www.dati.gov.it/api/3/action/package_relationships_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:19:40 ERROR 404: Not Found.
```

- [package_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_show)
- [resource_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.resource_show)
- [resource_view_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.resource_view_show)

```
$ wget http://www.dati.gov.it/api/3/action/resource_view_show
--2017-03-14 18:21:49--  http://www.dati.gov.it/api/3/action/resource_view_show
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:21:49 ERROR 404: Not Found.
```
- [resource_view_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.resource_view_list)

```
$ wget http://www.dati.gov.it/api/3/action/resource_view_list
--2017-03-14 18:22:21--  http://www.dati.gov.it/api/3/action/resource_view_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:22:22 ERROR 404: Not Found
```

- [revision_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.revision_show)

```
$ wget http://www.dati.gov.it/api/3/action/revision_show?id=ea447809-a0b9-4067-b789-59e41fcd579f
--2017-03-14 17:22:32--  http://www.dati.gov.it/api/3/action/revision_show?id=ea447809-a0b9-4067-b789-59e41fcd579f
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:22:34 ERROR 404: Not Found.
```

- [group_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_show)

```
$ wget http://www.dati.gov.it/api/3/action/group_show?id=ufficio-statistica
--2017-03-09 13:26:47--  http://www.dati.gov.it/api/3/action/group_show?id=ufficio-statistica
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-09 13:26:48 ERROR 404: Not Found.
```

- [organization_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_show)

```
$ wget http://www.dati.gov.it/api/3/action/organization_show?id=a6bc8e36-122e-4577-820a-cb6a13313b5b
--2017-03-14 17:28:02--  http://www.dati.gov.it/api/3/action/organization_show?id=a6bc8e36-122e-4577-820a-cb6a13313b5b
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:28:03 ERROR 404: Not Found.
```

- [group_package_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_package_show)
- [tag_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.tag_show)

```
$ wget http://www.dati.gov.it/api/3/action/tag_show?id=59d55a3d-3ff0-4b4e-8b38-794c050adc22
--2017-03-14 17:36:58--  http://www.dati.gov.it/api/3/action/tag_show?id=59d55a3d-3ff0-4b4e-8b38-794c050adc22
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:36:59 ERROR 404: Not Found.
```

- [user_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_show)

```
$ wget http://www.dati.gov.it/api/3/action/user_show?id=9bcba160-349c-4d14-8a53-d4168349d053
--2017-03-14 17:44:41--  http://www.dati.gov.it/api/3/action/user_show?id=9bcba160-349c-4d14-8a53-d4168349d053
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:44:41 ERROR 404: Not Found.
```

- [package_autocomplete](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_autocomplete)

```
$ wget "http://www.dati.gov.it/api/3/action/package_autocomplete?q=trasporto&limit=10"
--2017-03-14 19:28:48--  http://www.dati.gov.it/api/3/action/package_autocomplete?q=trasporto&limit=10
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: http://www.dati.gov.it/trasporto?limit=10 [following]
--2017-03-14 19:28:48--  http://www.dati.gov.it/trasporto?limit=10
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 19:28:49 ERROR 404: Not Found.
```

- [format_autocomplete](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.format_autocomplete)

```
$ wget "http://www.dati.gov.it/api/3/action/package_autocomplete?q=tx&limit=10"
--2017-03-14 17:51:09--  http://www.dati.gov.it/api/3/action/package_autocomplete?q=tx&limit=10
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: http://www.dati.gov.it/tx?limit=10 [following]
--2017-03-14 17:51:09--  http://www.dati.gov.it/tx?limit=10
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:51:10 ERROR 404: Not Found
```

- [user_autocomplete](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_autocomplete)

```
$ wget "http://www.dati.gov.it/api/3/action/user_autocomplete?q=uff&limit=10"
--2017-03-14 17:57:26--  http://www.dati.gov.it/api/3/action/user_autocomplete?q=uff&limit=10
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: http://www.dati.gov.it/uff?limit=10 [following]
--2017-03-14 17:57:26--  http://www.dati.gov.it/uff?limit=10
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:57:26 ERROR 404: Not Found.
```

- [organization_autocomplete](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_autocomplete)

```
$ wget "http://www.dati.gov.it/api/3/action/organization_autocomplete?q=org&limit=10"
--2017-03-14 17:59:02--  http://www.dati.gov.it/api/3/action/organization_autocomplete?q=org&limit=10
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: http://www.dati.gov.it/org?limit=10 [following]
--2017-03-14 17:59:02--  http://www.dati.gov.it/org?limit=10
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 17:59:02 ERROR 404: Not Found.
```

- [package_search](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_search)

```
$ wget http://www.dati.gov.it/api/3/action/package_search                    
--2017-03-14 18:00:03--  http://www.dati.gov.it/api/3/action/package_search
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:00:03 ERROR 404: Not Found.
```

- [resource_search](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.resource_search)

```
$ wget http://www.dati.gov.it/api/3/action/resource_search
--2017-03-14 18:00:46--  http://www.dati.gov.it/api/3/action/resource_search
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:00:46 ERROR 404: Not Found.
```

- [tag_search](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.tag_search)

```
$ wget http://www.dati.gov.it/api/3/action/tag_search     
--2017-03-14 18:01:43--  http://www.dati.gov.it/api/3/action/tag_search
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:01:44 ERROR 404: Not Found.
```

- [tag_autocomplete](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.tag_autocomplete)

```
$ wget "http://www.dati.gov.it/api/3/action/tag_autocomplete?q=Mobilit&limit=10"
--2017-03-14 18:03:18--  http://www.dati.gov.it/api/3/action/tag_autocomplete?q=Mobilit&limit=10
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: http://www.dati.gov.it/Mobilit?limit=10 [following]
--2017-03-14 18:03:19--  http://www.dati.gov.it/Mobilit?limit=10
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-14 18:03:19 ERROR 404: Not Found.
```

- [task_status_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.task_status_show)

TODO

- [term_translation_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.term_translation_show)

TODO

- [get_site_user](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.get_site_user)

```
$ wget http://www.dati.gov.it/api/3/action/get_site_user
--2017-03-15 11:20:48--  http://www.dati.gov.it/api/3/action/get_site_user
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:20:48 ERROR 404: Not Found.
```

- [status_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.status_show)

```
$ wget http://www.dati.gov.it/api/3/action/status_show
--2017-03-15 11:18:16--  http://www.dati.gov.it/api/3/action/status_show
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:18:18 ERROR 404: Not Found.
```

- [vocabulary_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.vocabulary_list)

```
$ wget http://www.dati.gov.it/api/3/action/vocabulary_list
--2017-03-15 11:17:29--  http://www.dati.gov.it/api/3/action/vocabulary_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:17:30 ERROR 404: Not Found.
```

- [vocabulary_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.vocabulary_show)

```
$ wget http://www.dati.gov.it/api/3/action/vocabulary_show?id=0
--2017-03-15 11:23:05--  http://www.dati.gov.it/api/3/action/vocabulary_show?id=0
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:23:06 ERROR 404: Not Found.
```

- [user_activity_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_activity_list)

```
$ wget http://www.dati.gov.it/api/3/action/user_activity_list?id=9bcba160-349c-4d14-8a53-d4168349d053
--2017-03-15 11:04:06--  http://www.dati.gov.it/api/3/action/user_activity_list?id=9bcba160-349c-4d14-8a53-d4168349d053
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:04:06 ERROR 404: Not Found.
```

- [package_activity_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_activity_list)

```
$ wget http://www.dati.gov.it/api/3/action/package_activity_list?id=3074974d-b4c7-4df9-809a-d266088de3a3
--2017-03-15 11:05:04--  http://www.dati.gov.it/api/3/action/package_activity_list?id=3074974d-b4c7-4df9-809a-d266088de3a3
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:05:05 ERROR 404: Not Found.
```

- [group_activity_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_activity_list)

```
$ wget http://www.dati.gov.it/api/3/action/group_activity_list?id=ufficio-statistica
--2017-03-15 11:06:45--  http://www.dati.gov.it/api/3/action/group_activity_list?id=ufficio-statistica
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:06:46 ERROR 404: Not Found.
```

- [organization_activity_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_activity_list)

```
$ wget http://www.dati.gov.it/api/3/action/organization_activity_list?id=a6bc8e36-122e-4577-820a-cb6a13313b5b
--2017-03-15 11:07:17--  http://www.dati.gov.it/api/3/action/organization_activity_list?id=a6bc8e36-122e-4577-820a-cb6a13313b5b
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-15 11:07:17 ERROR 404: Not Found.
```

- [recently_changed_packages_activity_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.recently_changed_packages_activity_list)

```
$ wget http://www.dati.gov.it/api/3/action/recently_changed_packages_activity_list
--2017-03-09 13:29:03--  http://www.dati.gov.it/api/3/action/recently_changed_packages_activity_list
Resolving www.dati.gov.it... 89.97.56.30
Connecting to www.dati.gov.it|89.97.56.30|:80... connected.
HTTP request sent, awaiting response... 404 Not Found
2017-03-09 13:29:04 ERROR 404: Not Found.
```

## TODO

- [activity_detail_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.activity_detail_list)
- [user_activity_list_html](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_activity_list_html)
- [package_activity_list_html](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.package_activity_list_html)
- [group_activity_list_html](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_activity_list_html)
- [organization_activity_list_html](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_activity_list_html)
- [recently_changed_packages_activity_list_html](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.recently_changed_packages_activity_list_html)
- [user_follower_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_follower_count)
- [dataset_follower_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dataset_follower_count)
- [group_follower_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_follower_count)
- [organization_follower_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_follower_count)
- [user_follower_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_follower_list)
- [dataset_follower_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dataset_follower_list)
- [group_follower_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_follower_list)
- [organization_follower_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_follower_list)
- [am_following_user](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.am_following_user)
- [am_following_dataset](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.am_following_dataset)
- [am_following_group](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.am_following_group)
- [followee_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.followee_count)
- [user_followee_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_followee_count)
- [dataset_followee_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dataset_followee_count)
- [group_followee_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_followee_count)
- [followee_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.followee_list)
- [user_followee_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.user_followee_list)
- [dataset_followee_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dataset_followee_list)
- [group_followee_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.group_followee_list)
- [organization_followee_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.organization_followee_list)
- [dashboard_activity_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dashboard_activity_list)
- [dashboard_activity_list_html](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dashboard_activity_list_html)
- [dashboard_new_activities_count](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.dashboard_new_activities_count)
- [member_roles_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.member_roles_list)
- [help_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.help_show)
- [config_option_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.config_option_show)
- [config_option_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.config_option_list)
- [job_list](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.job_list)
- [job_show](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.job_show)
