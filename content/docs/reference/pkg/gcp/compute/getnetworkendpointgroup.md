
---
title: "getNetworkEndpointGroup"
title_tag: "gcp.compute.getNetworkEndpointGroup"
meta_desc: "Documentation for the gcp.compute.getNetworkEndpointGroup function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access a Network Endpoint Group's attributes.

The NEG may be found by providing either a `self_link`, or a `name` and a `zone`.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Gcp = Pulumi.Gcp;

class MyStack : Stack
{
    public MyStack()
    {
        var neg1 = Output.Create(Gcp.Compute.GetNetworkEndpointGroup.InvokeAsync(new Gcp.Compute.GetNetworkEndpointGroupArgs
        {
            Name = "k8s1-abcdef01-myns-mysvc-8080-4b6bac43",
            Zone = "us-central1-a",
        }));
        var neg2 = Output.Create(Gcp.Compute.GetNetworkEndpointGroup.InvokeAsync(new Gcp.Compute.GetNetworkEndpointGroupArgs
        {
            SelfLink = "https://www.googleapis.com/compute/v1/projects/myproject/zones/us-central1-a/networkEndpointGroups/k8s1-abcdef01-myns-mysvc-8080-4b6bac43",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-gcp/sdk/v4/go/gcp/compute"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "k8s1-abcdef01-myns-mysvc-8080-4b6bac43"
		opt1 := "us-central1-a"
		_, err := compute.LookupNetworkEndpointGroup(ctx, &compute.LookupNetworkEndpointGroupArgs{
			Name: &opt0,
			Zone: &opt1,
		}, nil)
		if err != nil {
			return err
		}
		opt2 := "https://www.googleapis.com/compute/v1/projects/myproject/zones/us-central1-a/networkEndpointGroups/k8s1-abcdef01-myns-mysvc-8080-4b6bac43"
		_, err = compute.LookupNetworkEndpointGroup(ctx, &compute.LookupNetworkEndpointGroupArgs{
			SelfLink: &opt2,
		}, nil)
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
import pulumi_gcp as gcp

neg1 = gcp.compute.get_network_endpoint_group(name="k8s1-abcdef01-myns-mysvc-8080-4b6bac43",
    zone="us-central1-a")
neg2 = gcp.compute.get_network_endpoint_group(self_link="https://www.googleapis.com/compute/v1/projects/myproject/zones/us-central1-a/networkEndpointGroups/k8s1-abcdef01-myns-mysvc-8080-4b6bac43")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const neg1 = pulumi.output(gcp.compute.getNetworkEndpointGroup({
    name: "k8s1-abcdef01-myns-mysvc-8080-4b6bac43",
    zone: "us-central1-a",
}, { async: true }));
const neg2 = pulumi.output(gcp.compute.getNetworkEndpointGroup({
    selfLink: "https://www.googleapis.com/compute/v1/projects/myproject/zones/us-central1-a/networkEndpointGroups/k8s1-abcdef01-myns-mysvc-8080-4b6bac43",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getNetworkEndpointGroup {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getNetworkEndpointGroup<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetNetworkEndpointGroupArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetNetworkEndpointGroupResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_network_endpoint_group(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">project</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">self_link</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">zone</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetNetworkEndpointGroupResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupNetworkEndpointGroup<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupNetworkEndpointGroupArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupNetworkEndpointGroupResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupNetworkEndpointGroup` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetNetworkEndpointGroup </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetNetworkEndpointGroupResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetNetworkEndpointGroupArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group name.
Provide either this or a `self_link`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project to list versions in.
If it is not provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="selflink_csharp">
<a href="#selflink_csharp" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group self\_link.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="zone_csharp">
<a href="#zone_csharp" style="color: inherit; text-decoration: inherit;">Zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group availability zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group name.
Provide either this or a `self_link`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project to list versions in.
If it is not provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="selflink_go">
<a href="#selflink_go" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group self\_link.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="zone_go">
<a href="#zone_go" style="color: inherit; text-decoration: inherit;">Zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group availability zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group name.
Provide either this or a `self_link`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project to list versions in.
If it is not provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="selflink_nodejs">
<a href="#selflink_nodejs" style="color: inherit; text-decoration: inherit;">self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group self\_link.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="zone_nodejs">
<a href="#zone_nodejs" style="color: inherit; text-decoration: inherit;">zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group availability zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group name.
Provide either this or a `self_link`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the project to list versions in.
If it is not provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="self_link_python">
<a href="#self_link_python" style="color: inherit; text-decoration: inherit;">self_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group self\_link.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="zone_python">
<a href="#zone_python" style="color: inherit; text-decoration: inherit;">zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Network Endpoint Group availability zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getNetworkEndpointGroup Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="defaultport_csharp">
<a href="#defaultport_csharp" style="color: inherit; text-decoration: inherit;">Default<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The NEG default port.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NEG description.
{{% /md %}}</dd><dt class="property-"
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
        <span id="network_csharp">
<a href="#network_csharp" style="color: inherit; text-decoration: inherit;">Network</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The network to which all network endpoints in the NEG belong.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="networkendpointtype_csharp">
<a href="#networkendpointtype_csharp" style="color: inherit; text-decoration: inherit;">Network<wbr>Endpoint<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of network endpoints in this network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_csharp">
<a href="#size_csharp" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of network endpoints in the network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetwork_csharp">
<a href="#subnetwork_csharp" style="color: inherit; text-decoration: inherit;">Subnetwork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}subnetwork to which all network endpoints in the NEG belong.
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
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="selflink_csharp">
<a href="#selflink_csharp" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zone_csharp">
<a href="#zone_csharp" style="color: inherit; text-decoration: inherit;">Zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="defaultport_go">
<a href="#defaultport_go" style="color: inherit; text-decoration: inherit;">Default<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The NEG default port.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NEG description.
{{% /md %}}</dd><dt class="property-"
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
        <span id="network_go">
<a href="#network_go" style="color: inherit; text-decoration: inherit;">Network</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The network to which all network endpoints in the NEG belong.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="networkendpointtype_go">
<a href="#networkendpointtype_go" style="color: inherit; text-decoration: inherit;">Network<wbr>Endpoint<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of network endpoints in this network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_go">
<a href="#size_go" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of network endpoints in the network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetwork_go">
<a href="#subnetwork_go" style="color: inherit; text-decoration: inherit;">Subnetwork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}subnetwork to which all network endpoints in the NEG belong.
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
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="selflink_go">
<a href="#selflink_go" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zone_go">
<a href="#zone_go" style="color: inherit; text-decoration: inherit;">Zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="defaultport_nodejs">
<a href="#defaultport_nodejs" style="color: inherit; text-decoration: inherit;">default<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The NEG default port.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The NEG description.
{{% /md %}}</dd><dt class="property-"
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
        <span id="network_nodejs">
<a href="#network_nodejs" style="color: inherit; text-decoration: inherit;">network</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The network to which all network endpoints in the NEG belong.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="networkendpointtype_nodejs">
<a href="#networkendpointtype_nodejs" style="color: inherit; text-decoration: inherit;">network<wbr>Endpoint<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of network endpoints in this network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_nodejs">
<a href="#size_nodejs" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of network endpoints in the network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetwork_nodejs">
<a href="#subnetwork_nodejs" style="color: inherit; text-decoration: inherit;">subnetwork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}subnetwork to which all network endpoints in the NEG belong.
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
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="selflink_nodejs">
<a href="#selflink_nodejs" style="color: inherit; text-decoration: inherit;">self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zone_nodejs">
<a href="#zone_nodejs" style="color: inherit; text-decoration: inherit;">zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="default_port_python">
<a href="#default_port_python" style="color: inherit; text-decoration: inherit;">default_<wbr>port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The NEG default port.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The NEG description.
{{% /md %}}</dd><dt class="property-"
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
        <span id="network_python">
<a href="#network_python" style="color: inherit; text-decoration: inherit;">network</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The network to which all network endpoints in the NEG belong.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="network_endpoint_type_python">
<a href="#network_endpoint_type_python" style="color: inherit; text-decoration: inherit;">network_<wbr>endpoint_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Type of network endpoints in this network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_python">
<a href="#size_python" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of network endpoints in the network endpoint group.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetwork_python">
<a href="#subnetwork_python" style="color: inherit; text-decoration: inherit;">subnetwork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}subnetwork to which all network endpoints in the NEG belong.
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
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="self_link_python">
<a href="#self_link_python" style="color: inherit; text-decoration: inherit;">self_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zone_python">
<a href="#zone_python" style="color: inherit; text-decoration: inherit;">zone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
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

