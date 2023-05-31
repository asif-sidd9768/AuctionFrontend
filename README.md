# AuctionFrontend

```mermaid
graph LR
  Frontend-->|User services|Main_Backend
  Main_Backend-->|Auction data|Auction_Microservice
  Main_Backend-->|Real-time updates|Firebase_Realtime_Database
  Auction_Microservice-->|Real-time updates|Firebase_Realtime_Database

```
