# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-Active-blue)](https://audits.sherlock.xyz)
[![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com)
[![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com)
[![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz)

---

## 📊 Статистика

| Метрика | Значение |
|---|---|
| Проектов проанализировано | 10+ |
| Уязвимостей найдено | 136+ |
| Critical | 10 |
| High | 6 |
| Medium | 25+ |
| Low/Info | 95+ |
| Отчётов на рассмотрении | 2 (Medium — Aave V4) |
| Готовых отчётов | 37+ |
| Охвачено платформ | 5 |

---

## 🏆 Отчёты на рассмотрении

| # | Проект | Уязвимость | Severity | Платформа |
|---|---|---|---|---|
| 1 | Aave V4 | Unbounded Loop — setUserPositionManagers() | Medium | Sherlock |
| 2 | Aave V4 | Unbounded Loop — _calculateLiquidationAmounts() | Medium | Sherlock |

---

## 🔴 CRITICAL находки (10)

| # | Проект | Уязвимость | Файл | Риск |
|---|---|---|---|---|
| 1 | Aave V4 | Unprotected initialize() — Protocol Takeover | Hub.sol | $1B+ |
| 2 | Aave V4 | Unprotected initialize() — Spoke Hijacking | Spoke.sol | Полный контроль |
| 3 | Aave V4 | Unprotected initialize() | TokenizationSpoke.sol | Кража депозитов |
| 4 | Aave V4 | Unprotected initialize() | TreasurySpoke.sol | Кража комиссий |
| 5 | Paxos | Unprotected initialize() — Gold Token Hijack | PAXGImplementation.sol | $500M+ |
| 6 | Paxos | Unprotected initialize() — Token Hijack | PaxosToken.sol | Кража токенов |
| 7 | Lido | Unprotected initialize() — $30B Risk | StakingRouter.sol | $30B+ |
| 8 | Lido | Unprotected initialize() — Withdrawal Hijack | WithdrawalQueue.sol | Кража ETH |
| 9 | Lido | Unprotected initialize() | NodeOperatorsRegistry.sol | Контроль валидаторов |
| 10 | Paxos | upgradeTo() без zero-address check | AdminUpgradeabilityProxy.sol | Вечная блокировка |

---

## 🔍 Находки по проектам

### Lido DAO (24 находки)
| Тип | Severity | Файлы |
|---|---|---|
| Unprotected initialize() | Critical | StakingRouter, WithdrawalQueue, NodeOperatorsRegistry, Burner, AccountingOracle, ValidatorsExitBusOracle, SepoliaDepositAdapter |
| Integer Overflow 0.4.24 | Medium | Lido.sol, StETH.sol, StETHPermit.sol, NodeOperatorsRegistry.sol |
| Integer Overflow 0.6.12 | Low | WstETH.sol |
| delegatecall в Assembly | High | WithdrawalsManagerProxy.sol |
| sstore в Assembly | Medium | SigningKeys.sol, UnstructuredStorage.sol |
| Missing Input Validation | Low | 50+ функций |
| .transfer() 2300 gas | Low | SepoliaDepositAdapter.sol |
| Unsafe approve | High | NodeOperatorsRegistry.sol, Dashboard.sol |

### Paxos (22 находки)
| Тип | Severity | Файлы |
|---|---|---|
| Unprotected initialize() | Critical | PAXGImplementation.sol, PaxosToken.sol |
| upgradeTo без zero-address | Critical | AdminUpgradeabilityProxy.sol |
| Integer Overflow 0.4.24 | Medium | PAXGImplementation.sol, PaxosToken.sol, AddressUtils.sol |
| delegatecall в Assembly | High | PaxosTokenClaimableRewards.sol |
| Centralization — reclaimToken | Medium | PAXGImplementation.sol, PaxosToken.sol |
| Solana Admin minting | Medium | minter-controller |
| Zero-address checks missing | High | 20+ функций |

### Wormhole (9 находок)
| Тип | Severity | Файлы |
|---|---|---|
| Missing Input Validation | Low | Governance.sol |
| Missing Event Emission | Low | Governance.sol |
| Centralization — 13/19 guardians | Medium | Governance.sol |
| .transfer() 2300 gas | Medium | Governance.sol, Bridge.sol |
| 7 sstore без reentrancyGuard | Medium | TokenImplementation.sol |
| mstore/sstore в Assembly | Low | Bridge.sol, BytesLib.sol |

### Aave V4 (18 находок)
| Тип | Severity | Файлы |
|---|---|---|
| Unprotected initialize() | Critical | Hub.sol, Spoke.sol, TokenizationSpoke.sol, TreasurySpoke.sol |
| delegatecall в Assembly | High | Proxy.sol |
| Unbounded Loops | Medium | Spoke.sol:450, Spoke.sol:795 |
| Unchecked permit | Medium | Spoke.sol, TokenizationSpoke.sol |
| sstore без reentrancyGuard | Medium | HubConfigurator.sol |
| Zero-address checks missing | High | 10+ функций |
| Selector collisions | Low | AccessManager |

### Metric DEX (анализ завершён)
- Oracle staleness проверки
- Механизмы округления
- Anchored band clipping

### DRE App / dreUSD (анализ завершён)
- ERC-4626 vault accounting
- Withdrawal NFT queue
- Cross-chain compliance

### LayerZero Stellar (Code4rena)
- Rust / Soroban реализация
- TTL хранение
- Abstract Account паттерны

---

## 🛠 Технический стек

| Категория | Технологии |
|---|---|
| **Языки** | Solidity, Python, Rust (basics) |
| **Блокчейны** | Ethereum, Solana, Base, Arbitrum, Stellar |
| **Стандарты** | ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS, Diamond |
| **Протоколы** | Aave V4, Lido, Wormhole, Paxos, LayerZero |

**Типы уязвимостей:**
- Unprotected Proxy Initialization (Critical)
- Integer Overflow/Underflow
- DoS (Gas Exhaustion, Unbounded Loops, .transfer() 2300 gas)
- Access Control / Centralization
- Assembly delegatecall без валидации
- Assembly sstore/mstore corruption
- Unchecked return values (permit, approve, transferFrom)
- Missing zero-address checks
- Unsafe approve (front-running)
- Storage Collisions
- Diamond/Facet selector collisions
- Cross-chain race conditions
- Oracle Manipulation

---

## 📜 Обучение

- 🎮 Ethernaut CTF — в процессе
- 📋 Code4rena — LayerZero Stellar contest
- 🔍 Sherlock — активный участник (2 отчёта на рассмотрении)
- 🎓 MEV, Oracle Manipulation, Fuzzing — изучено
- 🔬 Assembly/Yul Deep Analysis — изучено
- ⛓️ Cross-chain безопасность — изучено
- 💎 Unprotected Proxy Initialization — найден 10 Critical

---

## 🎯 План

- [x] 136+ уязвимостей найдено
- [x] 10 Critical находок
- [x] 37+ отчётов готово
- [x] Глубокий анализ (assembly, selector collisions, cross-chain, proxy init)
- [ ] Получить первую выплату (Aave V4 — ждём)
- [ ] Junior Security Researcher
- [ ] Научиться Foundry фаззингу (Echidna)

---

## 📞 Контакты

- **GitHub:** [@Werety16451645](https://github.com/Werety16451645)
- **Sherlock:** @delayed
- **Immunefi:** @Delayed
- **Email:** werety1645@gmail.com

---

*Обновлено: 16 июля 2026*

