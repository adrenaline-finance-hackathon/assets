# adrenaline.finance 
# Synthetics on Steroids
## SUMMARY
We are creating an integrated defi platform which both:
i) provides exposure to real-world assets beyond crypto without having to let go of the underlying crypto position, nor having to trust custodians;
and ii) allows earning a yield on a diversified position within a liquidity pool of assets in the same class.
## PROBLEM STATEMENT
We believe that synthetic assets, thenceforth ‘Oracle-Pegged Assets’, have much room for expansion within the defi space. However, current solutions are most bottlenecked by systemic issues in complexity of use and oracle concentration (i.e. oracle trust).
As it stands, oracle-pegged tokens on EVM chains are very convoluted to use. For example, Synthetix requires four steps to purchase a synth: ETH → SNX → sUSD → sXAU, added to understanding its debt-shares and transaction taxes mechanics.  
Likewise, Mirror Protocol’s liquidity is poor on Ethereum/EVM chains, so would require two chain bridges to attain anything: ETH > UST (eth) > UST (terra) > mAUR (terra) > mXAU(eth); or else struggle with high slippage.
## VALUE PROPOSITION
Adrenaline will have a direct ETH/stETH/etc to oracle-pegged asset contract, wherein the minting contract itself takes both overcollateralisation (say, 150%) and oracle feed behaviours at once. This removes much of the user complexity compared with alternatives, and allows a wider userbase to access our oracle-pegged assets.
On oracle concentration, we believe that there is great space for other oracles, in addition from the dominant Chainlink implementations. Ultimately, the removal of custodian risk from asset-backed tokens creates another issue: oracle risk. Ultimately, if the underlying oracle data feed is disrupted, whether from deliberate interference or bugs, the price mechanics in mint could be compromised. Hence, our vision aims to take advantage of UMA price feeds in addition to those of Chainlink. 
Slippage should not be a large concern in the minting of our tokens, for our creation deals directly with an oracle. Further, our LP should inject liquidity into our own synths, as well as gain access to present liquidity on other tokens. Investors will also benefit from easily spreading oracle-custodian risk, within our equally-weighted custodian and oracle-pegged of the same asset e.g. gold, TSLA, etc.
## PROOF OF CONCEPT
We restricted our POC to a single real-world asset with the highest liquidity and number of successful tokens: gold. We selected four assets with the highest liquidity for our LP: one custodian, and two synthetic: Tether Gold (XAUt), Paxos Gold (PAXG), and our own adrXAU. 

 Our initial prototype will consist of two phases:
1. adrXAU
  We planned to fork Twindex’s direct ETH -> tAssets contracts on BSC, which allow for the creation of overcollateralised assets, as a base for our own ETH -> DOPAssets on Kovan testnet. Twindex uses Chainlink. Fortunately, UMA has native XAU price feeds, which we can implement into our contract instead.
There will be significant work to be done UI-wise, for Twindex UI is not OSS. 
2. XAU-LP
We planned to fork Saddle Finance’s UI, swap and pool contracts, currently enabling the exchange between multiple ETH, BTC and USD assets. We wish to change these over to XAU assets within our hackathon, and deploy these on Kovan.
## THE HACKATHON
We had multiple setbacks with our proof of concept throughout the hackathon, which made it difficult for us to present a finalised product. 
On the first day of the hackathon, we found our backend engineer hacker was ill and unable to attend, while another is injured. Alas, this became but a microcosm of our struggles over the next 36 hours.
Having lost a backend developer, we reduced our scope to the first of our two objectives.  However, team morale was low, and we were unable to recover from our slow start. 
Our forks were, too, less reliable than expected, and required bug fixing before being able to deploy. Thus, we realised we would need a longer time-scale to fulfill our vision to a high enough quality.  
 Our experience has been invaluable, and we have made friends, contacts, and learned many new skills as a result of this eventful weekend.
## VISION
Despite our short-term shortcomings, we believe in the project we wanted to complete. Thus, we plan to develop and complete the above POC and deploy on mainnet over a month, after which we will be able to consider further items in the roadmap:
- Own our own price feeds while staying outside of Chainlink, and create mechanism for a fallback oracle;
- Extend to other assets and asset classes, including tech stocks, 
- Move away from chainlink/fallback oracles
- We’re going to allow assets to be backed not only by ETH but stETH and other sound assets – increasing capital efficiency.
## FAQ
### Why are we creating our own synthetic platform?
We can develop this place to offer a higher number of oracle-pegged assets positions with one or two liquid tokens. This will allow our liquidity pools to potentially exploit assets where there are only one or two viable offerings.
### What’s different between Synthetix and us?
Ultimately, Synthetix gets around liquidity issues by backing all their oracle-pegged assets on via (mainly) one token: SNX. We believe this method to be restrictive, and cause structural concerns from its tautological nature in the longer term. Trust in the platform is two-fold: both confidence in the value of the token, whose transaction volumes will be a fraction of those of ETH, as well as the oracles. 

