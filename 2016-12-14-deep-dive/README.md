# December 14, 2016

## Deep Dive - Part One

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](./deep-dive-part-one/slides.pdf) | [Docker Compose](./deep-dive-part-one)

In this presentation, we started our deep dive series! We first took a step back to remember the problem space that Docker is trying to solve and remember that Docker is in the business of making tools.  While what they're doing is incredible, they are standing on the shoulders of giants. Having this perspective helps us better realize what's going on under the covers.

We then quickly moved into talking about what an image _actually_ is... literally a tar'ed copy of filesystem changes. We talked about how an image is pulled from a registry, including looking at a manifest for a public image.

Once we understood some of the mechanics of images, we dived into a few "pro tips" for image creation and optimization. These revolved around taking advantage of the build cache and reducing the number of layers we need to push/pull with each build.



## Deep Dive - Part Two

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](./deep-dive-part-two/slides.pdf) | [Docker Compose](./deep-dive-part-two) 

With a deeper understanding of how images actually work, we were ready to dive into how containers work! We started off by reminding ourselves of the differences between a container and an image.

From there, we dived into talking about namespaces and how they help provide isolation that feels like a separate VM, even though we're simply just running another process. We specifically talked about process, network, mount, and user namespaces and how each allows the process to have its own set of resources.

We then brought in the house vs apartment analogy mentioned by Mike Coleman in [his Docker blog post](https://blog.docker.com/2016/03/containers-are-not-vms/), with a reminder that containers are indeed sharing the kernel. To help protect those shared resources, one can use cgroups to limit resource utilization for a single container.

And finally, we reiterated the fact that containers are NOT VMs, but simply other processes running on the machine.

