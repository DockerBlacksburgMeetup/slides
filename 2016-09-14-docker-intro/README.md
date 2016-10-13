# September 14, 2016

## Basics Talk - Docker Overview

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](docker-basics.pdf) | [Google Drive](https://drive.google.com/open?id=1NZTl9NT1k7rDNgt8524546c1GfWXPWZsPu6MovYwk5Q)

Since this was the first meetup for the Docker Blacksburg Meetup, we started from the beginning.  What is Docker?  What's it trying to accomplish?  How are they trying to reach those goals?

After talking about the high-level goals, we dived into the terminal and practiced pulling images, starting containers, exposing ports, and creating new images.  We first created an image by using `docker commit`, but then learned about the more preferred method... using Dockerfiles.



## Use Case - Summit Loves Docker

- Presenter - [Michael Irwin](https://github.com/mikesir87)
- Slides - [PDF](summit-loves-docker.pdf) | [Google Drive](https://drive.google.com/open?id=1bGwyeJEo69gxmDNcsJxyKCMjtfaOfwrCVBH3S-EPPA4)

Our use case talk tonight was brought to us by Michael Irwin, a developer on CREST (Comprehensive Research Enterprise Systems Team) at Virginia Tech, where they are building research administration applications.  He highlighted how the team had the desire to allow acceptance testing to occur on individual feature branches before being merged into the main code branch.

He then talked about the three different phases of their QA environment, the pros and cons of each, and how they ended up where they are using Docker.  The final solution ended up with utilizing the [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) image, which allows for easy reverse proxying of containers.  This allowed easy isolation of each branch by isolating each application/database pair on a different subdomain.
