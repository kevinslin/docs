
---
title: "InstanceGrant"
title_tag: "alicloud.cen.InstanceGrant"
meta_desc: "Documentation for the alicloud.cen.InstanceGrant resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Provides a CEN child instance grant resource, which allow you to authorize a VPC or VBR to a CEN of a different account.

For more information about how to use it, see [Attach a network in a different account](https://www.alibabacloud.com/help/doc-detail/73645.htm).

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
        // Create a new instance-grant and use it to grant one child instance of account1 to a new CEN of account 2.
        var account1 = new AliCloud.Provider("account1", new AliCloud.ProviderArgs
        {
            AccessKey = "access123",
            SecretKey = "secret123",
        });
        var account2 = new AliCloud.Provider("account2", new AliCloud.ProviderArgs
        {
            AccessKey = "access456",
            SecretKey = "secret456",
        });
        var config = new Config();
        var name = config.Get("name") ?? "tf-testAccCenInstanceGrantBasic";
        var cen = new AliCloud.Cen.Instance("cen", new AliCloud.Cen.InstanceArgs
        {
        }, new CustomResourceOptions
        {
            Provider = alicloud.Account2,
        });
        var vpc = new AliCloud.Vpc.Network("vpc", new AliCloud.Vpc.NetworkArgs
        {
            CidrBlock = "192.168.0.0/16",
        }, new CustomResourceOptions
        {
            Provider = alicloud.Account1,
        });
        var fooInstanceGrant = new AliCloud.Cen.InstanceGrant("fooInstanceGrant", new AliCloud.Cen.InstanceGrantArgs
        {
            CenId = cen.Id,
            ChildInstanceId = vpc.Id,
            CenOwnerId = "uid2",
        }, new CustomResourceOptions
        {
            Provider = alicloud.Account1,
        });
        var fooInstanceAttachment = new AliCloud.Cen.InstanceAttachment("fooInstanceAttachment", new AliCloud.Cen.InstanceAttachmentArgs
        {
            InstanceId = cen.Id,
            ChildInstanceId = vpc.Id,
            ChildInstanceType = "VPC",
            ChildInstanceRegionId = "cn-qingdao",
            ChildInstanceOwnerId = "uid1",
        }, new CustomResourceOptions
        {
            Provider = alicloud.Account2,
            DependsOn = 
            {
                fooInstanceGrant,
            },
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/cen"
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/providers"
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/vpc"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi/config"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := providers.Newalicloud(ctx, "account1", &providers.alicloudArgs{
			AccessKey: pulumi.String("access123"),
			SecretKey: pulumi.String("secret123"),
		})
		if err != nil {
			return err
		}
		_, err = providers.Newalicloud(ctx, "account2", &providers.alicloudArgs{
			AccessKey: pulumi.String("access456"),
			SecretKey: pulumi.String("secret456"),
		})
		if err != nil {
			return err
		}
		cfg := config.New(ctx, "")
		name := "tf-testAccCenInstanceGrantBasic"
		if param := cfg.Get("name"); param != "" {
			name = param
		}
		cen, err := cen.NewInstance(ctx, "cen", nil, pulumi.Provider(alicloud.Account2))
		if err != nil {
			return err
		}
		vpc, err := vpc.NewNetwork(ctx, "vpc", &vpc.NetworkArgs{
			CidrBlock: pulumi.String("192.168.0.0/16"),
		}, pulumi.Provider(alicloud.Account1))
		if err != nil {
			return err
		}
		fooInstanceGrant, err := cen.NewInstanceGrant(ctx, "fooInstanceGrant", &cen.InstanceGrantArgs{
			CenId:           cen.ID(),
			ChildInstanceId: vpc.ID(),
			CenOwnerId:      pulumi.String("uid2"),
		}, pulumi.Provider(alicloud.Account1))
		if err != nil {
			return err
		}
		_, err = cen.NewInstanceAttachment(ctx, "fooInstanceAttachment", &cen.InstanceAttachmentArgs{
			InstanceId:            cen.ID(),
			ChildInstanceId:       vpc.ID(),
			ChildInstanceType:     pulumi.String("VPC"),
			ChildInstanceRegionId: pulumi.String("cn-qingdao"),
			ChildInstanceOwnerId:  pulumi.Int("uid1"),
		}, pulumi.Provider(alicloud.Account2), pulumi.DependsOn([]pulumi.Resource{
			fooInstanceGrant,
		}))
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
import pulumi_alicloud as alicloud
import pulumi_pulumi as pulumi

# Create a new instance-grant and use it to grant one child instance of account1 to a new CEN of account 2.
account1 = pulumi.providers.Alicloud("account1",
    access_key="access123",
    secret_key="secret123")
account2 = pulumi.providers.Alicloud("account2",
    access_key="access456",
    secret_key="secret456")
config = pulumi.Config()
name = config.get("name")
if name is None:
    name = "tf-testAccCenInstanceGrantBasic"
cen = alicloud.cen.Instance("cen", opts=pulumi.ResourceOptions(provider=alicloud["account2"]))
vpc = alicloud.vpc.Network("vpc", cidr_block="192.168.0.0/16",
opts=pulumi.ResourceOptions(provider=alicloud["account1"]))
foo_instance_grant = alicloud.cen.InstanceGrant("fooInstanceGrant",
    cen_id=cen.id,
    child_instance_id=vpc.id,
    cen_owner_id="uid2",
    opts=pulumi.ResourceOptions(provider=alicloud["account1"]))
foo_instance_attachment = alicloud.cen.InstanceAttachment("fooInstanceAttachment",
    instance_id=cen.id,
    child_instance_id=vpc.id,
    child_instance_type="VPC",
    child_instance_region_id="cn-qingdao",
    child_instance_owner_id="uid1",
    opts=pulumi.ResourceOptions(provider=alicloud["account2"],
        depends_on=[foo_instance_grant]))
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

// Create a new instance-grant and use it to grant one child instance of account1 to a new CEN of account 2.
const account1 = new alicloud.Provider("account1", {
    accessKey: "access123",
    secretKey: "secret123",
});
const account2 = new alicloud.Provider("account2", {
    accessKey: "access456",
    secretKey: "secret456",
});
const config = new pulumi.Config();
const name = config.get("name") || "tf-testAccCenInstanceGrantBasic";
const cen = new alicloud.cen.Instance("cen", {}, {
    provider: alicloud.account2,
});
const vpc = new alicloud.vpc.Network("vpc", {cidrBlock: "192.168.0.0/16"}, {
    provider: alicloud.account1,
});
const fooInstanceGrant = new alicloud.cen.InstanceGrant("fooInstanceGrant", {
    cenId: cen.id,
    childInstanceId: vpc.id,
    cenOwnerId: "uid2",
}, {
    provider: alicloud.account1,
});
const fooInstanceAttachment = new alicloud.cen.InstanceAttachment("fooInstanceAttachment", {
    instanceId: cen.id,
    childInstanceId: vpc.id,
    childInstanceType: "VPC",
    childInstanceRegionId: "cn-qingdao",
    childInstanceOwnerId: "uid1",
}, {
    provider: alicloud.account2,
    dependsOn: [fooInstanceGrant],
});
```


{{< /example >}}





{{% /examples %}}




## Create a InstanceGrant Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">InstanceGrant</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">InstanceGrantArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">InstanceGrant</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">cen_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">cen_owner_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">child_instance_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewInstanceGrant</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">InstanceGrantArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">InstanceGrant</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">InstanceGrant</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">InstanceGrantArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">InstanceGrantArgs</a></span>
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
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span>
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
        <span class="property-type"><a href="#inputs">InstanceGrantArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
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
        <span class="property-type"><a href="#inputs">InstanceGrantArgs</a></span>
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

## InstanceGrant Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The InstanceGrant resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cenid_csharp">
<a href="#cenid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenownerid_csharp">
<a href="#cenownerid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="childinstanceid_csharp">
<a href="#childinstanceid_csharp" style="color: inherit; text-decoration: inherit;">Child<wbr>Instance<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cenid_go">
<a href="#cenid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenownerid_go">
<a href="#cenownerid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="childinstanceid_go">
<a href="#childinstanceid_go" style="color: inherit; text-decoration: inherit;">Child<wbr>Instance<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cenid_nodejs">
<a href="#cenid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenownerid_nodejs">
<a href="#cenownerid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="childinstanceid_nodejs">
<a href="#childinstanceid_nodejs" style="color: inherit; text-decoration: inherit;">child<wbr>Instance<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cen_id_python">
<a href="#cen_id_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cen_owner_id_python">
<a href="#cen_owner_id_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>owner_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="child_instance_id_python">
<a href="#child_instance_id_python" style="color: inherit; text-decoration: inherit;">child_<wbr>instance_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the InstanceGrant resource produces the following output properties:



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



## Look up an Existing InstanceGrant Resource {#look-up}

Get an existing InstanceGrant resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">InstanceGrantState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">InstanceGrant</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">cen_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">cen_owner_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">child_instance_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> InstanceGrant</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetInstanceGrant<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">InstanceGrantState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">InstanceGrant</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">InstanceGrant</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">InstanceGrantState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_cenid_csharp">
<a href="#state_cenid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenownerid_csharp">
<a href="#state_cenownerid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_childinstanceid_csharp">
<a href="#state_childinstanceid_csharp" style="color: inherit; text-decoration: inherit;">Child<wbr>Instance<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_cenid_go">
<a href="#state_cenid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenownerid_go">
<a href="#state_cenownerid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_childinstanceid_go">
<a href="#state_childinstanceid_go" style="color: inherit; text-decoration: inherit;">Child<wbr>Instance<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_cenid_nodejs">
<a href="#state_cenid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenownerid_nodejs">
<a href="#state_cenownerid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_childinstanceid_nodejs">
<a href="#state_childinstanceid_nodejs" style="color: inherit; text-decoration: inherit;">child<wbr>Instance<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_cen_id_python">
<a href="#state_cen_id_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cen_owner_id_python">
<a href="#state_cen_owner_id_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>owner_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The owner UID of the  CEN which the child instance granted to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_child_instance_id_python">
<a href="#state_child_instance_id_python" style="color: inherit; text-decoration: inherit;">child_<wbr>instance_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the child instance to grant.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


CEN instance can be imported using the id, e.g.

```sh
 $ pulumi import alicloud:cen/instanceGrant:InstanceGrant example cen-abc123456:vpc-abc123456:uid123456
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-alicloud">https://github.com/pulumi/pulumi-alicloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`alicloud` Terraform Provider](https://github.com/aliyun/terraform-provider-alicloud).{{% /md %}}</dd>
</dl>

