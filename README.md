# MEV 봇 개발 로드맵

### 들어가며

MEV는 정말 신세계다.
전통 금융 업계에 종사하던 나에게 신선한 충격을 안겨주었고, 결과적으로 블록체인 기술에 대한 흥미로 이어지게 한 장본인이다.
풀타임으로 관련 기술 공부를 하기 위해서 직장을 그만뒀는데, 솔직히 조금 막막하다.
MEV 관련 자료는 웹상에도 잘 없고, 있다고 해도 영어와 프로그래밍을 모두 잘 해야 한다.
그리고 소스가 여기저기 뿌려져 있어서 MEV 여정을 시작하는 나같은 사람들에게 도움이 되고자 한 곳에 관련 자료를 모두 모아보았다.
거의 모든 자료가 영어라는 점은...

나는 차익거래와 마켓메이킹 전략에 관심이 많다.
그리고 이런 전략들은 모두 속도가 중요하다.
그래서 Go, Rust를 배우기로 결심했다.
아래의 많은 자료들은 Javascript, Go, Rust를 알아야 볼 수 있는 자료들이다.

### 1. 블록체인이란?

MEV 봇을 개발하려면 개발/금융 지식보다 블록체인 기술에 대한 이해가 필수적이다.
아무리 개발을 잘하고, 투자를 잘 하는 사람이라도 블록체인의 트랜잭션, 합의 원리, 가스비 관련된 지식이 없으면 경쟁에서 이길 수 없다.
당장 이해하기 어려운 영역이라면, 두고두고 기술에 대한 공부를 하는 것이 좋다.

##### 비트코인
- (고급) bitcoinbook: https://github.com/bitcoinbook/bitcoinbook
- (고급) grokking bitcoin: https://github.com/kallerosenbaum/grokkingbitcoin

##### 이더리움
- (초급) 이더리움 공식 사이트: https://ethereum.org/en/what-is-ethereum/
- (고급) mastering ethereum: https://github.com/ethereumbook/ethereumbook

### 2. 스마트 컨트랙트란?

쉽게 배울 수 있지만, 잘하기는 가장 어려운 영역.
다른 프로그래밍 언어보다 쉬워서 빨리 시작할 수 있지만, 결국 이더리움 기술에 대한 이해도가 높아져야 더 깊게 팔 수 있는 영역이다.
MEV 수익과 직결되는 보안, 비용 절감을 위해서 필수적으로 알고 있어야 하는 부분.

#### Solidity
- (초급) Patrick Collins 유투브: https://www.youtube.com/watch?v=umepbfKp5rI
- (초급) cryptozombies: https://cryptozombies.io/
- (고급) Solidity 공식 문서: https://docs.soliditylang.org/en/v0.8.20/
- (고급) Solidity by example: https://solidity-by-example.org/

##### 개발 환경
- (초급) Foundry: https://book.getfoundry.sh/
- (초급) Hardhat tutorial: https://hardhat.org/tutorial

### 3. 디파이란?

블록체인에 존재하는 모든 상품은 디파이와 엮여있다.
토큰, NFT, 대출, 청산, DEX.
디파이에 존재하는 레고 블록들을 잘 이해하고 활용해야 한다.

#### 토큰
- ERC20: https://ethereum.org/ko/developers/docs/standards/tokens/erc-20/
- ERC721: https://ethereum.org/ko/developers/docs/standards/tokens/erc-721/
- ERC1155: https://ethereum.org/ko/developers/docs/standards/tokens/erc-1155/

#### 대출 서비스
- MakerDAO (DAI): https://docs.makerdao.com/
- AAVE: https://docs.aave.com/hub/
- Compound: https://docs.compound.finance/

#### DEX (거래소)
거의 모든 DEX는 Uniswap 코드를 기반으로 만들어졌다.
스테이블코인 같은 경우 Curve의 스테이블스왑을 사용하는 경우가 많기 때문에 Curve도 빠지지 않고 보면 좋다.

- Uniswap: https://docs.uniswap.org/
- Curve: https://resources.curve.fi/

- Uniswap V3 쉽게 이해하기 (concentrated liquidity): https://uniswapv3book.com/docs/introduction/uniswap-v3/

몇달 뒤면 Uniswap V4가 나올 것 같다.
Uniswap은 모든 DEX의 엄마와도 같기 때문에 공부를 하면 좋다.

- Uniswap V4: https://github.com/Uniswap/v4-core

#### Flashloan
DeFi 투자가 CeFi 투자보다 자본 효율적일 수 있는 방법이다.
전통 시장에서 넘어오는 사람들이 가장 놀라는 부분이 바로 flashloan이고, 그만큼 이해하기 어려운 부분이기도 하다.
하지만, 블록체인 공부를 조금 하였고, transaction atomicity를 이해한다면, flashloan도 쉽게 이해할 수 있다.

