# AuctionFrontend

## Flow Diagram
```mermaid
graph LR
  Frontend-->|User services|Main_Backend
  Main_Backend-->|Auction data|Auction_Microservice
  Main_Backend-->|Real-time updates|Firebase_Realtime_Database
  Auction_Microservice-->|Real-time updates|Firebase_Realtime_Database
```

## Architecture

```mermaid
graph LR
  Frontend-->|Authentication|User_Service
  Frontend-->|Real-time updates|Firebase_Realtime_Database
  Auction_Service-->|Auction and Bid data|Main_Database
  Auction_Service-->|Real-time updates|Firebase_Realtime_Database
  Scheduler-->|Starting and ending auctions|Auction_Service
```

## Detailed architecture
This diagram represents the following:

    1. The frontend communicates with the Main Backend for user authentication and fetching auctions.
    2. The frontend communicates with the Auction Microservice for fetching specific auction details and placing a bid.
    3. The frontend receives real-time updates from the Firebase Realtime Database.
    4. The Main Backend communicates with the Auction Microservice to create an auction.
    5. The Main Backend uses user services data from the Main Database.
    6. The Main Backend sends real-time updates to the Firebase Realtime Database.
    7. The Auction Microservice sends auction data to the Main Database and real-time updates to the Firebase Realtime Database.
    8. The Main Database sends product data to the Main Backend.

```mermaid
graph LR
A[Frontend]
B[Main Backend]
C[Auction Microservice]
D[Firebase Realtime Database]
E[Main Database]

A -- User Authentication --> B
A -- Fetch Auctions --> B
A -- Fetch Auction Details --> C
A -- Place a Bid --> C
A -- Real-time Updates --> D

B -- Create Auction --> C
B -- User Services --> E
B -- Real-time Updates --> D

C -- Auction Data --> E
C -- Real-time Updates --> D

E -- Product Data --> B

```
