# Decentralized Identity Resources
A comprehensive overview of decentralized identity projects. 

## Precursors and Related Technology

### PGP: pretty good privacy
- [OpenPGP](https://www.openpgp.org/): open source version of PGP
- key servers ([reddit](https://www.reddit.com/r/GnuPG/comments/ix2gdj/what_pgp_key_server_to_use/)): searchable public keys and key signing
- key signing party ([Zimmermann-Sassaman](https://web.archive.org/web/20061205200342/http://sion.quickie.net/keysigning.txt), [Brennen](https://www.cryptnet.net/fdp/crypto/keysigning_party/en/keysigning_party.html)): in-person attestation of public keys using signatures to generate a web of trust. Zimmermann-Sassaman consists of 3 stages: before, during, and after. Before the leader accumulates all keys in a list, each participant verifies their key and prints out all keys and checksums. During the party, each participant attests to their fingerprint and then proves their identity with at least 2 government IDs. After, each participant signs other people's keys that were valid. 
- PGP web of trust ([wiki](https://en.wikipedia.org/wiki/Web_of_trust)): an emergent network of trust based on key signing. Problems include bootstapping, sybil attacks, difficulty of use for average user, key revocation, and key loss. 

### certificate authorities (CA) and HTTPS
- Provides secure websites and eliminates man-in-the-middle attack by using a hierarchy of certificates. Base certificates come preinstalled in OS and browser. 

### signalling in hard/soft forks
- activation, MASF, UASF ([link](https://bitcoinops.org/en/topics/soft-fork-activation)): Miner activated soft fork (MASF) is governance through block signalling. The more mining power or stake one has, the more blocks one can produce. Pools signal as a group. User activated soft fork (UASF) is governance through full nodes. The rules supported by the "economic majority" of full nodes is the winning rules. 

### decentralized DNS
- Namecoin ([whitepaper](https://www.namecoin.org/resources/whitepaper)): key/value pairs. If key (name) is not unique, transaction is invalid.
- Stacks ([docs](https://docs.stacks.co/docs/build-apps/references/bns), [whitepaper](https://assets.stacks.co/stacks.pdf)): layer on top of Bitcoin that includes name ownership

### schelling games and data oracles
- schelling games are relevant because they are a precusor to Kleros.
- original work by Thomas Schelling ([book](https://www.hup.harvard.edu/catalog.php?isbn=9780674840317))
- Schellingcoin: A minimal-trust universal data feed. ([post](https://blog.ethereum.org/2014/03/28/schellingcoin-a-minimal-trust-universal-data-feed/))
- Truthcoin ([whitepaper](http://www.truthcoin.info/papers/truthcoin-whitepaper.pdf/))

### decentralized data storage
- decentralized identity might use decentralized data storage for storing larger amounts of data (and then referencing it via a hash on the blockchain)
- IPFS ([whitepaper](https://github.com/ipfs/ipfs/blob/master/papers/ipfs-cap2pfs/ipfs-p2p-file-system.pdf)): A decentralized storage system that is essentially bittorrent with a distributed hash table (DHT) for routing and discovery.  
- Filecoin ([whitepaper](https://filecoin.io/filecoin.pdf))
- Siacoin and Skynet ([website](https://siasky.net/),[medium](https://blog.sia.tech/a-deep-dive-into-skynet-a0fa037feea)): unfortunately Skynet will not continue developing due to lack of funding

### decentralized social media
- decentralized identity could help reduce spam and verify people on social media
- [mastadon](mastodon.social)
- [pleroma](https://pleroma.social/)
- [bluesky](https://blueskyweb.org/)

### governance
- Decred ([docs](https://docs.decred.org/#what-is-decred)): governance focused blockchain that uses stake-based voting to decide software changes and budget allocations. Decred's consensus is a hybrid of POW and POS where POW generates a block and POS accepts/declines block. This allows for stakeholders to regulate the behavior of miners.
- Kleros ([whitepaper](https://kleros.io/whitepaper.pdf)): a stake-based court system where jurors are selected based on staked pinakion (PNK). Jurors that do not vote with majority have stake reallocated to majority jurors (Schelling game). Reallocation incentivizes jurors to actually participate and not vote randomly. However, it gives even more power to those with greater stake to influence the outcome.

### CAPTCHA: Completely Automated Public Turing test to tell Computers and Humans Apart
- original paper ([paper](https://link.springer.com/content/pdf/10.1007/3-540-39200-9_18.pdf))
- Idena FLIP ([medium](https://medium.com/idena/ai-resistant-captchas-are-they-really-possible-760ac5065bae)): Human-generated CAPTCHA. The theory is that it is easier for AIs to complete generated CAPTCHAs than human-generated CAPTCHAs.

## Current projects

### soulbound token (SBT): non-transferrable identity tokens
- original post ([paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4105763), [Vitalik](https://vitalik.ca/general/2022/01/26/soulbound.html), [ERC1155](https://eips.ethereum.org/EIPS/eip-1155))
- Masa ([website](https://www.masa.finance/)): One of the first SBTs launched on Ethereum. Creating a decentralized credit bureau.
- Kudos ([website](https://mintkudos.xyz/)): This is not a proof of personhood protocol but it can contribute to building a decentralized identity. Users can get soulbound tokens for achieving stuff. For example, a user could recieve a Kudos from a course they completed.
- Sismo ([docs](https://docs.sismo.io/sismo-docs/devs-technical-doc/sismo-protocol), [video](https://www.youtube.com/watch?v=6vCb6XwGSOk)): smart contracts (attestors) that can create a variety of SBTs using previous ethereum transactions. For example, an SBT showing Alice was active in a DAO.

### web of trust (WOT)
- BrightID ([whitepaper](https://www.brightid.org/whitepaper)): P2P web of trust. Nodes that are weakly connectly to graph or distantly connected to strong identities are discarded. This solution does not guarantee uniqueness of identity.
- duniter ([docs](https://duniter.org/blog/duniter-deep-dive-wot/))

### biometrics-based
- Worldcoin ([website](https://worldcoin.org)): Uses iris scanning device to generate proof of personhood. Hash of biometric stored for privacy purposes. Relies on trusted hardware.

### puzzle-based
- Idena ([docs](https://docs.idena.io/docs/wp/technology)): proof-of-personhood based on frequent CAPTCHA-like puzzles. Missing or failing identity tests slashes stake and downgrade identity status. Idena has it's own blockchain with POP consensus. There are three downsides. First, repeated validation is needed to maintain identity. Second, individuals fast at solving "flips" can have more than one identity. Lastly, AI will (likely) catch up with human ability to solve flips. 

### convincing humans
- Proof of Humanity ([paper](https://arxiv.org/ftp/arxiv/papers/2008/2008.05300.pdf)): People make a video of themselves saying they would like to join the registry while holding the text of their address. They must stake ethereum. People whose identities are already verified can vouch for new members by using their stake. People can challenge the identity and or a voucher of an identity. If there is a challenge there is an arbitration court that will resolve the challenge. Kleros courts are used to resolve the challenge.
- Upala ([docs](https://docs.upala.id/en/latest/whitepaper.html), [github](https://github.com/upala-digital-identity/upala)): users join a pool of members and have a currency value assigned to their identity. This currency can be redeemed by deleting their identity and this depletes the pool's account. This mechanism incentives pools to assign higher values to more trustworthy identities. User's want higher scores for lowest investment. Apps that want identity can require a minimum score to use the app. This solution does not guarantee uniqueness of identity.
- HumanityDAO ([medium](https://github.com/marbleprotocol/humanity), [github](https://github.com/marbleprotocol/humanity)): Dead project. Verification though DAO members voting on social media links and bio. Identity rejection forfeits user's stake. Only incentive to vote honestly is maintaining the future growth DAO (Cartel problem).

### corporate
- Microsoft ([sales pitch](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2DjfY))

## proof-of-personhood consensus (POP)
A consensus mechanism where each unique identity receieves equal voting power in consensus. When the number of identities is too large to efficiently run consensus, a subset of staking identities are randomly selected. The randomness source could be the previous block hash or VDF result. There is some small mandatory stake for any identity that wants to participate in consensus. With a reasonable group size, [pBFT](https://pmg.csail.mit.edu/papers/osdi99.pdf) or another BFT protocol can be used for efficient consensus. Every cooperating identity recieves a reward and non-cooperating entitites get slashed. In a consensus round, identities must not know who else is participating in consensus--otherwise there is a clear risk for collusion. BLS signature aggregation can be used (like in Casper) to make consensus more efficient. If fact, any secure POS consensus can be used for POP consensus because POP can be modeled as POS where all stakes are equal. POP suffers (like POS) from weak subjectivity, which is when a full node that joins or reconnects to the P2P network needs to ask peers what the correct head is (to avoid long range attacks). Weak subjectivity increases the scope of sybil attacks and also the importance of proper peer seeding. 51% attack in POP is 51% of identities colluding, which is significantly harder than in POS/POW--provided that the identity mechanism is secure. 

## use cases
1. less spam and misinformation
2. accurate ratings and reputations
3. democratic governance of DAOs and blockchains ([vitalik](https://vitalik.ca/general/2017/12/17/voting.html]), [quadratic voting](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2003531))
4. univeral basic income (UBI)
5. replacing CAPTCHA with signatures
6. replacing stake-based applications with identity-based equivalent applications (courts, data oracles, gitcoin, etc)

## further reading
1. https://bford.info/pub/dec/pop.pdf
2. https://arxiv.org/abs/1806.07583
3. https://eprint.iacr.org/2020/934.pdf
4. https://medium.com/ethereum-optimism/retroactive-public-goods-funding-33c9b7d00f0c
5. https://vitalik.ca/general/2017/03/14/forks_and_markets.html
6. https://vitalik.ca/general/2017/12/17/voting.html
7. https://vitalik.ca/general/2021/05/25/voting2.html
8. https://vitalik.ca/general/2021/08/16/voting3.html
9. https://vitalik.ca/general/2018/03/28/plutocracy.html