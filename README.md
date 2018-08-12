# Savenode Coin
Shell script to install a [Savenode Masternode](https://savenode.io/) on a Linux server running Ubuntu 16.04.
***

## VPS installation
```
wget -N https://raw.githubusercontent.com/zoldur/Savenode/master/savenode_install.sh
bash savenode_install.sh
```
***

## Desktop wallet setup

After the Masternode is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the Savenode Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** FOS to **MN1**. You need to send all 1000 coins in one single transaction.  **This is a tiered Masternode so the collateral will change**
4. Wait for 15 confirmations.
5. Go to **Help -> "Debug Window - Console"**
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
startmasternode alias 0 MN1
```
14. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
savenode-cli masternode status
```
***

## Usage:
```
savenode-cli masternode status #To check your MN status
savenode-cli getinfo #To get general info such as Savenode version and current block numnber
savenode-cli mnsync status #To check if your MN is synced.
```
Also, if you want to check/start/stop **Savenode**, run one of the following commands as **root**:

```
systemctl status Savenode #To check if Savenode service is running
systemctl start Savenode #To start Savenode service
systemctl stop Savenode #To stop Savenode service
systemctl is-enabled Savenode #To check if Savenode service is enabled on boot
```
***

## Donations
Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB
