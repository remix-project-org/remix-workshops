# Dey set plenti steps wey get stress

## To dey follow all this things go dey stressful, but na the point be that.

Where w dey go:

- To use voting contract wen 3 proposal input for di constructor dey.
- To give voting chance give 2 address join ( so na 3 voting adress we get).
- Get one address vote for proposal 1 (0-based index) and di oda two vote na for proposal 2.

1. Carry di 3_Ballot.sol from di sample soliditi files make you come compile am.  Con go the \*\*deploy &, run "" Module.

2. Select di **JavaScript VM** Environment.

3. Inside the contract parameter put ["0x5031000000000000000000000000000000000000000000000000000000000000", "0x5032000000000000000000000000000000000000000000000000000000000000", "0x5033000000000000000000000000000000000000000000000000000000000000"]\*\* con press the \*_Deploy button_.

4. Open di contract wey dem deploy.

5. Inside di **vote** function put 2 for dere.  E mean say you wey be di msg.sender and chairman go vote for proposal wen una dey position 2 wey be di last proposal for our list.

6. Now we go need give oda addresses di right to take vote.  Select anoda address for di account pulldown make you copy am den go back to di 1st address.  Paste di copy address enta di textbook wey dey next to di giveRightToVote function.  Again select anoda address dem copy am den go back go di 1st address again den paste am inside giveRightToVote.

7. Now you get 3 addresses wey get di right to take vote.

8. Enta go one of di addresses wey you give di right to take vote make you vote for proposal **1**.  (Put **1** for di textbox wey dey next to di vote function).  You go come switch go di oda two addresses and vote for proposal **2** wit dat one.

9. You go open di **Transactions wey dey recorded** for di section of di module - by say you click on top de caret. Click di hard disk icon for di **Transactions recorded** section to take save your steps.
   ![recorder](https://github.com/ethereum/remix-workshops/blob/master/Recorder/2_Record/images/recorder.png?raw=true "recorder")

10. You go get modal window wey go tell you if you wan save a file called **scenario.json**.  You go click OK.

11. Click di function **winningProposal** to confam say di final proposal don win — wey na di proposal for position 2 inside di array. **0: uint256: winningProposal_ 2**
