Start up a [docker registry][1] and [Shipyard][2] container.

    ./environment start

Wait until Shipyard has been deployed. Then run a [Shipyard agent][3] container.

    ./environment run

Login to [Shipyard][4] and visit the [Hosts][5] page to authorize the agent.


### Further Reading
* [Shipyard Project][6]
* [Working with a Docker Repository][7]
* [How to use your own registry][8]

[1]: https://index.docker.io/_/registry/
[2]: https://index.docker.io/u/shipyard/deploy/
[3]: https://index.docker.io/u/shipyard/agent/
[4]: http://localhost:8000/
[5]: http://localhost:8000/hosts
[6]: http://shipyard-project.com/
[7]: http://docs.docker.io/use/workingwithrepository/
[8]: http://blog.docker.io/2013/07/how-to-use-your-own-registry/
