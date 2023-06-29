# OPA Gatekeeper tutorial

## Overview

OPA Gatekeeper is a policy-as-code agent for inbound Kubernetes resource manifests. 

## Prerequisite

### Skills

* Rego policy language

* Kubernetes

### In your local machine

* minikube CLI

* kubectl CLI

* gator CLI - [Link](https://open-policy-agent.github.io/gatekeeper/website/docs/gator/)

* task CLI - [Link](https://taskfile.dev/installation/)

## Content List

* `constraint_templates` folder
  * Templates that contains local (`constraint_templates/in_house`) policies,
  * Kustomization YAML file (`constraint_templates/kustomization.yaml`) that import local policies and some policies from Gatekeeper policy library.

* `constraints` folder
  * Constraint YAML files that derived from templates from `constraint_templates` folder.

* `tests` folder
  * Test suite to test `constraint_templates/in_house` policy templates and policies.

* `config.yaml` file
  * Config YAML file that used to customize cluster-wide policy configurations.

* `Taskfile.yaml` file
  * Taskfile YAML file that used to automate scripts declaratively.

## Steps

Assume you have minikube set up. Steps below will setup basic constraints enforcement in it.

1. Run `task bootstrap`,

2. Run `task apply-templates`,

3. Run `task apply-constraints`,

4. To test policy enforcement against your minikube, you may apply the manifests in `tests/input`.