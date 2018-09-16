# Cloud computing
Type of internet based computing that provides shared computer processing resources and data.

- "bare metal" server with a virtualization layer on top of it
- IaaS: infrastructure as a service (e.g. OpenStack)
- PaaS: platform as a service
- SaaS: software as a service

## OpenStack
- gives components to set up cloud infrastructure, provides set of tools and services
- backed up by big IT companies

![OpenStack architecture](img/open-stack-architecture.png)

(source: [What Is OpenStack | OpenStack Tutorial For Beginners | OpenStack Training | Edureka])

- Keystone: authentication service (users and privilages)
- Glance: launches instances from the images (e.g. Gentoo, Debian, CentOS)
- Nova: computing domain
- Neutron: networking service, responsible for communication between services
- Swift: object storage component
- Cinder: block storage component
- Horizon: dashboard
- Ceilometer: part of telemetric project
- Heat: part of orchestration program.
>The mission of the OpenStack Orchestration program is to create a human- and machine-accessible service for managing the entire lifecycle of infrastructure and applications within OpenStack clouds.

## See also
- [What Is OpenStack | OpenStack Tutorial For Beginners | OpenStack Training | Edureka] (YouTube)

[What Is OpenStack | OpenStack Tutorial For Beginners | OpenStack Training | Edureka]: https://www.youtube.com/watch?v=Kfj5XiNdJN0
