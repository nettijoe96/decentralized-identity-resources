# decentralized-identity-resources
list of decentralized identity resources and projects

## definitions
TODO

## primitives
TODO

## precursors

### PGP: pretty good privacy
1. OpenPGP ([link](https://www.openpgp.org/)): open source version of PGP
2. key servers ([link](https://www.reddit.com/r/GnuPG/comments/ix2gdj/what_pgp_key_server_to_use/)): searchable public keys and key signing
3. key signing party ([Zimmermann-Sassaman](https://web.archive.org/web/20061205200342/http://sion.quickie.net/keysigning.txt), [Brennen](https://www.cryptnet.net/fdp/crypto/keysigning_party/en/keysigning_party.html)): in-person attestation of public keys using signatures to generate a web of trust. Zimmermann-Sassaman consists of 3 stages: before, during, and after. Before the leader accumulates all keys in a list, each participant verifies their key and prints out all keys and checksums. During the party, each participant attests to their fingerprint and then proves their identity with at least 2 government IDs. After, each participant signs other people's keys that were valid. 

### decentralized DNS
1. Namecoin ([whitepaper](https://www.namecoin.org/resources/whitepaper)): key/value pairs. If key (name) is not unique, transaction is invalid. It's own blockchain.
2. Stacks ([docs](https://docs.stacks.co/docs/build-apps/references/bns), [white](https://assets.stacks.co/stacks.pdf)): Bitcoin layer

### voting
1. quadratic voting ([paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2003531))

### governance
TODO

## Mechanisms

### CAPTCHA: Completely Automated Public Turing test to tell Computers and Humans Apart
1. original paper ([paper](https://link.springer.com/content/pdf/10.1007/3-540-39200-9_18.pdf))
2. Idena FLIP ([medium](https://medium.com/idena/ai-resistant-captchas-are-they-really-possible-760ac5065bae)): Human-generated CAPTCHA. The theory is that it is easier for AIs to complete generated CAPTCHAs than human-generated CAPTCHAs.

## projects
1. HumanityDAO ([medium](https://github.com/marbleprotocol/humanity), [github](https://github.com/marbleprotocol/humanity)): Verfication though DAO members voting on social media links and bio. Identity rejection forfeits user's stake. Only incentive to vote honestly is maintaining the future growth DAO (Cartel problem). 
2. 

## use cases
1. less spam and misinformation
2. accurate ratings and reputations
3. democratic governance ([vitalik](https://vitalik.ca/general/2017/12/17/voting.html]))
4. univeral basic income (UBI)
