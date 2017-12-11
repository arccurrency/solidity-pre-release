The contract code is designed to provide an ERC20 implementation of a stable coin called ARC. The code is based upon the zeppelin standard coin implementation.

The stable coin will be backed by a combination of investments and cash. The code utilises an oracle called through the ARCCoinCirculation contract. 

The oracle connects to the arccy website and retrieves the total amount of funds under management. The number of coins in circulation is governed by the number returned from the oracle. Coins can only be minted up to that value. Similarly to reduce the number in circulation (in the case the the amount fo funds and investments are reduced) the ARC coins to be burnt must be transferred back to the contracts owners wallet (which will be facilitated through the website) and then the burn function will be called.

Changes in circulation will be made through calls to the updateCirculation function, that will be invoked through the arccy.org website when the funds and investments value changes.

To deploy the ARC contract, the ARCCoinCirculation contract must be created first and the generated contract address passed as a parameter when instantiating the ARCCoin contract.
