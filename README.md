# Open Source Home Automation Packge

This is an open source implementation of several home automation needs. The geneeral idea is I wanted to take a Raspberry PI and control my house. I did NOT want to use IFTTT or other similar services, I wanted to roll my own. 

There are several related repos

[UI Layer](https://github.com/chadmott/homeAutomationUI)

[Lambda Functions](https://github.com/chadmott/lambdas)

[IP Sync Client](https://github.com/chadmott/ipsync-client)

[Node API Layer](https://github.com/chadmott/homeAutomationAPI)

## UI Layer

This is a mobile-first Angular 2.0 UI to interface with your house. I typically host this on AWS S3/CloudFront. 

More details [here](https://github.com/chadmott/homeAutomationUI)

## API Layer

This is an Node.js application that leverages express. Additionally, this API has the lighting conrtrol interface which uses zWave. 

More details [here](https://github.com/chadmott/homeAutomationAPI)

## IP Sync

The PI lives at my house, behind normal internet, so the IP address is subject to change. I dont really care for the public DYNDNS type solutions, so I created a custom one. The client lives in a docker container, and the server is a lambda function. 

More details [here](https://github.com/chadmott/ipsync-client)

## Lambdas

Here are a few lambda fuctions that the app uses. I use node-lambda to test these locally, so you will see those contructs here. 



### IP Sync

This responds to the IP sync request. If the user is authenticated, and the IP changes, the lambda will call Route53, and change the record. 

More details [here](https://github.com/chadmott/lambdas/tree/master/ipsync-server)

### API Responder

This handles the alexa commands. This is experimental/demo. 

More details [here](https://github.com/chadmott/lambdas/tree/master/apiCaller)
