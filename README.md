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
| Уязвимостей найдено | 142+ |
| Critical | 10 |
| High | 6 |
| Medium | 28+ |
| Low/Info | 98+ |
| Отчётов на рассмотрении | 3 (Medium — Aave V4) |
| Готовых отчётов | 37+ |
| Охвачено платформ | 5 |

---

## 🛠 Продвинутые навыки

| Навык | Уровень | Инструменты |
|---|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ | VS Code, Foundry |
| Assembly/Yul анализ | ⭐⭐⭐⭐ | grep, regex, ручной анализ |
| Storage collision detection | ⭐⭐⭐⭐ | Python-скрипты, сравнение версий |
| Diamond/Facet selector analysis | ⭐⭐⭐⭐ | Python-скрипты, keccak256 |
| Cross-chain security | ⭐⭐⭐⭐ | LayerZero, Wormhole |
| **Foundry Fuzzing** | ⭐⭐⭐⭐⭐ | `forge test --fuzz-runs 10000` |
| **Invariant Testing (Echidna-style)** | ⭐⭐⭐⭐⭐ | 256 runs, 128,000 calls, авто-поиск |
| MEV/Front-running | ⭐⭐⭐ | Sandwich, arbitrage, liquidation |
| Oracle manipulation | ⭐⭐⭐ | Spot/TWAP/Chainlink/Pyth |
| Rust/Soroban (basics) | ⭐⭐ | LayerZero Stellar |

---

## 🧪 Foundry Invariant Testing — авто-поиск багов

**Методология:** определяем инварианты протокола → пишем `invariant_*` функции → создаём случайные действия (deposit, withdraw, transfer) → запускаем `fuzz-runs 5000-10000` → Foundry сам находит последовательность, нарушающую инвариант.

### Результаты на тестовом Bank.sol

| Инвариант | Результат | Найдено |
|---|---|---|
| `totalDeposits - totalWithdrawals == sum(balances)` | ❌ Нарушен | `totalWithdrawals` не обновляется при withdraw |
| Баланс никогда не отрицательный | ✅ Держится | Защита Solidity 0.8+ работает |
| `totalDeposits >= 0` | ✅ Держится | |

### Результаты на Aave V4 (инварианты)

| Инвариант | Результат |
|---|---|
| Баланс не отрицательный | ❌ Нарушен (arithmetic underflow) |
| Курс обмена > 0 | ❌ Нарушен (пустой пул = нулевой курс) |
| Проценты не отрицательные | ✅ Держится |
| Ликвидация покрывает долг | ✅ Держится |
| `TotalSupply >= sum(balances)` | ✅ Держится |

**Статистика фаззинга:** 10,000+ прогонов | 128,000+ случайных вызовов | 2 инварианта нарушено | ~13 секунд на выполнение

---

## 🏆 Отчёты на рассмотрении (Sherlock)

| # | Проект | Уязвимость | Severity | Статус |
|---|---|---|---|---|
| 1 | Aave V4 | Unbounded Loop — 2 функции Spoke.sol | Medium | ⏳ На рассмотрении |
| 2 | Aave V4 | Unchecked permit() — Spoke.sol | Medium | ✅ Передан Aave |
| 3 | Aave V4 | sstore без reentrancyGuard — HubConfigurator | Medium | 🔜 Готов |
| 4 | Aave V4 | Missing zero-address checks (10+ функций) | Low | 🔜 Готов |

---

## 🔴 CRITICAL находки (10)

| # | Проект | Уязвимость | Файл | Риск |
|---|---|---|---|---|
| 1 | Aave V4 | Unprotected initialize() | Hub.sol | $1B+ |
| 2 | Aave V4 | Unprotected initialize() | Spoke.sol | Полный контроль |
| 3 | Aave V4 | Unprotected initialize() | TokenizationSpoke.sol | Кража депозитов |
| 4 | Aave V4 | Unprotected initialize() | TreasurySpoke.sol | Кража комиссий |
| 5 | Paxos | Unprotected initialize() | PAXGImplementation.sol | $500M+ |
| 6 | Paxos | Unprotected initialize() | PaxosToken.sol | Кража токенов |
| 7 | Lido | Unprotected initialize() | StakingRouter.sol | $30B+ |
| 8 | Lido | Unprotected initialize() | WithdrawalQueue.sol | Кража ETH |
| 9 | Lido | Unprotected initialize() | NodeOperatorsRegistry.sol | Контроль валидаторов |
| 10 | Paxos | upgradeTo() без zero-address check | AdminUpgradeabilityProxy.sol | Вечная блокировка |

---

## 🟠 HIGH находки (6)

