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
| Уязвимостей найдено | 29+ |
| Отчётов на рассмотрении | 2 (Medium — Aave V4) |
| Готовых отчётов | 27+ |
| Охвачено платформ | 5 |

---

## 🏆 Отчёты на рассмотрении

| # | Проект | Уязвимость | Severity | Платформа |
|---|---|---|---|---|
| 1 | Aave V4 | Unbounded Loop — setUserPositionManagers() | Medium | Sherlock |
| 2 | Aave V4 | Unbounded Loop — _calculateLiquidationAmounts() | Medium | Sherlock |

---

## 🔍 Находки по проектам

### Lido DAO (14 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Integer Overflow 0.4.24 | Medium | Lido.sol |
| 2 | Integer Overflow 0.4.24 | Medium | StETH.sol |
| 3 | Integer Overflow 0.4.24 | Medium | StETHPermit.sol |
| 4 | Integer Overflow 0.4.24 | Medium | NodeOperatorsRegistry.sol |
| 5 | Integer Overflow 0.6.12 | Low | WstETH.sol |
| 6 | Missing Input Validation | Low | 50+ функций |
| 7 | .transfer() 2300 gas limit | Low | SepoliaDepositAdapter.sol |
| 8 | delegatecall в Assembly | High | WithdrawalsManagerProxy.sol |
| 9 | 4 sstore без reentrancyGuard | Medium | NodeOperatorsRegistry.sol |
| 10 | sstore в Assembly | Medium | SigningKeys.sol |
| 11 | sstore в Assembly | Medium | UnstructuredStorage.sol |
| 12 | mstore без 0x40 | Low | SigningKeys.sol |
| 13 | Конфликт селектора deposit() | Low | Lido + StakingRouter |
| 14 | Конфликт селектора migrate() | Low | Lido + Burner |

### Paxos (12 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Integer Overflow 0.4.24 | Medium | PAXGImplementation.sol |
| 2 | Integer Overflow 0.4.24 | Medium | PaxosToken.sol |
| 3 | Integer Overflow 0.4.24 | Medium | AddressUtils.sol |
| 4 | Centralization — reclaimPAXG() | Medium | PAXGImplementation.sol |
| 5 | Centralization — reclaimToken() | Medium | PaxosToken.sol |
| 6 | TODO в production | Low | AddressUtils.sol |
| 7 | Centralization — Admin minting | Medium | Solana minter-controller |
| 8 | delegatecall в Assembly | High | PaxosTokenClaimableRewards.sol |
| 9 | sstore в Assembly | Medium | PAXG.sol |
| 10 | sstore в Assembly | Medium | AdminUpgradeabilityProxy.sol |
| 11 | Конфликт _transfer() — 6 контрактов | Low | Несколько файлов |
| 12 | Конфликт totalSupply() — 5 контрактов | Low | Несколько файлов |

### Wormhole (9 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Missing Input Validation | Low | Governance.sol |
| 2 | Missing Event Emission | Low | Governance.sol |
| 3 | Centralization — 13/19 guardians | Medium | Governance.sol |
| 4 | .transfer() 2300 gas | Medium | Governance.sol |
| 5 | .transfer() 2300 gas (3 места) | Medium | Bridge.sol |
| 6 | mstore без 0x40 | Low | Bridge.sol |
| 7 | sstore в Assembly | Low | BytesLib.sol |
| 8 | 7 записей без reentrancyGuard | Medium | TokenImplementation.sol |
| 9 | Конфликт chainId() — 8 контрактов | Low | Несколько файлов |

### Aave V4 (8 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Unbounded Loop | Medium | Spoke.sol:450 |
| 2 | Unbounded Loop | Medium | Spoke.sol:795 |
| 3 | delegatecall в Assembly | High | Proxy.sol |
| 4 | Unchecked permit | Medium | Spoke.sol |
| 5 | Unchecked permit | Medium | TokenizationSpoke.sol |
| 6 | 3 sstore без reentrancyGuard | Medium | HubConfigurator.sol |
| 7 | Конфликты селекторов (10+) | Low | AccessManager |
| 8 | nonce без require (20+ файлов) | Low | Несколько файлов |

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
| **Стандарты** | ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS |
| **Протоколы** | Aave V4, Lido, Wormhole, Paxos, LayerZero |

**Типы уязвимостей:**
- Integer Overflow/Underflow
- DoS (Gas Exhaustion, Unbounded Loops, .transfer() 2300 gas)
- Access Control / Centralization
- Assembly delegatecall без валидации
- Assembly sstore/mstore corruption
- Unchecked return values (permit, approve, transferFrom)
- Missing Input Validation
- Missing Events
- Diamond/Facet selector collisions
- Cross-chain race conditions (nonce/sequence)
- Oracle Manipulation

---

## 📜 Обучение

- 🎮 Ethernaut CTF — в процессе
- 📋 Code4rena — LayerZero Stellar contest
- 🔍 Sherlock — активный участник (2 отчёта на рассмотрении)
- 🎓 MEV, Oracle Manipulation, Fuzzing — изучено
- 🔬 Assembly/Yul анализ — изучено
- ⛓️ Cross-chain безопасность — изучено

---

## 🎯 План

- [x] 29+ уязвимостей найдено
- [x] 27+ отчётов готово
- [x] Глубокий анализ (assembly, selector collisions, cross-chain)
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

---

*Обновлено: 16 июля 2026*