- Aave flashloan: https://docs.aave.com/developers/guides/flash-loans
- Balancer flashloan (수수료 0%): https://docs.balancer.fi/reference/contracts/flash-loans.html
- Uniswap flashswap: https://docs.uniswap.org/contracts/v2/guides/smart-contract-integration/using-flash-swaps

### 4. MEV란?
MEV의 강자인 Paradigm.xyz의 리서치 자료를 한번 보면 좋다.

- Paradigm.xyz: https://www.paradigm.xyz/writing
- Frontier Research: https://frontier.tech/
- MEV toolkit: https://github.com/go-outside-labs/mev-toolkit
- EigenPhi: https://eigenphi.io/

MEV 봇이 무적은 아니다...
- Salmonella bot: https://github.com/Defi-Cartel/salmonella

### 5. Flashbots
MEV를 세상에 알린 Flashbots의 기술을 이해하고 사용한다.

- 메인 페이지: https://www.flashbots.net/
- Searcher가 되기 위한 준비: https://docs.flashbots.net/flashbots-auction/searchers/quick-start
- MEV-boost: https://docs.flashbots.net/flashbots-mev-boost/introduction

- MEV-boost를 활용한 간단한 Typescript 차익거래 봇: https://github.com/flashbots/simple-arbitrage
- MEV-share를 활용한 Javascript 차익거래 봇: https://github.com/flashbots/simple-blind-arbitrage

### 6. EVM 작동 원리 & GETH/RETH
결국 MEV 기회는 이더리움의 작동 원리에 있다.
중앙화된 전통 시장에서는 필요없던 miner, validator들이 사용하는 block building/proposing 과정에서 발생하는 비효율성을 이해한다.
이를 활용하고 싶다면, 새로운 블록이 블록체인 DB에 기록되는 합의(consensus) 과정을 잘 이해하고 있어야 한다.
이를 가장 확실하게 하는 방법은 GETH 혹은 RETH를 이해하는 방법이다. (특히, evm, state, consensus 부분)
GETH의 역사가 가장 깊고, Go 언어가 Rust보다 비교적 쉽지만, 새로 나온 Reth를 공부하는 것도 좋은 생각이다.
Reth는 Paradigm.xyz에서 직접 개발한 이더리움 implementation이고, MEV에 특화되어 있는 부분들이 있다.

- ethers-rs: https://github.com/gakonst/ethers-rs
- Reth: https://github.com/paradigmxyz/reth
- Reth에서 사용하는 revm: https://github.com/bluealloy/revm

- Solidity assembly: https://solidity-kr.readthedocs.io/ko/latest/assembly.html
- Huff 언어: https://docs.huff.sh/tutorial/overview/

- 시뮬레이션 서비스: https://tenderly.co/transaction-simulator
- revm을 활용한 트랜잭션 시뮬레이션 기반 MEV 차익거래 봇: https://github.com/mouseless-eth/rusty-sando

### 7. Gas 최적화

MEV를 보다보면 사이사이에 지불하는 fee가 많은데, 수익을 조금이라도 더 남기기 위해서는 gas 비용을 최적화하는 것이 중요하다.

- 0xkitsune의 gas optimization 테크닉: https://github.com/0xKitsune/EVM-Gas-Optimizations
- 사용된 툴: https://github.com/0xKitsune/gas-lab

- awesome-solidity-gas-optimization: https://github.com/0xisk/awesome-solidity-gas-optimization

### 8. 스마트 컨트랙트 보안 이슈

Christoph Michel의 블로그를 본다.

- 블로그: https://cmichel.io/
- Damn Vulnerable DeFi: https://cmichel.io/damn-vulnerable-de-fi-solutions/
- Ethernaut: https://cmichel.io/ethernaut-solutions/
- Capture the Ether: https://cmichel.io/capture-the-ether-solutions/

### 9. 유명한 MEV봇 샘플/템플렛

Degatchi의 블로그를 잘 본다.
- 블로그: https://degatchi.com/

Python을 좋아한다면, BowTiedDevil의 substack을 본다.
- substack: https://substack.com/@degencode

- (초급) degatchi/mev-template-rs: https://github.com/degatchi/mev-template-rs
- (초급) thasarito/simple-arbitrage-rs: https://github.com/thasarito/simple-arbitrage-rs
- (중급) refcell/subway-rs: https://github.com/refcell/subway-rs
- (고급) mouseless-eth/rusty-sando: https://github.com/mouseless-eth/rusty-sando
- (고급) 0xKitsune/cfmms-rs: https://github.com/0xKitsune/cfmms-rs
- (고급) paradigmxyz/artemis (sudoswap-opensea 차익거래): https://github.com/paradigmxyz/artemis

### 10. 알아두면 좋은 테크닉

- 재배포가 가능한 metamorphic 스마트 컨트랙트: https://github.com/0age/metamorphic
- multicall: https://github.com/mds1/multicall
