# Passing AWS credentials to molecule converge targets

## Issue

Converge stage fails because the target resource, docker for example, doesn't have access to the AWS credentials from the running host.

