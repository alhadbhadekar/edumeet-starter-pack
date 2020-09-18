# eduMeet

Starter-pack for eduMeet. Source ( https://github.com/edumeet/edumeet )

## Manual installation on MacBook

* Prerequisites:
Currently multiparty-meeting will only run on nodejs v13.x
To install see here [here](https://github.com/nodesource/distributions/blob/master/README.md#debinstall).

Install redis server

```bash
brew update
brew install redis
```

* Clone the project:

```bash
$ git clone https://github.com/alhadbhadekar/edumeet-starter-pack.git
$ cd edumeet-starter-pack
```

* Set up the browser app:

```bash
$ cd app
$ npm install
$ npm run build
```

This will build the client application and copy everythink to `server/public` from where the server can host client code to browser requests.

* Set up the server:

```bash
$ cd ..
$ cd server
$ npm install
```

* Modify IP address to your laptop IP address on line 366 of server/config.js file. For me I have put it as 192.168.2.22. Everytime we connect to new network we will have to change IP address in server/config.js file

```
		webRtcTransport :
		{
			listenIps :
			[
				// change 192.0.2.1 IPv4 to your server's IPv4 address!!
				{ ip: '192.168.2.22', announcedIp: null }

				// Can have multiple listening interfaces
				// change 2001:DB8::1 IPv6 to your server's IPv6 address!!
				// { ip: '2001:DB8::1', announcedIp: null }
			],
			initialAvailableOutgoingBitrate : 1000000,
			minimumAvailableOutgoingBitrate : 600000,
			// Additional options that are not part of WebRtcTransportOptions.
			maxIncomingBitrate              : 1500000
		}
	}
 ```
 
## Run it locally

* Start redis server in one terminal

```bash
redis-server
```

* Run the Node.js server application in a terminal:

```bash
$ cd server
$ npm start
```

* Go to Chrome and type localhost in address

* You will receive a certificate warning saying certificate is not secure. Use following document to install certificate locally in Chrome and make Chrime to trust this certificate https://www.andrewconnell.com/blog/updated-creating-and-trusting-self-signed-certs-on-macos-and-chrome/#add-certificate-to-trusted-root-authority. This will add certificate as a trusted entity.

* Go to Chrome again and type in localhost. You will see valid certificate and able to load edumeet





