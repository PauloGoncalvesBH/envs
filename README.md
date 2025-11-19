
# Using 1password to store environment variables

## Inject secrets in a command

[Comando `op inject`](https://developer.1password.com/docs/cli/reference/commands/inject)

```sh
echo "serverless config credentials --provider AWS --key {{ op://personal/aws/lambda/AWS_ACCESS_KEY_ID }} --secret {{ op://personal/aws/lambda/AWS_SECRET_ACCESS_KEY }}" | op inject
```

_output:_ 
> serverless config credentials --provider AWS --key 123KEY123 --secret 123SECRET123

## Alias

[Securely authenticate any CLI with 1Password](https://developer.1password.com/docs/cli/authenticate-clis)

### AWS

```sh
alias aws-auth="op run --env-file=$HOME/git/envs/aws.env --"
```

```sh
alias aws="op run --env-file=$HOME/git/envs/aws.env -- aws"
```

### Jira + Cursor MCP configuration

```json
"mcp-atlassian": {
  "command": "sh",
  "args": [
    "-c",
    "op run --env-file=$HOME/git/envs/jira.env -- docker run -i --rm -e CONFLUENCE_URL -e CONFLUENCE_USERNAME -e CONFLUENCE_API_TOKEN -e JIRA_URL -e JIRA_USERNAME -e JIRA_API_TOKEN ghcr.io/sooperset/mcp-atlassian:latest"
  ],
  "env": {}
}
```
