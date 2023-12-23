# nplus-instance

Umbrella chart to install various components and applications bundled

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install my-release nplus/nplus-instance
```

> Please read the documentation (like the **quick start guide**) before installing this chart. There are prerequisites which
> will make this release fail if not met.

## nplus-instance Chart Configuration

| Key | Description | Default |
|-----|-------------|---------|
global.database.account | DB account (if not using a secret) | `"nscale"` |
global.database.dialect | nscale DB server dialect | internal Postgres |
global.database.driverclass | nscale DB server driverclass | internal Postgres |
global.database.name | name of the nscale DB | internal Postgres |
global.database.password | DB password (if not using a secret) | `"nscale"` |
global.database.passwordEncoded | weather the password is stored encrypted | `"false"` |
global.database.schema | DB schema name | internal Postgres |
global.database.secret | DB credential secret (account, password) | none - using credentials |
global.database.url | The URL to the database | internal Postgres |
global.environment.ingress.class |  | `"public"` |
global.environment.ingress.domain |  |  |
global.environment.ingress.issuer |  |  |
global.environment.ingress.proxyip |  | `"0.0.0.0/0"` |
global.environment.storage.data.class |  |  |
global.environment.storage.file.class |  |  |
global.ingress.appRoot |  | `"/nscale_web"` |
global.ingress.domain |  |  |
global.instance.name |  | `"{{ .Release.Name }}"` |
global.license |  | `"nscale-license"` |
global.nappl.host |  | `"{{ include \"nplus.prefix\" . }}nappl.{{ .Release.Namespace }}"` |
global.nappl.instance |  | `"nscalealinst1"` |
global.nappl.port |  | `"8080"` |
global.nappl.ssl |  | `"0"` |
global.waitImage.name |  | `"wait"` |
global.waitImage.repo |  | `"cr.nplus.cloud/42i"` |
global.waitImage.tag |  | `"latest"` |
application.nappl.account |  | `"admin"` |
application.nappl.domain |  | `"nscale"` |
application.nappl.host |  | `"{{ include \"nplus.prefix\" . }}nappl.{{ .Release.Namespace }}"` |
application.nappl.instance |  | `"nscalealinst1"` |
application.nappl.password |  | `"admin"` |
application.nappl.port |  | `"8080"` |
application.nappl.secret |  |  |
application.nappl.ssl |  | `"0"` |
application.nstl |  | `"{{ include \"nplus.prefix\" . }}nstl.{{ .Release.Namespace }}"` |
application.rs |  | `"{{ include \"nplus.prefix\" . }}rs.{{ .Release.Namespace }}"` |
application.waitFor[0] |  | `"{{ include \"nplus.prefix\" . }}nappl.{{ .Release.Namespace }}.svc.cluster.local:8080 -t 1800"` |
application.wave |  | `3` |
components.application |  | `false` |
components.cmis |  | `false` |
components.database |  | `true` |
components.ilm |  | `false` |
components.mon |  | `false` |
components.nappl | defines if a nappl is included in this instance | `true` |
components.nappljobs | defines if a nappljobs should be used. please also make sure to check for the jobs setting | `false` |
components.nstl |  | `true` |
components.pipeliner |  | `false` |
components.rs |  | `true` |
components.web | defines if this instance includes a web component | `true` |
application.image.name |  | `"application-layer"` |
application.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
application.image.tag |  | `"ubi.9.1.1201.2023112921"` |
application.mounts.conf.path |  | `"/application"` |
application.mounts.pool.path |  | `"/pool"` |
application.nappl.account |  |  |
application.nappl.host |  |  |
application.nappl.instance |  |  |
application.nappl.password |  |  |
application.nappl.port |  |  |
application.nappl.secret |  |  |
application.nappl.ssl |  |  |
application.nstl |  |  |
application.rs |  |  |
application.wave |  |  |
cmis.image.name |  | `"cmis-connector"` |
cmis.image.pullPolicy |  | `"IfNotPresent"` |
cmis.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
cmis.image.tag |  | `"ubi.9.1.1200.2023112711"` |
cmis.ingress.backendProtocol |  | `"http"` |
cmis.ingress.enabled |  | `true` |
cmis.mounts.conf.path |  | `"/opt/ceyoniq/nscale-cmis-connector/conf"` |
cmis.mounts.temp.path |  | `"/opt/ceyoniq/nscale-cmis-connector/temp"` |
cmis.mounts.temp.size |  | `"1Gi"` |
cmis.replicaCount |  | `1` |
cmis.wave |  |  |
database.adminAccount | the database admin account, if not set by secret | `"postgres"` |
database.adminPassword | the database admin password, if not set by secret | `"postgres"` |
database.adminSecret | the secret with credentials (account, password) for the database admin account. This setting has priority over adminAccount and adminPassword |  |
database.image.name |  | `"postgres"` |
database.image.tag |  | `15` |
database.mounts.data.paths[0] |  | `"/var/lib/postgresql/data"` |
database.mounts.data.size |  | `"30Gi"` |
database.nscaleAccount | the technical account to own the nscale database, if not set by secret |  |
database.nscaleDB | name of the nscale database |  |
database.nscalePassword | password of the technical account, if not set by secret |  |
database.nscaleSecret | the secret with credentials (account, password) for the nscale technical account. This setting has priority over account and password |  |
database.replicaCount |  | `1` |
ilm.image.name |  | `"ilm-connector"` |
ilm.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
ilm.image.tag |  | `"ubi.9.1.1100.2023102502"` |
ilm.ingress.backendProtocol |  | `"http"` |
ilm.ingress.enabled |  | `true` |
ilm.mounts.conf.path |  | `"/opt/ceyoniq/nscale-for-sap/erp-connector-ilm/conf"` |
ilm.mounts.temp.path |  | `"/opt/ceyoniq/nscale-for-sap/erp-connector-ilm/temp"` |
ilm.mounts.temp.size |  | `"1Gi"` |
ilm.nappl.account |  |  |
ilm.nappl.host |  |  |
ilm.nappl.instance |  |  |
ilm.nappl.password |  |  |
ilm.nappl.port |  |  |
ilm.nappl.secret |  |  |
ilm.nappl.ssl |  |  |
ilm.replicaCount |  | `1` |
mon.image.name |  | `"monitoring-console"` |
mon.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
mon.image.tag |  | `"ubi.9.1.1000.2023091818"` |
mon.ingress.backendProtocol |  | `"http"` |
mon.ingress.enabled |  | `true` |
mon.mounts.conf.path |  | `"/opt/ceyoniq/nscale-monitoring/workspace"` |
mon.mounts.data.paths[0] |  | `"/opt/ceyoniq/nscale-monitoring/workspace/.metadata"` |
mon.mounts.data.size |  | `"10Gi"` |
mon.mounts.license.path |  | `"/opt/ceyoniq/nscale-monitoring/workspace/license.xml"` |
mon.replicaCount |  | `1` |
nappl.database.account | alternative 1: the account name of the technical DB user for nscale |  |
nappl.database.dialect | the database dialect to use |  |
nappl.database.driverclass | the driver class to use |  |
nappl.database.name | the name of the database to use | `""` |
nappl.database.password | alternative 1: the password of the technical DB user for nscale |  |
nappl.database.passwordEncoded | weather the DB password is stored encrypted |  |
nappl.database.schema | the database schema to use |  |
nappl.database.secret | alternative 2: use a secret for the account and password |  |
nappl.database.url | the DB URL |  |
nappl.image.name |  | `"application-layer"` |
nappl.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
nappl.image.tag |  | `"ubi.9.1.1201.2023112921"` |
nappl.ingress.backendProtocol |  | `"https"` |
nappl.ingress.enabled |  | `false` |
nappl.ingress.includeDefaultPaths |  | `true` |
nappl.ingress.inputPath |  | `"/nscalealinst1"` |
nappl.jobs |  | `true` |
nappl.mounts.conf.path |  | `"/opt/ceyoniq/nscale-server/application-layer/conf"` |
nappl.mounts.license.path |  | `"/opt/ceyoniq/nscale-server/application-layer/conf/license.xml"` |
nappl.mounts.logs.path |  | `"/opt/ceyoniq/nscale-server/application-layer/logs"` |
nappl.mounts.logs.size |  | `"1Gi"` |
nappl.mounts.temp.path |  | `"/opt/ceyoniq/nscale-server/application-layer/temp"` |
nappl.mounts.temp.size |  | `"5Gi"` |
nappl.nodeSelector | Kubernetes [`nodeSelector`](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector) to add to the Deployment. | `{}` |
nappl.priorityClassName | Set the priority class for the Application Layer deployment if desired |  |
nappl.replicaCount |  | `1` |
nappl.tolerations | List of Kubernetes [`tolerations`](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/) to add to the Deployment. | `[]` |
nappl.updateStrategy |  | `"RollingUpdate"` |
nappl.wave |  |  |
nappljobs.database.account | alternative 1: the account name of the technical DB user for nscale |  |
nappljobs.database.dialect | the database dialect to use |  |
nappljobs.database.driverclass | the driver class to use |  |
nappljobs.database.name | the name of the database to use | `""` |
nappljobs.database.password | alternative 1: the password of the technical DB user for nscale |  |
nappljobs.database.passwordEncoded | weather the DB password is stored encrypted |  |
nappljobs.database.schema | the database schema to use |  |
nappljobs.database.secret | alternative 2: use a secret for the account and password |  |
nappljobs.database.url | the DB URL |  |
nappljobs.image.name |  | `"application-layer"` |
nappljobs.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
nappljobs.image.tag |  | `"ubi.9.1.1201.2023112921"` |
nappljobs.ingress.backendProtocol |  | `"https"` |
nappljobs.ingress.enabled |  | `false` |
nappljobs.ingress.includeDefaultPaths |  | `true` |
nappljobs.ingress.inputPath |  | `"/nscalealinst1"` |
nappljobs.jobs |  | `true` |
nappljobs.mounts.conf.path |  | `"/opt/ceyoniq/nscale-server/application-layer/conf"` |
nappljobs.mounts.license.path |  | `"/opt/ceyoniq/nscale-server/application-layer/conf/license.xml"` |
nappljobs.mounts.logs.path |  | `"/opt/ceyoniq/nscale-server/application-layer/logs"` |
nappljobs.mounts.logs.size |  | `"1Gi"` |
nappljobs.mounts.temp.path |  | `"/opt/ceyoniq/nscale-server/application-layer/temp"` |
nappljobs.mounts.temp.size |  | `"5Gi"` |
nappljobs.nodeSelector | Kubernetes [`nodeSelector`](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector) to add to the Deployment. | `{}` |
nappljobs.priorityClassName | Set the priority class for the Application Layer deployment if desired |  |
nappljobs.replicaCount |  | `1` |
nappljobs.tolerations | List of Kubernetes [`tolerations`](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/) to add to the Deployment. | `[]` |
nappljobs.updateStrategy |  | `"RollingUpdate"` |
nappljobs.wave |  |  |
nstl.checkHighestDocId | enables checking the highest DocID when starting the server. this only makes sense, if you also set a separate volume for the highest ID This is a backup / restore feature to avoid data mangling | `"0"` |
nstl.dvCheckPath | sets the path of the highest ID file. |  |
nstl.image.name |  | `"storage-layer"` |
nstl.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
nstl.image.tag |  | `"ubi.9.1.1200.2023112112"` |
nstl.mounts.data.class | Sets the class of the data disk |  |
nstl.mounts.data.size | Sets the size of the data disk | `"50Gi"` |
nstl.mounts.logs.medium | the medium for the emptyDisk volume if you unset it, it drops it from the manifest |  |
nstl.mounts.logs.size | the sizeLimit for the emptyDisk volume if you unset it, it uses cluster defaults | `"10Gi"` |
pipeliner.dav.account | the dav user | `"pipeliner"` |
pipeliner.dav.image | the Image to use for the DAV server | `{"name":"dav","repo":"cr.nplus.cloud/42i","tag":"latest"}` |
pipeliner.dav.imagePullPolicy | the DAV server image pull policy | `"IfNotPresent"` |
pipeliner.dav.password | password of the dav user | `"pipeliner"` |
pipeliner.dav.secret | Alternatively, define a secret |  |
pipeliner.image.name |  | `"pipeliner"` |
pipeliner.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
pipeliner.image.tag |  | `"ubi.9.1.1201.2023113011"` |
pipeliner.ingress.enabled |  | `true` |
pipeliner.mounts.conf.path |  | `"/opt/ceyoniq/nscale-pipeliner/workdir/config/runtime"` |
pipeliner.mounts.data.paths[0] |  | `"/opt/ceyoniq/nscale-pipeliner/workdir/data"` |
pipeliner.mounts.data.size |  | `"10Gi"` |
pipeliner.mounts.license.path |  | `"/opt/ceyoniq/nscale-pipeliner/workdir/license.xml"` |
pipeliner.mounts.logs.path |  | `"/opt/ceyoniq/nscale-server/storage-layer/log"` |
pipeliner.replicaCount |  | `1` |
pipeliner.wave |  |  |
rs.image.name |  | `"rendition-server"` |
rs.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
rs.image.tag |  | `"ubi.9.1.1200.2023112209"` |
rs.ingress.backendProtocol |  | `"http"` |
rs.ingress.enabled |  | `false` |
rs.mounts.conf.path |  | `"/opt/ceyoniq/nscale-rendition-server/conf"` |
rs.mounts.file.paths[0] |  | `"/opt/ceyoniq/nscale-rendition-server/work"` |
rs.mounts.file.size |  | `"10Gi"` |
rs.mounts.license.path |  | `"/opt/ceyoniq/nscale-rendition-server/conf/license.xml"` |
rs.replicaCount |  | `1` |
web.image.name |  | `"application-layer-web"` |
web.image.repo |  | `"ceyoniq.azurecr.io/release/nscale"` |
web.image.tag |  | `"ubi.9.1.1200.2023112413"` |
web.ingress.backendProtocol | choose wether you want http or https as the backend protocol. This will encrypt traffic from the ingress controller to your pods if you set it to https. | `"http"` |
web.ingress.cookie | on component level, set cookie affinity for the ingress example: `XtConLoadBalancerSession` for nscale Web | component dependent |
web.ingress.enabled | on component level, enable or disable the ingress | component dependent |
web.ingress.inputPath | this defines the path (on component level) for this component Example: `nscale_web` for nscale Web | component dependent |
web.mounts.conf.path |  | `"/opt/ceyoniq/nscale-server/application-layer-web/conf"` |
web.replicaCount |  | `1` |

## Common Image Configuration

The `image` configuration consists of

- the Image Name
- the Image Repository
- the Image Tag
- the Image Pull Policy

If the Pull Policy is not set, it is automatically `IfNotPresent`.

The `Repository` can be overridden at Instance Level and Environment Level to accomodate multiple stages:

```
image:
  name: test
  tag: 1.0.0
  repo: cr.nplus.cloud          # Prio 3
  pullPolicy: Always
