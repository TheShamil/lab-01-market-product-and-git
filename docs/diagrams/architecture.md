## Product Choice

Telegram;
Link: <https://web.telegram.org/a/>;
Private messenger.

## Main components

![Telegram Component Diagram](./out/telegram/component-diagram/Component%20Diagram.svg)

[Telegram Component Diagram code](./src/telegram/component-diagram.puml)

MTProto Gateway (DC Entry). This component acts as the primary entry point for client connections, managing the specialized MTProto protocol to ensure secure and efficient communication between apps and the backend.

Auth & Session Service. This service manages user identities, handles login requests, and maintains active session states across multiple devices while coordinating with external SMS gateways for verification.

Message Handling Service. This is the core engine responsible for processing incoming messages, routing them to the correct recipients, and interacting with the database to ensure persistent delivery.

Sharded Chat DB. This data layer component stores the vast amount of chat history and user data by distributing it across multiple database shards to maintain high performance and scalability.

Event Bus (Kafka/Internal). The event bus serves as an asynchronous communication hub that allows different services, like the message and notification services, to broadcast and react to system events in real-time.

## Data flow

![Telegram Component Diagram](./out/telegram/sequence-diagram/Sequence%20Diagram.svg)

[Telegram Component Diagram code](./src/telegram/sequence-diagram.puml)

I will describe **Flow 1: Media Upload (Pre-flight)**, which covers the initial process of getting a media file from Alice's device into the Telegram infrastructure.

**Flow 1: Media Upload (Encrypted Parts).** In this group of actions, the file is not sent all at once; instead, the Mobile App breaks the media into encrypted chunks to ensure a reliable upload process. This occurs before the actual message is ever visible to the recipient.

**Component Interactions and Data Exchange.** The following components interact to complete the pre-flight upload:

- User Alice & Mobile App: Alice selects a photo, and the App initiates the process by calling the saveFilePart function.

- Mobile App & MTProto Gateway: The App sends a stream of bytes accompanied by a unique file_id_A. The Gateway acts as the entry point and issues an ACK (Acknowledgement) back to the app for every part successfully received.

- MTProto Gateway & Media Service: The Gateway streams the file data directly to the Media Service for processing.

- Media Service & Distributed DFS: The Media Service writes the file chunks to the Distributed File System (DFS). The DFS performs a checksum to verify data integrity and returns an "OK" status.

- Media Service & Sharded DB: Once the data is stored, the Media Service updates the Database to save the File Metadata, linking the file to Alice's account.

## Deployment

![Telegram Component Diagram](./out/telegram/deployment-diagram/Deployment%20Diagram.svg)

[Telegram Component Diagram code](./src/telegram/deployment-diagram.puml)

Deployment Locations:

- Client Tier: Apps run locally on Smartphones and Computers.

- Edge Layer: Gateways sit at the entry point of the Telegram Data Center.

- Internal Cluster: Core services and the Kafka bus run on application servers.

- Storage Cluster: Redis (Cache), Sharded DB, and DFS run on dedicated high-capacity storage nodes.

## Assumptions

Telegram's architecture is a multi-tier system where user apps connect via the MTProto protocol to a global infrastructure of edge gateways, core microservices, and specialized data layers (Sharded DB and DFS) to handle secure message routing, media storage, and real-time event propagation.

## Open questions

How does the data flow look like in secret chats?
