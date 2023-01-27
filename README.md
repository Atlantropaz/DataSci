# Liquidity & Sentiment Model For Crypto Equities

Crypto unlike most other equities does not really have "fundamentals"; 
however, like other equities, they all trade on macro liquidity conditions and market sentiment.
The motive of this project is to investigate the degree to which liquidity and sentiment plays a role in Cryptos like Bitcoin. <br>

## What is Macro Liquidity? 
Macro Liquidity for US investors includes at least one of the three components
- Fed’s Total Assets Less Eliminations from Consolidation (aka. **A**)
- Overnight Reverse Repurchase Agreements (aka. **RRP**)
- U.S. Treasury, General Account (aka. **TGA**)

## What is Sentiment? 
Bitcoin sentiment consists of two metrics from Bitcoin's perpetual contracts
- Open Interest 
- Funding Rate 

## Summary
Amongst 34 features including Sentiment, Liquidity and other attributes, XGBoost found 7 important ones 
which I will group them into three cateogries
- Traditional Attributes
  - Open, High, Low, Volume
- Liquidity Attribute
  - Net Liquidity including TGA (or **A - RRP**)
- Sentiment Attribute
  - Perpetual Open Interest
  - Perpetual Funding Rate 
<br>
To rank the significance amongst the three categories: Traditional > Sentiment > Liquidity. 
Thus, it seems that even though liquidity attribute plays a role in predicting Bitcoin's Close price, 
it seems that sentiment metrics and traditional metrics are in comparison more important. 
<br> <br>

After training several machine learning models, I found that a stacking ensemble model consist of **XGboost**, **Random Forest** and **Decision Tree** 
(all with fine-tuned hyper-params) achieves the highest **accuracy socre** of **0.97** 
and **second-lowest** of Mean Squared Error and Mean Absolute Error next to Decision Tree Model. 
<br> 

However, I'd like to point out that even though accuracy score is relatively high, average MAE of the stacking model using a walk-forward validation is about **635**, or equivalent to **2-4%** of price fluctuation for the testing set. Such models could have further rooms of improvement to decrease the MAE loss. 




