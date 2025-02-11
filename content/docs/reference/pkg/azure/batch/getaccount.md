
---
title: "getAccount"
title_tag: "azure.batch.getAccount"
meta_desc: "Documentation for the azure.batch.getAccount function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing Batch Account.


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
        var example = Output.Create(Azure.Batch.GetAccount.InvokeAsync(new Azure.Batch.GetAccountArgs
        {
            Name = "testbatchaccount",
            ResourceGroupName = "test",
        }));
        this.PoolAllocationMode = example.Apply(example => example.PoolAllocationMode);
    }

    [Output("poolAllocationMode")]
    public Output<string> PoolAllocationMode { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/batch"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		example, err := batch.LookupAccount(ctx, &batch.LookupAccountArgs{
			Name:              "testbatchaccount",
			ResourceGroupName: "test",
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("poolAllocationMode", example.PoolAllocationMode)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.batch.get_account(name="testbatchaccount",
    resource_group_name="test")
pulumi.export("poolAllocationMode", example.pool_allocation_mode)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.batch.getAccount({
    name: "testbatchaccount",
    resourceGroupName: "test",
});
export const poolAllocationMode = example.then(example => example.poolAllocationMode);
```


{{< /example >}}





{{% /examples %}}




## Using getAccount {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAccount<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAccountArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAccountResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_account(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAccountResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupAccount<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupAccountArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupAccountResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupAccount` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAccount </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAccountResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAccountArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}The name of the Batch account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where this Batch account exists.
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
    <dd>{{% md %}}The name of the Batch account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where this Batch account exists.
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
    <dd>{{% md %}}The name of the Batch account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where this Batch account exists.
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
    <dd>{{% md %}}The name of the Batch account.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where this Batch account exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAccount Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accountendpoint_csharp">
<a href="#accountendpoint_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Endpoint</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The account endpoint used to interact with the Batch service.
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
        <span id="keyvaultreferences_csharp">
<a href="#keyvaultreferences_csharp" style="color: inherit; text-decoration: inherit;">Key<wbr>Vault<wbr>References</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountkeyvaultreference">List&lt;Get<wbr>Account<wbr>Key<wbr>Vault<wbr>Reference&gt;</a></span>
    </dt>
    <dd>{{% md %}}The `key_vault_reference` block that describes the Azure KeyVault reference to use when deploying the Azure Batch account using the `UserSubscription` pool allocation mode.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_csharp">
<a href="#location_csharp" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure Region in which this Batch account exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolallocationmode_csharp">
<a href="#poolallocationmode_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Allocation<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The pool allocation mode configured for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="primaryaccesskey_csharp">
<a href="#primaryaccesskey_csharp" style="color: inherit; text-decoration: inherit;">Primary<wbr>Access<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account primary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="secondaryaccesskey_csharp">
<a href="#secondaryaccesskey_csharp" style="color: inherit; text-decoration: inherit;">Secondary<wbr>Access<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account secondary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storageaccountid_csharp">
<a href="#storageaccountid_csharp" style="color: inherit; text-decoration: inherit;">Storage<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Storage Account used for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}A map of tags assigned to the Batch account.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accountendpoint_go">
<a href="#accountendpoint_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Endpoint</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The account endpoint used to interact with the Batch service.
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
        <span id="keyvaultreferences_go">
<a href="#keyvaultreferences_go" style="color: inherit; text-decoration: inherit;">Key<wbr>Vault<wbr>References</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountkeyvaultreference">[]Get<wbr>Account<wbr>Key<wbr>Vault<wbr>Reference</a></span>
    </dt>
    <dd>{{% md %}}The `key_vault_reference` block that describes the Azure KeyVault reference to use when deploying the Azure Batch account using the `UserSubscription` pool allocation mode.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_go">
