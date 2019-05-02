---
title: Module servicenetworking
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->

<a href="../index.html">@pulumi/gcp</a> &gt; servicenetworking

<div class="toggleVisible" markdown="1">
<div class="collapsed" markdown="1">
<h2 class="pdoc-module-header toggleButton" title="Click to show Index">Index ▹</h2>
</div>
<div class="expanded" markdown="1">
<h2 class="pdoc-module-header toggleButton" title="Click to hide Index">Index ▾</h2>
<div class="pdoc-module-contents" markdown="1">
* <a href="#Connection">class Connection</a>
* <a href="#ConnectionArgs">interface ConnectionArgs</a>
* <a href="#ConnectionState">interface ConnectionState</a>

<a href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts">servicenetworking/connection.ts</a> 
</div>
</div>
</div>


<h2 class="pdoc-module-header" id="Connection">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L36">class <b>Connection</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">
<pre class="highlight"><span class='kd'>extends</span> <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#CustomResource'>CustomResource</a></pre>

> **Warning:** This resource is in beta, and should be used with the terraform-provider-google-beta provider.
See [Provider Versions](https://terraform.io/docs/providers/google/provider_versions.html) for more details on beta resources.

Manages a private VPC connection with a GCP service provider. For more information see
[the official documentation](https://cloud.google.com/vpc/docs/configure-private-services-access#creating-connection)
and
[API](https://cloud.google.com/service-infrastructure/docs/service-networking/reference/rest/v1/services.connections).

## Example usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const peeringNetwork = new gcp.compute.Network("peering_network", {});
const privateIpAlloc = new gcp.compute.GlobalAddress("private_ip_alloc", {
    addressType: "INTERNAL",
    network: peeringNetwork.selfLink,
    prefixLength: 16,
    purpose: "VPC_PEERING",
});
const foobar = new gcp.servicenetworking.Connection("foobar", {
    network: peeringNetwork.selfLink,
    reservedPeeringRanges: [privateIpAlloc.name],
    service: "servicenetworking.googleapis.com",
});
```

<h3 class="pdoc-member-header" id="Connection-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L64"> <b>constructor</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'></span><span class='kd'>new</span> Connection(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, args: <a href='#ConnectionArgs'>ConnectionArgs</a>, opts?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>)</pre>


Create a Connection resource with the given unique name, arguments, and options.

* `name` The _unique_ name of the resource.
* `args` The arguments to use to populate this resource&#39;s properties.
* `opts` A bag of options that control this resource&#39;s behavior.

</div>
<h3 class="pdoc-member-header" id="Connection-get">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L45">method <b>get</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'>public static </span>get(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, id: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#ID'>pulumi.ID</a>&gt;, state?: <a href='#ConnectionState'>ConnectionState</a>, opts?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>): <a href='#Connection'>Connection</a></pre>


Get an existing Connection resource's state with the given name, ID, and optional extra
properties used to qualify the lookup.

</div>
<h3 class="pdoc-member-header" id="Connection-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L14">method <b>getProvider</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): ProviderResource | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></pre>

</div>
<h3 class="pdoc-member-header" id="Connection-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L101">method <b>isInstance</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">

<pre class="highlight"><span class='kd'>static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span></pre>


Returns true if the given object is an instance of CustomResource.  This is designed to work even when
multiple copies of the Pulumi SDK have been loaded into the same process.

</div>
<h3 class="pdoc-member-header" id="Connection-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L96">property <b>id</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>id: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>Output</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#ID'>ID</a>&gt;;</pre>

id is the provider-assigned unique ID for this managed resource.  It is set during
deployments and may be missing (undefined) during planning phases.

</div>
<h3 class="pdoc-member-header" id="Connection-network">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L52">property <b>network</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>network: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Name of VPC network connected with service producers using VPC peering.

</div>
<h3 class="pdoc-member-header" id="Connection-reservedPeeringRanges">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L58">property <b>reservedPeeringRanges</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>reservedPeeringRanges: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>[]&gt;;</pre>

Named IP address range(s) of PEERING type reserved for
this service provider. Note that invoking this method with a different range when connection
is already established will not reallocate already provisioned service producer subnetworks.

</div>
<h3 class="pdoc-member-header" id="Connection-service">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L64">property <b>service</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'>public </span>service: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Provider peering service that is managing peering connectivity for a
service provider organization. For Google services that support this functionality it is
'servicenetworking.googleapis.com'.

</div>
<h3 class="pdoc-member-header" id="Connection-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L12">property <b>urn</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>urn: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Output'>Output</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#URN'>URN</a>&gt;;</pre>

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

</div>
</div>
<h2 class="pdoc-module-header" id="ConnectionArgs">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L125">interface <b>ConnectionArgs</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

The set of arguments for constructing a Connection resource.

<h3 class="pdoc-member-header" id="ConnectionArgs-network">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L129">property <b>network</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>network: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Name of VPC network connected with service producers using VPC peering.

</div>
<h3 class="pdoc-member-header" id="ConnectionArgs-reservedPeeringRanges">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L135">property <b>reservedPeeringRanges</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>reservedPeeringRanges: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;[]&gt;;</pre>

Named IP address range(s) of PEERING type reserved for
this service provider. Note that invoking this method with a different range when connection
is already established will not reallocate already provisioned service producer subnetworks.

</div>
<h3 class="pdoc-member-header" id="ConnectionArgs-service">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L141">property <b>service</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>service: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Provider peering service that is managing peering connectivity for a
service provider organization. For Google services that support this functionality it is
'servicenetworking.googleapis.com'.

</div>
</div>
<h2 class="pdoc-module-header" id="ConnectionState">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L103">interface <b>ConnectionState</b></a>
</h2>
<div class="pdoc-module-contents" markdown="1">

Input properties used for looking up and filtering Connection resources.

<h3 class="pdoc-member-header" id="ConnectionState-network">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L107">property <b>network</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>network?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Name of VPC network connected with service producers using VPC peering.

</div>
<h3 class="pdoc-member-header" id="ConnectionState-reservedPeeringRanges">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L113">property <b>reservedPeeringRanges</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>reservedPeeringRanges?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;[]&gt;;</pre>

Named IP address range(s) of PEERING type reserved for
this service provider. Note that invoking this method with a different range when connection
is already established will not reallocate already provisioned service producer subnetworks.

</div>
<h3 class="pdoc-member-header" id="ConnectionState-service">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-gcp/blob/65c7a44d62f0ea5edd3833c6f7b1f0c253503f0f/sdk/nodejs/servicenetworking/connection.ts#L119">property <b>service</b></a>
</h3>
<div class="pdoc-member-contents" markdown="1">
<pre class="highlight"><span class='kd'></span>service?: <a href='https://pulumi.io/reference/pkg/nodejs/@pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>

Provider peering service that is managing peering connectivity for a
service provider organization. For Google services that support this functionality it is
'servicenetworking.googleapis.com'.

</div>
</div>