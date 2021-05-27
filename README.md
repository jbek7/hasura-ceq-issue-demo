# hasura-ceq-issue-demo

- `docker-compose up`
- track all
- add permission for "manager" role as:
```json
{
  "_exists": {
    "_table": {
      "schema": "public",
      "name": "post_comment_permissions"
    },
    "_where": {
      "v_post_id": {
        "_ceq": [
          "post_id"
        ]
      }
    }
  }
}
```

And you should see 
```
Inconsistent object: in table "comments": in permission for role "manager": column "post_id" does not exist
```