<a href="#location_go" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure Region in which this Batch account exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolallocationmode_go">
<a href="#poolallocationmode_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Allocation<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The pool allocation mode configured for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="primaryaccesskey_go">
<a href="#primaryaccesskey_go" style="color: inherit; text-decoration: inherit;">Primary<wbr>Access<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account primary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="secondaryaccesskey_go">
<a href="#secondaryaccesskey_go" style="color: inherit; text-decoration: inherit;">Secondary<wbr>Access<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account secondary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storageaccountid_go">
<a href="#storageaccountid_go" style="color: inherit; text-decoration: inherit;">Storage<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Storage Account used for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of tags assigned to the Batch account.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accountendpoint_nodejs">
<a href="#accountendpoint_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Endpoint</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The account endpoint used to interact with the Batch service.
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
        <span id="keyvaultreferences_nodejs">
<a href="#keyvaultreferences_nodejs" style="color: inherit; text-decoration: inherit;">key<wbr>Vault<wbr>References</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountkeyvaultreference">Get<wbr>Account<wbr>Key<wbr>Vault<wbr>Reference[]</a></span>
    </dt>
    <dd>{{% md %}}The `key_vault_reference` block that describes the Azure KeyVault reference to use when deploying the Azure Batch account using the `UserSubscription` pool allocation mode.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_nodejs">
<a href="#location_nodejs" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure Region in which this Batch account exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolallocationmode_nodejs">
<a href="#poolallocationmode_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Allocation<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The pool allocation mode configured for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="primaryaccesskey_nodejs">
<a href="#primaryaccesskey_nodejs" style="color: inherit; text-decoration: inherit;">primary<wbr>Access<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account primary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="secondaryaccesskey_nodejs">
<a href="#secondaryaccesskey_nodejs" style="color: inherit; text-decoration: inherit;">secondary<wbr>Access<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Batch account secondary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storageaccountid_nodejs">
<a href="#storageaccountid_nodejs" style="color: inherit; text-decoration: inherit;">storage<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Storage Account used for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}A map of tags assigned to the Batch account.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="account_endpoint_python">
<a href="#account_endpoint_python" style="color: inherit; text-decoration: inherit;">account_<wbr>endpoint</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The account endpoint used to interact with the Batch service.
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
        <span id="key_vault_references_python">
<a href="#key_vault_references_python" style="color: inherit; text-decoration: inherit;">key_<wbr>vault_<wbr>references</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountkeyvaultreference">Sequence[Get<wbr>Account<wbr>Key<wbr>Vault<wbr>Reference]</a></span>
    </dt>
    <dd>{{% md %}}The `key_vault_reference` block that describes the Azure KeyVault reference to use when deploying the Azure Batch account using the `UserSubscription` pool allocation mode.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_python">
<a href="#location_python" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Azure Region in which this Batch account exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Batch account name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pool_allocation_mode_python">
<a href="#pool_allocation_mode_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>allocation_<wbr>mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The pool allocation mode configured for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="primary_access_key_python">
<a href="#primary_access_key_python" style="color: inherit; text-decoration: inherit;">primary_<wbr>access_<wbr>key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Batch account primary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="secondary_access_key_python">
<a href="#secondary_access_key_python" style="color: inherit; text-decoration: inherit;">secondary_<wbr>access_<wbr>key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Batch account secondary access key.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storage_account_id_python">
<a href="#storage_account_id_python" style="color: inherit; text-decoration: inherit;">storage_<wbr>account_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Storage Account used for this Batch account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of tags assigned to the Batch account.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getaccountkeyvaultreference">Get<wbr>Account<wbr>Key<wbr>Vault<wbr>Reference</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure identifier of the Azure KeyVault reference.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="url_csharp">
<a href="#url_csharp" style="color: inherit; text-decoration: inherit;">Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTPS URL of the Azure KeyVault reference.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure identifier of the Azure KeyVault reference.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="url_go">
<a href="#url_go" style="color: inherit; text-decoration: inherit;">Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTPS URL of the Azure KeyVault reference.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure identifier of the Azure KeyVault reference.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="url_nodejs">
<a href="#url_nodejs" style="color: inherit; text-decoration: inherit;">url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTPS URL of the Azure KeyVault reference.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Azure identifier of the Azure KeyVault reference.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="url_python">
<a href="#url_python" style="color: inherit; text-decoration: inherit;">url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTPS URL of the Azure KeyVault reference.
{{% /md %}}</dd></dl>
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

