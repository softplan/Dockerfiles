OpenShift Application Platform
==============================

[![Go Report Card](https://goreportcard.com/badge/github.com/openshift/origin)](https://goreportcard.com/report/github.com/openshift/origin)
[![GoDoc](https://godoc.org/github.com/openshift/origin?status.png)](https://godoc.org/github.com/openshift/origin)
[![Travis](https://travis-ci.org/openshift/origin.svg?branch=master)](https://travis-ci.org/openshift/origin)
[![Jenkins](https://ci.openshift.redhat.com/jenkins/buildStatus/icon?job=devenv_ami)](https://ci.openshift.redhat.com/jenkins/job/devenv_ami/)
[![Join the chat at freenode:openshift-dev](https://img.shields.io/badge/irc-freenode%3A%20%23openshift--dev-blue.svg)](http://webchat.freenode.net/?channels=%23openshift-dev)
[![Licensed under Apache License version 2.0](https://img.shields.io/github/license/openshift/origin.svg?maxAge=2592000)](https://www.apache.org/licenses/LICENSE-2.0)

***OpenShift Origin*** is a distribution of [Kubernetes](https://kubernetes.io) optimized for continuous application development and multi-tenant deployment.  OpenShift adds developer and operations-centric tools on top of Kubernetes to enable rapid application development, easy deployment and scaling, and long-term lifecycle maintenance for small and large teams.

[![Watch the full asciicast](https://github.com/openshift/origin/blob/master/docs/openshift-intro.gif)](https://asciinema.org/a/49402)

**Features:**

* Easily build applications with integrated service discovery and persistent storage.
* Quickly and easily scale applications to handle periods of increased demand.
  * Support for automatic high availability, load balancing, health checking, and failover.
* Push source code to your Git repository and automatically deploy containerized applications.
* Web console and command-line client for building and monitoring applications.
* Centralized administration and management of an entire stack, team, or organization.
  * Create reusable templates for components of your system, and iteratively deploy them over time.
  * Roll out modifications to software stacks to your entire organization in a controlled fashion.
  * Integration with your existing authentication mechanisms, including LDAP, Active Directory, and public OAuth providers such as GitHub.
* Multi-tenancy support, including team and user isolation of containers, builds, and network communication.
  * Allow developers to run containers securely with fine-grained controls in production.
  * Limit, track, and manage the developers and teams on the platform.
* Integrated Docker registry, automatic edge load balancing, cluster logging, and integrated metrics.

**Learn More:**

* **[Public Documentation](https://docs.openshift.org/latest/welcome/)**
  * **[API Documentation](https://docs.openshift.org/latest/rest_api/openshift_v1.html)**
* Our **[Trello Roadmap](https://ci.openshift.redhat.com/roadmap_overview.html)** covers the epics and stories being worked on (click through to individual items)

For questions or feedback, reach us on [IRC on #openshift-dev](https://botbot.me/freenode/openshift-dev/) on Freenode or post to our [mailing list](https://lists.openshift.redhat.com/openshiftmm/listinfo/dev).

Getting Started
---------------

### Installation

If you have downloaded the client tools from the [releases page](https://github.com/openshift/origin/releases), place the included binaries in your PATH.

* On any system with a Docker engine installed, you can run `oc cluster up` to get started immediately.  Try it out now!
* For a full cluster installation using [Ansible](https://github.com/openshift/openshift-ansible), follow the [Advanced Installation guide](https://docs.openshift.org/latest/install_config/install/advanced_install.html)
* To build and run from source, see [CONTRIBUTING.adoc](CONTRIBUTING.adoc)

### Concepts

OpenShift builds a developer-centric workflow around Docker containers and Kubernetes runtime concepts.  An **Image Stream** lets you easily tag, import, and publish Docker images from the integrated registry.  A **Build Config** allows you to launch Docker builds, build directly from source code, or trigger Jenkins Pipeline jobs whenever an image stream tag is updated.  A **Deployment Config** allows you to redeploy whenever a new image becomes available.  **Routes** make it trivial to expose your Kubernetes services via a public DNS name. As an administrator, you can enable your developers to request new **Projects** which come with predefined roles, quotas, and security controls to fairly divide access.

For more on the underlying concepts of OpenShift, please see the [documentation site](https://docs.openshift.org/latest/welcome/index.html).

### How to use this image

Run docker build to create an image. 

```bash
$ [sudo] docker build -t openshift-cli .
```

You can run `oc` client inside a docker container:

```bash
$ [sudo] docker run -it openshift-cli /bin/sh
$# oc login https://my-master-openshift.io
```
