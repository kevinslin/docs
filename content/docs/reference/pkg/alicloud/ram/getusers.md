
---
title: "getUsers"
title_tag: "alicloud.ram.getUsers"
meta_desc: "Documentation for the alicloud.ram.getUsers function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source provides a list of RAM users in an Alibaba Cloud account according to the specified filters.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using AliCloud = Pulumi.AliCloud;

class MyStack : Stack
{
    public MyStack()
    {
        var usersDs = Output.Create(AliCloud.Ram.GetUsers.InvokeAsync(new AliCloud.Ram.GetUsersArgs
        {
            GroupName = "group1",
            NameRegex = "^user",
            OutputFile = "users.txt",
            PolicyName = "AliyunACSDefaultAccess",
            PolicyType = "Custom",
        }));
        this.FirstUserId = usersDs.Apply(usersDs => usersDs.Users[0].Id);
    }

    [Output("firstUserId")]
    public Output<string> FirstUserId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/ram"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "group1"
		opt1 := "^user"
		opt2 := "users.txt"
		opt3 := "AliyunACSDefaultAccess"
		opt4 := "Custom"
		usersDs, err := ram.GetUsers(ctx, &ram.GetUsersArgs{
			GroupName:  &opt0,
			NameRegex:  &opt1,
			OutputFile: &opt2,
			PolicyName: &opt3,
			PolicyType: &opt4,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("firstUserId", usersDs.Users[0].Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_alicloud as alicloud

users_ds = alicloud.ram.get_users(group_name="group1",
    name_regex="^user",
    output_file="users.txt",
    policy_name="AliyunACSDefaultAccess",
    policy_type="Custom")
pulumi.export("firstUserId", users_ds.users[0].id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const usersDs = pulumi.output(alicloud.ram.getUsers({
    groupName: "group1",
    nameRegex: "^user",
    outputFile: "users.txt",
    policyName: "AliyunACSDefaultAccess",
    policyType: "Custom",
}, { async: true }));

export const firstUserId = usersDs.users[0].id;
```


{{< /example >}}





{{% /examples %}}




## Using getUsers {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getUsers<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetUsersArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetUsersResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_users(</span><span class="nx">group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">, </span><span class="nx">name_regex</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">output_file</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">policy_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">policy_type</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetUsersResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUsers<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetUsersArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetUsersResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetUsers` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetUsers </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetUsersResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetUsersArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="groupname_csharp">
<a href="#groupname_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific group name. Returned users are in the specified group.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}- A list of ram user IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter resulting users by their names.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policyname_csharp">
<a href="#policyname_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy name. If you set this parameter without setting `policy_type`, the later will be automatically set to `System`. Returned users are attached to the specified policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy type. Valid values are `Custom` and `System`. If you set this parameter, you must set `policy_name` as well.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="groupname_go">
<a href="#groupname_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific group name. Returned users are in the specified group.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}- A list of ram user IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter resulting users by their names.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policyname_go">
<a href="#policyname_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy name. If you set this parameter without setting `policy_type`, the later will be automatically set to `System`. Returned users are attached to the specified policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy type. Valid values are `Custom` and `System`. If you set this parameter, you must set `policy_name` as well.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="groupname_nodejs">
<a href="#groupname_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific group name. Returned users are in the specified group.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}- A list of ram user IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter resulting users by their names.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policyname_nodejs">
<a href="#policyname_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy name. If you set this parameter without setting `policy_type`, the later will be automatically set to `System`. Returned users are attached to the specified policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy type. Valid values are `Custom` and `System`. If you set this parameter, you must set `policy_name` as well.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="group_name_python">
<a href="#group_name_python" style="color: inherit; text-decoration: inherit;">group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific group name. Returned users are in the specified group.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}- A list of ram user IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regex string to filter resulting users by their names.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policy_name_python">
<a href="#policy_name_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy name. If you set this parameter without setting `policy_type`, the later will be automatically set to `System`. Returned users are attached to the specified policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Filter results by a specific policy type. Valid values are `Custom` and `System`. If you set this parameter, you must set `policy_name` as well.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getUsers Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of ram user IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_csharp">
<a href="#names_csharp" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of ram user names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="users_csharp">
<a href="#users_csharp" style="color: inherit; text-decoration: inherit;">Users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getusersuser">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Ram.<wbr>Outputs.<wbr>Get<wbr>Users<wbr>User&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of users. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupname_csharp">
<a href="#groupname_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policyname_csharp">
<a href="#policyname_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of ram user IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_go">
<a href="#names_go" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of ram user names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="users_go">
<a href="#users_go" style="color: inherit; text-decoration: inherit;">Users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getusersuser">[]Get<wbr>Users<wbr>User</a></span>
    </dt>
    <dd>{{% md %}}A list of users. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupname_go">
<a href="#groupname_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policyname_go">
<a href="#policyname_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of ram user IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_nodejs">
<a href="#names_nodejs" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of ram user names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="users_nodejs">
<a href="#users_nodejs" style="color: inherit; text-decoration: inherit;">users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getusersuser">Get<wbr>Users<wbr>User[]</a></span>
    </dt>
    <dd>{{% md %}}A list of users. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupname_nodejs">
<a href="#groupname_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policyname_nodejs">
<a href="#policyname_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of ram user IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_python">
<a href="#names_python" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of ram user names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="users_python">
<a href="#users_python" style="color: inherit; text-decoration: inherit;">users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getusersuser">Sequence[Get<wbr>Users<wbr>User]</a></span>
    </dt>
    <dd>{{% md %}}A list of users. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="group_name_python">
<a href="#group_name_python" style="color: inherit; text-decoration: inherit;">group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policy_name_python">
<a href="#policy_name_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getusersuser">Get<wbr>Users<wbr>User</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="createdate_csharp">
<a href="#createdate_csharp" style="color: inherit; text-decoration: inherit;">Create<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creation date of the user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The original id is user name, but it is user id in 1.37.0+.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="lastlogindate_csharp">
<a href="#lastlogindate_csharp" style="color: inherit; text-decoration: inherit;">Last<wbr>Login<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Last login date of the user. Removed from version 1.79.0.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the user.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="createdate_go">
<a href="#createdate_go" style="color: inherit; text-decoration: inherit;">Create<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creation date of the user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The original id is user name, but it is user id in 1.37.0+.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="lastlogindate_go">
<a href="#lastlogindate_go" style="color: inherit; text-decoration: inherit;">Last<wbr>Login<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Last login date of the user. Removed from version 1.79.0.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the user.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="createdate_nodejs">
<a href="#createdate_nodejs" style="color: inherit; text-decoration: inherit;">create<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creation date of the user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The original id is user name, but it is user id in 1.37.0+.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="lastlogindate_nodejs">
<a href="#lastlogindate_nodejs" style="color: inherit; text-decoration: inherit;">last<wbr>Login<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Last login date of the user. Removed from version 1.79.0.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the user.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="create_date_python">
<a href="#create_date_python" style="color: inherit; text-decoration: inherit;">create_<wbr>date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creation date of the user.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The original id is user name, but it is user id in 1.37.0+.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="last_login_date_python">
<a href="#last_login_date_python" style="color: inherit; text-decoration: inherit;">last_<wbr>login_<wbr>date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Last login date of the user. Removed from version 1.79.0.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the user.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-alicloud">https://github.com/pulumi/pulumi-alicloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`alicloud` Terraform Provider](https://github.com/aliyun/terraform-provider-alicloud).{{% /md %}}</dd>
</dl>

