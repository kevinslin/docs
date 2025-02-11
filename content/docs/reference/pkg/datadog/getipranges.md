
---
title: "getIpRanges"
title_tag: "datadog.getIpRanges"
meta_desc: "Documentation for the datadog.getIpRanges function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to retrieve information about Datadog's IP addresses.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Datadog = Pulumi.Datadog;

class MyStack : Stack
{
    public MyStack()
    {
        var test = Output.Create(Datadog.GetIpRanges.InvokeAsync());
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-datadog/sdk/v2/go/datadog"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := datadog.GetIpRanges(ctx, nil, nil)
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
import pulumi_datadog as datadog

test = datadog.get_ip_ranges()
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as datadog from "@pulumi/datadog";

const test = pulumi.output(datadog.getIpRanges({ async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getIpRanges {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getIpRanges<span class="p">(</span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetIpRangesResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_ip_ranges(</span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetIpRangesResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIpRanges<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetIpRangesResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetIpRanges` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetIpRanges </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetIpRangesResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}




## getIpRanges Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="agentsipv4s_csharp">
<a href="#agentsipv4s_csharp" style="color: inherit; text-decoration: inherit;">Agents<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="agentsipv6s_csharp">
<a href="#agentsipv6s_csharp" style="color: inherit; text-decoration: inherit;">Agents<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apiipv4s_csharp">
<a href="#apiipv4s_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apiipv6s_csharp">
<a href="#apiipv6s_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apmipv4s_csharp">
<a href="#apmipv4s_csharp" style="color: inherit; text-decoration: inherit;">Apm<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apmipv6s_csharp">
<a href="#apmipv6s_csharp" style="color: inherit; text-decoration: inherit;">Apm<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
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
        <span id="logsipv4s_csharp">
<a href="#logsipv4s_csharp" style="color: inherit; text-decoration: inherit;">Logs<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="logsipv6s_csharp">
<a href="#logsipv6s_csharp" style="color: inherit; text-decoration: inherit;">Logs<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="processipv4s_csharp">
<a href="#processipv4s_csharp" style="color: inherit; text-decoration: inherit;">Process<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="processipv6s_csharp">
<a href="#processipv6s_csharp" style="color: inherit; text-decoration: inherit;">Process<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="syntheticsipv4s_csharp">
<a href="#syntheticsipv4s_csharp" style="color: inherit; text-decoration: inherit;">Synthetics<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="syntheticsipv6s_csharp">
<a href="#syntheticsipv6s_csharp" style="color: inherit; text-decoration: inherit;">Synthetics<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooksipv4s_csharp">
<a href="#webhooksipv4s_csharp" style="color: inherit; text-decoration: inherit;">Webhooks<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooksipv6s_csharp">
<a href="#webhooksipv6s_csharp" style="color: inherit; text-decoration: inherit;">Webhooks<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="agentsipv4s_go">
<a href="#agentsipv4s_go" style="color: inherit; text-decoration: inherit;">Agents<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="agentsipv6s_go">
<a href="#agentsipv6s_go" style="color: inherit; text-decoration: inherit;">Agents<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apiipv4s_go">
<a href="#apiipv4s_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apiipv6s_go">
<a href="#apiipv6s_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apmipv4s_go">
<a href="#apmipv4s_go" style="color: inherit; text-decoration: inherit;">Apm<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apmipv6s_go">
<a href="#apmipv6s_go" style="color: inherit; text-decoration: inherit;">Apm<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
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
        <span id="logsipv4s_go">
<a href="#logsipv4s_go" style="color: inherit; text-decoration: inherit;">Logs<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="logsipv6s_go">
<a href="#logsipv6s_go" style="color: inherit; text-decoration: inherit;">Logs<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="processipv4s_go">
<a href="#processipv4s_go" style="color: inherit; text-decoration: inherit;">Process<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="processipv6s_go">
<a href="#processipv6s_go" style="color: inherit; text-decoration: inherit;">Process<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="syntheticsipv4s_go">
<a href="#syntheticsipv4s_go" style="color: inherit; text-decoration: inherit;">Synthetics<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="syntheticsipv6s_go">
<a href="#syntheticsipv6s_go" style="color: inherit; text-decoration: inherit;">Synthetics<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooksipv4s_go">
<a href="#webhooksipv4s_go" style="color: inherit; text-decoration: inherit;">Webhooks<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooksipv6s_go">
<a href="#webhooksipv6s_go" style="color: inherit; text-decoration: inherit;">Webhooks<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="agentsipv4s_nodejs">
<a href="#agentsipv4s_nodejs" style="color: inherit; text-decoration: inherit;">agents<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="agentsipv6s_nodejs">
<a href="#agentsipv6s_nodejs" style="color: inherit; text-decoration: inherit;">agents<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apiipv4s_nodejs">
<a href="#apiipv4s_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apiipv6s_nodejs">
<a href="#apiipv6s_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apmipv4s_nodejs">
<a href="#apmipv4s_nodejs" style="color: inherit; text-decoration: inherit;">apm<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apmipv6s_nodejs">
<a href="#apmipv6s_nodejs" style="color: inherit; text-decoration: inherit;">apm<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
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
        <span id="logsipv4s_nodejs">
<a href="#logsipv4s_nodejs" style="color: inherit; text-decoration: inherit;">logs<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="logsipv6s_nodejs">
<a href="#logsipv6s_nodejs" style="color: inherit; text-decoration: inherit;">logs<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="processipv4s_nodejs">
<a href="#processipv4s_nodejs" style="color: inherit; text-decoration: inherit;">process<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="processipv6s_nodejs">
<a href="#processipv6s_nodejs" style="color: inherit; text-decoration: inherit;">process<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="syntheticsipv4s_nodejs">
<a href="#syntheticsipv4s_nodejs" style="color: inherit; text-decoration: inherit;">synthetics<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="syntheticsipv6s_nodejs">
<a href="#syntheticsipv6s_nodejs" style="color: inherit; text-decoration: inherit;">synthetics<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooksipv4s_nodejs">
<a href="#webhooksipv4s_nodejs" style="color: inherit; text-decoration: inherit;">webhooks<wbr>Ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooksipv6s_nodejs">
<a href="#webhooksipv6s_nodejs" style="color: inherit; text-decoration: inherit;">webhooks<wbr>Ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="agents_ipv4s_python">
<a href="#agents_ipv4s_python" style="color: inherit; text-decoration: inherit;">agents_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="agents_ipv6s_python">
<a href="#agents_ipv6s_python" style="color: inherit; text-decoration: inherit;">agents_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="api_ipv4s_python">
<a href="#api_ipv4s_python" style="color: inherit; text-decoration: inherit;">api_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="api_ipv6s_python">
<a href="#api_ipv6s_python" style="color: inherit; text-decoration: inherit;">api_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apm_ipv4s_python">
<a href="#apm_ipv4s_python" style="color: inherit; text-decoration: inherit;">apm_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="apm_ipv6s_python">
<a href="#apm_ipv6s_python" style="color: inherit; text-decoration: inherit;">apm_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
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
        <span id="logs_ipv4s_python">
<a href="#logs_ipv4s_python" style="color: inherit; text-decoration: inherit;">logs_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="logs_ipv6s_python">
<a href="#logs_ipv6s_python" style="color: inherit; text-decoration: inherit;">logs_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="process_ipv4s_python">
<a href="#process_ipv4s_python" style="color: inherit; text-decoration: inherit;">process_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="process_ipv6s_python">
<a href="#process_ipv6s_python" style="color: inherit; text-decoration: inherit;">process_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="synthetics_ipv4s_python">
<a href="#synthetics_ipv4s_python" style="color: inherit; text-decoration: inherit;">synthetics_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="synthetics_ipv6s_python">
<a href="#synthetics_ipv6s_python" style="color: inherit; text-decoration: inherit;">synthetics_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooks_ipv4s_python">
<a href="#webhooks_ipv4s_python" style="color: inherit; text-decoration: inherit;">webhooks_<wbr>ipv4s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="webhooks_ipv6s_python">
<a href="#webhooks_ipv6s_python" style="color: inherit; text-decoration: inherit;">webhooks_<wbr>ipv6s</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-datadog">https://github.com/pulumi/pulumi-datadog</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`datadog` Terraform Provider](https://github.com/terraform-providers/terraform-provider-datadog).{{% /md %}}</dd>
</dl>

