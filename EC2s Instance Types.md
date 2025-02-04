There are many different types of instances, in many different sizes. 

Each might differ in many ways and are often optimised for a specific purpose:
- **Raw** resources
- **ratio of resources** ( more CPU vs more memory I/O  etc)
- **Storage** and **Data Bandwidth**
- System archecture / vendor (ARM vs x86, Intel vs AMD)
- additional features (GPUs or FGPAs)

EC2 catagories:
- **general purpose** - default and diverse workload use. Equal ratio of resources
- **compute optimised** - CPU optimised for media processing, HPC, scientific modelling or ML
- **memory optimised** - processing large in memery data sets or DB workloads
- **Accelerated Computing** - Hardware GPUs or custom programmable hardware like FPGAs
- **Storage Optimised** - sequential and random IO - data warehousing 

How to decode the EC2 naming scheme:
![[Pasted image 20250122161947.webp|533]]
- The family refers to a specific type of computing, only a few are particularly important
- generation is the current iteration of the family (**always select the most recent generation**)
- sometime there are additional capabilities after the family and generation
- instance size refers to how much memory and CPU is allocated

Here is a general overview of some types that are suited to certain compute loads:
![[Pasted image 20250122162028.webp]]

