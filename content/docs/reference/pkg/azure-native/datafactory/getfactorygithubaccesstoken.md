
---
title: "getFactoryGitHubAccessToken"
title_tag: "azure-native.datafactory.getFactoryGitHubAccessToken"
meta_desc: "Documentation for the azure-native.datafactory.getFactoryGitHubAccessToken function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Get GitHub access token response definition.
API Version: 2018-06-01.




## Using getFactoryGitHubAccessToken {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getFactoryGitHubAccessToken<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetFactoryGitHubAccessTokenArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetFactoryGitHubAccessTokenResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_factory_git_hub_access_token(</span><span class="nx">factory_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">git_hub_access_code</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">git_hub_access_token_base_url</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">git_hub_client_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetFactoryGitHubAccessTokenResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFactoryGitHubAccessToken<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetFactoryGitHubAccessTokenArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetFactoryGitHubAccessTokenResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetFactoryGitHubAccessToken` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetFactoryGitHubAccessToken </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetFactoryGitHubAccessTokenResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetFactoryGitHubAccessTokenArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="factoryname_csharp">
<a href="#factoryname_csharp" style="color: inherit; text-decoration: inherit;">Factory<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The factory name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="githubaccesscode_csharp">
<a href="#githubaccesscode_csharp" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Access<wbr>Code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access code.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="githubaccesstokenbaseurl_csharp">
<a href="#githubaccesstokenbaseurl_csharp" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Access<wbr>Token<wbr>Base<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access token base URL.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="githubclientid_csharp">
<a href="#githubclientid_csharp" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub application client ID.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="factoryname_go">
<a href="#factoryname_go" style="color: inherit; text-decoration: inherit;">Factory<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The factory name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="githubaccesscode_go">
<a href="#githubaccesscode_go" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Access<wbr>Code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access code.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="githubaccesstokenbaseurl_go">
<a href="#githubaccesstokenbaseurl_go" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Access<wbr>Token<wbr>Base<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access token base URL.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="githubclientid_go">
<a href="#githubclientid_go" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub application client ID.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="factoryname_nodejs">
<a href="#factoryname_nodejs" style="color: inherit; text-decoration: inherit;">factory<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The factory name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="githubaccesscode_nodejs">
<a href="#githubaccesscode_nodejs" style="color: inherit; text-decoration: inherit;">git<wbr>Hub<wbr>Access<wbr>Code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access code.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="githubaccesstokenbaseurl_nodejs">
<a href="#githubaccesstokenbaseurl_nodejs" style="color: inherit; text-decoration: inherit;">git<wbr>Hub<wbr>Access<wbr>Token<wbr>Base<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access token base URL.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="githubclientid_nodejs">
<a href="#githubclientid_nodejs" style="color: inherit; text-decoration: inherit;">git<wbr>Hub<wbr>Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub application client ID.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="factory_name_python">
<a href="#factory_name_python" style="color: inherit; text-decoration: inherit;">factory_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The factory name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="git_hub_access_code_python">
<a href="#git_hub_access_code_python" style="color: inherit; text-decoration: inherit;">git_<wbr>hub_<wbr>access_<wbr>code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}GitHub access code.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="git_hub_access_token_base_url_python">
<a href="#git_hub_access_token_base_url_python" style="color: inherit; text-decoration: inherit;">git_<wbr>hub_<wbr>access_<wbr>token_<wbr>base_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}GitHub access token base URL.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="git_hub_client_id_python">
<a href="#git_hub_client_id_python" style="color: inherit; text-decoration: inherit;">git_<wbr>hub_<wbr>client_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}GitHub application client ID.{{% /md %}}</dd></dl>
{{% /choosable %}}




## getFactoryGitHubAccessToken Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="githubaccesstoken_csharp">
<a href="#githubaccesstoken_csharp" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Access<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access token.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="githubaccesstoken_go">
<a href="#githubaccesstoken_go" style="color: inherit; text-decoration: inherit;">Git<wbr>Hub<wbr>Access<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access token.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="githubaccesstoken_nodejs">
<a href="#githubaccesstoken_nodejs" style="color: inherit; text-decoration: inherit;">git<wbr>Hub<wbr>Access<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}GitHub access token.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="git_hub_access_token_python">
<a href="#git_hub_access_token_python" style="color: inherit; text-decoration: inherit;">git_<wbr>hub_<wbr>access_<wbr>token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}GitHub access token.{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

