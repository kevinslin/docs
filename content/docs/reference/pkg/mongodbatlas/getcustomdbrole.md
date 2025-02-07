
---
title: "getCustomDbRole"
title_tag: "mongodbatlas.getCustomDbRole"
meta_desc: "Documentation for the mongodbatlas.getCustomDbRole function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

`mongodbatlas.CustomDbRole` describe a Custom DB Role. This represents a custom db role.

> **NOTE:** Groups and projects are synonymous terms. You may find group_id in the official documentation.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Mongodbatlas = Pulumi.Mongodbatlas;

class MyStack : Stack
{
    public MyStack()
    {
        var testRole = new Mongodbatlas.CustomDbRole("testRole", new Mongodbatlas.CustomDbRoleArgs
        {
            Actions = 
            {
                new Mongodbatlas.Inputs.CustomDbRoleActionArgs
                {
                    Action = "UPDATE",
                    Resources = 
                    {
                        new Mongodbatlas.Inputs.CustomDbRoleActionResourceArgs
                        {
                            CollectionName = "",
                            DatabaseName = "anyDatabase",
                        },
                    },
                },
                new Mongodbatlas.Inputs.CustomDbRoleActionArgs
                {
                    Action = "INSERT",
                    Resources = 
                    {
                        new Mongodbatlas.Inputs.CustomDbRoleActionResourceArgs
                        {
                            CollectionName = "",
                            DatabaseName = "anyDatabase",
                        },
                    },
                },
            },
            ProjectId = "<PROJECT-ID>",
            RoleName = "myCustomRole",
        });
        var test = Output.Tuple(testRole.ProjectId, testRole.RoleName).Apply(values =>
        {
            var projectId = values.Item1;
            var roleName = values.Item2;
            return Mongodbatlas.GetCustomDbRole.InvokeAsync(new Mongodbatlas.GetCustomDbRoleArgs
            {
                ProjectId = projectId,
                RoleName = roleName,
            });
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-mongodbatlas/sdk/go/mongodbatlas"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		testRole, err := mongodbatlas.NewCustomDbRole(ctx, "testRole", &mongodbatlas.CustomDbRoleArgs{
			Actions: mongodbatlas.CustomDbRoleActionArray{
				&mongodbatlas.CustomDbRoleActionArgs{
					Action: pulumi.String("UPDATE"),
					Resources: mongodbatlas.CustomDbRoleActionResourceArray{
						&mongodbatlas.CustomDbRoleActionResourceArgs{
							CollectionName: pulumi.String(""),
							DatabaseName:   pulumi.String("anyDatabase"),
						},
					},
				},
				&mongodbatlas.CustomDbRoleActionArgs{
					Action: pulumi.String("INSERT"),
					Resources: mongodbatlas.CustomDbRoleActionResourceArray{
						&mongodbatlas.CustomDbRoleActionResourceArgs{
							CollectionName: pulumi.String(""),
							DatabaseName:   pulumi.String("anyDatabase"),
						},
					},
				},
			},
			ProjectId: pulumi.String("<PROJECT-ID>"),
			RoleName:  pulumi.String("myCustomRole"),
		})
		if err != nil {
			return err
		}
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_mongodbatlas as mongodbatlas

test_role = mongodbatlas.CustomDbRole("testRole",
    actions=[
        mongodbatlas.CustomDbRoleActionArgs(
            action="UPDATE",
            resources=[mongodbatlas.CustomDbRoleActionResourceArgs(
                collection_name="",
                database_name="anyDatabase",
            )],
        ),
        mongodbatlas.CustomDbRoleActionArgs(
            action="INSERT",
            resources=[mongodbatlas.CustomDbRoleActionResourceArgs(
                collection_name="",
                database_name="anyDatabase",
            )],
        ),
    ],
    project_id="<PROJECT-ID>",
    role_name="myCustomRole")
test = pulumi.Output.all(test_role.project_id, test_role.role_name).apply(lambda project_id, role_name: mongodbatlas.get_custom_db_role(project_id=project_id,
    role_name=role_name))
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as mongodbatlas from "@pulumi/mongodbatlas";

const testRole = new mongodbatlas.CustomDbRole("test_role", {
    actions: [
        {
            action: "UPDATE",
            resources: [{
                collectionName: "",
                databaseName: "anyDatabase",
            }],
        },
        {
            action: "INSERT",
            resources: [{
                collectionName: "",
                databaseName: "anyDatabase",
            }],
        },
    ],
    projectId: "<PROJECT-ID>",
    roleName: "myCustomRole",
});
const test = pulumi.all([testRole.projectId, testRole.roleName]).apply(([projectId, roleName]) => mongodbatlas.getCustomDbRole({
    projectId: projectId,
    roleName: roleName,
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getCustomDbRole {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getCustomDbRole<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetCustomDbRoleArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetCustomDbRoleResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_custom_db_role(</span><span class="nx">inherited_roles</span><span class="p">:</span> <span class="nx">Optional[Sequence[GetCustomDbRoleInheritedRoleArgs]]</span> = None<span class="p">, </span><span class="nx">project_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">role_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetCustomDbRoleResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupCustomDbRole<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupCustomDbRoleArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupCustomDbRoleResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupCustomDbRole` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetCustomDbRole </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetCustomDbRoleResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetCustomDbRoleArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to create the database user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="rolename_csharp">
<a href="#rolename_csharp" style="color: inherit; text-decoration: inherit;">Role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="inheritedroles_csharp">
<a href="#inheritedroles_csharp" style="color: inherit; text-decoration: inherit;">Inherited<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">List&lt;Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to create the database user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="rolename_go">
<a href="#rolename_go" style="color: inherit; text-decoration: inherit;">Role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="inheritedroles_go">
<a href="#inheritedroles_go" style="color: inherit; text-decoration: inherit;">Inherited<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">[]Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to create the database user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="rolename_nodejs">
<a href="#rolename_nodejs" style="color: inherit; text-decoration: inherit;">role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="inheritedroles_nodejs">
<a href="#inheritedroles_nodejs" style="color: inherit; text-decoration: inherit;">inherited<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique ID for the project to create the database user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_name_python">
<a href="#role_name_python" style="color: inherit; text-decoration: inherit;">role_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="inherited_roles_python">
<a href="#inherited_roles_python" style="color: inherit; text-decoration: inherit;">inherited_<wbr>roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">Sequence[Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getCustomDbRole Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="actions_csharp">
<a href="#actions_csharp" style="color: inherit; text-decoration: inherit;">Actions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleaction">List&lt;Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rolename_csharp">
<a href="#rolename_csharp" style="color: inherit; text-decoration: inherit;">Role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="inheritedroles_csharp">
<a href="#inheritedroles_csharp" style="color: inherit; text-decoration: inherit;">Inherited<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">List&lt;Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="actions_go">
<a href="#actions_go" style="color: inherit; text-decoration: inherit;">Actions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleaction">[]Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rolename_go">
<a href="#rolename_go" style="color: inherit; text-decoration: inherit;">Role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="inheritedroles_go">
<a href="#inheritedroles_go" style="color: inherit; text-decoration: inherit;">Inherited<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">[]Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="actions_nodejs">
<a href="#actions_nodejs" style="color: inherit; text-decoration: inherit;">actions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleaction">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rolename_nodejs">
<a href="#rolename_nodejs" style="color: inherit; text-decoration: inherit;">role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="inheritedroles_nodejs">
<a href="#inheritedroles_nodejs" style="color: inherit; text-decoration: inherit;">inherited<wbr>Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="actions_python">
<a href="#actions_python" style="color: inherit; text-decoration: inherit;">actions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleaction">Sequence[Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="role_name_python">
<a href="#role_name_python" style="color: inherit; text-decoration: inherit;">role_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="inherited_roles_python">
<a href="#inherited_roles_python" style="color: inherit; text-decoration: inherit;">inherited_<wbr>roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleinheritedrole">Sequence[Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getcustomdbroleaction">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="action_csharp">
<a href="#action_csharp" style="color: inherit; text-decoration: inherit;">Action</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Required) Name of the privilege action. For a complete list of actions available in the Atlas API, see Custom Role Actions.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resources_csharp">
<a href="#resources_csharp" style="color: inherit; text-decoration: inherit;">Resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleactionresource">List&lt;Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action<wbr>Resource<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}(Required) Contains information on where the action is granted. Each object in the array either indicates a database and collection on which the action is granted, or indicates that the action is granted on the cluster resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="action_go">
<a href="#action_go" style="color: inherit; text-decoration: inherit;">Action</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Required) Name of the privilege action. For a complete list of actions available in the Atlas API, see Custom Role Actions.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resources_go">
<a href="#resources_go" style="color: inherit; text-decoration: inherit;">Resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleactionresource">[]Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action<wbr>Resource</a></span>
    </dt>
    <dd>{{% md %}}(Required) Contains information on where the action is granted. Each object in the array either indicates a database and collection on which the action is granted, or indicates that the action is granted on the cluster resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="action_nodejs">
<a href="#action_nodejs" style="color: inherit; text-decoration: inherit;">action</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Required) Name of the privilege action. For a complete list of actions available in the Atlas API, see Custom Role Actions.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resources_nodejs">
<a href="#resources_nodejs" style="color: inherit; text-decoration: inherit;">resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleactionresource">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action<wbr>Resource[]</a></span>
    </dt>
    <dd>{{% md %}}(Required) Contains information on where the action is granted. Each object in the array either indicates a database and collection on which the action is granted, or indicates that the action is granted on the cluster resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="action_python">
<a href="#action_python" style="color: inherit; text-decoration: inherit;">action</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Required) Name of the privilege action. For a complete list of actions available in the Atlas API, see Custom Role Actions.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resources_python">
<a href="#resources_python" style="color: inherit; text-decoration: inherit;">resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getcustomdbroleactionresource">Sequence[Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action<wbr>Resource<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}(Required) Contains information on where the action is granted. Each object in the array either indicates a database and collection on which the action is granted, or indicates that the action is granted on the cluster resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getcustomdbroleactionresource">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Action<wbr>Resource</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cluster_csharp">
<a href="#cluster_csharp" style="color: inherit; text-decoration: inherit;">Cluster</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="collectionname_csharp">
<a href="#collectionname_csharp" style="color: inherit; text-decoration: inherit;">Collection<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="databasename_csharp">
<a href="#databasename_csharp" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cluster_go">
<a href="#cluster_go" style="color: inherit; text-decoration: inherit;">Cluster</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="collectionname_go">
<a href="#collectionname_go" style="color: inherit; text-decoration: inherit;">Collection<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="databasename_go">
<a href="#databasename_go" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cluster_nodejs">
<a href="#cluster_nodejs" style="color: inherit; text-decoration: inherit;">cluster</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="collectionname_nodejs">
<a href="#collectionname_nodejs" style="color: inherit; text-decoration: inherit;">collection<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="databasename_nodejs">
<a href="#databasename_nodejs" style="color: inherit; text-decoration: inherit;">database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cluster_python">
<a href="#cluster_python" style="color: inherit; text-decoration: inherit;">cluster</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="collection_name_python">
<a href="#collection_name_python" style="color: inherit; text-decoration: inherit;">collection_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="database_name_python">
<a href="#database_name_python" style="color: inherit; text-decoration: inherit;">database_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getcustomdbroleinheritedrole">Get<wbr>Custom<wbr>Db<wbr>Role<wbr>Inherited<wbr>Role</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="databasename_csharp">
<a href="#databasename_csharp" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="rolename_csharp">
<a href="#rolename_csharp" style="color: inherit; text-decoration: inherit;">Role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="databasename_go">
<a href="#databasename_go" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="rolename_go">
<a href="#rolename_go" style="color: inherit; text-decoration: inherit;">Role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="databasename_nodejs">
<a href="#databasename_nodejs" style="color: inherit; text-decoration: inherit;">database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="rolename_nodejs">
<a href="#rolename_nodejs" style="color: inherit; text-decoration: inherit;">role<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="database_name_python">
<a href="#database_name_python" style="color: inherit; text-decoration: inherit;">database_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_name_python">
<a href="#role_name_python" style="color: inherit; text-decoration: inherit;">role_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the custom role.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-mongodbatlas">https://github.com/pulumi/pulumi-mongodbatlas</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`mongodbatlas` Terraform Provider](https://github.com/mongodb/terraform-provider-mongodbatlas).{{% /md %}}</dd>
</dl>

