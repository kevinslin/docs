
---
title: "getNotificationRegistration"
title_tag: "azure-native.providerhub.getNotificationRegistration"
meta_desc: "Documentation for the azure-native.providerhub.getNotificationRegistration function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

The notification registration definition.
API Version: 2020-11-20.




## Using getNotificationRegistration {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getNotificationRegistration<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetNotificationRegistrationArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetNotificationRegistrationResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_notification_registration(</span><span class="nx">notification_registration_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">provider_namespace</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetNotificationRegistrationResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupNotificationRegistration<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupNotificationRegistrationArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupNotificationRegistrationResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupNotificationRegistration` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetNotificationRegistration </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetNotificationRegistrationResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetNotificationRegistrationArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notificationregistrationname_csharp">
<a href="#notificationregistrationname_csharp" style="color: inherit; text-decoration: inherit;">Notification<wbr>Registration<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The notification registration.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providernamespace_csharp">
<a href="#providernamespace_csharp" style="color: inherit; text-decoration: inherit;">Provider<wbr>Namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource provider hosted within ProviderHub.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notificationregistrationname_go">
<a href="#notificationregistrationname_go" style="color: inherit; text-decoration: inherit;">Notification<wbr>Registration<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The notification registration.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providernamespace_go">
<a href="#providernamespace_go" style="color: inherit; text-decoration: inherit;">Provider<wbr>Namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource provider hosted within ProviderHub.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notificationregistrationname_nodejs">
<a href="#notificationregistrationname_nodejs" style="color: inherit; text-decoration: inherit;">notification<wbr>Registration<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The notification registration.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providernamespace_nodejs">
<a href="#providernamespace_nodejs" style="color: inherit; text-decoration: inherit;">provider<wbr>Namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource provider hosted within ProviderHub.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notification_registration_name_python">
<a href="#notification_registration_name_python" style="color: inherit; text-decoration: inherit;">notification_<wbr>registration_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The notification registration.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="provider_namespace_python">
<a href="#provider_namespace_python" style="color: inherit; text-decoration: inherit;">provider_<wbr>namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource provider hosted within ProviderHub.{{% /md %}}</dd></dl>
{{% /choosable %}}




