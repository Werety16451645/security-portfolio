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
| Уязвимостей найдено | 22+ |
| Отчётов на рассмотрении | 2 (Medium — Aave V4) |
| Готовых отчётов | 20+ |
| Охвачено платформ | 5 |

---

## 🏆 Отчёты на рассмотрении

| # | Проект | Уязвимость | Severity | Платформа |
|---|---|---|---|---|
| 1 | Aave V4 | Unbounded Loop — setUserPositionManagers() | Medium | Sherlock |
| 2 | Aave V4 | Unbounded Loop — _calculateLiquidationAmounts() | Medium | Sherlock |

---

## 🔍 Находки по проектам

### Lido DAO (7 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Integer Overflow 0.4.24 | Medium | Lido.sol |
| 2 | Integer Overflow 0.4.24 | Medium | StETH.sol |
| 3 | Integer Overflow 0.4.24 | Medium | StETHPermit.sol |
| 4 | Integer Overflow 0.4.24 | Medium | NodeOperatorsRegistry.sol |
| 5 | Integer Overflow 0.6.12 | Low | WstETH.sol |
| 6 | Missing Input Validation | Low | 50+ функций |
| 7 | .transfer() 2300 gas limit | Low | SepoliaDepositAdapter.sol |

### Paxos (7 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Integer Overflow 0.4.24 | Medium | PAXGImplementation.sol |
| 2 | Integer Overflow 0.4.24 | Medium | PaxosToken.sol |
| 3 | Integer Overflow 0.4.24 | Medium | AddressUtils.sol |
| 4 | Centralization — reclaimPAXG() | Medium | PAXGImplementation.sol |
| 5 | Centralization — reclaimToken() | Medium | PaxosToken.sol |
| 6 | TODO в production | Low | AddressUtils.sol |
| 7 | Centralization — Admin minting | Medium | Solana minter-controller |

### Wormhole (5 находок)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Missing Input Validation | Low | Governance.sol |
| 2 | Missing Event Emission | Low | Governance.sol |
| 3 | Centralization — 13/19 guardians | Medium | Governance.sol |
| 4 | .transfer() 2300 gas | Medium | Governance.sol |
| 5 | .transfer() 2300 gas (3 места) | Medium | Bridge.sol |

### Aave V4 (2 находки на рассмотрении)
| # | Уязвимость | Severity | Файл |
|---|---|---|---|
| 1 | Unbounded Loop | Medium | Spoke.sol:450 |
| 2 | Unbounded Loop | Medium | Spoke.sol:795 |

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
- Missing Input Validation
- Missing Events
- Oracle Manipulation

---

## 📜 Обучение

- 🎮 Ethernaut CTF — в процессе
- 📋 Code4rena — LayerZero Stellar contest
- 🔍 Sherlock — активный участник (2 отчёта на рассмотрении)
- 🎓 MEV, Oracle Manipulation, Fuzzing — изучено

---

## 🎯 План

- [x] 22+ уязвимостей найдено
- [x] 20+ отчётов готово
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
