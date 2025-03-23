IRSA (IAM roles for service accounts) enables Kubernetes applications to access AWS APIs via their attached service accounts.

1. Deploy IAM OIDC provider ( 1 per cluster )
2. Create an IAM role with the appropriate trust policy that scopes the role to a specific service account via IAM conditions
3. Attach the required permissions to the role via a role policy 
4. Create a service account , annotate it with the role ARN and attach the SA to the pod/deployment that needs to access AWS APIs