# Bitbucket

* You can test Bitbucket webhooks with [ngrok](https://ngrok.com/) locally
* See [Bitbucket: Manage webhooks](https://confluence.atlassian.com/bitbucket/manage-webhooks-735643732.html)

```json
[
    {
        "method": "POST",
        "path": "/bitbucket-commit",
        "command": "echo New commit from $COMMIT_AUTHOR_NAME: $COMMIT_MESSAGE",
        "parseJson": [
            {
                "query": "payload.push.changes.0.commits.0.message",
                "variable": "COMMIT_MESSAGE"
            },
            {
                "query": "payload.push.changes.0.commits.0.author.user.display_name",
                "variable": "COMMIT_AUTHOR_NAME"
            }
        ]
    }
]
```
