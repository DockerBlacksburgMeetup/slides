# October 12, 2016

## Basics Overview - Docker Compose

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](docker-compose-basics.pdf) | [Google Drive](https://docs.google.com/presentation/d/1WHhq_EuLgwUpnbfDwPyxU3LfljNj0MUt3ia0QohGWCY/edit?usp=sharing)
- [Demo Repo](https://github.com/mikesir87/docker-compose-demo)

In this meetup, we talked about running multi-container applications.  We first started talking about using container linking when using `docker run`.  Once we had a container linked, we saw that the link is specified in the container's `/etc/hosts` file.

After learning about linking, we moved to learning Docker Compose to define our services.  We also made note that links aren't necessary (with Docker Compose v2), as a new network is created and all containers in the network are using a Docker-provided DNS that resolves the names for us.

We wrapped up the basics talk by updating our Docker Compose file to build the images, rather than relying on having them already on the host machine.



## Use Case - Rackspace Webmail Development with Docker Compose

- Presenter - [Jon Armstrong](https://github.com/jon-armstrong)
- Slides - [PDF](rse_docker_compose.pdf)
- [Demo Repo](https://github.com/jon-armstrong/docker-compose-demo)

Our use case talk was brought to us by Jon Armstrong from Rackspace.  He talked about the migration that his team has gone through from each developer having a collection of cloud servers to a Docker compose-based development environment.  He talked about some of the challenges they experienced, but also how they overcame them.

He then presented a demo project in which he showed an example of the project structure and how they are using their `docker-compose.yml` files, with some apps calling others and even extending other docker-compose files.

