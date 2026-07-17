# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-3_Reports_Submitted-blue)](https://audits.sherlock.xyz) [![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com) [![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com) [![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz)

---

## 📊 Общая статистика

| Категория | Количество |
|---|---|
| 🔴 Critical | 10 |
| 🟠 High | 6 |
| 🟡 Medium | 30+ |
| 🔵 Low / Info | 99+ |
| **Всего находок** | **145+** |
| Готовых отчётов | 39+ |
| На рассмотрении (Sherlock) | 3 |
| Проектов проанализировано | 10+ |
| Платформ охвачено | 5 |

---

## 🛠 Технические навыки

| Навык | Уровень | Инструменты |
|---|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ | VS Code, Foundry |
| Foundry Fuzzing | ⭐⭐⭐⭐⭐ | forge test --fuzz-runs 10000 |
| Invariant Testing (Echidna-style) | ⭐⭐⭐⭐⭐ | 256 seq / 128K calls |
| Assembly / Yul анализ | ⭐⭐⭐⭐ | grep, regex, ручной анализ |
| Storage Collision Detection | ⭐⭐⭐⭐ | Python-скрипты |
| Diamond / Facet Selectors | ⭐⭐⭐⭐ | keccak256 анализ |
| Cross-chain Security | ⭐⭐⭐⭐ | LayerZero, Wormhole |
| Ethernaut CTF | ⭐⭐⭐⭐ | 14 уровней пройдено |
| MEV / Front-running | ⭐⭐⭐ | Sandwich, Arbitrage |
| Oracle Manipulation | ⭐⭐⭐ | Spot, TWAP, Chainlink, Pyth |
| Rust / Solana Audit | ⭐⭐⭐ | Anchor, SPL Token |

---

## 🔬 Foundry Invariant Testing

Методология: инварианты протокола → invariant_* функции → случайные действия (deposit, withdraw, transfer) → fuzz-runs 5000-10000 → авто-поиск нарушений.

| Тест | Инвариант | Результат |
|---|---|---|
| Bank.sol | totalDeposits - totalWithdrawals == sum(balances) | ❌ Нарушен |
| Bank.sol | Баланс никогда не отрицательный | ✅ Держится |
| Aave V4 | Курс обмена > 0 | ❌ Нарушен |
| Aave V4 | Баланс не отрицательный | ❌ Нарушен |
| Aave V4 | Проценты ≥ 0 | ✅ Держится |
| Aave V4 | Ликвидация покрывает долг | ✅ Держится |

Статистика: 10,000+ прогонов · 128,000+ вызовов · 2 инварианта нарушено · ~13 сек на выполнение.

---

## 🏆 Отчёты на рассмотрении — Sherlock

| # | Проект | Уязвимость | Severity | Статус |
|---|---|---|---|---|
| 1 | Aave V4 | Unbounded Loop (×2) — Spoke.sol | 🟡 Medium | ⏳ Ждём |
| 2 | Aave V4 | Unchecked permit() — Spoke.sol | 🟡 Medium | ✅ У команды |
| 3 | Aave V4 | sstore без reentrancyGuard | 🟡 Medium | 🔜 Готов |
| 4 | Aave V4 | Missing zero-address checks (10+) | 🔵 Low | 🔜 Готов |

---

## 🔴 CRITICAL находки

| # | Проект | Суть | Файл | Риск |
|---|---|---|---|---|
| 1 | Aave V4 | initialize() без защиты | Hub.sol | $1B+ |
| 2 | Aave V4 | initialize() без защиты | Spoke.sol | Полный контроль |
| 3 | Aave V4 | initialize() без защиты | TokenizationSpoke.sol | Кража депозитов |
| 4 | Aave V4 | initialize() без защиты | TreasurySpoke.sol | Кража комиссий |
| 5 | Paxos | initialize() без защиты | PAXGImplementation.sol | $500M+ |
| 6 | Paxos | initialize() без защиты | PaxosToken.sol | Кража токенов |
| 7 | Lido | initialize() без защиты | StakingRouter.sol | $30B+ |
| 8 | Lido | initialize() без защиты | WithdrawalQueue.sol | Кража ETH |
| 9 | Lido | initialize() без защиты | NodeOperatorsRegistry.sol | Валидаторы |
| 10 | Paxos | upgradeTo(address(0)) | AdminUpgradeabilityProxy.sol | Вечная блокировка |

---

## 🟠 HIGH находки

| # | Проект | Суть | Файл |
|---|---|---|---|
| 1 | Aave V4 | delegatecall в Assembly | Proxy.sol |
| 2 | Paxos | delegatecall в Assembly | PaxosTokenClaimableRewards.sol |
| 3 | Lido | delegatecall в Assembly | WithdrawalsManagerProxy.sol |
| 4 | Lido | Unsafe approve | NodeOperatorsRegistry.sol |
| 5 | Lido | Unsafe approve | Dashboard.sol |
| 6 | Aave V4 | Unsafe approve | SafeERC20.sol |

---

## 🟡 MEDIUM находки

