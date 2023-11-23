# Package version

Package are built using the snapshot version, be sure to pin the exact correct version in the keycloak dockerfile.

# Build and deploy

This plugging has been modified to be compatible with keycloak version 21.1.2

To compile and publish a new version you need to:

Acquire an Codeartifact token with permission to push. Assuming you have configured an AWS profile named `publish2codeartifact` that can do so:
```
export CODEARTIFACT_AUTH_TOKEN=$(aws --profile=publish2codeartifact get-authorization-token --domain=alayacare --query=authorizationToken --output=text)
```

Then:
```
mvn deploy -Dkeycloak.version=<keycloak version>
```

Ex:
```
mvn deploy -Dkeycloak.version=21.1.2
```
