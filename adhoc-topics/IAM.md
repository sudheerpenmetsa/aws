## IAM
  Using IAM, we can create and manage AWS users, and use permissions to allow and deny their access to AWS resources.
### Mainly there are 4 components in IAM
    - Users
    - Groups
        The users created, can also be divided among groups, and then the rules and policies that apply on the group, apply on the user level as well.
    - Roles
        An IAM role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications or AWS services such as EC2.  
    - Policies
        To assign permissions to a user, group, roles, or resource, you create a policy, which is a document that explicitly lists permissions.