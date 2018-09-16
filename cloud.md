# Cloud computing
Type of internet based computing that provides shared computer processing resources and data.

- "bare metal" server with a virtualization layer on top of it
- IaaS: infrastructure as a service (e.g. OpenStack)
- PaaS: platform as a service
- SaaS: software as a service

## Table of contents
* [OpenStack](#openstack)
* [VM](#vm)
* [Cgroups and namespaces](#cgroups-ang-namespaces)
* [LXC](#lxc)
* [Docker](#docker)
* [Kubernetes](#kubernetes)
* [See also](#see-also)

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

## VM
(source: [Virtual Machine])
>Virtual machine (VM) is an emulation of a computer system. Virtual machines are based on computer architectures and provide functionality of a physical computer. Their implementations may involve specialized hardware, software, or a combination.

>Some virtual machines, such as QEMU, are designed to also emulate different architectures and allow execution of software applications and operating systems written for another CPU or architecture.

>Operating-system-level virtualization allows the resources of a computer to be partitioned via the kernel's support for multiple isolated user space instances

![vm](https://www.veeam.com/blog/wp-content/uploads/2015/10/2015-Q4-Physical-Servers-vs-VMs.png)

[img source](https://www.veeam.com/blog/why-virtual-machine-backups-different.html)

VM emulates hardware and kernel (see picture on the right) - this can have a negative impact on a performance.

## Cgroups and namespaces
(source: [difference between cgroups and namespaces])

## LXC
todo

## Docker
todo

## Kubernetes
todo

## See also
- [What Is OpenStack | OpenStack Tutorial For Beginners | OpenStack Training | Edureka] (YouTube)
- [Virtual Machine] (Wikipedia)
- [difference between cgroups and namespaces] (StackOverflow)
- [Containers: cgroups, Linux kernel namespaces, ufs, Docker, and intro to Kubernetes pods] (YouTube)


[What Is OpenStack | OpenStack Tutorial For Beginners | OpenStack Training | Edureka]: https://www.youtube.com/watch?v=Kfj5XiNdJN0
[difference between cgroups and namespaces]: https://stackoverflow.com/a/34825184
[Virtual Machine]: https://en.wikipedia.org/wiki/Virtual_machine
[Containers: cgroups, Linux kernel namespaces, ufs, Docker, and intro to Kubernetes pods]: https://www.youtube.com/watch?v=el7768BNUPw
