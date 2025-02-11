
---
title: "getVpcAttachment"
title_tag: "aws.ec2transitgateway.getVpcAttachment"
meta_desc: "Documentation for the aws.ec2transitgateway.getVpcAttachment function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Get information on an EC2 Transit Gateway VPC Attachment.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### By Filter


{{< example csharp >}}

```csharp
using Pulumi;
using Aws = Pulumi.Aws;

class MyStack : Stack
{
    public MyStack()
    {
        var example = Output.Create(Aws.Ec2TransitGateway.GetVpcAttachment.InvokeAsync(new Aws.Ec2TransitGateway.GetVpcAttachmentArgs
        {
            Filters = 
            {
                new Aws.Ec2TransitGateway.Inputs.GetVpcAttachmentFilterArgs
                {
                    Name = "vpc-id",
                    Values = 
                    {
                        "vpc-12345678",
                    },
                },
            },
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-aws/sdk/v3/go/aws/ec2transitgateway"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := ec2transitgateway.LookupVpcAttachment(ctx, &ec2transitgateway.LookupVpcAttachmentArgs{
			Filters: []ec2transitgateway.GetVpcAttachmentFilter{
				ec2transitgateway.GetVpcAttachmentFilter{
					Name: "vpc-id",
					Values: []string{
						"vpc-12345678",
					},
				},
			},
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
import pulumi_aws as aws

example = aws.ec2transitgateway.get_vpc_attachment(filters=[aws.ec2transitgateway.GetVpcAttachmentFilterArgs(
    name="vpc-id",
    values=["vpc-12345678"],
)])
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = pulumi.output(aws.ec2transitgateway.getVpcAttachment({
    filters: [{
        name: "vpc-id",
        values: ["vpc-12345678"],
    }],
}, { async: true }));
```


{{< /example >}}




### By Identifier


{{< example csharp >}}

```csharp
using Pulumi;
using Aws = Pulumi.Aws;

class MyStack : Stack
{
    public MyStack()
    {
        var example = Output.Create(Aws.Ec2TransitGateway.GetVpcAttachment.InvokeAsync(new Aws.Ec2TransitGateway.GetVpcAttachmentArgs
        {
            Id = "tgw-attach-12345678",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-aws/sdk/v3/go/aws/ec2transitgateway"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "tgw-attach-12345678"
		_, err := ec2transitgateway.LookupVpcAttachment(ctx, &ec2transitgateway.LookupVpcAttachmentArgs{
			Id: &opt0,
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
import pulumi_aws as aws

example = aws.ec2transitgateway.get_vpc_attachment(id="tgw-attach-12345678")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = pulumi.output(aws.ec2transitgateway.getVpcAttachment({
    id: "tgw-attach-12345678",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getVpcAttachment {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getVpcAttachment<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetVpcAttachmentArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetVpcAttachmentResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_vpc_attachment(</span><span class="nx">filters</span><span class="p">:</span> <span class="nx">Optional[Sequence[GetVpcAttachmentFilterArgs]]</span> = None<span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">tags</span><span class="p">:</span> <span class="nx">Optional[Mapping[str, str]]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetVpcAttachmentResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupVpcAttachment<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupVpcAttachmentArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupVpcAttachmentResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupVpcAttachment` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetVpcAttachment </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetVpcAttachmentResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetVpcAttachmentArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="filters_csharp">
