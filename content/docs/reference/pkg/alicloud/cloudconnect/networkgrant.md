
---
title: "NetworkGrant"
title_tag: "alicloud.cloudconnect.NetworkGrant"
meta_desc: "Documentation for the alicloud.cloudconnect.NetworkGrant resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Provides a Cloud Connect Network Grant resource. If the CEN instance to be attached belongs to another account, authorization by the CEN instance is required.

For information about Cloud Connect Network Grant and how to use it, see [What is Cloud Connect Network Grant](https://www.alibabacloud.com/help/doc-detail/94543.htm).

> **NOTE:** Available in 1.63.0+

> **NOTE:** Only the following regions support create Cloud Connect Network Grant. [`cn-shanghai`, `cn-shanghai-finance-1`, `cn-hongkong`, `ap-southeast-1`, `ap-southeast-2`, `ap-southeast-3`, `ap-southeast-5`, `ap-northeast-1`, `eu-central-1`]

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
        var ccnAccount = new AliCloud.Provider("ccnAccount", new AliCloud.ProviderArgs
        {
        });
        var cenAccount = new AliCloud.Provider("cenAccount", new AliCloud.ProviderArgs
        {
            Region = "cn-hangzhou",
            AccessKey = "xxxxxx",
            SecretKey = "xxxxxx",
        });
        var cen = new AliCloud.Cen.Instance("cen", new AliCloud.Cen.InstanceArgs
        {
        }, new CustomResourceOptions
        {
            Provider = alicloud.Cen_account,
        });
        var ccn = new AliCloud.CloudConnect.Network("ccn", new AliCloud.CloudConnect.NetworkArgs
        {
            IsDefault = true,
        }, new CustomResourceOptions
        {
            Provider = alicloud.Ccn_account,
        });
        var @default = new AliCloud.CloudConnect.NetworkGrant("default", new AliCloud.CloudConnect.NetworkGrantArgs
        {
            CcnId = ccn.Id,
            CenId = cen.Id,
            CenUid = "xxxxxx",
        }, new CustomResourceOptions
        {
            DependsOn = 
            {
                ccn,
                cen,
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
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/cloudconnect"
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/providers"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := providers.Newalicloud(ctx, "ccnAccount", nil)
		if err != nil {
			return err
		}
		_, err = providers.Newalicloud(ctx, "cenAccount", &providers.alicloudArgs{
			Region:    pulumi.String("cn-hangzhou"),
			AccessKey: pulumi.String("xxxxxx"),
			SecretKey: pulumi.String("xxxxxx"),
		})
		if err != nil {
			return err
		}
		cen, err := cen.NewInstance(ctx, "cen", nil, pulumi.Provider(alicloud.Cen_account))
		if err != nil {
			return err
		}
		ccn, err := cloudconnect.NewNetwork(ctx, "ccn", &cloudconnect.NetworkArgs{
			IsDefault: pulumi.Bool(true),
		}, pulumi.Provider(alicloud.Ccn_account))
		if err != nil {
			return err
		}
		_, err = cloudconnect.NewNetworkGrant(ctx, "_default", &cloudconnect.NetworkGrantArgs{
			CcnId:  ccn.ID(),
			CenId:  cen.ID(),
			CenUid: pulumi.String("xxxxxx"),
		}, pulumi.DependsOn([]pulumi.Resource{
			ccn,
			cen,
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

ccn_account = pulumi.providers.Alicloud("ccnAccount")
cen_account = pulumi.providers.Alicloud("cenAccount",
    region="cn-hangzhou",
    access_key="xxxxxx",
    secret_key="xxxxxx")
cen = alicloud.cen.Instance("cen", opts=pulumi.ResourceOptions(provider=alicloud["cen_account"]))
ccn = alicloud.cloudconnect.Network("ccn", is_default=True,
opts=pulumi.ResourceOptions(provider=alicloud["ccn_account"]))
default = alicloud.cloudconnect.NetworkGrant("default",
    ccn_id=ccn.id,
    cen_id=cen.id,
    cen_uid="xxxxxx",
    opts=pulumi.ResourceOptions(depends_on=[
            ccn,
            cen,
        ]))
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const ccnAccount = new alicloud.Provider("ccnAccount", {});
const cenAccount = new alicloud.Provider("cenAccount", {
    region: "cn-hangzhou",
    accessKey: "xxxxxx",
    secretKey: "xxxxxx",
});
const cen = new alicloud.cen.Instance("cen", {}, {
    provider: alicloud.cen_account,
});
const ccn = new alicloud.cloudconnect.Network("ccn", {isDefault: "true"}, {
    provider: alicloud.ccn_account,
});
const _default = new alicloud.cloudconnect.NetworkGrant("default", {
    ccnId: ccn.id,
    cenId: cen.id,
    cenUid: "xxxxxx",
}, {
    dependsOn: [
        ccn,
        cen,
    ],
});
```


{{< /example >}}





{{% /examples %}}




## Create a NetworkGrant Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">NetworkGrant</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">NetworkGrantArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">NetworkGrant</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">ccn_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">cen_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">cen_uid</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewNetworkGrant</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">NetworkGrantArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">NetworkGrant</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">NetworkGrant</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">NetworkGrantArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">NetworkGrantArgs</a></span>
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
        <span class="property-type"><a href="#inputs">NetworkGrantArgs</a></span>
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
        <span class="property-type"><a href="#inputs">NetworkGrantArgs</a></span>
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

## NetworkGrant Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The NetworkGrant resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ccnid_csharp">
<a href="#ccnid_csharp" style="color: inherit; text-decoration: inherit;">Ccn<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenid_csharp">
<a href="#cenid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenuid_csharp">
<a href="#cenuid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ccnid_go">
<a href="#ccnid_go" style="color: inherit; text-decoration: inherit;">Ccn<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenid_go">
<a href="#cenid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenuid_go">
<a href="#cenuid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ccnid_nodejs">
<a href="#ccnid_nodejs" style="color: inherit; text-decoration: inherit;">ccn<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenid_nodejs">
<a href="#cenid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cenuid_nodejs">
<a href="#cenuid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ccn_id_python">
<a href="#ccn_id_python" style="color: inherit; text-decoration: inherit;">ccn_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cen_id_python">
<a href="#cen_id_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="cen_uid_python">
<a href="#cen_uid_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the NetworkGrant resource produces the following output properties:



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



## Look up an Existing NetworkGrant Resource {#look-up}

Get an existing NetworkGrant resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">NetworkGrantState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">NetworkGrant</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">ccn_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">cen_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">cen_uid</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> NetworkGrant</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNetworkGrant<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">NetworkGrantState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">NetworkGrant</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">NetworkGrant</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">NetworkGrantState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_ccnid_csharp">
<a href="#state_ccnid_csharp" style="color: inherit; text-decoration: inherit;">Ccn<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenid_csharp">
<a href="#state_cenid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenuid_csharp">
<a href="#state_cenuid_csharp" style="color: inherit; text-decoration: inherit;">Cen<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_ccnid_go">
<a href="#state_ccnid_go" style="color: inherit; text-decoration: inherit;">Ccn<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenid_go">
<a href="#state_cenid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenuid_go">
<a href="#state_cenuid_go" style="color: inherit; text-decoration: inherit;">Cen<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_ccnid_nodejs">
<a href="#state_ccnid_nodejs" style="color: inherit; text-decoration: inherit;">ccn<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenid_nodejs">
<a href="#state_cenid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cenuid_nodejs">
<a href="#state_cenuid_nodejs" style="color: inherit; text-decoration: inherit;">cen<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_ccn_id_python">
<a href="#state_ccn_id_python" style="color: inherit; text-decoration: inherit;">ccn_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the CCN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cen_id_python">
<a href="#state_cen_id_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the CEN instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_cen_uid_python">
<a href="#state_cen_uid_python" style="color: inherit; text-decoration: inherit;">cen_<wbr>uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the account to which the CEN instance belongs.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


The Cloud Connect Network Grant can be imported using the instance_id, e.g.

```sh
 $ pulumi import alicloud:cloudconnect/networkGrant:NetworkGrant example ccn-abc123456:cen-abc123456
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

