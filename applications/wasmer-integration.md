# EOS Network Foundation Grant Proposal

- **Project Name:** Rust contract support on Antelope with Wasmer
- **Team Name:** DELIGHT LABS
- **EOS Payment Address:** delightlabs1
- **[Level](https://github.com/eosnetworkfoundation/grant-framework#grant-levels):** 3
- **Pomelo Grant(s):** 0

## Contact

- **Contact Name:** Bryan RHEE
- **Contact Email:** contact@delightlabs.io
- **Website:** [https://delightlabs.io/](https://delightlabs.io/)

## Project Overview

### Overview

- **Name:** Rust contract support on Antelope with Wasmer
- **Brief Description:** Mount Wasmer VM on Antelope and make Rust be available to write a smart contract.
- **Relationship to EOSIO:** More than C++, many developers using other languages could access & come into Antelope ecosystem and become to be an Antelope builder. We set the first target to Rust.
- **Reason for Interest:** We want to contribute in non-token area, like infrastructure. As our past experience of building on EOSIO, it run so fast but it seemed that few developers can understand and be a builder. C++ was essential language 10+ years ago, but the trend moves as time goes by. For making bigger builder pool, modern language support & language diversity are essential.

### Project Details

- Missions in brief
  - Wasmer mount on Antelope without breaking compatibility with past state DB data made by previous contracts in EOS VM
  - Develop Antelope contract developer tool (Antelope CDT) on Rust
- Why Rust as a contract language?
  - As Rust was born from the problem of C++, Rust is in similar position & system with C++
  - Rust - WASM compiler doesn't come out as fresh but updated & fixed with long enough history. It's stable enough than any other source language and continuously updated.
  - Rust is now broadly adopted as a frontend language for writing a WASM smart contract
- Why mount [Wasmer](https://wasmer.io/)? How would EOS VM be?
  - Both EOS VM and Wasmer execute a compiled WASM, not run as interpreter (wasmi)
  - Both of them are ranked in the fastest tier. [Wasm runtime benchmark in 2021](https://00f.net/2021/02/22/webassembly-runtimes-benchmarks/)
  - To compatible Rust with EOS VM, [Rust-LLVM](https://rust-lang.github.io/compiler-team/working-groups/llvm/) is needed but it is **not yet officially developed** but still in incubation period. Seems to be too long to wait to use a stable version.
  - On the side of CDT development, the compiled WASM executing on Wasmer is guranteed. We can focus on mapping between Rust code and current EOS VM instruction
  - On the side of communication between Wasmer and Antelope, we can focus on following current communication spec between EOS VM and Antelope transcation module.
  - As the contract state data on current Antelope has no dependency with EOS VM, we believe to mount Wasmer without data collision.

### Ecosystem Fit

By this implementation, Antelope can broad to one more contract language, Rust. And this would be the basis to broad to more language ecosystem. As recently WASM can be made from Golang and Javascript, we look forward Antelope to cover more popular language users.

## Team

### Team members

- **Team Leader:** Yeon HWANG

### Legal Structure

- **Registered Legal Entity:** Organized as a limited company. Fully supports social security & taxation service
- **Registered Address:** Hyecheon Bldg 1126-7 (11th flr), 354 Gangnam-daero, Gangnam, Seoul, SOUTH KOREA

### Team Experience

- Before blockchain, well experience in OS & emulator development (Tizen)
- Much experience in validating Cosmos SDK based projects & ETH layer 2 blockchains
- Experience in blockchain core development (connect between Tendermint & WASM execution engine)
- 1st dApp on Terra(now Terra classic): Terraswap - enough experience of WASM-based smart contract development & action processing
- Mainnet technical partner of Xpla (former C2X)
- EOSIO based project building experience (Polaris of Chain Partners, mentor & participant of EOSIO hackathon)

### Team Org Repos

[https://github.com/DELIGHT-LABS](https://github.com/DELIGHT-LABS)

### Team Member Repos

- Yeon HWANG: [https://github.com/caramis](https://github.com/caramis)
- Joon LEE: [https://github.com/jbamlee](https://github.com/jbamlee)
- Young LEE: [https://github.com/jhlee-young](https://github.com/jhlee-young)
- Sooyoung HA: [https://github.com/yoosah](https://github.com/yoosah)
- Bryan RHEE: [https://github.com/psy2848048](https://github.com/psy2848048)
- Joowon YUN: [https://github.com/JoowonYun](https://github.com/JoowonYun)
- Maro KIM: [https://github.com/honeymaro](https://github.com/honeymaro)

### Team LinkedIn Profiles (if available)

- Yeon HWANG: [https://www.linkedin.com/in/yeon-hwang/](https://www.linkedin.com/in/yeon-hwang/)
- Joon LEE: [https://www.linkedin.com/in/joonbum-lee-173354112/](https://www.linkedin.com/in/joonbum-lee-173354112/)
- Young LEE: [https://www.linkedin.com/in/jihyunglee/](https://www.linkedin.com/in/jihyunglee/)
- Derick MOON: [https://www.linkedin.com/in/sanghoon-moon-79b5a81b2/](https://www.linkedin.com/in/sanghoon-moon-79b5a81b2/)
- Sooyoung HA: [https://www.linkedin.com/in/sooyoung-ha-9a0195140/](https://www.linkedin.com/in/sooyoung-ha-9a0195140/)
- Bryan RHEE: [https://www.linkedin.com/in/psy2848048/](https://www.linkedin.com/in/psy2848048/)
- Joowon YUN: [https://www.linkedin.com/in/joowon-yun-520a1557/](https://www.linkedin.com/in/joowon-yun-520a1557/)
- Maro KIM: [https://www.linkedin.com/in/maro/](https://www.linkedin.com/in/maro/)

## Development Status

7 developers (1 FE, 1 data, 5 BE & system) and 1 product designer are working in DELIGHT LABS. We had full experience in Cosmos SDK projects - both of validation & dApp building. Especially, we validate 10+ projects including Terra classic, Terra 2.0, ORBS, Xpla, Oasis protocol, Fetch.ai, Findora, Casperlabs, SSV, Rizon, Medibloc, and so on, and we build & operate 1st dApp and AMM DEX - Terraswap on both of Terra classic & 2.0.

Not only dApp but we're also directly handles their core logic. Here are the referneces below:

- Tendermint/Cosmos-SDK - Casperlabs EE engine (wasmi-based WASM executor) connection [Cosmos-side repo](https://github.com/psy2848048/friday), [EE repo](https://github.com/psy2848048/CasperLabs)
- EVM integration on Cosmwasm in XPLA chain (ongoing) [Repo](https://github.com/xpladev/xpla)

As like mentioned above, our team has enough experience in blochchain industry, and now we start to expand our area to Antelope(and come back to our homeland). With not only our blockchain core experience but also enough knowledge in CS background, we will contribute and build strong basis on Antelope ecosystem.

- Twitter: [https://twitter.com/delightlabs_io](https://twitter.com/delightlabs_io)

## Development Roadmap

### Overview

- **Total Estimated Duration:** ?

### Milestone 1 - Research & MVP

#### Action items

- Research current implementation in communicating between Tx executor & EOS VM
- Research Wasmer communication API spec
- Research how to load & store the state into the internal DB
- Research the feasibility the output of Wasmer VM is compatible to current EOS VM state
- Meeting with EOSIO contributors if necessary
- Implement `Hello world` printing feature on Antelope - Wasmer by WASM contract

#### Expected outcome

- `nodeos` integrated with very limitted Wasmer API for printing `Hello world`

- **Estimated duration:** 12 weeks
- **FTE:** 2
- **Costs:** USD ? K

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | `nodeos` with Wasmer | Wasmer-connected `nodeos` with baisc API integration |

### Milestone 2 - Singleton CRUD

#### Action items

- First phase of implementing an interaction among state DB, transaction module, & Wasmer
- Singleton CRUD implementation & test in detail
  - Trigger save to an object by the test contract, and it actually saves into state DB
  - Trigger load from an object by the test contract, it actually loads from state DB, and the value are same
  - Trigger update from an object by the test contract, and it actually replaces of state DB
  - Trigger delete from an object by the test contract, and it actually deletes from state DB

#### Expected outcome

- Test contract
- `nodeos` with singleton CRUD available

- **Estimated duration:** 4 weeks
- **FTE:** 2
- **Costs:** USD ? K

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | `nodeos` with Wasmer | `nodeos` with singleton CRUD available |

### Milestone 3 - Cover all data structure

#### Action items

- Gather all types of data store (e.g. vector, etc)
- Implementate their data processing
- Testing
  - CRUD are availble of all data structure
  - Deferred action triggered from Wasmer can trigger EOS VM contract and executes well, and vice versa
- Make nodeos to be ready to ship into testnet

#### Expected outcome

- Test contract
- `nodeos` in ready-to-ship state

- **Estimated duration:** 8 weeks
- **FTE:** 2
- **Costs:** USD ? K

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | `nodeos` with Wasmer | Be ready to ship |

### Milestone 4 - Rust Antelope CDT

#### Action items

- Will work this milestone in parallel way with Wasmer integration (milestone 2~3)
- Gather APIs from current `eosio.cdt`
- Implementing their APIs, plus some additional convenient features
- Resturcture current `schema` of basic Cosmwasm form and convert into ABI form

#### Expected outcome

- Rust contract compileable `antelope.cdt`

- **Estimated duration:** 12 weeks
- **FTE:** 2
- **Costs:** USD ? K

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | `antelope.cdt` with Wasmer | Antelope contract can be written in Rust, compilable into WASM, and run on Antelope with Wasmer VM |

### Milestone 5 - Documentation

#### Expected outcome

- Revise operation guide
- Add Rust-based contract howto guide
- Add `antelope.cdt` specification

- **Estimated duration:** 4 weeks
- **FTE:** 2
- **Costs:** USD ? K

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | Documentation | Revised documentation according to Wasmer integration |

### Milestone 6 - Release on testnet & technical support

#### Action items

- Join into BP call and introduce how to install and operate
- Technical support & bugfix

- **Estimated duration:** 52 weeks
- **FTE:** 1
- **Costs:** USD ? K

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | Technical support | Support technical inquiries, and provide fixes if necessary |

## Future Plans

This proposal can make Antelope developer pool broaden to Rust developers. But it is not all. By this task, Golang-based & Javascript-based CDT could be appeared. Then, the pool will be much more bigger in the exponential way. Once their compiler goes stable, we'll conttribute their CDT of each lauguage.

## Additional Information

N/A

**How did you hear about the Grants Program?** From one member of the committee, and had a F2F meeting