<a href="#filters_csharp" style="color: inherit; text-decoration: inherit;">Filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">List&lt;Get<wbr>Vpc<wbr>Attachment<wbr>Filter<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks containing name-values filters. Detailed below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="filters_go">
<a href="#filters_go" style="color: inherit; text-decoration: inherit;">Filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">[]Get<wbr>Vpc<wbr>Attachment<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks containing name-values filters. Detailed below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="filters_nodejs">
<a href="#filters_nodejs" style="color: inherit; text-decoration: inherit;">filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">Get<wbr>Vpc<wbr>Attachment<wbr>Filter[]</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks containing name-values filters. Detailed below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="filters_python">
<a href="#filters_python" style="color: inherit; text-decoration: inherit;">filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">Sequence[Get<wbr>Vpc<wbr>Attachment<wbr>Filter<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks containing name-values filters. Detailed below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getVpcAttachment Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appliancemodesupport_csharp">
<a href="#appliancemodesupport_csharp" style="color: inherit; text-decoration: inherit;">Appliance<wbr>Mode<wbr>Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether Appliance Mode support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dnssupport_csharp">
<a href="#dnssupport_csharp" style="color: inherit; text-decoration: inherit;">Dns<wbr>Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway VPC Attachment identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ipv6support_csharp">
<a href="#ipv6support_csharp" style="color: inherit; text-decoration: inherit;">Ipv6Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetids_csharp">
<a href="#subnetids_csharp" style="color: inherit; text-decoration: inherit;">Subnet<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="transitgatewayid_csharp">
<a href="#transitgatewayid_csharp" style="color: inherit; text-decoration: inherit;">Transit<wbr>Gateway<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpcid_csharp">
<a href="#vpcid_csharp" style="color: inherit; text-decoration: inherit;">Vpc<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpcownerid_csharp">
<a href="#vpcownerid_csharp" style="color: inherit; text-decoration: inherit;">Vpc<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filters_csharp">
<a href="#filters_csharp" style="color: inherit; text-decoration: inherit;">Filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">List&lt;Get<wbr>Vpc<wbr>Attachment<wbr>Filter&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appliancemodesupport_go">
<a href="#appliancemodesupport_go" style="color: inherit; text-decoration: inherit;">Appliance<wbr>Mode<wbr>Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether Appliance Mode support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dnssupport_go">
<a href="#dnssupport_go" style="color: inherit; text-decoration: inherit;">Dns<wbr>Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway VPC Attachment identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ipv6support_go">
<a href="#ipv6support_go" style="color: inherit; text-decoration: inherit;">Ipv6Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetids_go">
<a href="#subnetids_go" style="color: inherit; text-decoration: inherit;">Subnet<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="transitgatewayid_go">
<a href="#transitgatewayid_go" style="color: inherit; text-decoration: inherit;">Transit<wbr>Gateway<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpcid_go">
<a href="#vpcid_go" style="color: inherit; text-decoration: inherit;">Vpc<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpcownerid_go">
<a href="#vpcownerid_go" style="color: inherit; text-decoration: inherit;">Vpc<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filters_go">
<a href="#filters_go" style="color: inherit; text-decoration: inherit;">Filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">[]Get<wbr>Vpc<wbr>Attachment<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appliancemodesupport_nodejs">
<a href="#appliancemodesupport_nodejs" style="color: inherit; text-decoration: inherit;">appliance<wbr>Mode<wbr>Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether Appliance Mode support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dnssupport_nodejs">
<a href="#dnssupport_nodejs" style="color: inherit; text-decoration: inherit;">dns<wbr>Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway VPC Attachment identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ipv6support_nodejs">
<a href="#ipv6support_nodejs" style="color: inherit; text-decoration: inherit;">ipv6Support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnetids_nodejs">
<a href="#subnetids_nodejs" style="color: inherit; text-decoration: inherit;">subnet<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="transitgatewayid_nodejs">
<a href="#transitgatewayid_nodejs" style="color: inherit; text-decoration: inherit;">transit<wbr>Gateway<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpcid_nodejs">
<a href="#vpcid_nodejs" style="color: inherit; text-decoration: inherit;">vpc<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpcownerid_nodejs">
<a href="#vpcownerid_nodejs" style="color: inherit; text-decoration: inherit;">vpc<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filters_nodejs">
<a href="#filters_nodejs" style="color: inherit; text-decoration: inherit;">filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">Get<wbr>Vpc<wbr>Attachment<wbr>Filter[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appliance_mode_support_python">
<a href="#appliance_mode_support_python" style="color: inherit; text-decoration: inherit;">appliance_<wbr>mode_<wbr>support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether Appliance Mode support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dns_support_python">
<a href="#dns_support_python" style="color: inherit; text-decoration: inherit;">dns_<wbr>support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway VPC Attachment identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ipv6_support_python">
<a href="#ipv6_support_python" style="color: inherit; text-decoration: inherit;">ipv6_<wbr>support</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subnet_ids_python">
<a href="#subnet_ids_python" style="color: inherit; text-decoration: inherit;">subnet_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="transit_gateway_id_python">
<a href="#transit_gateway_id_python" style="color: inherit; text-decoration: inherit;">transit_<wbr>gateway_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}EC2 Transit Gateway identifier
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpc_id_python">
<a href="#vpc_id_python" style="color: inherit; text-decoration: inherit;">vpc_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="vpc_owner_id_python">
<a href="#vpc_owner_id_python" style="color: inherit; text-decoration: inherit;">vpc_<wbr>owner_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filters_python">
<a href="#filters_python" style="color: inherit; text-decoration: inherit;">filters</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getvpcattachmentfilter">Sequence[Get<wbr>Vpc<wbr>Attachment<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getvpcattachmentfilter">Get<wbr>Vpc<wbr>Attachment<wbr>Filter</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the filter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="values_csharp">
<a href="#values_csharp" style="color: inherit; text-decoration: inherit;">Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}List of one or more values for the filter.
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
    <dd>{{% md %}}Name of the filter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="values_go">
<a href="#values_go" style="color: inherit; text-decoration: inherit;">Values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of one or more values for the filter.
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
    <dd>{{% md %}}Name of the filter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="values_nodejs">
<a href="#values_nodejs" style="color: inherit; text-decoration: inherit;">values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of one or more values for the filter.
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
    <dd>{{% md %}}Name of the filter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="values_python">
<a href="#values_python" style="color: inherit; text-decoration: inherit;">values</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}List of one or more values for the filter.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-aws">https://github.com/pulumi/pulumi-aws</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`aws` Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws).{{% /md %}}</dd>
</dl>

