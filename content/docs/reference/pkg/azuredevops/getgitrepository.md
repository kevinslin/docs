
---
title: "getGitRepository"
title_tag: "azuredevops.getGitRepository"
meta_desc: "Documentation for the azuredevops.getGitRepository function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about a **single** (existing) Git Repository within Azure DevOps.
To read information about **multiple** Git Repositories use the data source `azuredevops.getRepositories`
## Relevant Links

- [Azure DevOps Service REST API 5.1 - Git API](https://docs.microsoft.com/en-us/rest/api/azure/devops/git/?view=azure-devops-rest-5.1)


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using AzureDevOps = Pulumi.AzureDevOps;

class MyStack : Stack
{
    public MyStack()
    {
        var project = Output.Create(AzureDevOps.GetProject.InvokeAsync(new AzureDevOps.GetProjectArgs
        {
            Name = "contoso-project",
        }));
        var singleRepo = project.Apply(project => Output.Create(AzureDevOps.GetGitRepository.InvokeAsync(new AzureDevOps.GetGitRepositoryArgs
        {
            ProjectId = project.Id,
            Name = "contoso-repo",
        })));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azuredevops/sdk/go/azuredevops"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "contoso-project"
		project, err := azuredevops.LookupProject(ctx, &azuredevops.LookupProjectArgs{
			Name: &opt0,
		}, nil)
		if err != nil {
			return err
		}
		_, err = azuredevops.GetGitRepository(ctx, &azuredevops.GetGitRepositoryArgs{
			ProjectId: project.Id,
			Name:      "contoso-repo",
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
import pulumi_azuredevops as azuredevops

project = azuredevops.get_project(name="contoso-project")
single_repo = azuredevops.get_git_repository(project_id=project.id,
    name="contoso-repo")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azuredevops from "@pulumi/azuredevops";

const project = azuredevops.getProject({
    name: "contoso-project",
});
const singleRepo = project.then(project => azuredevops.getGitRepository({
    projectId: project.id,
    name: "contoso-repo",
}));
```


{{< /example >}}





{{% /examples %}}




## Using getGitRepository {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getGitRepository<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetGitRepositoryArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetGitRepositoryResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_git_repository(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">project_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetGitRepositoryResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGitRepository<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetGitRepositoryArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetGitRepositoryResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetGitRepository` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetGitRepository </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetGitRepositoryResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetGitRepositoryArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}Name of the Git repository to retrieve
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of project to list Git repositories
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
    <dd>{{% md %}}Name of the Git repository to retrieve
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of project to list Git repositories
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
    <dd>{{% md %}}Name of the Git repository to retrieve
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of project to list Git repositories
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
    <dd>{{% md %}}Name of the Git repository to retrieve
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of project to list Git repositories
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getGitRepository Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="defaultbranch_csharp">
<a href="#defaultbranch_csharp" style="color: inherit; text-decoration: inherit;">Default<wbr>Branch</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ref of the default branch.
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
        <span id="isfork_csharp">
<a href="#isfork_csharp" style="color: inherit; text-decoration: inherit;">Is<wbr>Fork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Git repository name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project identifier to which the Git repository belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="remoteurl_csharp">
<a href="#remoteurl_csharp" style="color: inherit; text-decoration: inherit;">Remote<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTPS Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_csharp">
<a href="#size_csharp" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Compressed size (bytes) of the repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sshurl_csharp">
<a href="#sshurl_csharp" style="color: inherit; text-decoration: inherit;">Ssh<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SSH Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="url_csharp">
<a href="#url_csharp" style="color: inherit; text-decoration: inherit;">Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Details REST API endpoint for the Git Repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="weburl_csharp">
<a href="#weburl_csharp" style="color: inherit; text-decoration: inherit;">Web<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Url of the Git repository web view
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="defaultbranch_go">
<a href="#defaultbranch_go" style="color: inherit; text-decoration: inherit;">Default<wbr>Branch</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ref of the default branch.
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
        <span id="isfork_go">
<a href="#isfork_go" style="color: inherit; text-decoration: inherit;">Is<wbr>Fork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Git repository name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project identifier to which the Git repository belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="remoteurl_go">
<a href="#remoteurl_go" style="color: inherit; text-decoration: inherit;">Remote<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTPS Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_go">
<a href="#size_go" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Compressed size (bytes) of the repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sshurl_go">
<a href="#sshurl_go" style="color: inherit; text-decoration: inherit;">Ssh<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SSH Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="url_go">
<a href="#url_go" style="color: inherit; text-decoration: inherit;">Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Details REST API endpoint for the Git Repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="weburl_go">
<a href="#weburl_go" style="color: inherit; text-decoration: inherit;">Web<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Url of the Git repository web view
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="defaultbranch_nodejs">
<a href="#defaultbranch_nodejs" style="color: inherit; text-decoration: inherit;">default<wbr>Branch</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ref of the default branch.
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
        <span id="isfork_nodejs">
<a href="#isfork_nodejs" style="color: inherit; text-decoration: inherit;">is<wbr>Fork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Git repository name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project identifier to which the Git repository belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="remoteurl_nodejs">
<a href="#remoteurl_nodejs" style="color: inherit; text-decoration: inherit;">remote<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTPS Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_nodejs">
<a href="#size_nodejs" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Compressed size (bytes) of the repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sshurl_nodejs">
<a href="#sshurl_nodejs" style="color: inherit; text-decoration: inherit;">ssh<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SSH Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="url_nodejs">
<a href="#url_nodejs" style="color: inherit; text-decoration: inherit;">url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Details REST API endpoint for the Git Repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="weburl_nodejs">
<a href="#weburl_nodejs" style="color: inherit; text-decoration: inherit;">web<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Url of the Git repository web view
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="default_branch_python">
<a href="#default_branch_python" style="color: inherit; text-decoration: inherit;">default_<wbr>branch</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ref of the default branch.
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
        <span id="is_fork_python">
<a href="#is_fork_python" style="color: inherit; text-decoration: inherit;">is_<wbr>fork</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Git repository name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Project identifier to which the Git repository belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="remote_url_python">
<a href="#remote_url_python" style="color: inherit; text-decoration: inherit;">remote_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}HTTPS Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_python">
<a href="#size_python" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Compressed size (bytes) of the repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ssh_url_python">
<a href="#ssh_url_python" style="color: inherit; text-decoration: inherit;">ssh_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SSH Url to clone the Git repository
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="url_python">
<a href="#url_python" style="color: inherit; text-decoration: inherit;">url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Details REST API endpoint for the Git Repository.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="web_url_python">
<a href="#web_url_python" style="color: inherit; text-decoration: inherit;">web_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Url of the Git repository web view
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azuredevops">https://github.com/pulumi/pulumi-azuredevops</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azuredevops` Terraform Provider](https://github.com/microsoft/terraform-provider-azuredevops).{{% /md %}}</dd>
</dl>

