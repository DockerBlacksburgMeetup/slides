For this demo, Michael Irwin talked started by doing a quick overview of how Summit development works and then dived into the [Bacabs](https://github.com/mikesir87/bacabs) dashboard that is used to aid in QA testing.

# Slides

The Summit Development pipeline (credit [Carl Harris](https://github.com/ceharris)). With every push of code...

- Code is built and tested
- Docker image is created
- Docker stack is deployed (new image plus database)
- Bacabs dashboard hears of new deployment and updates dashboard
- QA testers use dashboard to get to deployment to test

![Summit Development Pipeline](summit-pipeline.png)


The QA environment has a load balancer/reverse proxy ([Traefik](https://traefik.io/)) that provides host-based routing. Each app service has labels that define the host, which Traefik discovers and uses in its config.

In order to get traffic, the apps need to be on the same network as Traefik. That's the `qa-application` network in the slide below. Then, each stack has its own network to allow its app (and only its app) to talk to the database container.

![Bacabs Networking](bacabs-networks.png)

In order to keep things up-to-date and super responsive, everything is event driven!

- Bacabs uses a "Docker Event Watcher" component that listens for Docker events (container start/stops and health status). 
- When an event arrives, the watcher pulls out relavant details and publishes an event to Redis. 
- The backend handles the event and updates the current set of deployments
- Any updates are then pushed (via WebSocket) to each connected clients' dashboard

![Bacabs Event Listening](bacabs-event-listening.png)



## Running the Demo

1. Start a Swarm (won't go into it here)

2. Set the `$HOST` variable to the hostname for your machine. All apps will be found under it (cats1.$HOST, cats2.$HOST, groceries.$HOST)

3. Deploy the Bacabs stack
```
docker stack deploy -c docker-stack-bacabs.yml bacabs
```

4. After a moment, you should be able to open your browser to http://[your $HOST] and see the Bacabs dashboard.  Of course, there isn't much to see yet. So, let's launch some apps!
5. Deploy an app - cats 1.0
```
docker stack deploy -c docker-stack-cats1.yml cats-1
```
After a moment, you should see a `cats-1.0` app deployed in a new "cats" group on the Bacabs dashboard.

6. Let's deploy another version of cats!
```
docker stack deploy -c docker-stack-cats2.yml cats-2
```
After a moment, you should now see a `cats-1.1` app deployed, also in the "cats" group on the dashboard.

7. This time, let's deploy an entirely different app stack (one with a database). This app has healthchecks enabled, so will give us a green thumbs up once the healthchecks are passing.
```
docker stack deploy -c docker-stack-groceries.yml groceries
```
And after a moment, boom! There it is! Give it a few seconds and you should see the health status go green.

### Tearing it all down

```
docker stack rm bacabs
docker stack rm cats-1
docker stack rm cats-2
docker stack rm groceries
```