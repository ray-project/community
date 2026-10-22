# SIG accelerator Charter & Vision

## Background

Ray enables programmers to seamlessly scale AI workloads on their cluster. All AI workloads run on accelerators, most commonly NVIDIA GPUs, and increasingly TPUs and AMD GPUs. Over the past years, the diversity of accelerators have increased not only due to different vendors entering the market but also different SKUs being produced by existing vendors.

This results in a growing number of issues that the Ray team is unable to support, including:

* [https\://github.com/ray-project/ray/pull/65417](https://github.com/ray-project/ray/pull/65417)  
* [https\://github.com/ray-project/ray/pull/65550](https://github.com/ray-project/ray/pull/65550)

One single vendor will not be able to handle the emerging ecosystem. Thus, starting a multi-vendor SIG with a designated charter is our recommended path for enabling Ray to work well on any hardware.

## SIG accelerator Charter

**Make Ray work seamlessly for the widening ecosystem of modern accelerators.**

The Accelerator Special Interest Group aims to bring together hardware vendors, Ray contributors, and application developers to define and advance a shared, vendor-neutral roadmap for accelerator support in Ray. This public interest group will be responsible for enabling Ray workloads to continue evolving in an era of fragmented, specialized accelerators.

## Scope

The SIG is responsible for the development and maintenance of the Ray accelerator integrations and testing. 

Relationship with Ray Core: Ray Core owns general mechanisms and policies and the SIG will provide the hardware-specific pieces to plug into core. And jointly come up with an interface between the two.

### In scope

* Development and maintenance of accelerator-specific capabilities in Ray  
  * Accelerator discovery and labeling   
  * RDT support \- ensure best practices for accelerator transport/data movement   
  * Observability and dashboarding  
* Maintenance of accelerator-specific testing and CI  
* Ensure that the Ray roadmap is properly informed by upcoming/pre-release hardware changes and that we have early access to hardware for day 0 support.  
* Influence the roadmap of related accelerator projects for synergy. E.g. CUDA, NCCL, Jax, PyTorch/TorchTPU  
* Testing. Recipes (including config)  
* Scheduling / placement: Evolve the topology aware support (rack topology evolving)  
* Transport (RDMA, GPUDirect)

### Out of scope

* New scheduling primitives and functionality will be maintained by the Ray Core team  
* Accelerator awareness in Ray Serve, Ray Data, and Ray Train will be implemented by the respective library maintenance teams as well  
  * We can expand the scope to libraries later on.

## Code and binaries

[https\://github.com/ray-project/ray/tree/master/python/ray/\_private/accelerators](https://github.com/ray-project/ray/tree/master/python/ray/_private/accelerators)   
[https\://github.com/ray-project/ray/tree/master/python/ray/tests/accelerators](https://github.com/ray-project/ray/tree/master/python/ray/tests/accelerators)  
[https\://github.com/ray-project/ray/tree/master/python/ray/util/accelerators](https://github.com/ray-project/ray/tree/master/python/ray/util/accelerators) 

## Leadership

### Technical leads

* Mengjin Yan (Anyscale)  
* Ryan O’Leary (Google)

### Chairs

* Zhe Zhang (NVIDIA)

Given that this is the first chartered SIG that Ray is starting, the TSC will be responsible for deciding new chairs/leads. By default, chairs and leads are installed for 1 year terms. 

# Vision for Accelerators on Ray

SIG vision \- The chair is responsible for making sure we have proper representation from different vendors (NVIDIA, AMD, TPU, Inferentia), and that the different vendors are able to properly contribute and maintain the respective capability.

Technical vision \- Ray should be accelerator-aware and support a wide range of hardware

* Accelerator tiering:  
  * Starting prioritized accelerators should be:  
    * TPU (different versions)  
    * NVIDIA GPUs (especially datacenter SKUs \- VR, GB, H, B, L, A)  
  * We would like to support the following accelerators in the future:  
    * Consumer NVIDIA GPU   
    * Apple Metal  
    * AMD  
  * Tiering should be based both on market share but also the ability to support from the Ray community.  
  * We are open to promoting more accelerators to the primary tier as their usage amongst the Ray community becomes more widespread.  
* The Ray experience for blessed accelerators should be:  
  * Schedulable  
    * Ray should be able to detect / be aware of different hardware SKUs  
  * Observable  
    * Ray should be able to display proper accelerator metrics on the dashboard  
  * Tested  
    * Ray should have proper CI testing for blessed accelerators to make sure the above behavior does not regress
