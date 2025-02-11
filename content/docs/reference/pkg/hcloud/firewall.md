
---
title: "Firewall"
title_tag: "hcloud.Firewall"
meta_desc: "Documentation for the hcloud.Firewall resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Provides a Hetzner Cloud Firewall to represent a Load Balancer in the Hetzner Cloud.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using HCloud = Pulumi.HCloud;

class MyStack : Stack
{
    public MyStack()
    {
        var myfirewall = new HCloud.Firewall("myfirewall", new HCloud.FirewallArgs
        {
            Rules = 
            {
                new HCloud.Inputs.FirewallRuleArgs
                {
                    Direction = "in",
                    Protocol = "icmp",
                    SourceIps = 
                    {
                        "0.0.0.0/0",
                        "::/0",
                    },
                },
            },
        });
        var node1 = new HCloud.Server("node1", new HCloud.ServerArgs
        {
            Image = "debian-9",
            ServerType = "cx11",
            FirewallIds = 
            {
                myfirewall.Id,
            },
        });
    }

}
```


{{< /example >}}


{{< example go >}}

Coming soon!

{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_hcloud as hcloud

myfirewall = hcloud.Firewall("myfirewall", rules=[hcloud.FirewallRuleArgs(
    direction="in",
    protocol="icmp",
    source_ips=[
        "0.0.0.0/0",
        "::/0",
    ],
)])
node1 = hcloud.Server("node1",
    image="debian-9",
    server_type="cx11",
    firewall_ids=[myfirewall.id])
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as hcloud from "@pulumi/hcloud";

const myfirewall = new hcloud.Firewall("myfirewall", {rules: [{
    direction: "in",
    protocol: "icmp",
    sourceIps: [
        "0.0.0.0/0",
        "::/0",
    ],
}]});
const node1 = new hcloud.Server("node1", {
    image: "debian-9",
    serverType: "cx11",
    firewallIds: [myfirewall.id],
});
```


{{< /example >}}





{{% /examples %}}




## Create a Firewall Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">Firewall</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">?:</span> <span class="nx"><a href="#inputs">FirewallArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">Firewall</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">labels</span><span class="p">:</span> <span class="nx">Optional[Mapping[str, Any]]</span> = None<span class="p">, </span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">rules</span><span class="p">:</span> <span class="nx">Optional[Sequence[FirewallRuleArgs]]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewFirewall</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx"><a href="#inputs">FirewallArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Firewall</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">Firewall</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">FirewallArgs</a></span><span class="p">? </span><span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        class="property-optional" title="Optional">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">FirewallArgs</a></span>
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
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span>
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
        class="property-optional" title="Optional">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">FirewallArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
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
        class="property-optional" title="Optional">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">FirewallArgs</a></span>
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

## Firewall Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The Firewall resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="labels_csharp">
<a href="#labels_csharp" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="rules_csharp">
<a href="#rules_csharp" style="color: inherit; text-decoration: inherit;">Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">List&lt;Pulumi.<wbr>HCloud.<wbr>Inputs.<wbr>Firewall<wbr>Rule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="labels_go">
<a href="#labels_go" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="rules_go">
<a href="#rules_go" style="color: inherit; text-decoration: inherit;">Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">[]Firewall<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="labels_nodejs">
<a href="#labels_nodejs" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="rules_nodejs">
<a href="#rules_nodejs" style="color: inherit; text-decoration: inherit;">rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">Firewall<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="labels_python">
<a href="#labels_python" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="rules_python">
<a href="#rules_python" style="color: inherit; text-decoration: inherit;">rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">Sequence[Firewall<wbr>Rule<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the Firewall resource produces the following output properties:



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



## Look up an Existing Firewall Resource {#look-up}

Get an existing Firewall resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">FirewallState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">Firewall</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">labels</span><span class="p">:</span> <span class="nx">Optional[Mapping[str, Any]]</span> = None<span class="p">, </span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">rules</span><span class="p">:</span> <span class="nx">Optional[Sequence[FirewallRuleArgs]]</span> = None<span class="p">) -&gt;</span> Firewall</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFirewall<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">FirewallState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Firewall</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">Firewall</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">FirewallState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_labels_csharp">
<a href="#state_labels_csharp" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_csharp">
<a href="#state_name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_rules_csharp">
<a href="#state_rules_csharp" style="color: inherit; text-decoration: inherit;">Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">List&lt;Pulumi.<wbr>HCloud.<wbr>Inputs.<wbr>Firewall<wbr>Rule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_labels_go">
<a href="#state_labels_go" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_go">
<a href="#state_name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_rules_go">
<a href="#state_rules_go" style="color: inherit; text-decoration: inherit;">Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">[]Firewall<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_labels_nodejs">
<a href="#state_labels_nodejs" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_nodejs">
<a href="#state_name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_rules_nodejs">
<a href="#state_rules_nodejs" style="color: inherit; text-decoration: inherit;">rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">Firewall<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_labels_python">
<a href="#state_labels_python" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}User-defined labels (key-value pairs) should be created with.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_python">
<a href="#state_name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Firewall.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_rules_python">
<a href="#state_rules_python" style="color: inherit; text-decoration: inherit;">rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#firewallrule">Sequence[Firewall<wbr>Rule<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of a Rule from this Firewall.
{{% /md %}}</dd></dl>
{{% /choosable %}}






