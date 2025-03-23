Pod Identities, like IRSA enable Kubernetes applications to access AWS APIs via their attached service accounts but they do not require an OIDC provider.

**EKS with Fargate does not support Pod Identities as of now, so  use IRSA instead**

1. Deploy the pod identity agent
2. Create a role with a relevant trust policy. 
3. Attach permissions to the role via a role policy. 
4. Create a pod identity assocation in AWS to associate a Kubernetes service account wtih an IAM role
5. Add the service account to the pod/deployment that needs to access AWS APIs