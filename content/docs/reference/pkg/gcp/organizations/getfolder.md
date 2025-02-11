
---
title: "getFolder"
title_tag: "gcp.organizations.getFolder"
meta_desc: "Documentation for the gcp.organizations.getFolder function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to get information about a Google Cloud Folder.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const myFolder1 = gcp.organizations.getFolder({
    folder: "folders/12345",
    lookupOrganization: true,
});
const myFolder2 = gcp.organizations.getFolder({
    folder: "folders/23456",
});
export const myFolder1Organization = myFolder1.then(myFolder1 => myFolder1.organization);
export const myFolder2Parent = myFolder2.then(myFolder2 => myFolder2.parent);
```
```python
import pulumi
import pulumi_gcp as gcp

my_folder1 = gcp.organizations.get_folder(folder="folders/12345",
    lookup_organization=True)
my_folder2 = gcp.organizations.get_folder(folder="folders/23456")
pulumi.export("myFolder1Organization", my_folder1.organization)
pulumi.export("myFolder2Parent", my_folder2.parent)
```
```csharp
using Pulumi;
using Gcp = Pulumi.Gcp;

class MyStack : Stack
{
    public MyStack()
    {
        var myFolder1 = Output.Create(Gcp.Organizations.GetFolder.InvokeAsync(new Gcp.Organizations.GetFolderArgs
        {
            Folder = "folders/12345",
            LookupOrganization = true,
        }));
        var myFolder2 = Output.Create(Gcp.Organizations.GetFolder.InvokeAsync(new Gcp.Organizations.GetFolderArgs
        {
            Folder = "folders/23456",
        }));
        this.MyFolder1Organization = myFolder1.Apply(myFolder1 => myFolder1.Organization);
        this.MyFolder2Parent = myFolder2.Apply(myFolder2 => myFolder2.Parent);
    }

    [Output("myFolder1Organization")]
    public Output<string> MyFolder1Organization { get; set; }
    [Output("myFolder2Parent")]
    public Output<string> MyFolder2Parent { get; set; }
}
```
```go
package main

import (
	"github.com/pulumi/pulumi-gcp/sdk/v4/go/gcp/organizations"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := true
		myFolder1, err := organizations.LookupFolder(ctx, &organizations.LookupFolderArgs{
			Folder:             "folders/12345",
			LookupOrganization: &opt0,
		}, nil)
		if err != nil {
			return err
		}
		myFolder2, err := organizations.LookupFolder(ctx, &organizations.LookupFolderArgs{
			Folder: "folders/23456",
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("myFolder1Organization", myFolder1.Organization)
		ctx.Export("myFolder2Parent", myFolder2.Parent)
		return nil
	})
}
```




## Using getFolder {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getFolder<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetFolderArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetFolderResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_folder(</span><span class="nx">folder</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">lookup_organization</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetFolderResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupFolder<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupFolderArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupFolderResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupFolder` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetFolder </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetFolderResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetFolderArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folder_csharp">
<a href="#folder_csharp" style="color: inherit; text-decoration: inherit;">Folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Folder in the form `{folder_id}` or `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lookuporganization_csharp">
<a href="#lookuporganization_csharp" style="color: inherit; text-decoration: inherit;">Lookup<wbr>Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` to find the organization that the folder belongs, `false` to avoid the lookup. It searches up the tree. (defaults to `false`)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folder_go">
<a href="#folder_go" style="color: inherit; text-decoration: inherit;">Folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Folder in the form `{folder_id}` or `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lookuporganization_go">
<a href="#lookuporganization_go" style="color: inherit; text-decoration: inherit;">Lookup<wbr>Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` to find the organization that the folder belongs, `false` to avoid the lookup. It searches up the tree. (defaults to `false`)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folder_nodejs">
<a href="#folder_nodejs" style="color: inherit; text-decoration: inherit;">folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Folder in the form `{folder_id}` or `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lookuporganization_nodejs">
<a href="#lookuporganization_nodejs" style="color: inherit; text-decoration: inherit;">lookup<wbr>Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}`true` to find the organization that the folder belongs, `false` to avoid the lookup. It searches up the tree. (defaults to `false`)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folder_python">
<a href="#folder_python" style="color: inherit; text-decoration: inherit;">folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Folder in the form `{folder_id}` or `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lookup_organization_python">
<a href="#lookup_organization_python" style="color: inherit; text-decoration: inherit;">lookup_<wbr>organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` to find the organization that the folder belongs, `false` to avoid the lookup. It searches up the tree. (defaults to `false`)
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getFolder Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="createtime_csharp">
<a href="#createtime_csharp" style="color: inherit; text-decoration: inherit;">Create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Organization was created. A timestamp in RFC3339 UTC "Zulu" format, accurate to nanoseconds. Example: "2014-10-02T15:01:23.045123456Z".
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="displayname_csharp">
<a href="#displayname_csharp" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder's display name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folder_csharp">
<a href="#folder_csharp" style="color: inherit; text-decoration: inherit;">Folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folderid_csharp">
<a href="#folderid_csharp" style="color: inherit; text-decoration: inherit;">Folder<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
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
        <span id="lifecyclestate_csharp">
<a href="#lifecyclestate_csharp" style="color: inherit; text-decoration: inherit;">Lifecycle<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Folder's current lifecycle state.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder in the form `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="organization_csharp">
<a href="#organization_csharp" style="color: inherit; text-decoration: inherit;">Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If `lookup_organization` is enable, the resource name of the Organization that the folder belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_csharp">
<a href="#parent_csharp" style="color: inherit; text-decoration: inherit;">Parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the parent Folder or Organization.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lookuporganization_csharp">
<a href="#lookuporganization_csharp" style="color: inherit; text-decoration: inherit;">Lookup<wbr>Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="createtime_go">
<a href="#createtime_go" style="color: inherit; text-decoration: inherit;">Create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Organization was created. A timestamp in RFC3339 UTC "Zulu" format, accurate to nanoseconds. Example: "2014-10-02T15:01:23.045123456Z".
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="displayname_go">
<a href="#displayname_go" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder's display name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folder_go">
<a href="#folder_go" style="color: inherit; text-decoration: inherit;">Folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folderid_go">
<a href="#folderid_go" style="color: inherit; text-decoration: inherit;">Folder<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
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
        <span id="lifecyclestate_go">
