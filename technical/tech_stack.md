# TechOverflow

## Principles & Guidelines

We follow in its entirety:
- https://github.com/zalando/engineering-principles
- https://opensource.zalando.com/restful-api-guidelines/

We use Zally to verify -- https://github.com/zalando/zally

We follow the principles defined in:
```
Accelerate: The Science of Lean Software and DevOps: Building and Scaling High Performing Technology Organizations 
http://a.co/d/59dKG2d

1. Optimize for code-to-production
2. Optimize for Mean-time-to-failure
3. Optimize for Mean-time-to-resolution
```

In general; automate everything, avoid bloated, general-purpose libraries that come with too many goodies

## Tech stack

Although we've made our first picks, the technology choices are all up for discussion.

1. Container orchestration: Kubernetes
1. Build: Maven, Docker, CI/CD
1. Source code analysis: Black duck or White source
1. Continuous security: Security Monkey and OWASP ZAP
1. Journey tests: Locust.io
1. Performance tests: Locust.io  

### Microservice & Network related 
1. Service mesh: Istio
1. Service-to-Service TLS: Istio
1. Identity: Istio + JWT -- https://istio.io/docs/concepts/security/
1. Circuit-breaker: Istio + nginmesh as replacement of Envoy (maybe?)
1. Bulkhead: Istio
1. Traffic shaping: Istio
1. A/B testing: Istio
1. Canaries: Istio
1. Service lookups: Kubernetes DNS
1. API Gateway: GraphQL
1. Web: React + Graphql and/or Redux (to be decided)


# Java
1. CQRS & Event sourcing: Axon framework 
1. Webserver: Micronaut or alternatively Undertow or Ratpack
1. Tests: Axon framework + Fongo, but also Micronaut testing
1. Clean-code: Lombok

### Messaging
Potentially Nakadi.io in combination with Rabbit

### Monitoring / Dashboards

1. Redash for custom (business) dashboards
1. Istio sidecar generated metrics using Prometheus, Grafana
1. Sentry exception capturing
1. PagerDuty (or similar)
1. Central logging (undecided)
1. Tracing using Jaeger, OpenZipkin or AWS equivalent 

### AWS

We'll use AWS as cloud provider
