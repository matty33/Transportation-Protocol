## The Third Generation of Transportaion

The Global Hackathon is in the initial phases of building the OceanBound Protocol Framework. A transportation protocol that aggregates the data of every transportation application and service to store on multiple blockchains.  Currently users are having to coordinate the use of multiple applications just to get from point A to point B.  Companies that are in the business of delivering goods are having to expend millions of dollars to research efficient transportation of their goods and build infrastructure.

![oceanbound_framework](https://user-images.githubusercontent.com/7444521/55461724-fe8d0700-55a9-11e9-8190-4933e2c5eff3.jpg)


We give you the infrastructure and development frameworks to build your transportaion applications.  Companies stake their own transportation and mobility data in exchange for integrations with other established companies in the space.  This collaboration of partners reward business and users with a seamless transportation experience and a central resource for connecting things.


TGH is looking to solve countless problems in this space through cross-chain transactions and data-sharing.  We are looking to have our community actively participate to help us build this protocol.  Finding ways to make each application on their respective chain feature rich or dive deep and enable the exchange of information across different blockchains. 


![transportation_protocol](https://user-images.githubusercontent.com/7444521/55461325-07310d80-55a9-11e9-82ef-4a3609052270.jpg)



https://mobidev.biz/blog/blockchain-demo-logistics-transportation


Product Structure


Components & Applied Technologies

1. Blockchain: Hyperledger Sawtooth
Hyperledger Sawtooth is a popular modular framework for building distributed ledgers for Blockchain applications, providing digital records—deliveries in our case—that are maintained without centralized authority or implementation. It is stable in production, having excellent documentation and SDKs for multiple programming languages: Go, Java, JavaScript, Python, and Rust.

Our blockchain consists of 3 subcomponents: API, Validator, and Transaction Processor. The first two are standard components, while the third one is a custom component that allows to manage deliveries and their states, which are encoded using protocol buffers. The history of transactions is available for each delivery.

Additionally, you may check Sawtooth Explorer to see blocks and transactions.



2. Consensus algorithm: Proof of Elapsed Time (POET)
Consensus is a decision-making process in which members of a group agree to develop and support fair decisions, considering mutual interests. The mechanism we used in this blockchain demo is POET, based on the principles of a fair lottery system across the largest possible number of network participants.



3. Flutter-based mobile application
There is a cross-platform application for couriers, compatible with iOS and Android and based on Google's Flutter, one of the most promising app development frameworks. It sends data about delivery status via an API based on Node.js. QR/barcode scanning (with planned addition of NFC) is used to identify deliveries.



4. Single page Web application
This logistics demo also includes a React-based Web app for regular users. It communicates with Node.js API through a secure Caddy-based proxy server, which is used to route requests to internal components of the system. In addition, Google Maps API is used to display delivery routes.



5. Raspberry Pi + Python
Raspberry Pi is connected to this blockchain with in order to retrieve GPS data from AI-Thinker A7 GPRS/GSM module and send it to Node.js API through the Caddy server. We applied Python SDK and CLI tools for these purposes, while Sawtooth REST API is used to update delivery states with new geolocation. Any other IoT devices can be connected to the system.



6. Node.js API
The Node.js component of our blockchain demo acts as additional business logic layer between clients and Hyperledger Sawtooth. It serializes requests using the protocol buffers mechanism, validates inputs and provides endpoints to the Web application. The requests are then forwarded to Sawtooth Rest API.



7. Docker
The Docker stack (including Swarm and Compose) is used to simplify local development and production deployment, ensuring high scalability in the future. The entire logistics platform is currently hosted on DigitalOcean Cloud.
