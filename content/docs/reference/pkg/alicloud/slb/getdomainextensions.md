
---
title: "getDomainExtensions"
title_tag: "alicloud.slb.getDomainExtensions"
meta_desc: "Documentation for the alicloud.slb.getDomainExtensions function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source provides the domain extensions associated with a server load balancer listener.

> **NOTE:** Available in 1.60.0+


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
        var foo = Output.Create(AliCloud.Slb.GetDomainExtensions.InvokeAsync(new AliCloud.Slb.GetDomainExtensionsArgs
        {
            FrontendPort = "fake-port",
            Ids = 
            {
                "fake-de-id",
            },
            LoadBalancerId = "fake-lb-id",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/slb"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := slb.GetDomainExtensions(ctx, &slb.GetDomainExtensionsArgs{
			FrontendPort: "fake-port",
			Ids: []string{
				"fake-de-id",
			},
			LoadBalancerId: "fake-lb-id",
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
import pulumi_alicloud as alicloud

foo = alicloud.slb.get_domain_extensions(frontend_port="fake-port",
    ids=["fake-de-id"],
    load_balancer_id="fake-lb-id")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const foo = pulumi.output(alicloud.slb.getDomainExtensions({
    frontendPort: Number.parseFloat("fake-port"),
    ids: ["fake-de-id"],
    loadBalancerId: "fake-lb-id",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getDomainExtensions {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getDomainExtensions<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetDomainExtensionsArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetDomainExtensionsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_domain_extensions(</span><span class="nx">frontend_port</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">, </span><span class="nx">ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">, </span><span class="nx">load_balancer_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">output_file</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetDomainExtensionsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDomainExtensions<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetDomainExtensionsArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetDomainExtensionsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetDomainExtensions` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetDomainExtensions </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetDomainExtensionsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetDomainExtensionsArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="frontendport_csharp">
<a href="#frontendport_csharp" style="color: inherit; text-decoration: inherit;">Frontend<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The frontend port used by the HTTPS listener of the SLB instance. Valid values: 1–65535.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="loadbalancerid_csharp">
<a href="#loadbalancerid_csharp" style="color: inherit; text-decoration: inherit;">Load<wbr>Balancer<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SLB instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}IDs of the SLB domain extensions.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="frontendport_go">
<a href="#frontendport_go" style="color: inherit; text-decoration: inherit;">Frontend<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The frontend port used by the HTTPS listener of the SLB instance. Valid values: 1–65535.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="loadbalancerid_go">
<a href="#loadbalancerid_go" style="color: inherit; text-decoration: inherit;">Load<wbr>Balancer<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SLB instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}IDs of the SLB domain extensions.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="frontendport_nodejs">
<a href="#frontendport_nodejs" style="color: inherit; text-decoration: inherit;">frontend<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The frontend port used by the HTTPS listener of the SLB instance. Valid values: 1–65535.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="loadbalancerid_nodejs">
<a href="#loadbalancerid_nodejs" style="color: inherit; text-decoration: inherit;">load<wbr>Balancer<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SLB instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}IDs of the SLB domain extensions.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="frontend_port_python">
<a href="#frontend_port_python" style="color: inherit; text-decoration: inherit;">frontend_<wbr>port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The frontend port used by the HTTPS listener of the SLB instance. Valid values: 1–65535.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="load_balancer_id_python">
<a href="#load_balancer_id_python" style="color: inherit; text-decoration: inherit;">load_<wbr>balancer_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the SLB instance.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}IDs of the SLB domain extensions.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getDomainExtensions Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="extensions_csharp">
<a href="#extensions_csharp" style="color: inherit; text-decoration: inherit;">Extensions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainextensionsextension">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Slb.<wbr>Outputs.<wbr>Get<wbr>Domain<wbr>Extensions<wbr>Extension&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of SLB domain extension. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="frontendport_csharp">
<a href="#frontendport_csharp" style="color: inherit; text-decoration: inherit;">Frontend<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
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
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="loadbalancerid_csharp">
<a href="#loadbalancerid_csharp" style="color: inherit; text-decoration: inherit;">Load<wbr>Balancer<wbr>Id</a>
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
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="extensions_go">
<a href="#extensions_go" style="color: inherit; text-decoration: inherit;">Extensions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainextensionsextension">[]Get<wbr>Domain<wbr>Extensions<wbr>Extension</a></span>
    </dt>
    <dd>{{% md %}}A list of SLB domain extension. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="frontendport_go">
<a href="#frontendport_go" style="color: inherit; text-decoration: inherit;">Frontend<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
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
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="loadbalancerid_go">
<a href="#loadbalancerid_go" style="color: inherit; text-decoration: inherit;">Load<wbr>Balancer<wbr>Id</a>
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
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="extensions_nodejs">
<a href="#extensions_nodejs" style="color: inherit; text-decoration: inherit;">extensions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainextensionsextension">Get<wbr>Domain<wbr>Extensions<wbr>Extension[]</a></span>
    </dt>
    <dd>{{% md %}}A list of SLB domain extension. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="frontendport_nodejs">
<a href="#frontendport_nodejs" style="color: inherit; text-decoration: inherit;">frontend<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
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
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="loadbalancerid_nodejs">
<a href="#loadbalancerid_nodejs" style="color: inherit; text-decoration: inherit;">load<wbr>Balancer<wbr>Id</a>
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
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="extensions_python">
<a href="#extensions_python" style="color: inherit; text-decoration: inherit;">extensions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainextensionsextension">Sequence[Get<wbr>Domain<wbr>Extensions<wbr>Extension]</a></span>
    </dt>
    <dd>{{% md %}}A list of SLB domain extension. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="frontend_port_python">
<a href="#frontend_port_python" style="color: inherit; text-decoration: inherit;">frontend_<wbr>port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
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
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="load_balancer_id_python">
<a href="#load_balancer_id_python" style="color: inherit; text-decoration: inherit;">load_<wbr>balancer_<wbr>id</a>
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
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getdomainextensionsextension">Get<wbr>Domain<wbr>Extensions<wbr>Extension</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="domain_csharp">
<a href="#domain_csharp" style="color: inherit; text-decoration: inherit;">Domain</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the domain extension.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="servercertificateid_csharp">
<a href="#servercertificateid_csharp" style="color: inherit; text-decoration: inherit;">Server<wbr>Certificate<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the certificate used by the domain name.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="domain_go">
<a href="#domain_go" style="color: inherit; text-decoration: inherit;">Domain</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the domain extension.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="servercertificateid_go">
<a href="#servercertificateid_go" style="color: inherit; text-decoration: inherit;">Server<wbr>Certificate<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the certificate used by the domain name.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="domain_nodejs">
<a href="#domain_nodejs" style="color: inherit; text-decoration: inherit;">domain</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the domain extension.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="servercertificateid_nodejs">
<a href="#servercertificateid_nodejs" style="color: inherit; text-decoration: inherit;">server<wbr>Certificate<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the certificate used by the domain name.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="domain_python">
<a href="#domain_python" style="color: inherit; text-decoration: inherit;">domain</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The domain name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the domain extension.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="server_certificate_id_python">
<a href="#server_certificate_id_python" style="color: inherit; text-decoration: inherit;">server_<wbr>certificate_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the certificate used by the domain name.
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