Aave V4 (7): Unbounded Loops (2), Unchecked permit (2), sstore без Guard, Invariant violations (2). Lido (6): Integer Overflow 0.4.24 (4), Assembly sstore (2). Paxos (8): Integer Overflow 0.4.24 (3), Centralization reclaim (2), Solana admin, Solana timelock, Assembly sstore (2). Wormhole (5): Centralization 13/19 guardians, .transfer() gas (2), sstore без Guard (7 writes), Re-entrancy Governance. Paxos Solana (2): Admin transfer без timelock, Centralization.

---

## 🔵 LOW / INFO находки

Missing Input Validation (50+) · Missing Events · TODO в production · Конфликты селекторов (30+) · Missing zero-address checks (10+) · .transfer() gas limit · nonce без проверок (40+) · mstore без 0x40.

---

## 📁 Проекты

**Lido DAO** (24 находки): Unprotected initialize (7) · Integer Overflow 0.4.24 (4) · delegatecall Assembly · sstore Assembly · Unsafe approve (2) · Missing validation · .transfer() gas limit.

**Paxos** (24 находки): Unprotected initialize (2) · upgradeTo zero-address · Integer Overflow 0.4.24 (3) · delegatecall Assembly · Centralization (3) · Solana Admin minting · Solana timelock missing · Zero-address checks (20+).

**Wormhole** (10 находок): Missing validation · Missing events · Centralization 13/19 · .transfer() gas limit (4) · sstore без reentrancyGuard (7 writes) · Assembly corruption · Re-entrancy risk Governance.

**Aave V4** (20 находок): Unprotected initialize (4) · delegatecall Assembly · Unbounded Loops (2) · Unchecked permit (2) · sstore без reentrancyGuard · Zero-address checks (10+) · Selector collisions · Invariant violations (2).

**Metric DEX** (анализ завершён): Oracle staleness · Anchored band clipping · Rounding mechanisms.

**DRE App / dreUSD** (анализ завершён): ERC-4626 vault · Withdrawal NFT · Cross-chain compliance.

**LayerZero Stellar** (Code4rena): Rust/Soroban · TTL storage · Abstract Account patterns.

**Phantom** (scope изучен): Solana PSOL/CASH · Client-Side · Web · Infrastructure.

---

## 🛠 Технологический стек

| Категория | Технологии |
|---|---|
| **Языки** | Solidity, Python, Rust (basics) |
| **Фреймворки** | Foundry (fuzzing, invariant testing, PoC), Anchor (Solana) |
| **Блокчейны** | Ethereum, Solana, Base, Arbitrum, Stellar |
| **Стандарты** | ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS, Diamond, SPL Token |
| **Протоколы** | Aave V4, Lido, Wormhole, Paxos, LayerZero, Phantom |

**20 категорий уязвимостей:** Unprotected Proxy Init · Integer Overflow/Underflow · DoS (Gas, Loops, .transfer) · Access Control/Centralization · Assembly delegatecall · Assembly sstore/mstore · Unchecked returns · Missing zero-address · Unsafe approve · Storage Collisions · Diamond selector collisions · Cross-chain race · Oracle manipulation · Exchange rate · Arithmetic underflow · ReentrancyGuard bypass · Empty pool exploit · Invariant violations · Accounting corruption · Missing Timelock.

---

## 📜 Обучение

| Ресурс | Прогресс |
|---|---|
| 🎮 Ethernaut CTF | 14 уровней пройдено |
| 📋 Code4rena | LayerZero Stellar contest |
| 🔍 Sherlock | 3 отчёта на рассмотрении |
| 🎓 MEV & Oracle | Sandwich, TWAP, Chainlink — изучено |
| 🔬 Assembly/Yul | Deep Analysis — изучено |
| ⛓️ Cross-chain | LayerZero, Wormhole — изучено |
| 💎 Proxy Init | 10 Critical найдено |
| 🧪 Fuzzing | 10,000+ прогонов |
| 🔬 Invariant Testing | 128,000+ вызовов |
| 🦀 Rust/Solana | minter-controller проанализирован |

---

## 🎯 План развития

- [x] 145+ уязвимостей найдено
- [x] 10 Critical находок
- [x] 39+ отчётов готово
- [x] Assembly/Storage/Selector глубокий анализ
- [x] Foundry Fuzzing освоен
- [x] Foundry Invariant Testing освоен (128K+ вызовов)
- [x] 14 уровней Ethernaut пройдено
- [x] Rust/Solana audit начат
- [x] 3 отчёта на рассмотрении Sherlock
- [ ] Получить первую выплату (Aave V4 — ждём)
- [ ] Пройти Ethernaut до конца
- [ ] Echidna (нативный фаззер)
- [ ] Формальная верификация (Certora)

---

## 📞 Контакты

| Платформа | Контакт |
|---|---|
| **GitHub** | [@Werety16451645](https://github.com/Werety16451645) |
| **Sherlock** | @delayed |
| **Immunefi** | @Delayed |
| **Email** | werety1645@gmail.com |

---

*Обновлено: 17 июля 2026*
