
---
title: "NetworkInterfaceSecurityGroupAssociation"
title_tag: "azure.network.NetworkInterfaceSecurityGroupAssociation"
meta_desc: "Documentation for the azure.network.NetworkInterfaceSecurityGroupAssociation resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Manages the association between a Network Interface and a Network Security Group.

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
        var exampleResourceGroup = new Azure.Core.ResourceGroup("exampleResourceGroup", new Azure.Core.ResourceGroupArgs
        {
            Location = "West Europe",
        });
        var exampleVirtualNetwork = new Azure.Network.VirtualNetwork("exampleVirtualNetwork", new Azure.Network.VirtualNetworkArgs
        {
            AddressSpaces = 
            {
                "10.0.0.0/16",
            },
            Location = exampleResourceGroup.Location,
            ResourceGroupName = exampleResourceGroup.Name,
        });
        var exampleSubnet = new Azure.Network.Subnet("exampleSubnet", new Azure.Network.SubnetArgs
        {
            ResourceGroupName = exampleResourceGroup.Name,
            VirtualNetworkName = exampleVirtualNetwork.Name,
            AddressPrefixes = 
            {
                "10.0.2.0/24",
            },
        });
        var exampleNetworkSecurityGroup = new Azure.Network.NetworkSecurityGroup("exampleNetworkSecurityGroup", new Azure.Network.NetworkSecurityGroupArgs
        {
            Location = exampleResourceGroup.Location,
            ResourceGroupName = exampleResourceGroup.Name,
        });
        var exampleNetworkInterface = new Azure.Network.NetworkInterface("exampleNetworkInterface", new Azure.Network.NetworkInterfaceArgs
        {
            Location = exampleResourceGroup.Location,
            ResourceGroupName = exampleResourceGroup.Name,
            IpConfigurations = 
            {
                new Azure.Network.Inputs.NetworkInterfaceIpConfigurationArgs
                {
                    Name = "testconfiguration1",
                    SubnetId = exampleSubnet.Id,
                    PrivateIpAddressAllocation = "Dynamic",
                },
            },
        });
        var exampleNetworkInterfaceSecurityGroupAssociation = new Azure.Network.NetworkInterfaceSecurityGroupAssociation("exampleNetworkInterfaceSecurityGroupAssociation", new Azure.Network.NetworkInterfaceSecurityGroupAssociationArgs
        {
            NetworkInterfaceId = exampleNetworkInterface.Id,
            NetworkSecurityGroupId = exampleNetworkSecurityGroup.Id,
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/core"
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/network"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		exampleResourceGroup, err := core.NewResourceGroup(ctx, "exampleResourceGroup", &core.ResourceGroupArgs{
			Location: pulumi.String("West Europe"),
		})
		if err != nil {
			return err
		}
		exampleVirtualNetwork, err := network.NewVirtualNetwork(ctx, "exampleVirtualNetwork", &network.VirtualNetworkArgs{
			AddressSpaces: pulumi.StringArray{
				pulumi.String("10.0.0.0/16"),
			},
			Location:          exampleResourceGroup.Location,
			ResourceGroupName: exampleResourceGroup.Name,
		})
		if err != nil {
			return err
		}
		exampleSubnet, err := network.NewSubnet(ctx, "exampleSubnet", &network.SubnetArgs{
			ResourceGroupName:  exampleResourceGroup.Name,
			VirtualNetworkName: exampleVirtualNetwork.Name,
			AddressPrefixes: pulumi.StringArray{
				pulumi.String("10.0.2.0/24"),
			},
		})
		if err != nil {
			return err
		}
		exampleNetworkSecurityGroup, err := network.NewNetworkSecurityGroup(ctx, "exampleNetworkSecurityGroup", &network.NetworkSecurityGroupArgs{
			Location:          exampleResourceGroup.Location,
			ResourceGroupName: exampleResourceGroup.Name,
		})
		if err != nil {
			return err
		}
		exampleNetworkInterface, err := network.NewNetworkInterface(ctx, "exampleNetworkInterface", &network.NetworkInterfaceArgs{
			Location:          exampleResourceGroup.Location,
			ResourceGroupName: exampleResourceGroup.Name,
			IpConfigurations: network.NetworkInterfaceIpConfigurationArray{
				&network.NetworkInterfaceIpConfigurationArgs{
					Name:                       pulumi.String("testconfiguration1"),
					SubnetId:                   exampleSubnet.ID(),
					PrivateIpAddressAllocation: pulumi.String("Dynamic"),
				},
			},
		})
		if err != nil {
			return err
		}
		_, err = network.NewNetworkInterfaceSecurityGroupAssociation(ctx, "exampleNetworkInterfaceSecurityGroupAssociation", &network.NetworkInterfaceSecurityGroupAssociationArgs{
			NetworkInterfaceId:     exampleNetworkInterface.ID(),
			NetworkSecurityGroupId: exampleNetworkSecurityGroup.ID(),
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
import pulumi_azure as azure

example_resource_group = azure.core.ResourceGroup("exampleResourceGroup", location="West Europe")
example_virtual_network = azure.network.VirtualNetwork("exampleVirtualNetwork",
    address_spaces=["10.0.0.0/16"],
    location=example_resource_group.location,
    resource_group_name=example_resource_group.name)
example_subnet = azure.network.Subnet("exampleSubnet",
    resource_group_name=example_resource_group.name,
    virtual_network_name=example_virtual_network.name,
    address_prefixes=["10.0.2.0/24"])
example_network_security_group = azure.network.NetworkSecurityGroup("exampleNetworkSecurityGroup",
    location=example_resource_group.location,
    resource_group_name=example_resource_group.name)
example_network_interface = azure.network.NetworkInterface("exampleNetworkInterface",
    location=example_resource_group.location,
    resource_group_name=example_resource_group.name,
    ip_configurations=[azure.network.NetworkInterfaceIpConfigurationArgs(
        name="testconfiguration1",
        subnet_id=example_subnet.id,
        private_ip_address_allocation="Dynamic",
    )])
example_network_interface_security_group_association = azure.network.NetworkInterfaceSecurityGroupAssociation("exampleNetworkInterfaceSecurityGroupAssociation",
    network_interface_id=example_network_interface.id,
    network_security_group_id=example_network_security_group.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const exampleResourceGroup = new azure.core.ResourceGroup("exampleResourceGroup", {location: "West Europe"});
const exampleVirtualNetwork = new azure.network.VirtualNetwork("exampleVirtualNetwork", {
    addressSpaces: ["10.0.0.0/16"],
    location: exampleResourceGroup.location,
    resourceGroupName: exampleResourceGroup.name,
});
const exampleSubnet = new azure.network.Subnet("exampleSubnet", {
    resourceGroupName: exampleResourceGroup.name,
    virtualNetworkName: exampleVirtualNetwork.name,
    addressPrefixes: ["10.0.2.0/24"],
});
const exampleNetworkSecurityGroup = new azure.network.NetworkSecurityGroup("exampleNetworkSecurityGroup", {
    location: exampleResourceGroup.location,
    resourceGroupName: exampleResourceGroup.name,
});
const exampleNetworkInterface = new azure.network.NetworkInterface("exampleNetworkInterface", {
    location: exampleResourceGroup.location,
    resourceGroupName: exampleResourceGroup.name,
    ipConfigurations: [{
        name: "testconfiguration1",
        subnetId: exampleSubnet.id,
        privateIpAddressAllocation: "Dynamic",
    }],
});
const exampleNetworkInterfaceSecurityGroupAssociation = new azure.network.NetworkInterfaceSecurityGroupAssociation("exampleNetworkInterfaceSecurityGroupAssociation", {
    networkInterfaceId: exampleNetworkInterface.id,
    networkSecurityGroupId: exampleNetworkSecurityGroup.id,
});
```


{{< /example >}}





{{% /examples %}}




## Create a NetworkInterfaceSecurityGroupAssociation Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">NetworkInterfaceSecurityGroupAssociation</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">NetworkInterfaceSecurityGroupAssociationArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">NetworkInterfaceSecurityGroupAssociation</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">network_interface_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">network_security_group_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewNetworkInterfaceSecurityGroupAssociation</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">NetworkInterfaceSecurityGroupAssociationArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">NetworkInterfaceSecurityGroupAssociation</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">NetworkInterfaceSecurityGroupAssociation</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">NetworkInterfaceSecurityGroupAssociationArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">NetworkInterfaceSecurityGroupAssociationArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

{{% choosable language python %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type">
            <a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">ResourceOptions</a>
        </span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties"><dt
        class="property-optional" title="Optional">
        <span>ctx</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span>
    </dt>
    <dd>
      Context object for the current deployment.
    </dd><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">NetworkInterfaceSecurityGroupAssociationArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">NetworkInterfaceSecurityGroupAssociationArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

## NetworkInterfaceSecurityGroupAssociation Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The NetworkInterfaceSecurityGroupAssociation resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="networkinterfaceid_csharp">
<a href="#networkinterfaceid_csharp" style="color: inherit; text-decoration: inherit;">Network<wbr>Interface<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="networksecuritygroupid_csharp">
<a href="#networksecuritygroupid_csharp" style="color: inherit; text-decoration: inherit;">Network<wbr>Security<wbr>Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="networkinterfaceid_go">
<a href="#networkinterfaceid_go" style="color: inherit; text-decoration: inherit;">Network<wbr>Interface<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="networksecuritygroupid_go">
<a href="#networksecuritygroupid_go" style="color: inherit; text-decoration: inherit;">Network<wbr>Security<wbr>Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="networkinterfaceid_nodejs">
<a href="#networkinterfaceid_nodejs" style="color: inherit; text-decoration: inherit;">network<wbr>Interface<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="networksecuritygroupid_nodejs">
<a href="#networksecuritygroupid_nodejs" style="color: inherit; text-decoration: inherit;">network<wbr>Security<wbr>Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="network_interface_id_python">
<a href="#network_interface_id_python" style="color: inherit; text-decoration: inherit;">network_<wbr>interface_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="network_security_group_id_python">
<a href="#network_security_group_id_python" style="color: inherit; text-decoration: inherit;">network_<wbr>security_<wbr>group_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the NetworkInterfaceSecurityGroupAssociation resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}



## Look up an Existing NetworkInterfaceSecurityGroupAssociation Resource {#look-up}

Get an existing NetworkInterfaceSecurityGroupAssociation resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">NetworkInterfaceSecurityGroupAssociationState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">NetworkInterfaceSecurityGroupAssociation</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">network_interface_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">network_security_group_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> NetworkInterfaceSecurityGroupAssociation</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNetworkInterfaceSecurityGroupAssociation<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">NetworkInterfaceSecurityGroupAssociationState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">NetworkInterfaceSecurityGroupAssociation</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">NetworkInterfaceSecurityGroupAssociation</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">NetworkInterfaceSecurityGroupAssociationState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Optional">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

The following state arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_networkinterfaceid_csharp">
<a href="#state_networkinterfaceid_csharp" style="color: inherit; text-decoration: inherit;">Network<wbr>Interface<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_networksecuritygroupid_csharp">
<a href="#state_networksecuritygroupid_csharp" style="color: inherit; text-decoration: inherit;">Network<wbr>Security<wbr>Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_networkinterfaceid_go">
<a href="#state_networkinterfaceid_go" style="color: inherit; text-decoration: inherit;">Network<wbr>Interface<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_networksecuritygroupid_go">
<a href="#state_networksecuritygroupid_go" style="color: inherit; text-decoration: inherit;">Network<wbr>Security<wbr>Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_networkinterfaceid_nodejs">
<a href="#state_networkinterfaceid_nodejs" style="color: inherit; text-decoration: inherit;">network<wbr>Interface<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_networksecuritygroupid_nodejs">
<a href="#state_networksecuritygroupid_nodejs" style="color: inherit; text-decoration: inherit;">network<wbr>Security<wbr>Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_network_interface_id_python">
<a href="#state_network_interface_id_python" style="color: inherit; text-decoration: inherit;">network_<wbr>interface_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_network_security_group_id_python">
<a href="#state_network_security_group_id_python" style="color: inherit; text-decoration: inherit;">network_<wbr>security_<wbr>group_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Network Security Group which should be attached to the Network Interface. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


Associations between Network Interfaces and Network Security Group can be imported using the `resource id`, e.g.

```sh
 $ pulumi import azure:network/networkInterfaceSecurityGroupAssociation:NetworkInterfaceSecurityGroupAssociation association1 "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mygroup1/providers/microsoft.network/networkInterfaces/example|/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/group1/providers/Microsoft.Network/networkSecurityGroups/group1"
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure">https://github.com/pulumi/pulumi-azure</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azurerm` Terraform Provider](https://github.com/terraform-providers/terraform-provider-azurerm).{{% /md %}}</dd>
</dl>

