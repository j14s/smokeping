# Smokeping Chart(Helm v3)

This chart deploys SmokePing

## Introduction

This chart leverages the excellent [container work of the Linux Server group](https://github.com/linuxserver/docker-smokeping)


## Official Documentation

Official SmokePing project documentation found [here](https://oss.oetiker.ch/smokeping/)

## Prerequisites

- Helm v3.X
- Kubernetes 1.4+ with Beta APIs enabled
- __Suggested:__ PV provisioner support in the underlying infrastructure to support backups of etcd

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
$ git clone https://github.com/j14s/smokeping
$ edit smokeping/config/Targets to your liking.
$ helm install my-release ./smokeping
```

__Note__: By default this installs without provisioning a PVC. Use '--set persistence.enabled=true' to provision a PVC on deployment

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
$ helm delete my-release
```

The command removes all the Kubernetes components EXCEPT the persistent volume.

## Configuration

The following table lists the configurable parameters of the zetcd chart and their default values. Check the etcd-operator chart for additional configuration options

| Parameter                                         | Description                                                          | Default                                        |
| ------------------------------------------------- | -------------------------------------------------------------------- | ---------------------------------------------- |
| `persistence.enabled`                             | Provision a PVC                                                      | `false`                                        |


Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example:

```bash
$ helm install my-release --set persistence.enabled=true
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while
installing the chart. For example:

```bash
$ helm install my-release -f values.yaml stable/zetcd
```