## Projects ideas

Project maintainers and mentors, please submit the ideas below (under the Proposed Project Ideas section) section using the [template](/PROJECT_IDEA_TEMPLATE.md).

### Template

```
#### CNCF Project Name
##### Title

- Description:
- Recommended Skills:
- Mentor(s):
- Upstream Issue (URL):
```

### Sample

#### Prometheus (sample)

##### Refactor the APIs for better readability and less maintenance overhead

- Description: Currently the HTTP API is not very well organized and needs some tidying up. The actual course of action is not decided yet, but [go-kit](https://github.com/go-kit/kit) looks like a good fit.
- Recommended Skills: golang
- Mentor(s): [@Krasi Georgiev](https://github.com/krasi-georgiev)
- Issue: <https://github.com/prometheus/prometheus/issues/3416>


## Participating Projects

#### Kubernetes

##### Improvements to Cluster API provider for GCP (CAPG)

- Description: The Cluster API is a Kubernetes project to bring declarative, Kubernetes-style APIs to cluster creation, configuration, and management. CAPG provides this Kubernetes-native declarative infrastructure for GCP. The project would start with some help wanted issues around quick start and documentation, this will help with understanding mentee with CAPI/CAPG concepts and current implementation. Then we will move on to some long pending improvements documented in the issues link below.
- Recommended Skills: Golang, unit and feature testing.
- Mentor(s): Davanum Srinivas (@dims), Carlos Tadeu Panato Junior (@cpanato)
- Issue: https://github.com/kubernetes-sigs/cluster-api-provider-gcp/issues

##### Improve SIG-Node testing using Kubetest2

- Description: Kubernetes currently uses Kubetest as the interface for launching and running e2e tests. There is a new [kubetest2](https://github.com/kubernetes-sigs/kubetest2) that is in the process of being developed and will need to be rolled out to various CI harnesses and jobs. As part of this project we will focus on SIG-Node related CI jobs. Here's how we currently test SIG-Node related code - [e2e-node-tests.md](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-node/e2e-node-tests.md). There will be a lot of interesting problems to solve and this work is critical to how we test kubernetes not just in GCP, but also across all the other cloud providers going forward.
- Recommended Skills: Golang, python, bash, unit and feature testing.
- Mentor(s): Davanum Srinivas (@dims), Amit Watve (@amwat)
- Enhancement : https://github.com/kubernetes/enhancements/tree/master/keps/sig-testing/2464-kubetest2-ci-migration

#### Kubernetes Policy Working Group (WG)

The Kubernetes policy working group focuses on developing tools and solutions that make Kubernetes secure and easiser to use.

##### KubeArmor support for Policy Report CRD

- Description:
  This project will periodically generate or update a [Policy Report Custom Resource (CR)](https://github.com/kubernetes-sigs/wg-policy-prototypes/blob/master/policy-report/README.md) based on events collected from KubeArmor. This could be implemented as a feature in KubeArmor or developed as an external adapter. The candidate will learn about Kubernetes controllers and various security topics.
- Recommended Skills: Linux, Golang, CLI, Kubernetes
- Mentor(s): Jim Bugwadia (@JimBugwadia), Mritunjay Kumar Sharma (@mritunjaysharma394)
- Upstream Issue (URL): https://github.com/kubernetes-sigs/wg-policy-prototypes/issues/59

#### Vitess

##### Add complete parsing support for MySQL constructs

- Description: Vitess is a database clustering system for horizontal scaling of MySQL. One of the key goals of Vitess is to emulate MySQL behavior even while running multiple MySQL instances so that ORMs and frameworks work seamlessly. Vitess has its own in-built SQL-parser which it uses to understand the query and represent as structs for further processing. As of now, a lot of MySQL constructs are not parsed and result in syntax errors. For example, we do not have complete support to parse [partition constructs](https://dev.mysql.com/doc/refman/5.7/en/partitioning-overview.html). Parsing for a lot of the newer features in MySQL 8.0 is also missing. The task of the mentee would be to add parsing support for such constructs. 
- Recommended Skills: go, SQL, yacc, compilers and lexers
- Mentor(s): Manan Gupta (@GuptaManan100)
- Issue: <https://github.com/vitessio/vitess/issues/8604>

##### Add support for comparing strings using collations and character-sets

- Description: Vitess does not yet have support for collations and character-sets. So, to compare varchar strings Vitess needs to rely on [WEIGHT_STRING](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_weight-string) function for now. As per MySQL documentation, WEIGHT_STRING is a debugging function, meant only for internal use. Having the ability to compare strings using collation and character set support we will be able to better implement ORDER BY, GROUP BY, JOIN. It will also allow us to leverage more advanced join techniques than what we currently implement.
- Recommended Skills: go, SQL
- Mentor(s): Vicent Marti (@vmg)
- Issue: <https://github.com/vitessio/vitess/issues/8606>

##### Add support for Upgrade/Downgrade Testing

- Description: Currently Vitess has a rich set of functional tests that are run as part of every commit to catch regressions early. However, they are not sufficient to assess the quality of the product for production rollout. We currently do not test for incompatibilities introduced via upgrade, and ensuring that users can downgrade one level if they need to backout of a failed upgrade. The scenarios will need to be written down, and then tests can be written using GitHub actions:
    - Document Supported Upgrade/Downgrade Scenario
    - Author GitHub actions tests to checkout 2 versions, test scenarios.
- Recommended Skills: go, GitHub Actions, docker
- Mentor(s): Harshit Gangal (@harshit-gangal)
- Issue: <https://github.com/vitessio/vitess/issues/4989>

#### Kyverno

##### Scalability testing for Kyverno

- Description:
  Define and execute scalability tests for Kyverno on large Kubernetes clusters with several namespaces and resources. The candidate has to propose and execute a performance test plan and help optimize resource usage of Kyverno for different loads for large Kubernetes clusters.
- Recommended Skills: Kubernetes, Golang, Test
- Mentor(s): Shuting Zhao (@realshuting)
- Upstream Issue (URL): https://github.com/kyverno/kyverno/issues/2248

##### Extend Kyverno test command to cover generate policies & improve test coverage

- Description:
  Extend the Kyverno CLI to cover generate policies and improve tests coverage for Kyverno. Based on the test results, the candidate has to add more unit/E2E tests.
- Recommended Skills: Golang, Test
- Mentor(s): Shuting Zhao (@realshuting), Jim Bugwadia (@JimBugwadia)
- Upstream Issue (URL): https://github.com/kyverno/kyverno/issues/2249

##### Security model and processes for Kyverno

- Description:
  Improve security model and processes for Kyverno. Document security processes, help define a threat model with risks and mitagation, and add best practice processes like publishing signed images.
- Recommended Skills: Kubernetes, Security, Documentation
- Mentor(s): Jim Bugwadia (@JimBugwadia)
- Upstream Issue (URL): https://github.com/kyverno/kyverno/issues/2250


#### Chaos Mesh

##### Monitoring Metrics about Chaos Mesh

- Description: Observability is very important for each application, we want to monitor more things of Chaos Mesh components, enrich the metrics for both logic patterns and performance data. We want to let users could watch the status of Chaos Mesh on grafana dashboard, and developers could using time-series metrics for debugging and profiling.
- Recommended Skills: golang, prometheus, grafana
- Mentor(s): [@ZhiqiangZhou](https://github.com/strrl)
- Issue: <https://github.com/chaos-mesh/chaos-mesh/issues/2198>

#### KubeVela

##### Integration with developing time to provide consistent experience

- Description: Users can use KubeVela to do application delivery and management. In this project, we hope to integrate KubeVela with developing time. So developers can have a consitent experience between local development and production deploy. There're multiple developing tools such as Tilt or Nocalhost, both of them can integrate with KubeVela by supporting KubeVela Application YAML.
- Recommended Skills: Golang, Kubernetes
- Mentor(s): Jianbo Sun (@wonderflow)
- Upstream Issue (URL): https://github.com/oam-dev/kubevela/issues/795

##### Building An Machine Learning Platform on KubeVela

- Description: Data scientists need a ML platform to develop, test, and deploy ML models easily. In this project, we will design and build a self-service ML platform on top of KubeVela. We will use KubeVela to provide high level workflow and APIs to glue and simplify deployment pipelines. We will also use Cloud resources to support deployment and operations tasks like domain routing, monitoring, health checking, etc.
- Recommended Skills: Golang, Kubernetes
- Mentor(s): Hongchao Deng (@hongchaodeng)
- Upstream Issue (URL): https://github.com/oam-dev/kubevela/issues/2061


#### Support remote Terraform HCL (Git repo or ConfigMap) in Terraform Controller

- Description: Currently Terraform Controller supports inline HCL, but community users normally already stored Terraform
  HCLs remotely (in Git repo or ConfigMap). Terraform Controller should support remote HCLs.
- Recommended Skills: Golang, Terraform
- Mentor(s): ZhengXi Zhou (@zzxwill)
- Upstream Issue (URL): https://github.com/oam-dev/terraform-controller/issues/46

##### Build Gitops continuous deployment tools on kubevela

- Description: Kubevela is like Lego, you can build any platform you need based on kubevela. And GitOps is very popular and user friendly. In this project, we will build Gitops continuous deployment tools on kubevela.
- Recommended Skills: Golang, Kubernetes
- Mentor(s): Jian Li (@leejanee)
- Upstream Issue (URL): https://github.com/oam-dev/kubevela/issues/2062


#### WasmEdge

##### Support WASI-Crypto proposal

- Description: After WasmEdge provides an experimental API, WASI Socket, for supporting Berkeley Sockets API in Wasm. WasmEdge enabled a new way to open a new socket, listen to an existed socket, and send and receive data. Moreover, it will be nice if we can do more things in the related features such as SSL support. To achieve this feature, one possible way is to compile the OpenSSL library to Wasm and link it as a library. However, the performance may be not good, because all the computation jobs are done at the wasm level. Here is an alternative way, instead of the previous one, we can wrap the OpenSSL library to Wasm external functions. For example, binding `ssl_connect` to `(import "openssl" "ssl_connect" ... )`. Unfortunately, this is not an easy way to do it. To simply the workload, we decide to implement the WASI-crypto proposal first, and then use this proposal to make the above things happen.
- Recommended Skills: C++, Rust
- Mentor(s): Hung-Ying Tai (@hydai), Shen-Ta Hsieh (@ibmibmibm)
- Upstream Issue (URL): https://github.com/WasmEdge/WasmEdge/issues/345

##### Support Wasm-Signature proposal

- Description: The wasm-Signature proposal is specifically about embedded digital signatures in WebAssembly modules, not about package/OCI signatures. When distributing WebAssembly modules, it will be nice if we can have a way to verify. To achieve this target, we choose a Wasm-Signature proposal as our implementation standard. With this proposal, WasmEdge can provide `sign` and `verify` features.
- Recommended Skills: C++, Rust
- Mentor(s): Hung-Ying Tai (@hydai), Shen-Ta Hsieh (@ibmibmibm)
- Upstream Issue (URL): https://github.com/WasmEdge/WasmEdge/issues/344

##### Support WASI-NN proposal

- Description: Machine Learning is a big topic nowadays. WasmEdge already provides [a set of TensorFlow host functions](https://github.com/second-state/wasmedge_tensorflow_interface) to enable the ML inference in WebAssembly. However, these TensorFlow host functions are defined by us and they are just a Wasm function binding from the [TensorFlow C API](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/c/c_api.h). Here comes a standard, the [WASI-NN proposal](https://github.com/WebAssembly/wasi-nn) provides a new way to perform neural network inferencing by using a runtime-provided implementation that can leverage host native optimizations, CPU multi-threading, or powerful hardware devices such as GPUs or TPUs.
- Recommended Skills: C++, Rust
- Mentor(s): Hung-Ying Tai (@hydai), Yi-Ying He (@q82419)
- Upstream Issue (URL): https://github.com/WasmEdge/WasmEdge/issues/343

##### Support Wasm-C-API proposal

- Description: The wasm-c-api proposal provides the C and C++ API for WASM runtimes. Even though WasmEdge already provided the C API, it's proper to implement the wasm-c-API proposal for the general C/C++ API. In the current status, we've already implemented the non-runtime data structures on the branch. Then, we need to finish the runtime implementation.
- Recommended Skills: C++
- Mentor(s): Hung-Ying Tai (@hydai), Yi-Ying He (@q82419)
- Upstream Issue (URL): https://github.com/WasmEdge/WasmEdge/issues/306

#### LitmusChaos

##### Develop E2E dashboard with CI/CD pipeline details and enhance litmus e2e website

- Description: This project aims to build an E2E Web dashboard that will display the CI/CD pipeline details of [scheduled](https://litmuschaos.github.io/litmus-e2e/generic-pipeline/pipeline-runs/pod-level-run.html) and [manual](https://github.com/litmuschaos/litmus-e2e/tree/master/.github/workflows) runs. It should contain all the litmus backend and portal pipelines and can be easily switched or add more pipelines. Currently, [these](https://github.com/litmuschaos/litmus-e2e/tree/master/.github/workflows) are the pipeline present in the e2e.

- Recommended Skills: Golang, JavaScript, ReactJS
- Mentor(s): Udit Gaurav (@uditgaurav), Soumya Ghosh Dastidar (@gdsoumya)
- Upstream Issue (URL): https://github.com/litmuschaos/litmus/issues/3112

##### Develop/Enhance E2E test-cases for ChaosCenter

- Description: This project aims to develop/enhance the E2E test cases for ChaosCenter. The ChaosCenter is a single source of truth to control all the different Chaos Activities happening around Litmus. From the ChaosCenter you get the freedom to manage every single part of Litmus and shape your workflows exactly the way you want them.

- Recommended Skills: Golang, JavaScript, Kubernetes
- Mentor(s): Vedant Shrotria (@Jonsy13), Raj Babu Das (@rajdas98)
- Upstream Issue (URL): https://github.com/litmuschaos/litmus/issues/3114


#### Tremor

##### Solidify and generalize error handling code in the runtime

- Description: The runtimes error handling code stems from ancient times where rust was younger, and we were more naive. As such, it is more grown than designed in many places. With the knowledge of the past three years and stabilization of the codebase, now is a good time to polish it and make errors an exciting user experience.
- Recommended Skills: rust
- Mentor(s): [@Matthias Wahl](https://github.com/mfelsche), [@Heinz Gies](https://github.com/Licenser), [@Darach Ennis](https://github.com/darach)
- Issue: <https://github.com/tremor-rs/tremor-runtime/issues/1175>

##### AWS (s3) connectors

- Description: Tremor supports a number of other systems to connect one, yet one of the most wide spread API's in the cloud world (S3) isn't yet supported. This is a chance to shine and build something many users will enjoy.
- Recommended Skills: rust
- Mentor(s): [@Matthias Wahl](https://github.com/mfelsche), [@Heinz Gies](https://github.com/Licenser), [@Darach Ennis](https://github.com/darach)
- Issue: <https://github.com/tremor-rs/tremor-runtime/issues/1176>

#### Thanos

##### Add groupcache (and improve) backend for the caching bucket in Thanos Store

- Description: This project is about implementing the [groupcache](https://github.com/golang/groupcache) back-end for the caching bucket. Caching bucket is a generic mechanism for caching requests to remote object storage. All of the other caching mechanisms currently suffer from the [cache stampede](https://en.wikipedia.org/wiki/Cache_stampede) problem and it is impossible to "properly" solve this problem with them. This is where `groupcache` comes in. Some work has already been [done](https://github.com/GiedriusS/thanos/commit/d269ce25b744b02c6d4d99f0e2e72af812e45f37) so you will have to something work off of. `Groupcache` also needs some improvements with regards to fetching multiple keys at once to improve the performance even more. In the end your work will make not just Thanos faster but also cheaper because less requests will need to be made to the remote object storage.
- Recommended Skills: Go
- Mentor(s): Giedrius Statkevičius (@GiedriusS), Prem Saraswat (@onprem)
- Upstream Issue (URL): https://github.com/thanos-io/thanos/issues/2962

##### Migrate Thanos to the New Protocol Buffers v2 API

- Description: This project is about updating and optimizing the [protocol buffers](https://developers.google.com/protocol-buffers) implementation used for communication throughout the Thanos project. Thanos relies heavily on gRPC and protocol buffers for communication between its many components, and now with the release of the [new Golang API for protocol buffers](https://blog.golang.org/protobuf-apiv2) and the deprecation of the old API, Thanos should be updated to benefit from the improvements in the ecosystem. As part of this project, the protocol buffers generator used in Thanos will be migrated to one that supports the new API and brings other improvements, such as reducing memory allocations. This project will help make Thanos faster and ensure that we stay up to date with the latest libraries.
- Recommended Skills: Go, protocol buffers
- Mentor(s): Lucas Servén Marín (@squat), Kemal Akkoyun (@kakkoyun), Giedrius Statkevičius (@GiedriusS)
- Upstream Issue (URL): <https://github.com/thanos-io/thanos/issues/4557>

##### Add metrics to track the progress for compaction and downsampling 

- Description: This project is about improving the observability of the Thanos compactor component to help user track the current progress. Thanos compactor usually has to deal with large TSDB blocks for compaction and downsampling. When the data are large, it takes a long time to finish the compaction or downsampling. Now users have to check the bucket UI manually to see whether the work is done. It would be better to have a more fine-grained way to tell the progress of compaction and downsampling. We can have some metrics to track the work and even integrate the stats into the UI.
- Recommended Skills: Go
- Mentor(s): Ben Ye (@yeya24)
- Upstream Issue (URL): 
  - <https://github.com/thanos-io/thanos/issues/3985>
  - <https://github.com/thanos-io/thanos/issues/3478>

#### etcd

##### Etcd.io Docs/SEO Improvement Plan Continuation

- Description:
  This project is the continuation of the [etcd.io website](https://etcd.io) docs improvement work. While the relocation of the primary documentation, SEO, and site look and feel work has already been done, there is still more work to be done to implement the new information architecture that has been proposed. This includes working with the mentors and project maintainers to write new pages, adapt existing ones, and write blog posts.
- Recommended Skills:
  - Technical writing
  - Documentation
  - English
  - git/GitHub
  - Some web design & coding skills may be helpful, but are not required.
- Mentor(s):
  - Primary
    - [Nate Waddington](https://github.com/nate-double-u)
    - [Celeste Horgan](https://github.com/celestehorgan)
  - Adjunct
    - [Josh Berkus](https://github.com/jberkus)
    - [Sahdev Zala](https://github.com/spzala)
- Upstream Issue (URL):
  - [Etcd.io Docs/SEO Improvement Plan](https://github.com/etcd-io/website/issues/65)
  - [New IA implementation](https://github.com/etcd-io/website/issues/267)



#### Buildpacks

##### Update Builder implementation to 0.1 Builder Spec

- Description: In Cloud Native Buildpacks, [Builders](https://buildpacks.io/docs/concepts/components/builder/) are distributed OCI images that act as the complete context for the building of an application. They came into existance by necessity and have risen to be an essential concept that now needs a specification. As part of this project, you will help us make the necessary changes to [pack](https://github.com/buildpacks/pack) to adhere to the specification as well as  _finalize_ the specification itself. This will have to be done with consideration to existing implementations in efforts to prevent unintentionally breaking anyone's existing workflow.
- Recommended Skills: Go, OCI Containers
- Mentor(s): Javier Romero (@jromero)
- Upstream Issue (URL): <https://github.com/buildpacks/pack/issues/945>

##### Web Redesign of Feature Comparison

- Description: Cloud Native Buildpacks is a specification and set of tools that help you take source code and convert them into OCI images. Sound familiar? Maybe you've heard of Docker, Source-2-Image, Kaniko, etc. Well you are not alone. The goal of this project is to refactor our existing ["features" page](https://buildpacks.io/features/#comparison) to provide an easier to comprehend comparison across other similar solutions. Through this project, you'll research each alternative, learn how they compare and aim to provide that information to the users in an easy to digest format. This will include designing and implementing a better format to compare projects and their features side-by-side.
- Recommended Skills: OCI Containers, JavaScript, CSS, HTML, Design
- Mentor(s): Javier Romero (@jromero)
- Upstream Issue (URL): <https://github.com/buildpacks/docs/issues/389>