<a href="#lifecyclestate_go" style="color: inherit; text-decoration: inherit;">Lifecycle<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Folder's current lifecycle state.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder in the form `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="organization_go">
<a href="#organization_go" style="color: inherit; text-decoration: inherit;">Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If `lookup_organization` is enable, the resource name of the Organization that the folder belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_go">
<a href="#parent_go" style="color: inherit; text-decoration: inherit;">Parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the parent Folder or Organization.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lookuporganization_go">
<a href="#lookuporganization_go" style="color: inherit; text-decoration: inherit;">Lookup<wbr>Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="createtime_nodejs">
<a href="#createtime_nodejs" style="color: inherit; text-decoration: inherit;">create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Organization was created. A timestamp in RFC3339 UTC "Zulu" format, accurate to nanoseconds. Example: "2014-10-02T15:01:23.045123456Z".
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="displayname_nodejs">
<a href="#displayname_nodejs" style="color: inherit; text-decoration: inherit;">display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder's display name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folder_nodejs">
<a href="#folder_nodejs" style="color: inherit; text-decoration: inherit;">folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folderid_nodejs">
<a href="#folderid_nodejs" style="color: inherit; text-decoration: inherit;">folder<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
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
        <span id="lifecyclestate_nodejs">
<a href="#lifecyclestate_nodejs" style="color: inherit; text-decoration: inherit;">lifecycle<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Folder's current lifecycle state.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder in the form `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="organization_nodejs">
<a href="#organization_nodejs" style="color: inherit; text-decoration: inherit;">organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If `lookup_organization` is enable, the resource name of the Organization that the folder belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_nodejs">
<a href="#parent_nodejs" style="color: inherit; text-decoration: inherit;">parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the parent Folder or Organization.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lookuporganization_nodejs">
<a href="#lookuporganization_nodejs" style="color: inherit; text-decoration: inherit;">lookup<wbr>Organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="create_time_python">
<a href="#create_time_python" style="color: inherit; text-decoration: inherit;">create_<wbr>time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Organization was created. A timestamp in RFC3339 UTC "Zulu" format, accurate to nanoseconds. Example: "2014-10-02T15:01:23.045123456Z".
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="display_name_python">
<a href="#display_name_python" style="color: inherit; text-decoration: inherit;">display_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The folder's display name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folder_python">
<a href="#folder_python" style="color: inherit; text-decoration: inherit;">folder</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="folder_id_python">
<a href="#folder_id_python" style="color: inherit; text-decoration: inherit;">folder_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
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
        <span id="lifecycle_state_python">
<a href="#lifecycle_state_python" style="color: inherit; text-decoration: inherit;">lifecycle_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Folder's current lifecycle state.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder in the form `folders/{folder_id}`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="organization_python">
<a href="#organization_python" style="color: inherit; text-decoration: inherit;">organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `lookup_organization` is enable, the resource name of the Organization that the folder belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_python">
<a href="#parent_python" style="color: inherit; text-decoration: inherit;">parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource name of the parent Folder or Organization.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lookup_organization_python">
<a href="#lookup_organization_python" style="color: inherit; text-decoration: inherit;">lookup_<wbr>organization</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-gcp">https://github.com/pulumi/pulumi-gcp</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`google-beta` Terraform Provider](https://github.com/hashicorp/terraform-provider-google-beta).{{% /md %}}</dd>
</dl>