## Supporting Types



<h4 id="firewallrule">Firewall<wbr>Rule</h4>

{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="direction_csharp">
<a href="#direction_csharp" style="color: inherit; text-decoration: inherit;">Direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direction of the Firewall Rule. `in`
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="protocol_csharp">
<a href="#protocol_csharp" style="color: inherit; text-decoration: inherit;">Protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Protocol of the Firewall Rule. `tcp`, `icmp`, `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="destinationips_csharp">
<a href="#destinationips_csharp" style="color: inherit; text-decoration: inherit;">Destination<wbr>Ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="port_csharp">
<a href="#port_csharp" style="color: inherit; text-decoration: inherit;">Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Port of the Firewall Rule. Required when `protocol` is `tcp` or `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sourceips_csharp">
<a href="#sourceips_csharp" style="color: inherit; text-decoration: inherit;">Source<wbr>Ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}List of CIDRs that are allowed within this Firewall Rule
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="direction_go">
<a href="#direction_go" style="color: inherit; text-decoration: inherit;">Direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direction of the Firewall Rule. `in`
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="protocol_go">
<a href="#protocol_go" style="color: inherit; text-decoration: inherit;">Protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Protocol of the Firewall Rule. `tcp`, `icmp`, `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="destinationips_go">
<a href="#destinationips_go" style="color: inherit; text-decoration: inherit;">Destination<wbr>Ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="port_go">
<a href="#port_go" style="color: inherit; text-decoration: inherit;">Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Port of the Firewall Rule. Required when `protocol` is `tcp` or `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sourceips_go">
<a href="#sourceips_go" style="color: inherit; text-decoration: inherit;">Source<wbr>Ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of CIDRs that are allowed within this Firewall Rule
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="direction_nodejs">
<a href="#direction_nodejs" style="color: inherit; text-decoration: inherit;">direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direction of the Firewall Rule. `in`
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="protocol_nodejs">
<a href="#protocol_nodejs" style="color: inherit; text-decoration: inherit;">protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Protocol of the Firewall Rule. `tcp`, `icmp`, `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="destinationips_nodejs">
<a href="#destinationips_nodejs" style="color: inherit; text-decoration: inherit;">destination<wbr>Ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="port_nodejs">
<a href="#port_nodejs" style="color: inherit; text-decoration: inherit;">port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Port of the Firewall Rule. Required when `protocol` is `tcp` or `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="sourceips_nodejs">
<a href="#sourceips_nodejs" style="color: inherit; text-decoration: inherit;">source<wbr>Ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of CIDRs that are allowed within this Firewall Rule
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="direction_python">
<a href="#direction_python" style="color: inherit; text-decoration: inherit;">direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Direction of the Firewall Rule. `in`
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="protocol_python">
<a href="#protocol_python" style="color: inherit; text-decoration: inherit;">protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Protocol of the Firewall Rule. `tcp`, `icmp`, `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="destination_ips_python">
<a href="#destination_ips_python" style="color: inherit; text-decoration: inherit;">destination_<wbr>ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="port_python">
<a href="#port_python" style="color: inherit; text-decoration: inherit;">port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Port of the Firewall Rule. Required when `protocol` is `tcp` or `udp`
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="source_ips_python">
<a href="#source_ips_python" style="color: inherit; text-decoration: inherit;">source_<wbr>ips</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}List of CIDRs that are allowed within this Firewall Rule
{{% /md %}}</dd></dl>
{{% /choosable %}}
## Import


Firewalls can be imported using its `id`

```sh
 $ pulumi import hcloud:index/firewall:Firewall myfw <id>
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-hcloud">https://github.com/pulumi/pulumi-hcloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`hcloud` Terraform Provider](https://github.com/hetznercloud/terraform-provider-hcloud).{{% /md %}}</dd>
</dl>

