# AppEcrAction

Github Action to create an ECR repository if it's missing for a Finalcad app.

  aws-role:
    description: 'Aws role to apply changes'
    required: true
  aws-region:
    description: 'Aws region'
    default: 'eu-central-1'
  environment:
    description: 'Finalcad envrionment: production, staging, sandbox'
    require: true
  registry:
    description: 'Registry name'
    required: true

## Inputs

### `aws-role`
[**Required**] AWS role allowing Secret manager usage

### `aws-region`
AWS region for ECR checks, Default: eu-central-1

### `environment`
[**Required**] Finalcad envrionment: production, staging, sandbox

### `registry`
[**Required**] Full registry name

## Usage

```yaml
- name: Create ecr
  uses: FinalCAD/AppEcrAction@v0.0.1
  with:
    aws-role: ${{ secrets.DEPLOY_ROLE_MASTER }}
    environment: sandbox
    registry: api1-service-api
```
