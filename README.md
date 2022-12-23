# decentralized-identity-resources
A comprehensive overview of decentralized identity

# Precursors and Related Projects

### PGP: pretty good privacy
1. OpenPGP ([link](https://www.openpgp.org/)): open source version of PGP
2. key servers ([link](https://www.reddit.com/r/GnuPG/comments/ix2gdj/what_pgp_key_server_to_use/)): searchable public keys and key signing
3. key signing party ([Zimmermann-Sassaman](https://web.archive.org/web/20061205200342/http://sion.quickie.net/keysigning.txt), [Brennen](https://www.cryptnet.net/fdp/crypto/keysigning_party/en/keysigning_party.html)): in-person attestation of public keys using signatures to generate a web of trust. Zimmermann-Sassaman consists of 3 stages: before, during, and after. Before the leader accumulates all keys in a list, each participant verifies their key and prints out all keys and checksums. During the party, each participant attests to their fingerprint and then proves their identity with at least 2 government IDs. After, each participant signs other people's keys that were valid. 
4. PGP web of trust ([wiki](https://en.wikipedia.org/wiki/Web_of_trust): an emergent network of trust based on key signing. Problems include bootstapping, sybil attacks, difficulty of use for average user, key revocation, and key loss. 

### signalling in hard/soft forks
1. activation, MASF, UASF ([link](https://bitcoinops.org/en/topics/soft-fork-activation)): Miner activated soft fork (MASF) is governance through block signalling. The more mining power or stake one has, the more blocks one can produce. Pools signal as a group. User activated soft fork (UASF) is governance through full nodes. The rules supported by the "economic majority" of full nodes is the winning rules. 

### Certificate Authorities (CA) and HTTPS
1. Provides secure websites and eliminates man-in-the-middle attack by using a hierarchy of certificates. Base certificates come preinstalled in OS and browser. 

### decentralized DNS
1. Namecoin ([whitepaper](https://www.namecoin.org/resources/whitepaper)): key/value pairs. If key (name) is not unique, transaction is invalid.
2. Stacks ([docs](https://docs.stacks.co/docs/build-apps/references/bns), [white](https://assets.stacks.co/stacks.pdf)): Bitcoin layer

### governance
1. Kleros ([whitepaper](https://kleros.io/whitepaper.pdf): 

## Mechanisms

### CAPTCHA: Completely Automated Public Turing test to tell Computers and Humans Apart
1. original paper ([paper](https://link.springer.com/content/pdf/10.1007/3-540-39200-9_18.pdf))
2. Idena FLIP ([medium](https://medium.com/idena/ai-resistant-captchas-are-they-really-possible-760ac5065bae)): Human-generated CAPTCHA. The theory is that it is easier for AIs to complete generated CAPTCHAs than human-generated CAPTCHAs.

### Soulbound Token (SBT): non-transferrable identity tokens
1. original post ([paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4105763), [Vitalik](https://vitalik.ca/general/2022/01/26/soulbound.html))
2. 

## Decentralized Identity Projects
1. Idena ([link](https://docs.idena.io/docs/wp/technology)): proof-of-personhood based on frequent CAPTCHA-like puzzles. Missing or failing identity tests slashes stake and downgrade identity status. Idena has it's own blockchain with POP consensus. There are three downsides. First, repeated validation is needed to maintain identity. Second, individuals fast at solving "flips" can have more than one identity. Lastly, AI will (likely) catch up with human ability to solve flips. 
2. Upala ([link](https://docs.upala.id/en/latest/whitepaper.html), [github](https://github.com/upala-digital-identity/upala)): users join a pool of members and have a currency value assigned to their identity. This currency can be redeemed by deleting their identity and this depletes the pool's account. This mechanism incentives pools to assign higher values to more trustworthy identities. User's want higher scores for lowest investment. Apps that want identity can require a minimum score to use the app. This solution does not guarantee uniqueness of identity.
3. BrightID ([whitepaper](https://www.brightid.org/whitepaper)): P2P web of trust. Nodes that are weakly connectly to graph or distantly connected to strong identities are discarded. This solution does not guarantee uniqueness of identity.
4. duniter ([link](https://duniter.org/blog/duniter-deep-dive-wot/): TODO
5. Masa ([link](https://www.masa.finance/))
6. Kudos ([link](https://mintkudos.xyz/): This is not a proof of personhood protocol but it can contribute to building a decentralized identity. Users can get soulbound tokens for achieving stuff. For example, if a user could get a Kudos from a course they completed. 
7. Proof of Humanity ([paper](https://arxiv.org/ftp/arxiv/papers/2008/2008.05300.pdf)): People make a video of themselves saying they would like to join the registry while holding the text of their address. They must stake ethereum. People whose identities are already verified can vouch for new members by using their stake. People can challenge the identity and or a voucher of an identity. If there is a challenge there is an arbitration court that will resolve the challenge. Kleros courts are used to resolve the challenge.
8. Sismo ([link](https://docs.sismo.io/sismo-docs/devs-technical-doc/sismo-protocol)
9. Worldcoin ([link](https://worldcoin.org/introducing-worldcoin)): Uses iris scanning device to generate proof of personhood. Hash of biometric stored for privacy purposes. Relies on trusted hardware.
10. HumanityDAO ([medium](https://github.com/marbleprotocol/humanity), [github](https://github.com/marbleprotocol/humanity)): Dead project. Verfication though DAO members voting on social media links and bio. Identity rejection forfeits user's stake. Only incentive to vote honestly is maintaining the future growth DAO (Cartel problem).
11. more projects: [duniter](https://duniter.org/blog/theoretical), 

## Proof-of-personhood consensus (POP)
TODO

## Use cases
1. less spam and misinformation
2. accurate ratings and reputations
3. democratic governance ([vitalik](https://vitalik.ca/general/2017/12/17/voting.html]), [quadratic voting](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2003531))
4. univeral basic income (UBI)
5. replacing CAPTCHA with signatures
