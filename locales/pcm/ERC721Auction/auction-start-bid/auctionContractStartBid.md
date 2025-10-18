For here we go create di function to take start di auction and di function to take bid for NFT.

### Start am

We go use control structue to sabi if some kind conditions dey met before we fit make di seller start auction.

We go first see if di seller don start (line 49). If e don start and awa state variable `started` returns `true` we go exit di function come throway exception.

Di second thing an to check weda di seller dey execute di function (line50). We don already create function to take store di seller address wen dem deploy di contract for di `seller` state variable and you fit now check if de account wey dey execute di start function na di seller. If not we go throw exception enter.

Di next one we go transfer di NFT wey dey up to fit auction from di seller reach di contract (line 52).
Na we set di state variable `started` go `true` (line 53), come create date wey di auction go end (line 54). For dis matta e go be seven days from wen dem start di start function. We fit use suffix like `days` after literal number to take specify di units of time. If you wan sabi more about di time unit go look di <a href="https://docs.soliditylang.org/en/latest/units-and-global-variables.html#time-units" target="_blank">solidity wey dem document</a>.

Las las we go emit our `Start()` event (line 56).

### Di bid

Before di function caller fit make bid, we to dey sure say some kind conditions dem meet am. Di auctiom suppose don start (line 60), di auction no go don end (line 61) and di bid (di value wey dem add go di call) need to high pass di high bid wey dey current (line 62).

Now we wan store di bid of di bid wey high and current pass before we go make new bid.
First tin first make we see if bidder dey (line 64). For dis function di call na di first bid den di next line no go need.
For our mapping `bids` (line 34) we go map di key, di `address` of di bidder, to di value, a `uint` wey dey represent di whole amount of ETH wey di bidder don bid for auction before e widraw.
If bidder dey we go add di last bid (`highestBid`) of di `highestBidder` to di whole value of di bids wey dem don make (line 65) beefore you widraw.
We dey store di bids unto say w wan make di bidder make e widraw di ETH dem dey use take make bids if dem no come be di highest bidder.

After dat wan we do put de Bidder wey high wel well to de account wey dey cal de function (line 68) and de highestBid to dier own bid de value wey dem send wit de call (line 69).

Finally we don emit de bid event we be (line 71).

## De Asignment

1. U go deploy NFT contract. U fit use NFT contract wey we create for our own solidity NFT course Learneth course.

2. U go mint urself NFT wit de token 0.

3. U go deploy de EngishAuction contract. U go use de address of NFT contact as argument wey be for _nft parameter, 0 for de nftld, and 1 to te `_startBid`.

4. U go call de approve function of ur own NFT contract wit de address of de auction contract as argument for de to parameter, and0 wey be for de tokend. E go gree make di contract transfer di token ey wan dey auctioned.

5. Put call for di `start` function of your auction contract. If you call di `started` function now, e suppose come back `true`. Wen you put call for di `highestBid` functione suppose go back 1.

6. Put di value wey you fit join to transaction go 3 Wei make you call di bid functiom of di conrakt of di auction. If you put call for di `highestBid` function e suppose go back 3.