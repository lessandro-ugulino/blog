+++
title = "Debugging Kubernetes cluster pt.2"
date = "2021-11-19"
description = "Troubleshooting steps to help you understand a fix some K8s issues - part 2"
nofeed = true
math = true
notaxonomy = false
commentable = true
hidden = false
norobots = true
nodate = false
hidemeta = false
+++

### Related Articles

[Debugging Kubernetes cluster — part1](https://blog.ugulino.com/posts/19_oct_21/)

### Requirements

1. Install [Krew](https://krew.sigs.k8s.io/docs/user-guide/setup/install/?utm_source=thenewstack&utm_medium=website&utm_campaign=platform")

2. Install *resource-capacity* plugin

`kubectl krew install resource-capacity`

3. Install *lineage* plugin

`kubectl krew install lineage`

4. Install [kail](https://github.com/boz/kail).

5. Install *blame* plugin

`kubectl krew install blame`

### Troubleshooting commands

1. `kubectl get events — field-selector type=Warning — all-namespaces`

![Image alt](images/get_events.png)

This command will show all warnings events in the cluster.

2. `kubectl get nodes -o wide — label-columns topology.kubernetes.io/zone`