# Hypergraph-Based Analysis of ERC-721 Token Transactions on Ethereum

## Overview
This project analyzes Ethereum's ERC-721 token transactions using hypergraph theory to uncover patterns in NFT trades. Initially, traditional graph theory was used, but due to its limitations in capturing only pairwise interactions, hypergraphs were employed to better represent multi-party interactions. By treating each unique token address as a hyperedge, we extract insights into how addresses interact over time.

## Limitations of Traditional Graphs
While traditional graph methods provided valuable insights into the number of wallets and transactions, they had significant limitations:
- Inability to capture multi-wallet interactions: Traditional graphs only depict pairwise relationships, failing to show how multiple wallets participate in a single transaction.
- Lack of token-specific insights: They do not effectively capture which tokens were transferred between wallets or how token interactions evolved over time.
- Higher-order transaction complexity: Traditional graphs struggle to represent higher-order relationships where multiple participants engage in a single transaction.
- No community detection: We can analyze wallets and transactions, but we cannot determine which tokens were exchanged between a set of wallets over time.

These limitations led to the adoption of hypergraphs, which enable a more comprehensive representation of multi-wallet transactions in NFT trading.

## Dataset
The dataset comprises Ethereum NFT transactions from 2015 to 2024, including:
- Block number
- Timestamp
- Transaction hash
- Sender & recipient addresses
- Flags for smart contracts

## Preprocessing Steps
- Timestamp conversion to `yy-mm-dd` format
- Splitting transaction files by day
- Labeling addresses

## Hypergraph Construction
Each unique token address represents a hyperedge, and the interacting wallet addresses form nodes.
- Daily hypergraph generation from transaction data
- Node degrees indicate the number of days a wallet is active
- Contract vs. user behavior is analyzed by identifying contract-associated addresses

## Analysis and Findings
- Temporal evolution of NFT trades across years
- Degree distribution of nodes (wallets)
- Identification of influential nodes in NFT transactions
- Behavioral differences between EOAs and smart contracts
- Filtering anomalous accounts that act as both smart contracts and EOAs

## Tools & Technologies Used
- Python, Pandas, NumPy, NetworkX
- Hypergraph libraries for analysis
- Matplotlib, Seaborn for visualization

## Future Work
I am focusing on analyzing the temporal-topological properties of higher-order evolving networks, studying how NFT transaction structures change over time and identifying key trends in NFT market evolution.

## How to Run
1. Clone this repository:
   ```sh
   git clone https://github.com/your-username/hypergraph-nft-analysis.git
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Run the preprocessing script:
   ```sh
   python preprocess.py
   ```
4. Generate hypergraphs:
   ```sh
   python construct_hypergraph.py
   ```
5. Perform analysis:
   ```sh
   python analyze.py
   ```

## Contribution
Feel free to open issues or contribute via pull requests! 🚀