## getNotificationRegistration Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Fully qualified resource ID for the resource. Ex - /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceProviderNamespace}/{resourceType}/{resourceName}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="properties_csharp">
<a href="#properties_csharp" style="color: inherit; text-decoration: inherit;">Properties</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationregistrationresponseproperties">Pulumi.<wbr>Azure<wbr>Native.<wbr>Provider<wbr>Hub.<wbr>Outputs.<wbr>Notification<wbr>Registration<wbr>Response<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_csharp">
<a href="#type_csharp" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the resource. E.g. "Microsoft.Compute/virtualMachines" or "Microsoft.Storage/storageAccounts"{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}Fully qualified resource ID for the resource. Ex - /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceProviderNamespace}/{resourceType}/{resourceName}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="properties_go">
<a href="#properties_go" style="color: inherit; text-decoration: inherit;">Properties</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationregistrationresponseproperties">Notification<wbr>Registration<wbr>Response<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_go">
<a href="#type_go" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the resource. E.g. "Microsoft.Compute/virtualMachines" or "Microsoft.Storage/storageAccounts"{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}Fully qualified resource ID for the resource. Ex - /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceProviderNamespace}/{resourceType}/{resourceName}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="properties_nodejs">
<a href="#properties_nodejs" style="color: inherit; text-decoration: inherit;">properties</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationregistrationresponseproperties">Notification<wbr>Registration<wbr>Response<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_nodejs">
<a href="#type_nodejs" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the resource. E.g. "Microsoft.Compute/virtualMachines" or "Microsoft.Storage/storageAccounts"{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}Fully qualified resource ID for the resource. Ex - /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceProviderNamespace}/{resourceType}/{resourceName}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="properties_python">
<a href="#properties_python" style="color: inherit; text-decoration: inherit;">properties</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationregistrationresponseproperties">Notification<wbr>Registration<wbr>Response<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_python">
<a href="#type_python" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the resource. E.g. "Microsoft.Compute/virtualMachines" or "Microsoft.Storage/storageAccounts"{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="notificationendpointresponse">Notification<wbr>Endpoint<wbr>Response</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="locations_csharp">
<a href="#locations_csharp" style="color: inherit; text-decoration: inherit;">Locations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationdestination_csharp">
<a href="#notificationdestination_csharp" style="color: inherit; text-decoration: inherit;">Notification<wbr>Destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="locations_go">
<a href="#locations_go" style="color: inherit; text-decoration: inherit;">Locations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationdestination_go">
<a href="#notificationdestination_go" style="color: inherit; text-decoration: inherit;">Notification<wbr>Destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="locations_nodejs">
<a href="#locations_nodejs" style="color: inherit; text-decoration: inherit;">locations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationdestination_nodejs">
<a href="#notificationdestination_nodejs" style="color: inherit; text-decoration: inherit;">notification<wbr>Destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="locations_python">
<a href="#locations_python" style="color: inherit; text-decoration: inherit;">locations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notification_destination_python">
<a href="#notification_destination_python" style="color: inherit; text-decoration: inherit;">notification_<wbr>destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="notificationregistrationresponseproperties">Notification<wbr>Registration<wbr>Response<wbr>Properties</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="includedevents_csharp">
<a href="#includedevents_csharp" style="color: inherit; text-decoration: inherit;">Included<wbr>Events</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="messagescope_csharp">
<a href="#messagescope_csharp" style="color: inherit; text-decoration: inherit;">Message<wbr>Scope</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationendpoints_csharp">
<a href="#notificationendpoints_csharp" style="color: inherit; text-decoration: inherit;">Notification<wbr>Endpoints</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationendpointresponse">List&lt;Pulumi.<wbr>Azure<wbr>Native.<wbr>Provider<wbr>Hub.<wbr>Inputs.<wbr>Notification<wbr>Endpoint<wbr>Response<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationmode_csharp">
<a href="#notificationmode_csharp" style="color: inherit; text-decoration: inherit;">Notification<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="includedevents_go">
<a href="#includedevents_go" style="color: inherit; text-decoration: inherit;">Included<wbr>Events</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="messagescope_go">
<a href="#messagescope_go" style="color: inherit; text-decoration: inherit;">Message<wbr>Scope</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationendpoints_go">
<a href="#notificationendpoints_go" style="color: inherit; text-decoration: inherit;">Notification<wbr>Endpoints</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationendpointresponse">[]Notification<wbr>Endpoint<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationmode_go">
<a href="#notificationmode_go" style="color: inherit; text-decoration: inherit;">Notification<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="includedevents_nodejs">
<a href="#includedevents_nodejs" style="color: inherit; text-decoration: inherit;">included<wbr>Events</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="messagescope_nodejs">
<a href="#messagescope_nodejs" style="color: inherit; text-decoration: inherit;">message<wbr>Scope</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationendpoints_nodejs">
<a href="#notificationendpoints_nodejs" style="color: inherit; text-decoration: inherit;">notification<wbr>Endpoints</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationendpointresponse">Notification<wbr>Endpoint<wbr>Response[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notificationmode_nodejs">
<a href="#notificationmode_nodejs" style="color: inherit; text-decoration: inherit;">notification<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="included_events_python">
<a href="#included_events_python" style="color: inherit; text-decoration: inherit;">included_<wbr>events</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="message_scope_python">
<a href="#message_scope_python" style="color: inherit; text-decoration: inherit;">message_<wbr>scope</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notification_endpoints_python">
<a href="#notification_endpoints_python" style="color: inherit; text-decoration: inherit;">notification_<wbr>endpoints</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#notificationendpointresponse">Sequence[Notification<wbr>Endpoint<wbr>Response<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="notification_mode_python">
<a href="#notification_mode_python" style="color: inherit; text-decoration: inherit;">notification_<wbr>mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

