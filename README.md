# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-3_Reports_Submitted-blue)](https://audits.sherlock.xyz)
[![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com)
[![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com)
[![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz)

---

## 📊 Статистика

| Метрика | Значение |
|---|---|
| Проектов проанализировано | 10+ |
| Уязвимостей найдено | 140+ |
| Critical | 10 |
| High | 6 |
| Medium | 27+ |
| Low/Info | 97+ |
| Отчётов на рассмотрении | 3 (Medium — Aave V4) |
| Готовых отчётов | 37+ |
| Охвачено платформ | 5 |

---

## 🛠 Продвинутые навыки

| Навык | Уровень |
|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ |
| Assembly/Yul анализ | ⭐⭐⭐⭐ |
| Storage collision detection | ⭐⭐⭐⭐ |
| Diamond/Facet selector analysis | ⭐⭐⭐⭐ |
| Cross-chain security | ⭐⭐⭐⭐ |
| **Foundry Fuzzing (инвариант-тесты)** | ⭐⭐⭐⭐ |
| MEV/Front-running | ⭐⭐⭐ |
| Oracle manipulation | ⭐⭐⭐ |
| Rust/Soroban (basics) | ⭐⭐ |

---

## 🏆 Отчёты на рассмотрении (Sherlock)

| # | Проект | Уязвимость | Severity | Статус |
|---|---|---|---|---|
| 1 | Aave V4 | Unbounded Loop — setUserPositionManagers() + _calculateLiquidationAmounts() | Medium | ⏳ |
| 2 | Aave V4 | Unchecked permit() Return Value — Spoke.sol | Medium | ✅ Передан Aave |
| 3 | Aave V4 | Multiple Storage Writes Without ReentrancyGuard — HubConfigurator | Medium | 🔜 Готов |
| 4 | Aave V4 | Missing Zero-Address Checks — Multiple Functions | Low | 🔜 Готов |

---

## 🔬 Foundry Fuzzing — автоматический поиск багов

| Инвариант | Результат | Что найдено |
|---|---|---|
| Баланс никогда не отрицательный | ❌ Нарушен | Arithmetic underflow — нет проверки |
| Курс обмена всегда > 0 | ❌ Нарушен | Пустой пул = нулевой курс |
| Проценты не отрицательные | ✅ Держится | Защита работает |
| Ликвидация покрывает долг | ✅ Держится | Логика верна |
| TotalSupply >= sum balances | ✅ Держится | Accounting корректен |

**Инструменты:** Foundry, forge test --fuzz-runs 5000, invariant testing

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
Unprotected initialize (7) | Integer Overflow 0.4.24 (4) | delegatecall Assembly | sstore Assembly | Unsafe approve | Missing validation | .transfer() gas limit

### Paxos (22 находки)
Unprotected initialize (2) | upgradeTo zero-address | Integer Overflow 0.4.24 (3) | delegatecall Assembly | Centralization (3) | Solana Admin minting | Zero-address checks (20+)

### Wormhole (9 находок)
Missing validation | Missing events | Centralization 13/19 | .transfer() gas limit (4) | sstore без reentrancyGuard (7 writes) | Assembly corruption

### Aave V4 (20 находок)
Unprotected initialize (4) | delegatecall Assembly | Unbounded Loops (2) | Unchecked permit (2) | sstore без reentrancyGuard | Zero-address checks (10+) | Selector collisions | **Foundry Fuzzing — 2 инварианта нарушены**

### Metric DEX (анализ завершён)
Oracle staleness | Anchored band clipping | Rounding mechanisms

### DRE App / dreUSD (анализ завершён)
ERC-4626 vault | Withdrawal NFT | Cross-chain compliance

### LayerZero Stellar (Code4rena)
Rust/Soroban | TTL storage | Abstract Account patterns

---

## 🛠 Технический стек

| Категория | Технологии |
|---|---|
| **Языки** | Solidity, Python, Rust (basics) |
| **Фреймворки** | Foundry (fuzzing, invariant tests, PoC) |
| **Блокчейны** | Ethereum, Solana, Base, Arbitrum, Stellar |
| **Стандарты** | ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS, Diamond |
| **Протоколы** | Aave V4, Lido, Wormhole, Paxos, LayerZero |

**Типы уязвимостей (18 категорий):**
Unprotected Proxy Initialization | Integer Overflow/Underflow | DoS (Gas Exhaustion, Unbounded Loops, .transfer()) | Access Control/Centralization | Assembly delegatecall без валидации | Assembly sstore/mstore corruption | Unchecked return values | Missing zero-address checks | Unsafe approve | Storage Collisions | Diamond/Facet selector collisions | Cross-chain race conditions | Oracle Manipulation | Exchange rate manipulation | Arithmetic underflow | ReentrancyGuard bypass | Empty pool exploitation | Invariant violations

---

## 📜 Обучение и сертификации

- 🎮 Ethernaut CTF — в процессе
- 📋 Code4rena — LayerZero Stellar contest
- 🔍 Sherlock — 3 отчёта на рассмотрении
- 🎓 MEV, Oracle Manipulation, Fuzzing — изучено
- 🔬 Assembly/Yul Deep Analysis — изучено
- ⛓️ Cross-chain безопасность — изучено
- 💎 Unprotected Proxy Initialization — 10 Critical найдено
- 🧪 **Foundry Invariant Fuzzing — 5000 runs, 2 инварианта нарушены**

---

## 🎯 План

- [x] 140+ уязвимостей найдено
- [x] 10 Critical находок
- [x] 37+ отчётов готово
- [x] Assembly/Storage/Selector глубокий анализ
- [x] **Foundry Fuzzing освоен**
- [x] 3 отчёта на рассмотрении Sherlock
- [ ] Получить первую выплату (Aave V4 — ждём)
- [ ] Junior Security Researcher
- [ ] Echidna advanced fuzzing

---

## 📞 Контакты

- **GitHub:** [@Werety16451645](https://github.com/Werety16451645)
- **Sherlock:** @delayed
- **Immunefi:** @Delayed
- **Email:** werety1645@gmail.com

---

*Обновлено: 17 июля 2026 — добавлен Foundry Fuzzing*
