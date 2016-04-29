# Container Orchestration with Kubernetes, Docker Swarm and Mesos/Marathon

http://beta.craft-conf.com/speaker/AdrianMouat

- Orchestration is coordinating containers/hosts to get an app running, to
  scale it, and all that stuff
  and all that stuff with containers/hosts/etc. in the background
- Swarm and Compose is the official solution of Docker Inc.
  - It uses the same API as Docker Engine
  - Swarm is mainly doing the clustering (having multiple containers on one
    host) and Compose is doing the orchestration (setting up networking,
    etc.).
  - You have strategies for choosing hosts. Binpack fills up hosts before
    moving on to the next one, spread of course is the opposite.
  - You have filters to set up stuff like 'I want this container on a node
    labelled staging'
- Note: There are live demos which I am not writing commentary for.
- Compose is pulling all used images on all affected nodes, not just the
  ones they are running on. Funny.
- In docker-compose.yml you can set affinities to have multiple containers
  run on the same node.
- `docker-compose scale` will launch new containers. Cool!
- To have load balancing with this, you'll need a 3rd party tool, such as
  Consul or `fluxctl`
- TODO: Play with fluxctl
- Swarm & Compose's rebalancing and master replication are still a WIP
- Then we have Apache Mesos, which is older than Docker, and is used by
  Twitter, Airbnb, and eBay
- Mesos is also fairly more complex, Mesos Agents run on nodes, to execute
  tasks and report resources, while the Mesos Master delegates tasks. Zookeeper
  is used as a HA database for all this data, and then you even need some
  framework that coordinates with the master, like Marathon or Aurora.
- Narathon works with simple RESTful endpoints, and has a nice web UI
- Add Traefik as well which gets the dest IPs and ports and you can use it to
  get a load balanced service.
- Mesos is pretty battle-tested but needs 3rd party tools and is not especially
  Docker-friendly
- Kubernetes is based on Google's experience with containers, and has a bunch
  of features baked in in an opinionated way, including load balancing
- Pods are an atomic unit of a group of containers that are scheduled together.
  - You use single container pods for single containers.
- You can key-value label your stuff
- Services are stable endpoints that are routed to containers.
- Mangle Kubernetes stuff with the `kubectl` CLI tool
- `kubectl scale` works here as well, is pretty fast.
- Kubernetes needs you to understand a bunch of new concepts but is designed
  around containers
  - Kubernetes has a solution for secrets as well, and a lot more advenced
    things

