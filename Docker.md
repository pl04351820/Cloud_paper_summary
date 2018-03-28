### Docker 

#### key insights
- Virtualize OS based on LXC. 
- Provide resource management strategy.

#### Architecture
![Docker](/images/Docker.jpg)

1. Docker Client: Communication strategy (http)
2. Docker Daemon: Receive request from client and management the back-end system.
    - Docker server. Gateway as communication.(gorilla)
    - Engine. Essential model, monitoring the jobs.
    - Jobs. Basic elemetn in docker engine. 
3. Docker Register: Docker hub. (Search/pull/push)
4. Graph: local repo management.
5. Driver: Management the environment of container.
    - Graphdriver: handle for storage management. docker image build.  
    - Networkdriver: Vitrualization. NAT, VPC
    - execdriver: Namespace/cgroups.
6. Libcontainer
    - The interface for button layer. Connect Driver with Linux Kernel. This design make the system easy to scale out. 
7. Docker container (rootfts)  
    - Specify the location of image to define rootfs.
    - Specify physical resource allocation. 
    - Networking and security strategy
    - Use CLI to communicate and run jobs.

### Advantage
- Easy to deploy, Achieve Devops.
- Good for microservice architecture, easy to scale out.

### Disadvantage
- Waste CPU resource. The vritualization is a process for wasting CPU resource. 