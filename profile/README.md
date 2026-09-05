# kgxlabs

**Building an infrastructure stack and a platform for deploying complete applications.**

kgxlabs is the home of [kgx](https://github.com/kgxlabs), an infrastructure platform under development. The goal is to let developers deploy and operate complete applications, including frontends, backend services, databases, and caches, through one integrated platform.

We are building the underlying infrastructure components alongside the systems that provision compute, run workloads, connect services, and manage deployments. Each component has a focused responsibility within the larger stack, with standalone use where practical.

## The deployment experience

A developer should be able to describe an application and its dependencies, then let kgx prepare the infrastructure and bring it online. The platform will coordinate compute provisioning, workload execution, networking, configuration, and service lifecycle management.

The goal extends beyond the first successful deployment: users should be able to inspect application health and logs, release updates, roll back changes, and recover persistent data.

## The infrastructure stack

The initial direction spans the following areas. These describe the intended architecture, not a list of completed capabilities. More components may emerge as the platform develops.

| Area | Intended responsibility |
| --- | --- |
| HTTP | Serve and route application traffic through [kghttp](https://github.com/kgxlabs/kghttp) |
| Database | Store and retrieve durable application data |
| Cache | Provide in-memory caching through [kgcache](https://github.com/kgxlabs/kgcache) |
| Container runtime | Execute and isolate application workloads |
| Deployment orchestration | Provision resources and coordinate application releases and service lifecycles |
| Supporting systems | Provide networking, persistent storage, configuration, secrets, identity, and observability as the platform requires |

### Projects

- [kghttp](https://github.com/kgxlabs/kghttp): an HTTP layer written in Go, providing an HTTP/1.1 client and server, request and response parsing, and transfer handling. It is being developed as the HTTP foundation of kgx.
- [kgcache](https://github.com/kgxlabs/kgcache): an in-memory cache server written in Zig, evolving toward a drop-in Redis replacement and the cache layer of kgx. It currently implements a subset of Redis functionality and is not yet a drop-in replacement.

## Three-year roadmap

The target is a working end-to-end application deployment platform within three years. These milestones express the intended progression; scope and sequencing will evolve with implementation experience.

| Stage | Target outcome |
| --- | --- |
| Year 1: foundations | Develop the initial infrastructure components and establish a repeatable path to deploy a small application using kgx components. |
| Year 2: integration | Bring frontend, backend, database, and cache services together with networking, configuration, and persistent storage in a complete application deployment. |
| Year 3: operations | Support ongoing operation through health visibility, updates, rollback, backup, and recovery, and validate the integrated stack with real applications. |

This organization README owns the platform vision and roadmap. Component repositories document their implementation, supported behavior, and current limitations.

## Current status

[kgx](https://github.com/kgxlabs) is an early-stage development effort. The integrated platform described here is the destination being built toward. Follow the linked project repositories for implemented capabilities and ongoing work.

- [kghttp](https://github.com/kgxlabs/kghttp): implements an HTTP/1.1 client and server in Go, including request and response parsing, chunked transfer handling, and trailers.
- [kgcache](https://github.com/kgxlabs/kgcache): implements a subset of Redis functionality over RESP2 in Zig, including string storage, expiration, snapshots, and append-only persistence. It is not yet a drop-in Redis replacement.

Both components are under active development. See their repositories for supported behavior, usage, and known limitations.
