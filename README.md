# Dune-Analytics
A collection of SQL queries and interactive dashboards created on Dune for analyzing blockchain data, including DeFi protocols, NFTs, token transfers, and DAO activities.

## Features  
- Prebuilt queries for DeFi, NFT, and DAO analytics.  
- Dashboards to visualize key metrics and trends.  
- Supports Ethereum and other EVM-compatible chains.  
- Easy-to-modify SQL queries for custom insights.  

## Dashboards  
Explore the dashboards on Dune:  
- [DeFi Analytics](https://dune.com/yourusername/defi-dashboard)  
- [NFT Market Trends](https://dune.com/yourusername/nft-dashboard)  
- [DAO Governance Insights](https://dune.com/yourusername/dao-dashboard)  

## How to Use  
1. Visit the respective dashboard link above.  
2. Fork or modify the queries to suit your use case.  
3. Visualize data and export results as needed.  

## Query Examples  
### Total Volume on Uniswap  
```sql  
SELECT  
  date_trunc('day', block_time) AS day,  
  SUM(volume_usd) AS total_volume  
FROM  
  swaps  
WHERE  
  platform = 'Uniswap'  
GROUP BY  
  day  
ORDER BY  
  day;
```

### Active Wallets in the Last 7 Days
```sql
SELECT  
  COUNT(DISTINCT wallet_address) AS active_wallets  
FROM  
  transactions  
WHERE  
  block_time >= current_date - interval '7 days';
```
