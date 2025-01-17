# GitHub::Repositories::Collaborator

The Collaborators resource allows you to add, invite, and remove collaborators from a repository.

## Syntax

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON

<pre>
{
    "Type" : "GitHub::Repositories::Collaborator",
    "Properties" : {
        "<a href="#githubaccess" title="GitHubAccess">GitHubAccess</a>" : <i>String</i>,
        "<a href="#owner" title="Owner">Owner</a>" : <i>String</i>,
        "<a href="#repository" title="Repository">Repository</a>" : <i>String</i>,
        "<a href="#username" title="Username">Username</a>" : <i>String</i>,
        "<a href="#permission" title="Permission">Permission</a>" : <i>String</i>,
        "<a href="#permissions" title="Permissions">Permissions</a>" : <i><a href="permissions.md">Permissions</a></i>,
    }
}
</pre>

### YAML

<pre>
Type: GitHub::Repositories::Collaborator
Properties:
    <a href="#githubaccess" title="GitHubAccess">GitHubAccess</a>: <i>String</i>
    <a href="#owner" title="Owner">Owner</a>: <i>String</i>
    <a href="#repository" title="Repository">Repository</a>: <i>String</i>
    <a href="#username" title="Username">Username</a>: <i>String</i>
    <a href="#permission" title="Permission">Permission</a>: <i>String</i>
    <a href="#permissions" title="Permissions">Permissions</a>: <i><a href="permissions.md">Permissions</a></i>
</pre>

## Properties

#### GitHubAccess

Personal Access Token

_Required_: Yes

_Type_: String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### Owner

The account owner of the repository. The name is not case sensitive.

_Required_: Yes

_Type_: String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### Repository

The name of the repository. The name is not case sensitive.

_Required_: Yes

_Type_: String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### Username

The handle for the GitHub user account.

_Required_: Yes

_Type_: String

_Pattern_: <code>^(?=[a-zA-Z0-9._]{7,20}$)(?!.*[_.]{2})[^_.].*[^_.]$</code>

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### Permission

The permission to grant the collaborator. Only valid on organization-owned repositories. In addition to the enumerated values, you can also specify a custom repository role name, if the owning organization has defined any..

_Required_: No

_Type_: String

_Allowed Values_: <code>pull</code> | <code>push</code> | <code>admin</code> | <code>maintain</code> | <code>triage</code>

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### Permissions

The permission granted the collaborator.

_Required_: No

_Type_: <a href="permissions.md">Permissions</a>

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

## Return Values

### Fn::GetAtt

The `Fn::GetAtt` intrinsic function returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

For more information about using the `Fn::GetAtt` intrinsic function, see [Fn::GetAtt](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-getatt.html).

#### InvitationId

Invitation identifier

