
---
title: "getEventHub"
title_tag: "azure.eventhub.getEventHub"
meta_desc: "Documentation for the azure.eventhub.getEventHub function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing EventHub.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Azure = Pulumi.Azure;

class MyStack : Stack
{
    public MyStack()
    {
        var example = Output.Create(Azure.EventHub.GetEventHub.InvokeAsync(new Azure.EventHub.GetEventHubArgs
        {
            Name = "search-eventhub",
            ResourceGroupName = "search-service",
            NamespaceName = "search-eventhubns",
        }));
        this.EventhubId = example.Apply(example => example.Id);
    }

    [Output("eventhubId")]
    public Output<string> EventhubId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/eventhub"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		example, err := eventhub.LookupEventHub(ctx, &eventhub.LookupEventHubArgs{
			Name:              "search-eventhub",
			ResourceGroupName: "search-service",
			NamespaceName:     "search-eventhubns",
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("eventhubId", example.Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.eventhub.get_event_hub(name="search-eventhub",
    resource_group_name="search-service",
    namespace_name="search-eventhubns")
pulumi.export("eventhubId", example.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.eventhub.getEventHub({
    name: "search-eventhub",
    resourceGroupName: "search-service",
    namespaceName: "search-eventhubns",
});
export const eventhubId = example.then(example => example.id);
```


{{< /example >}}





{{% /examples %}}




## Using getEventHub {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getEventHub<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetEventHubArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetEventHubResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_event_hub(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">namespace_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetEventHubResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupEventHub<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupEventHubArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupEventHubResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupEventHub` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetEventHub </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetEventHubResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetEventHubArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this EventHub.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespacename_csharp">
<a href="#namespacename_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the EventHub Namespace where the EventHub exists.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Resource Group where the EventHub exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this EventHub.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespacename_go">
<a href="#namespacename_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the EventHub Namespace where the EventHub exists.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Resource Group where the EventHub exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this EventHub.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespacename_nodejs">
<a href="#namespacename_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the EventHub Namespace where the EventHub exists.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Resource Group where the EventHub exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of this EventHub.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespace_name_python">
<a href="#namespace_name_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the EventHub Namespace where the EventHub exists.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Resource Group where the EventHub exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getEventHub Result {#result}

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
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespacename_csharp">
<a href="#namespacename_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partitioncount_csharp">
<a href="#partitioncount_csharp" style="color: inherit; text-decoration: inherit;">Partition<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of partitions in the EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partitionids_csharp">
<a href="#partitionids_csharp" style="color: inherit; text-decoration: inherit;">Partition<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The identifiers for the partitions of this EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
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
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespacename_go">
<a href="#namespacename_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partitioncount_go">
<a href="#partitioncount_go" style="color: inherit; text-decoration: inherit;">Partition<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of partitions in the EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partitionids_go">
<a href="#partitionids_go" style="color: inherit; text-decoration: inherit;">Partition<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers for the partitions of this EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
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
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespacename_nodejs">
<a href="#namespacename_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partitioncount_nodejs">
<a href="#partitioncount_nodejs" style="color: inherit; text-decoration: inherit;">partition<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of partitions in the EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partitionids_nodejs">
<a href="#partitionids_nodejs" style="color: inherit; text-decoration: inherit;">partition<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The identifiers for the partitions of this EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
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
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespace_name_python">
<a href="#namespace_name_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partition_count_python">
<a href="#partition_count_python" style="color: inherit; text-decoration: inherit;">partition_<wbr>count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of partitions in the EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="partition_ids_python">
<a href="#partition_ids_python" style="color: inherit; text-decoration: inherit;">partition_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers for the partitions of this EventHub.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure">https://github.com/pulumi/pulumi-azure</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azurerm` Terraform Provider](https://github.com/terraform-providers/terraform-provider-azurerm).{{% /md %}}</dd>
</dl>

