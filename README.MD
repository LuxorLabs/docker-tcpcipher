Luxor Tcpcipher
===========
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

`luxor-tcpcipher` is a stratum-compatible proxy for establishing encrypted 
connections between clients and the mining pool.

- Secure encrpyted connection circumvents limitations for clients 
accessing the mining pool behind a firewall.
- Simple setup. Just install docker, set `redirectTo` config option and 
run `docker compose up`.
- Low memory footprint - works on most devices.



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[contributors-url]: https://github.com/LuxorLabs/docker-tcpcipher/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[stars-url]: https://github.com/LuxorLabs/docker-tcpcipher/stargazers
[issues-shield]: https://img.shields.io/github/issues/LuxorLabs/docker-tcpcipher.svg?style=for-the-badge
[issues-url]: https://github.com/LuxorLabs/docker-tcpcipher/issues

Getting Started
---------------
To get started with Luxor Tcpcipher, there are a few requirements for your computer.
We highly recommend setting up a machine on-premise in the datacenter.

First, we must install Docker. You can do that [here](https://www.docker.com/get-started).

The latest versions of Docker on certain operating systems includes docker-compose by default. However, some OS have `docker-compose` as a seperate package. You can view your operating system settings through the setup guide [here](https://docs.docker.com/compose/install/).

Once Docker is installed, clone this repo into your local system:
```
git clone https://github.com/LuxorLabs/docker-tcpcipher.git
```

Then `cd` into the root directory:
```
cd docker-tcpcipher
```

Finally, you can bootup the entire Luxor Tcpcipher stack with docker-compose.

If you have a Docker instance with compose built in you can run:
```
docker compose up
```

If you have a Docker instance with a seperate `docker-compose` installation, you
can run:
```
docker-compose up
```

Notice the main difference is the `-` which references the specific binary we're
using.

To stop Luxor Tcipcipher at any time, just run `docker compose down` or
`docker-compose down`, depending on your system setup.

You can also run the Docker containers in the background with:
```
docker compose up -d
```

Tcpcipher Config
---------------
Tcpcipher already comes configured to encrypt received data before sending it 
to the decrypting tcpcipher. The only additional configuration needed is to 
specify  the user the encrypted messages should be associated with. This is by
updating `redirectTo = "customer-username"` in `/tcpcipher/config.toml` to the
customer username to credit messages to. 
For example if the customer username  to credit shares to is `firebird`, 
the configuration will be updated to `redirectTo = "firebird"`.


To switch the miners over to use the tcpcipher, just update the Stratum URL: 
```
<tcpcipher_ip_adr>:8383
```

System Requirements
---------------
The full Relay installation will require:
- 100Mb of disk space for the docker images
- 250Mb of memory for relay instance


Happy hashing!









