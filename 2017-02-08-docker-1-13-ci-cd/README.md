# February 8, 2017

## What's New in Docker 1.13?

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](./docker-1-13/slides.pdf) | [Docker Compose](./docker-1-13)

In this presentation, we went over several of the updates released with Docker 1.13, ranging from CLI restructuring to deploying stacks using Docker Compose.  We moved fairly quickly through it all, mentioning when and where you might want to use some of the updates.


## Introduction to CI/CD

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](./intro-to-ci-cd/slides.pdf) | [Docker Compose](./intro-to-ci-cd)

We started off with a discussion of why CI/CD is important and how it's made its way into software. The roots started several decades ago with the Toyota Production System (TPS) where Toyota looked to reduce waste in their production lines by building a pipeline with quality checks throughout, instead of waiting until the end (just one facet of TPS). By adopting many of the same ideas into software, we start to look like an Agile team that builds things as needed (rather than define all requirements up front), test code often using automated builds, and prepare ourselves to release code to production at any point.  Michael presented many of the benefits he's seen having a CI/CD pipeline and how both users and developers have benefited from it.

Afterwards, we jumped into a hands-on lab, led by the instructor, where we forked a GitHub project, created an automated build on Docker Hub, and deployed the app on to [Play with Docker](http://play-with-docker.com). Then, we made a change to the project locally, pushed the change, and saw the Docker image get created automatically. We then deployed the updated image to our running service.

Although the lab used a very simple pipeline, it showed the power of having such a pipeline. We wrapped up talking about how each organization can build a similar pipeline, swapping out tools at each stage with what their organization already has.

