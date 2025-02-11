
---
title: "getSecurityContact"
title_tag: "azure-native.security.getSecurityContact"
meta_desc: "Documentation for the azure-native.security.getSecurityContact function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Contact details and configurations for notifications coming from Azure Security Center.
API Version: 2020-01-01-preview.




## Using getSecurityContact {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getSecurityContact<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetSecurityContactArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetSecurityContactResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_security_contact(</span><span class="nx">security_contact_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetSecurityContactResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupSecurityContact<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupSecurityContactArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupSecurityContactResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupSecurityContact` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetSecurityContact </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetSecurityContactResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetSecurityContactArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="securitycontactname_csharp">
<a href="#securitycontactname_csharp" style="color: inherit; text-decoration: inherit;">Security<wbr>Contact<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the security contact object{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="securitycontactname_go">
<a href="#securitycontactname_go" style="color: inherit; text-decoration: inherit;">Security<wbr>Contact<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the security contact object{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="securitycontactname_nodejs">
<a href="#securitycontactname_nodejs" style="color: inherit; text-decoration: inherit;">security<wbr>Contact<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the security contact object{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="security_contact_name_python">
<a href="#security_contact_name_python" style="color: inherit; text-decoration: inherit;">security_<wbr>contact_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the security contact object{{% /md %}}</dd></dl>
{{% /choosable %}}




## getSecurityContact Result {#result}

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
    <dd>{{% md %}}Resource Id{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_csharp">
<a href="#type_csharp" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="alertnotifications_csharp">
<a href="#alertnotifications_csharp" style="color: inherit; text-decoration: inherit;">Alert<wbr>Notifications</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsealertnotifications">Pulumi.<wbr>Azure<wbr>Native.<wbr>Security.<wbr>Outputs.<wbr>Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Alert<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications about new security alerts{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="emails_csharp">
<a href="#emails_csharp" style="color: inherit; text-decoration: inherit;">Emails</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}List of email addresses which will get notifications from Azure Security Center by the configurations defined in this security contact.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="notificationsbyrole_csharp">
<a href="#notificationsbyrole_csharp" style="color: inherit; text-decoration: inherit;">Notifications<wbr>By<wbr>Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsenotificationsbyrole">Pulumi.<wbr>Azure<wbr>Native.<wbr>Security.<wbr>Outputs.<wbr>Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Notifications<wbr>By<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="phone_csharp">
<a href="#phone_csharp" style="color: inherit; text-decoration: inherit;">Phone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security contact's phone number{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}Resource Id{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_go">
<a href="#type_go" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="alertnotifications_go">
<a href="#alertnotifications_go" style="color: inherit; text-decoration: inherit;">Alert<wbr>Notifications</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsealertnotifications">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Alert<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications about new security alerts{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="emails_go">
<a href="#emails_go" style="color: inherit; text-decoration: inherit;">Emails</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}List of email addresses which will get notifications from Azure Security Center by the configurations defined in this security contact.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="notificationsbyrole_go">
<a href="#notificationsbyrole_go" style="color: inherit; text-decoration: inherit;">Notifications<wbr>By<wbr>Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsenotificationsbyrole">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Notifications<wbr>By<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="phone_go">
<a href="#phone_go" style="color: inherit; text-decoration: inherit;">Phone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security contact's phone number{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}Resource Id{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_nodejs">
<a href="#type_nodejs" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="alertnotifications_nodejs">
<a href="#alertnotifications_nodejs" style="color: inherit; text-decoration: inherit;">alert<wbr>Notifications</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsealertnotifications">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Alert<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications about new security alerts{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="emails_nodejs">
<a href="#emails_nodejs" style="color: inherit; text-decoration: inherit;">emails</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}List of email addresses which will get notifications from Azure Security Center by the configurations defined in this security contact.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="notificationsbyrole_nodejs">
<a href="#notificationsbyrole_nodejs" style="color: inherit; text-decoration: inherit;">notifications<wbr>By<wbr>Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsenotificationsbyrole">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Notifications<wbr>By<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="phone_nodejs">
<a href="#phone_nodejs" style="color: inherit; text-decoration: inherit;">phone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security contact's phone number{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}Resource Id{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_python">
<a href="#type_python" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="alert_notifications_python">
<a href="#alert_notifications_python" style="color: inherit; text-decoration: inherit;">alert_<wbr>notifications</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsealertnotifications">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Alert<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications about new security alerts{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="emails_python">
<a href="#emails_python" style="color: inherit; text-decoration: inherit;">emails</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}List of email addresses which will get notifications from Azure Security Center by the configurations defined in this security contact.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="notifications_by_role_python">
<a href="#notifications_by_role_python" style="color: inherit; text-decoration: inherit;">notifications_<wbr>by_<wbr>role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#securitycontactpropertiesresponsenotificationsbyrole">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Notifications<wbr>By<wbr>Role</a></span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="phone_python">
<a href="#phone_python" style="color: inherit; text-decoration: inherit;">phone</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security contact's phone number{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="securitycontactpropertiesresponsealertnotifications">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Alert<wbr>Notifications</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="minimalseverity_csharp">
<a href="#minimalseverity_csharp" style="color: inherit; text-decoration: inherit;">Minimal<wbr>Severity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines the minimal alert severity which will be sent as email notifications{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_csharp">
<a href="#state_csharp" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines if email notifications will be sent about new security alerts{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="minimalseverity_go">
<a href="#minimalseverity_go" style="color: inherit; text-decoration: inherit;">Minimal<wbr>Severity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines the minimal alert severity which will be sent as email notifications{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_go">
<a href="#state_go" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines if email notifications will be sent about new security alerts{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="minimalseverity_nodejs">
<a href="#minimalseverity_nodejs" style="color: inherit; text-decoration: inherit;">minimal<wbr>Severity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines the minimal alert severity which will be sent as email notifications{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_nodejs">
<a href="#state_nodejs" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines if email notifications will be sent about new security alerts{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="minimal_severity_python">
<a href="#minimal_severity_python" style="color: inherit; text-decoration: inherit;">minimal_<wbr>severity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Defines the minimal alert severity which will be sent as email notifications{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_python">
<a href="#state_python" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Defines if email notifications will be sent about new security alerts{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="securitycontactpropertiesresponsenotificationsbyrole">Security<wbr>Contact<wbr>Properties<wbr>Response<wbr>Notifications<wbr>By<wbr>Role</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="roles_csharp">
<a href="#roles_csharp" style="color: inherit; text-decoration: inherit;">Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}Defines which RBAC roles will get email notifications from Azure Security Center. List of allowed RBAC roles: {{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_csharp">
<a href="#state_csharp" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="roles_go">
<a href="#roles_go" style="color: inherit; text-decoration: inherit;">Roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Defines which RBAC roles will get email notifications from Azure Security Center. List of allowed RBAC roles: {{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_go">
<a href="#state_go" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="roles_nodejs">
<a href="#roles_nodejs" style="color: inherit; text-decoration: inherit;">roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Defines which RBAC roles will get email notifications from Azure Security Center. List of allowed RBAC roles: {{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_nodejs">
<a href="#state_nodejs" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="roles_python">
<a href="#roles_python" style="color: inherit; text-decoration: inherit;">roles</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}Defines which RBAC roles will get email notifications from Azure Security Center. List of allowed RBAC roles: {{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_python">
<a href="#state_python" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Defines whether to send email notifications from Azure Security Center to persons with specific RBAC roles on the subscription.{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