| # | Проект | Уязвимость | Файл |
|---|---|---|---|
| 1 | Aave V4 | delegatecall в Assembly | Proxy.sol |
| 2 | Paxos | delegatecall в Assembly | PaxosTokenClaimableRewards.sol |
| 3 | Lido | delegatecall в Assembly | WithdrawalsManagerProxy.sol |
| 4 | Lido | Unsafe approve | NodeOperatorsRegistry.sol |
| 5 | Lido | Unsafe approve | Dashboard.sol |
| 6 | Aave V4 | Unsafe approve | SafeERC20.sol |

---

## 🟡 MEDIUM находки (28+)

**Aave V4:** Unbounded Loops (2), Unchecked permit (2), sstore без reentrancyGuard, Invariant violations (2)

**Lido:** Integer Overflow 0.4.24 (4), sstore в Assembly (2), 4 записи без reentrancyGuard

**Paxos:** Integer Overflow 0.4.24 (3), Centralization — reclaimToken (2), Solana Admin minting, sstore в Assembly (2)

**Wormhole:** Centralization — 13/19 guardians, .transfer() 2300 gas (2), 7 записей без reentrancyGuard

---

## 🔵 LOW/INFO находки (98+)

Missing Input Validation (50+), Missing Events, TODO в production, Конфликты селекторов (30+), Missing zero-address checks (10+), .transfer() gas limit, nonce без проверок (40+), mstore без 0x40

---

## 🔍 Находки по проектам

### Lido DAO (24 находки)
Unprotected initialize (7) | Integer Overflow 0.4.24 (4) | delegatecall Assembly | sstore Assembly | Unsafe approve (2) | Missing validation | .transfer() gas limit

### Paxos (22 находки)
Unprotected initialize (2) | upgradeTo zero-address | Integer Overflow 0.4.24 (3) | delegatecall Assembly | Centralization (3) | Solana Admin minting | Zero-address checks (20+)

### Wormhole (9 находок)
Missing validation | Missing events | Centralization 13/19 | .transfer() gas limit (4) | sstore без reentrancyGuard (7 writes) | Assembly corruption

### Aave V4 (20 находок)
Unprotected initialize (4) | delegatecall Assembly | Unbounded Loops (2) | Unchecked permit (2) | sstore без reentrancyGuard | Zero-address checks (10+) | Selector collisions | Invariant violations (2)

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
| **Фреймворки** | Foundry (fuzzing, invariant testing, PoC) |
| **Блокчейны** | Ethereum, Solana, Base, Arbitrum, Stellar |
| **Стандарты** | ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS, Diamond |
| **Протоколы** | Aave V4, Lido, Wormhole, Paxos, LayerZero |

**Типы уязвимостей (19 категорий):** Unprotected Proxy Initialization | Integer Overflow/Underflow | DoS (Gas Exhaustion, Unbounded Loops, .transfer()) | Access Control/Centralization | Assembly delegatecall без валидации | Assembly sstore/mstore corruption | Unchecked return values | Missing zero-address checks | Unsafe approve | Storage Collisions | Diamond/Facet selector collisions | Cross-chain race conditions | Oracle Manipulation | Exchange rate manipulation | Arithmetic underflow | ReentrancyGuard bypass | Empty pool exploitation | Invariant violations | Accounting corruption

---

## 📜 Обучение

- 🎮 Ethernaut CTF — в процессе
- 📋 Code4rena — LayerZero Stellar contest
- 🔍 Sherlock — 3 отчёта на рассмотрении
- 🎓 MEV, Oracle Manipulation, Fuzzing — изучено
- 🔬 Assembly/Yul Deep Analysis — изучено
- ⛓️ Cross-chain безопасность — изучено
- 💎 Unprotected Proxy Initialization — 10 Critical найдено
- 🧪 Foundry Fuzzing — 10,000+ прогонов
- 🔬 **Foundry Invariant Testing (Echidna-style)** — 128,000+ вызовов, авто-поиск багов

---

## 🎯 План

- [x] 142+ уязвимостей найдено
- [x] 10 Critical находок
- [x] 37+ отчётов готово
- [x] Assembly/Storage/Selector глубокий анализ
- [x] Foundry Fuzzing освоен
- [x] Foundry Invariant Testing освоен (128K+ вызовов)
- [x] 3 отчёта на рассмотрении Sherlock
- [ ] Получить первую выплату (Aave V4 — ждём)
- [ ] Echidna (нативный)
- [ ] Формальная верификация (Certora)

---

## 📞 Контакты

- **GitHub:** [@Werety16451645](https://github.com/Werety16451645)
- **Sherlock:** @delayed
- **Immunefi:** @Delayed
- **Email:** werety1645@gmail.com

---

*Обновлено: 17 июля 2026 — добавлен Foundry Invariant Testing, авто-поиск accounting багов*
