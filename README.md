
[Securely authenticate any CLI with 1Password](https://developer.1password.com/docs/cli/authenticate-clis)

## Injetar secrets em um comando

[Comando `op inject`](https://developer.1password.com/docs/cli/reference/commands/inject)

```sh
echo "serverless config credentials --provider AWS --key {{ op://personal/aws/lambda/AWS_ACCESS_KEY_ID }} --secret {{ op://personal/aws/lambda/AWS_SECRET_ACCESS_KEY }}" | op inject
```

_output:_ 
> serverless config credentials --provider AWS --key 123KEY123 --secret 123SECRET123

## Alias

### AWS

```sh
alias aws-auth="op run --env-file=$HOME/git/envs/aws.env --"
```

```sh
alias aws="op run --env-file=$HOME/git/envs/aws.env -- aws"
```
