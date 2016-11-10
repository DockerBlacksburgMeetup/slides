# November 9, 2016

## Basics Overview - Docker Swarm

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](docker-swarm.pdf) | [Google Drive](https://docs.google.com/presentation/d/1ACfVSjDdS5OMILJAQ5SYtphwS9Pxa4WdlZ9FO_KuL3Y/edit?usp=sharing)

In this meetup, we started our dive into orchestration.  We first highlighted two of the shortcomings of Docker Compose - 1) It works on only a single node/host and 2) it's purely "fire and forget".  While these are acceptable for local development, they're obviously not preferred for production usage.

We then learned about Docker Swarm and its out-of-the-box features.  We talked about its security, its routing mesh, and the new service commands that are built into the Docker engine.

We wrapped up by going through a few slides that showed commands and graphically showed how to create a cluster, deploy a service, scale it up and down, and what happens when node failure occurs.



## Hands-on Lab

- [Link to lab](https://github.com/mikesir87/docker-swarm-intro)
