<!-- Code generated by solo-kit. DO NOT EDIT. -->

### Package: `kubernetes.plugins.gloo.solo.io` 
##### Types:


- [UpstreamSpec](#UpstreamSpec)
  



##### Source File: [github.com/solo-io/gloo/projects/gloo/api/v1/plugins/kubernetes/kubernetes.proto](https://github.com/solo-io/gloo/blob/master/projects/gloo/api/v1/plugins/kubernetes/kubernetes.proto)





---
### <a name="UpstreamSpec">UpstreamSpec</a>

 
Upstream Spec for Kubernetes Upstreams
Kubernetes Upstreams represent a set of one or more addressable pods for a Kubernetes Service
the Gloo Kubernetes Upstream maps to a single service port. Because Kubernetes Services support mulitple ports,
Gloo requires that a different upstream be created for each port
Kubernetes Upstreams are typically generated automatically by Gloo from the Kubernetes API

```yaml
"service_name": string
"service_namespace": string
"service_port": int
"selector": map<string, string>
"service_spec": .plugins.gloo.solo.io.ServiceSpec

```

| Field | Type | Description | Default |
| ----- | ---- | ----------- |----------- | 
| `service_name` | `string` | The name of the Kubernetes Service |  |
| `service_namespace` | `string` | The namespace where the Service lives |  |
| `service_port` | `int` | The access port port of the kubernetes service is listening. This port is used by Gloo to look up the corresponding port on the pod for routing. |  |
| `selector` | `map<string, string>` | Allows finer-grained filtering of pods for the Upstream. Gloo will select pods based on their labels if any are provided here. (see [Kubernetes labels and selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/) |  |
| `service_spec` | [.plugins.gloo.solo.io.ServiceSpec](../service_spec.proto.sk.md#ServiceSpec) | An optional Service Spec describing the service listening at this address |  |





<!-- Start of HubSpot Embed Code -->
<script type="text/javascript" id="hs-script-loader" async defer src="//js.hs-scripts.com/5130874.js"></script>
<!-- End of HubSpot Embed Code -->