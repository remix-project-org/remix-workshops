For dis place, we go finish di contract, come do function to take commot di bids wey akant don make, come create di function to take stop di auction.

### Commot am

We been make local variabu `bal` (balance) wey dey keep di whole value wey de function caller don make (line 75) time wey dem widraw last. We fit carry dis value go `bal` make we access di bids im maps come dey use di adress wey Di function caller get as di key.

Now, we go carry di value of di address of di function caller go 0 for di bids im map unto say dem go commot d while value of di bids (line 76).

As e be now we fit commot di amount of di ETH from di contract go di funkshon mallee come emit di `Withdraw` event (line 79).

### Di end

Before di funkshon kaller go fit do anytime on top di funkshon come end di auction we go need check if dem meet some kind things. Di aukshon need to don start sef (line 83), di end date of di aukshon go nid to don reach (line 84), and di auction no suppose end (line 85).

As de auction go end, we don set di state variables `ended` go `true` (line 87).

We don see if person join for di auction come do bid wey dey NFT (line 88).

If bid dey, we go transfa di NFT come from contrakt go who bid pass (line 89) come transfa di ETH wey dem send from who bid high pass go di contrakt, now go di address of who auction him thing wey dey sell di NFT (line 90).

If person no bid for di NFT, we go carry am go meet who get am (line 92).

Now now, we come emit di `End` event (line 95).

## De Asignment

1. U go deploy NFT contract. U fit use NFT contract wey we create for our own LearnEth "Solidity NFT Course".

2. U go mint urself NFT wit de tokenld 0.

3. Just to take test how e be, change di value wey dem put for di `endAt` state variable (line 54) from `7 days` go \`5 minis.

4. Use dis EnglishAuction contract. Use di NFT contract im address take argue di `_nft` parameter, 0 for `_nftId`, and 1 for `_startingBid`.

5. Make you put call for di `approve` function for your NFT contract wit di address of di auction contract take argue for di `to` parameter, and 0 for di `tokenId`.

6. Put call for di `start` function of your auction contract.

7. Run Bid 2 Ether wey dey use akant 1 and 3 Ether wey dey use akant 2. Wen you put call for di function for who bid pass e go carry di adress of akant 2 go back.

8. Make you call di widraw function with akant 1. For akant 1 for wetin remain you go see di 2 Ether if you commot transaction fees.

9. If 5 minutes commot, put call for di end function. Put call for di function wey don end wey suppose come back true.

For di NFT contrakt wen you put call for who get di function wit di tokenld 0, e suppose give Una di address of akant 2 back. Put eyes for wetin remain for akant 1 e suppose don go up by 3 Ether commot some fees wey e take transact.
