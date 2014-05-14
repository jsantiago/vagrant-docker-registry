Start up a [docker registry][1] and [Shipyard][2] container.

    ./environment start

Wait until Shipyard has been deployed. Then run a [Shipyard agent][3] container.

    ./environment run

Login to [Shipyard][4] and visit the [Hosts][5] page to authorize the agent.

To push to your local repository:

    ./environment ssh

    # Pull down the latest busybox images
    docker pull busybox

    # Create your own tag
    docker tag busybox localhost:5000/busybox:0.1.0

    # Push your tagged version
    docker push localhost:5000/busybox

    # Clean up old images
    docker rmi busybox
    docker rmi localhost:5000/busybox:0.1.0

    # Confirm you can pull down your tagged version
    docker pull localhost:5000/busybox

To view all the tags for that image:

    curl -X GET http://localhost:5000/v1/repositories/busybox/tags
    {"0.1.0": "2d8e5b282c81244037eb15b2068e1c46319c1a42b80493acb128da24b2090739"}

To delete a tag:

    curl -X DELETE http://localhost:5000/v1/repositories/busybox/tags/0.1.0


### Further Reading
* [Shipyard Project][6]
* [Working with a Docker Repository][7]
* [How to use your own registry][8]
* [Docker Registry API][9]

[1]: https://index.docker.io/_/registry/
[2]: https://index.docker.io/u/shipyard/deploy/
[3]: https://index.docker.io/u/shipyard/agent/
[4]: http://localhost:8000/
[5]: http://localhost:8000/hosts
[6]: http://shipyard-project.com/
[7]: http://docs.docker.io/use/workingwithrepository/
[8]: http://blog.docker.io/2013/07/how-to-use-your-own-registry/
[9]: http://docs.docker.io/reference/api/registry_api/
