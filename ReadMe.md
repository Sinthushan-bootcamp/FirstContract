# Unit 20 - "Making First Contract"

In all three contracts the message sender is playing the role of HR and ensuring the employees of the made up company are receiving the correct wage.

## AssociateProfitSplitter

In this contract all three employees get the exact same amount. It is the amount sent by HR divided by 3 for each employee. Any remainder (msg.value - amount * 3) will go back to the msg sender or HR in our pretend example

![MSG_Sender_beg](Images/msg_sender_balance_beg.PNG?raw=true)
![Deployment](Images/AssociateProfitSplitter_deployed.PNG?raw=true)
![MSG_Sender_sft](Images/msg_sender_balance_aft.PNG?raw=true)

## TieredProfitSplitter

In this contract we get a bit smarter and the three employee now have different roles. Each role commands a different percentage of the total payroll. CEO get 60%, CTO gets 25%, and Bob gets 15%. We keep a tally of of the amounts going to each of these employees and distribute the difference of the contract value and the tallied amount to the message sender (aka HR):

![MSG_Sender_beg](Images/msg_sender_balance_beg2.PNG?raw=true)
![Deployment](Images/deployed2.PNG?raw=true)
![MSG_Sender_sft](Images/msg_sender_balance_aft2.PNG?raw=true)

## DeferredEquityPlan

In this example the employees receive 1000 chares over 4 years. Each year the employee receives 250 shares. THere are check to ensure that a year has passed before initial share payout and that a year has passed since the last payout for all subsequent payouts.

We are using the Kovan testnet for this. the Address is 0x9cC038d046F7b5b3Fd9e77cB62C1e5CECc52Fb3A

To make this work we need to call the fast forward function four times.THe we click distribute and we should see 250 under distributed shares.

![MSG_Sender_beg](Images/msg_sender_balance_beg3.PNG?raw=true)
![Deployment](Images/deployed3.PNG?raw=true)