global:
  repo: myrepo_i1               # Prio 4
  repoOverride: myrepo_i2       # Prio 2
  environment:
    repo: myrepo_e1             # Prio 5
    repoOverride: myrepo_e2     # Prio 1
```

In this example, finding the repo to use would be:

```helm
$repo := global.environment.repoOverride | default global.repoOverride | default image.repo | default global.repo | default global.environment.repo
```

**The Use Case** is to easily enable you to download the images to a private and secure registry. *nplus* by default uses the official registries, but
that is most likely not wanted by enterprise customers. So you can just set your own registry in the environment and keep dev, qa and prod apart and secured.

## Common Ingress Configuration

The Ingress Configuration can be performed at various levels:

- Per Component / Chart
  `ingress.`
- Per Instance
  `global.ingress.`
- Per Environment
  `global.environment.ingress.`

This enables you to have configuration yaml files per environment (e.g. for DEV, QA and PROD) setting environment defaults.
You then do not have to touch the Instance configuration.

Example:

```
helm upgrade -i \
    --values $SAMPLES/big-instance.yaml \
    --values $SAMPLES/applications.yaml \
    --values $SAMPLES/dev.yaml \
    demo nplus/instance-argo
```

You might have your Instance values in the `big-instance` file, the Apps you want to have deployed to that instance
in the `applications` file, and then you add your default setting for the `dev` stage, potentionally overwriting anything
from the above. The priority in this is *last one wins*.

> The Values are taken by the chart in the following order:
> Component, then Instance, then Environment.

If no value is set, the configuration is dropped from the manifest.

In the following table, you see what value can be defined in which section:

| Key  | Component  | Instance  | Environment |
| ---- | ----------- | ----------- | ----------- |
|domain | ✔︎ | ✔︎ |✔︎|
|issuer | ✔︎ | ✔︎ |✔︎|
|proxyip | ✔︎ | ✔︎ | `0.0.0.0/0` |
|class | ✔︎ | ✔︎ | `public` |
|enabled | ✔︎ | - |-|
|backendProtocol | ✔︎ | - |-|
|cookie | ✔︎ | - |-|
|inputPath | ✔︎ | - |-|

For the component ingress, you can specify the following values:

| Key | Description | Default |
|-----|-------------|---------|
backendProtocol | choose wether you want http or https as the backend protocol. This will encrypt traffic from the ingress controller to your pods if you set it to https. | `"http"` |
class | sets the ingressclass to use. e.g. `public` or `nginx` | `"public"` |
cookie | on component level, set cookie affinity for the ingress example: `XtConLoadBalancerSession` for nscale Web | component dependent |
domain | sets the ingress domain, like `tenant1.mydomain.com`. If no domain is set, no ingress will be configured automatically | none |
enabled | on component level, enable or disable the ingress | component dependent |
inputPath | this defines the path (on component level) for this component Example: `nscale_web` for nscale Web | component dependent |
issuer | if you use *cert-manager* or any other certificate issuer, you can add the class here to hand certificate issuing requests to this issuer. if you do not set any issuer, the chart will generate a self-signed certificate for your ingress (if you defined a domain) |  |
proxyip | if you use a reverse proxy in front of your cluster, allow incoming traffic from this IP range | `"0.0.0.0/0"` |

## Common Storage Configuration

This works just the same way as the Ingress settings: The Configuration can be performed at various levels:

- Per Component / Chart
  `storage.`
- Per Instance
  `global.storage.`
- Per Environment
  `global.environment.storage.`

This enables you to have configuration yaml files per environment (e.g. for DEV, QA and PROD) setting environment defaults.
You then do not have to touch the Instance configuration.

For storage, there are several volume types:

- **conf**, Shared File, RWX, global per environment
- **data**, Disk, RWO, optional per component
- **file**, Shared File, RWX, optional per ReplicaSet
- **temp**, EmptyDir
- **log**, EmptyDir, should be empty, so just in case
- **pool**, optional path on the conf share mounted by some components

### conf

The *conf* storage is a global PVC with RWX (file) shared by every component in the environment. The component creates a sub directory
on the share and mounts it to the config directory in the container.

`storage.conf.name` sets the name of the PVC to be created and used.
`mounts.conf.path` defines the target directory in the container.

As the environment normally provides the *conf* share, you can set the class and the size in the environment.

### data

Every component can create a data PVC with RWO (disk). You can set the `class` for this disk directly at the mount definition `mounts.data.class`. If unset, it uses the definition for the data class from `global.storage.data.class` or from the environment definition at `global.environment.storage.data.class`.

If the class is not defined, it is not included in the manifest and so the cluster default is taken.

Set the size at `mounts.data.size`.  No default for the size.

### file

Every component can create a file PVC with RWX (shared file). You can set the `class` for this share directly at the mount definition `mounts.file.class`. If unset, it uses the definition for the file class from `global.storage.file.class` or from the environment definition at `global.environment.storage.file.class`.

If the class is not defined, it is not included in the manifest and so the cluster default is taken.

Set the size at `mounts.file.size`.  No default for the size.

This file mount is used for example for the *nscale Rendition Server* to create a common workload directory for all PODs across cluster nodes.

### temp

If a *temp* mount point is given in the values file, it creates an `emptyDir` volume with the `sizeLimit` of `mounts.temp.size`. If no limit is given, the volume will have no limit and the cluster node default is used.

If you want to back this volume by memory, specify `mounts.temp.medium: memory`. Be aware, that this will utilize a RAM disk and count against your PODs ressources.

> The *nscale Application Layer* caches fulltext data in temp. Please be aware of your component behaviour when setting medium and size. Your plugins might be requireing speed or size.

### logs

If a *logs* mount point is given in the values file, it creates an `emptyDir` volume with the `sizeLimit` of `mounts.logs.size`. If no limit is given, the volume will have no limit and the cluster node default is used.

The components are writing logs to `stdout` and `stderr`, so the logs directory should not be necessary. This is just in case any plugin writes something to the contaainers file system.

Additionally, if you use the *nplus Administrator Server* component, you might want the legacy way of reading log files, and this would be the storage for that.

### pool

You can define a path at `mount.pool`, then this component will have access. This is used to hand binary data to the components, such as plugins or *nscale Generic Base Apps* along with the *nscale App Installer*.

### Setting storage values

| Key  | Component  | Instance  | Environment |
| ---- | ----------- | ----------- | ----------- |
| conf.name | ✔︎ | ✔︎ | `conf` |
| data.class | ✔︎ | ✔︎ | ✔︎ |
| data.size | ✔︎ | - | - |
| data.paths | predefined list | - | - |
| file.class | ✔︎ | ✔︎ | ✔︎ |
| file.size | ✔︎ | - | - |
| file.paths | predefined list | - | - |
| temp.size | ✔︎ | - | - |
| temp.medium | ✔︎ | - | - |
| temp.path | predefined | - | - |
| logs.size | ✔︎ | - | - |
| logs.medium | ✔︎ | - | - |
| logs.path | predefined | - | - |

Avoid to change the values marked as *predefined*.

## Security settings

You can set the security options per *component*, per *instance* or per *environment*.
The priority is:

1. component
2. instance
3. environment

It is recommended to set the security per environment to make sure you do not forget a component.

### Illumio

Example `environment` setting for Illumio:

```
global:
  environment:
    security:
      illumio:
        enabled: true
        loc: "mylocation"
        supplier: "mysupplier"
        platform: "myplatform"
        readinessGates:
          - conditionType: "com.illumio.policy-ready"
```

### Calico

Example `environment` setting for Calico:

```
# TODO
```

### Security Conext

You can add a `containerSecurityContext` to the component by adding it in the values file:

```
security:
  containerSecurityContext:
    capabilities:
      drop: ["ALL"]
```

Additionally, add a `podSecurityContext` if desired:

```
security:
  podSecurityContext:
    runAsNonRoot: true
    runAsUser: 1000
    runAsGroup: 1000
```

> **Note**: This setting can not be set on instance or environment level.

## Ressources

### Kubernetes

By default, no resources are set on the container. Thus, Kubernetes handles the container with best effort.

Ressources can be set at

| Key | Description | Default |
|-----|-------------|---------|
| ressources.requests.cpu | sets the request, which is the minimum guaranteed | - |
| ressources.requests.memory | sets the request, which is the minimum guaranteed | - |
| ressources.limits.cpu | sets the limit, which is the maximum allowed | - |
| ressources.limits.memory | sets the request, which is the maximum allowed | - |

- if nothing is defined, Kubernetes handles it BestEffort
- if requests are defined, but no limits, Kubernetes handles it Burstable
- if both are defined, Kubernetes handles it Guaranteed

Please take caution when setting parameters and also have a look at this interesting article regarding resources and JVM resource handling:

https://xebia.com/blog/kubernetes-and-the-jvm/

### JVM

For those components implemented in Java, it is possible to set Java Options:

- nscale CMIS Connector
- nscale ILM Connector
- nscale Application Layer
- nscale Rendition Server
- nscale Web

| Key | Description | Default |
|-----|-------------|---------|
| javaOpts.javaMaxRamPercentage | Maximum memory given to Java in % | - |
| javaOpts.javaMinMem | Minimum memory given to Java | - |
| javaOpts.javaMaxMem | Maximum memory given to Java | - |
| javaOpts.javaMisc | Additional Java Options | - |

> **Note**: if you defined settings for *appDynamics*, the agent will automatically be added to the Java Options when the above components are run. Please refer to `global.appDynamics.agent` for more information.