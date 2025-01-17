---
title: jaeger
type: tracer
status: stable
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/tracer/jaeger.go
-->

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


Send spans to a [Jaeger](https://www.jaegertracing.io/) agent.


<Tabs defaultValue="common" values={[
  { label: 'Common', value: 'common', },
  { label: 'Advanced', value: 'advanced', },
]}>

<TabItem value="common">

```yaml
# Common config fields, showing default values
tracer:
  jaeger:
    agent_address: localhost:6831
    collector_url: ""
    service_name: benthos
    sampler_type: const
    flush_interval: ""
```

</TabItem>
<TabItem value="advanced">

```yaml
# All config fields, showing default values
tracer:
  jaeger:
    agent_address: localhost:6831
    collector_url: ""
    service_name: benthos
    sampler_type: const
    sampler_manager_address: ""
    sampler_param: 1
    tags: {}
    flush_interval: ""
```

</TabItem>
</Tabs>

## Fields

### `agent_address`

The address of a Jaeger agent to send tracing events to.


Type: `string`  
Default: `"localhost:6831"`  

```yaml
# Examples

agent_address: jaeger-agent:6831
```

### `collector_url`

The URL of a Jaeger collector to send tracing events to. If set, this will override `agent_address`.


Type: `string`  
Default: `""`  

```yaml
# Examples

collector_url: https://jaeger-collector:14268/api/traces
```

### `service_name`

A name to provide for this service.


Type: `string`  
Default: `"benthos"`  

### `sampler_type`

The sampler type to use.


Type: `string`  
Default: `"const"`  

| Option | Summary |
|---|---|
| `const` | A constant decision for all traces, either 1 or 0. |
| `probabilistic` | The sampler makes a random sampling decision with the probability of sampling equal to the value of sampler param. |
| `ratelimiting` | The sampler uses a leaky bucket rate limiter to ensure that traces are sampled with a certain constant rate. |
| `remote` | The sampler consults Jaeger agent for the appropriate sampling strategy to use in the current service. |


### `sampler_manager_address`

An optional address of a sampler manager.


Type: `string`  
Default: `""`  

### `sampler_param`

A parameter to use for sampling. This field is unused for some sampling types.


Type: `number`  
Default: `1`  

### `tags`

A map of tags to add to tracing spans.


Type: `object`  
Default: `{}`  

### `flush_interval`

The period of time between each flush of tracing spans.


Type: `string`  
Default: `""`  


