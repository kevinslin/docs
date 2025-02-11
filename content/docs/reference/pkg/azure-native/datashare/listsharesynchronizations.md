
---
title: "listShareSynchronizations"
title_tag: "azure-native.datashare.listShareSynchronizations"
meta_desc: "Documentation for the azure-native.datashare.listShareSynchronizations function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

List response for get ShareSynchronization.
API Version: 2020-09-01.




## Using listShareSynchronizations {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>listShareSynchronizations<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">ListShareSynchronizationsArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">ListShareSynchronizationsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>list_share_synchronizations(</span><span class="nx">account_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">filter</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">orderby</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">share_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">skip_token</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> ListShareSynchronizationsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>ListShareSynchronizations<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">ListShareSynchronizationsArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">ListShareSynchronizationsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `ListShareSynchronizations` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">ListShareSynchronizations </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">ListShareSynchronizationsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">ListShareSynchronizationsArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountname_csharp">
<a href="#accountname_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharename_csharp">
<a href="#sharename_csharp" style="color: inherit; text-decoration: inherit;">Share<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="filter_csharp">
<a href="#filter_csharp" style="color: inherit; text-decoration: inherit;">Filter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filters the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="orderby_csharp">
<a href="#orderby_csharp" style="color: inherit; text-decoration: inherit;">Orderby</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Sorts the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="skiptoken_csharp">
<a href="#skiptoken_csharp" style="color: inherit; text-decoration: inherit;">Skip<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Continuation token{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountname_go">
<a href="#accountname_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharename_go">
<a href="#sharename_go" style="color: inherit; text-decoration: inherit;">Share<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="filter_go">
<a href="#filter_go" style="color: inherit; text-decoration: inherit;">Filter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filters the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="orderby_go">
<a href="#orderby_go" style="color: inherit; text-decoration: inherit;">Orderby</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Sorts the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="skiptoken_go">
<a href="#skiptoken_go" style="color: inherit; text-decoration: inherit;">Skip<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Continuation token{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountname_nodejs">
<a href="#accountname_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharename_nodejs">
<a href="#sharename_nodejs" style="color: inherit; text-decoration: inherit;">share<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="filter_nodejs">
<a href="#filter_nodejs" style="color: inherit; text-decoration: inherit;">filter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Filters the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="orderby_nodejs">
<a href="#orderby_nodejs" style="color: inherit; text-decoration: inherit;">orderby</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Sorts the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="skiptoken_nodejs">
<a href="#skiptoken_nodejs" style="color: inherit; text-decoration: inherit;">skip<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Continuation token{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="account_name_python">
<a href="#account_name_python" style="color: inherit; text-decoration: inherit;">account_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="share_name_python">
<a href="#share_name_python" style="color: inherit; text-decoration: inherit;">share_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the share.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="filter_python">
<a href="#filter_python" style="color: inherit; text-decoration: inherit;">filter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Filters the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="orderby_python">
<a href="#orderby_python" style="color: inherit; text-decoration: inherit;">orderby</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sorts the results using OData syntax.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="skip_token_python">
<a href="#skip_token_python" style="color: inherit; text-decoration: inherit;">skip_<wbr>token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Continuation token{{% /md %}}</dd></dl>
{{% /choosable %}}




## listShareSynchronizations Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="value_csharp">
<a href="#value_csharp" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#sharesynchronizationresponse">List&lt;Pulumi.<wbr>Azure<wbr>Native.<wbr>Data<wbr>Share.<wbr>Outputs.<wbr>Share<wbr>Synchronization<wbr>Response&gt;</a></span>
    </dt>
    <dd>{{% md %}}Collection of items of type DataTransferObjects.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nextlink_csharp">
<a href="#nextlink_csharp" style="color: inherit; text-decoration: inherit;">Next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Url of next result page.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="value_go">
<a href="#value_go" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#sharesynchronizationresponse">[]Share<wbr>Synchronization<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}Collection of items of type DataTransferObjects.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nextlink_go">
<a href="#nextlink_go" style="color: inherit; text-decoration: inherit;">Next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Url of next result page.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="value_nodejs">
<a href="#value_nodejs" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#sharesynchronizationresponse">Share<wbr>Synchronization<wbr>Response[]</a></span>
    </dt>
    <dd>{{% md %}}Collection of items of type DataTransferObjects.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nextlink_nodejs">
<a href="#nextlink_nodejs" style="color: inherit; text-decoration: inherit;">next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Url of next result page.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="value_python">
<a href="#value_python" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#sharesynchronizationresponse">Sequence[Share<wbr>Synchronization<wbr>Response]</a></span>
    </dt>
    <dd>{{% md %}}Collection of items of type DataTransferObjects.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="next_link_python">
<a href="#next_link_python" style="color: inherit; text-decoration: inherit;">next_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Url of next result page.{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="sharesynchronizationresponse">Share<wbr>Synchronization<wbr>Response</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="synchronizationmode_csharp">
<a href="#synchronizationmode_csharp" style="color: inherit; text-decoration: inherit;">Synchronization<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Synchronization mode{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumeremail_csharp">
<a href="#consumeremail_csharp" style="color: inherit; text-decoration: inherit;">Consumer<wbr>Email</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumername_csharp">
<a href="#consumername_csharp" style="color: inherit; text-decoration: inherit;">Consumer<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumertenantname_csharp">
<a href="#consumertenantname_csharp" style="color: inherit; text-decoration: inherit;">Consumer<wbr>Tenant<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Tenant name of the consumer who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="durationms_csharp">
<a href="#durationms_csharp" style="color: inherit; text-decoration: inherit;">Duration<wbr>Ms</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}synchronization duration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="endtime_csharp">
<a href="#endtime_csharp" style="color: inherit; text-decoration: inherit;">End<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}End time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="message_csharp">
<a href="#message_csharp" style="color: inherit; text-decoration: inherit;">Message</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}message of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="starttime_csharp">
<a href="#starttime_csharp" style="color: inherit; text-decoration: inherit;">Start<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}start time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="status_csharp">
<a href="#status_csharp" style="color: inherit; text-decoration: inherit;">Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Raw Status{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="synchronizationid_csharp">
<a href="#synchronizationid_csharp" style="color: inherit; text-decoration: inherit;">Synchronization<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Synchronization id{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="synchronizationmode_go">
<a href="#synchronizationmode_go" style="color: inherit; text-decoration: inherit;">Synchronization<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Synchronization mode{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumeremail_go">
<a href="#consumeremail_go" style="color: inherit; text-decoration: inherit;">Consumer<wbr>Email</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumername_go">
<a href="#consumername_go" style="color: inherit; text-decoration: inherit;">Consumer<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumertenantname_go">
<a href="#consumertenantname_go" style="color: inherit; text-decoration: inherit;">Consumer<wbr>Tenant<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Tenant name of the consumer who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="durationms_go">
<a href="#durationms_go" style="color: inherit; text-decoration: inherit;">Duration<wbr>Ms</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}synchronization duration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="endtime_go">
<a href="#endtime_go" style="color: inherit; text-decoration: inherit;">End<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}End time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="message_go">
<a href="#message_go" style="color: inherit; text-decoration: inherit;">Message</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}message of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="starttime_go">
<a href="#starttime_go" style="color: inherit; text-decoration: inherit;">Start<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}start time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="status_go">
<a href="#status_go" style="color: inherit; text-decoration: inherit;">Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Raw Status{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="synchronizationid_go">
<a href="#synchronizationid_go" style="color: inherit; text-decoration: inherit;">Synchronization<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Synchronization id{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="synchronizationmode_nodejs">
<a href="#synchronizationmode_nodejs" style="color: inherit; text-decoration: inherit;">synchronization<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Synchronization mode{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumeremail_nodejs">
<a href="#consumeremail_nodejs" style="color: inherit; text-decoration: inherit;">consumer<wbr>Email</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumername_nodejs">
<a href="#consumername_nodejs" style="color: inherit; text-decoration: inherit;">consumer<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumertenantname_nodejs">
<a href="#consumertenantname_nodejs" style="color: inherit; text-decoration: inherit;">consumer<wbr>Tenant<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Tenant name of the consumer who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="durationms_nodejs">
<a href="#durationms_nodejs" style="color: inherit; text-decoration: inherit;">duration<wbr>Ms</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}synchronization duration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="endtime_nodejs">
<a href="#endtime_nodejs" style="color: inherit; text-decoration: inherit;">end<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}End time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="message_nodejs">
<a href="#message_nodejs" style="color: inherit; text-decoration: inherit;">message</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}message of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="starttime_nodejs">
<a href="#starttime_nodejs" style="color: inherit; text-decoration: inherit;">start<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}start time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="status_nodejs">
<a href="#status_nodejs" style="color: inherit; text-decoration: inherit;">status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Raw Status{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="synchronizationid_nodejs">
<a href="#synchronizationid_nodejs" style="color: inherit; text-decoration: inherit;">synchronization<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Synchronization id{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="synchronization_mode_python">
<a href="#synchronization_mode_python" style="color: inherit; text-decoration: inherit;">synchronization_<wbr>mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Synchronization mode{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumer_email_python">
<a href="#consumer_email_python" style="color: inherit; text-decoration: inherit;">consumer_<wbr>email</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumer_name_python">
<a href="#consumer_name_python" style="color: inherit; text-decoration: inherit;">consumer_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the user who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="consumer_tenant_name_python">
<a href="#consumer_tenant_name_python" style="color: inherit; text-decoration: inherit;">consumer_<wbr>tenant_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Tenant name of the consumer who created the synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="duration_ms_python">
<a href="#duration_ms_python" style="color: inherit; text-decoration: inherit;">duration_<wbr>ms</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}synchronization duration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="end_time_python">
<a href="#end_time_python" style="color: inherit; text-decoration: inherit;">end_<wbr>time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}End time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="message_python">
<a href="#message_python" style="color: inherit; text-decoration: inherit;">message</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}message of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="start_time_python">
<a href="#start_time_python" style="color: inherit; text-decoration: inherit;">start_<wbr>time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}start time of synchronization{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="status_python">
<a href="#status_python" style="color: inherit; text-decoration: inherit;">status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Raw Status{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="synchronization_id_python">
<a href="#synchronization_id_python" style="color: inherit; text-decoration: inherit;">synchronization_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Synchronization id{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

