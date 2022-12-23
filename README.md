# Decentralized Identity Resources
A comprehensive overview of decentralized identity projects. 

## Precursors

### PGP: pretty good privacy
- [OpenPGP](https://www.openpgp.org/): open source version of PGP
- key servers ([reddit](https://www.reddit.com/r/GnuPG/comments/ix2gdj/what_pgp_key_server_to_use/)): searchable public keys and key signing
- key signing party ([Zimmermann-Sassaman](https://web.archive.org/web/20061205200342/http://sion.quickie.net/keysigning.txt), [Brennen](https://www.cryptnet.net/fdp/crypto/keysigning_party/en/keysigning_party.html)): in-person attestation of public keys using signatures to generate a web of trust. Zimmermann-Sassaman consists of 3 stages: before, during, and after. Before the leader accumulates all keys in a list, each participant verifies their key and prints out all keys and checksums. During the party, each participant attests to their fingerprint and then proves their identity with at least 2 government IDs. After, each participant signs other people's keys that were valid. 
- PGP web of trust ([wiki](https://en.wikipedia.org/wiki/Web_of_trust)): an emergent network of trust based on key signing. Problems include bootstapping, sybil attacks, difficulty of use for average user, key revocation, and key loss. 

### signalling in hard/soft forks
- activation, MASF, UASF ([link](https://bitcoinops.org/en/topics/soft-fork-activation)): Miner activated soft fork (MASF) is governance through block signalling. The more mining power or stake one has, the more blocks one can produce. Pools signal as a group. User activated soft fork (UASF) is governance through full nodes. The rules supported by the "economic majority" of full nodes is the winning rules. 

### certificate authorities (CA) and HTTPS
- Provides secure websites and eliminates man-in-the-middle attack by using a hierarchy of certificates. Base certificates come preinstalled in OS and browser. 

### decentralized DNS
- Namecoin ([whitepaper](https://www.namecoin.org/resources/whitepaper)): key/value pairs. If key (name) is not unique, transaction is invalid.
- Stacks ([docs](https://docs.stacks.co/docs/build-apps/references/bns), [whitepaper](https://assets.stacks.co/stacks.pdf)): Bitcoin layer TODO

### governance
- Kleros ([whitepaper](https://kleros.io/whitepaper.pdf)): TODO

### CAPTCHA: Completely Automated Public Turing test to tell Computers and Humans Apart
- original paper ([paper](https://link.springer.com/content/pdf/10.1007/3-540-39200-9_18.pdf))
- Idena FLIP ([medium](https://medium.com/idena/ai-resistant-captchas-are-they-really-possible-760ac5065bae)): Human-generated CAPTCHA. The theory is that it is easier for AIs to complete generated CAPTCHAs than human-generated CAPTCHAs.

## Current projects

### soulbound token (SBT): non-transferrable identity tokens
- original post ([paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4105763), [Vitalik](https://vitalik.ca/general/2022/01/26/soulbound.html), [ERC1155](https://eips.ethereum.org/EIPS/eip-1155))
- Masa ([website](https://www.masa.finance/)): One of the first SBTs launched on Ethereum. Creating a decentralized credit bureau.
- Kudos ([website](https://mintkudos.xyz/)): This is not a proof of personhood protocol but it can contribute to building a decentralized identity. Users can get soulbound tokens for achieving stuff. For example, a user could recieve a Kudos from a course they completed.
- Sismo ([docs](https://docs.sismo.io/sismo-docs/devs-technical-doc/sismo-protocol), [video](https://www.youtube.com/watch?v=6vCb6XwGSOk)): TODO

### web of trust
- BrightID ([whitepaper](https://www.brightid.org/whitepaper)): P2P web of trust. Nodes that are weakly connectly to graph or distantly connected to strong identities are discarded. This solution does not guarantee uniqueness of identity.
- duniter ([docs](https://duniter.org/blog/duniter-deep-dive-wot/)): TODO

### biometrics-based
- Worldcoin ([website](https://worldcoin.org)): Uses iris scanning device to generate proof of personhood. Hash of biometric stored for privacy purposes. Relies on trusted hardware.
- Proof of Humanity ([paper](https://arxiv.org/ftp/arxiv/papers/2008/2008.05300.pdf)): People make a video of themselves saying they would like to join the registry while holding the text of their address. They must stake ethereum. People whose identities are already verified can vouch for new members by using their stake. People can challenge the identity and or a voucher of an identity. If there is a challenge there is an arbitration court that will resolve the challenge. Kleros courts are used to resolve the challenge.

### puzzle-based
- Idena ([docs](https://docs.idena.io/docs/wp/technology)): proof-of-personhood based on frequent CAPTCHA-like puzzles. Missing or failing identity tests slashes stake and downgrade identity status. Idena has it's own blockchain with POP consensus. There are three downsides. First, repeated validation is needed to maintain identity. Second, individuals fast at solving "flips" can have more than one identity. Lastly, AI will (likely) catch up with human ability to solve flips. 

### open-ended approaches
- Upala ([docs](https://docs.upala.id/en/latest/whitepaper.html), [github](https://github.com/upala-digital-identity/upala)): users join a pool of members and have a currency value assigned to their identity. This currency can be redeemed by deleting their identity and this depletes the pool's account. This mechanism incentives pools to assign higher values to more trustworthy identities. User's want higher scores for lowest investment. Apps that want identity can require a minimum score to use the app. This solution does not guarantee uniqueness of identity.
- HumanityDAO ([medium](https://github.com/marbleprotocol/humanity), [github](https://github.com/marbleprotocol/humanity)): Dead project. Verfication though DAO members voting on social media links and bio. Identity rejection forfeits user's stake. Only incentive to vote honestly is maintaining the future growth DAO (Cartel problem).

## proof-of-personhood consensus (POP)
A consensus mechanism where each unique identity receieves equal voting power in consensus. When number of identities is too large to efficiently run consensus, a subset of staking identities are randomly selected. The randomness source could be the previous block hash or VDF result. There is some small mandatory stake for any identity that wants to participate in consensus. With a reasonable group size, [pBFT](https://pmg.csail.mit.edu/papers/osdi99.pdf) or another BFT protocol can be used for efficient consensus. Every cooperating identity recieves a reward and non-cooperating entitites get slashed. In a consensus round, identities must not know who else is participating in consensus--otherwise there is a clear risk for collusion. BLS signature aggregation can be used (like in Casper) to make consensus more efficient. If fact, any secure POS consensus can be used for POP consensus because POP can be modeled as POS where all stakes are equal. Proof-of-personhood protocols run into the problem of weak subjectivity (like POS). Weak subjectivity is when a full node that joins or reconnects to the P2P network needs to ask peers what the correct head is (to avoid long range attacks).

## use cases
1. less spam and misinformation
2. accurate ratings and reputations
3. democratic governance ([vitalik](https://vitalik.ca/general/2017/12/17/voting.html]), [quadratic voting](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2003531))
4. univeral basic income (UBI)
5. replacing CAPTCHA with signatures
