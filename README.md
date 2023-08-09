# AppEcrAction

Github Action to create an ECR repository if it's missing for a Finalcad app.

## Inputs

### `aws-role`
[**Required**] AWS role allowing Secret manager usage

### `aws-region`
AWS region for ECR checks, Default: eu-central-1

### `environment`
[**Required**] Finalcad envrionment: production, staging, sandbox

### `registry`
[**Required**] Full registry name

### `pulling-accounts`
Comma separated list of account number allowed to pull beside principal account, Default: empty

## Usage

```yaml
- name: Create ecr
  uses: FinalCAD/AppEcrAction@v0.0.1
  with:
    aws-role: ${{ secrets.DEPLOY_ROLE_MASTER }}
    environment: sandbox
    registry: api1-service-api
```

```yaml
- name: Create ecr
  uses: FinalCAD/AppEcrAction@v0.0.1
  with:
    aws-role: ${{ secrets.DEPLOY_ROLE_MASTER }}
    environment: sandbox
    registry: api1-service-api
    pulling-accounts: "10101001010,2021020020"
```
