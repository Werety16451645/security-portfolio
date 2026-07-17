# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-3_Reports_Submitted-blue)](https://audits.sherlock.xyz) [![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com) [![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com) [![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz) [![CTF](https://img.shields.io/badge/CTF_Playground-Live-white)](https://werety16451645.github.io/ctf-playground)

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

## 🎯 CTF Playground — собственный проект

Интерактивная платформа для обучения Web3-безопасности:

🌐 **[werety16451645.github.io/ctf-playground](https://werety16451645.github.io/ctf-playground)**

| Характеристика | Описание |
|---|---|
| **Уровней** | 21 |
| **Категорий уязвимостей** | 21 |
| **Языки** | English / Русский |
| **Режим обучения** | Подсказки + теория на каждом уровне |
| **Технологии** | HTML, CSS, JavaScript |
| **Дизайн** | Ч/б минимализм, терминальный стиль |

**Уровни:** Re-entrancy, Flash Loan, Oracle Manipulation, Sandwich Attack, Governance Attack, Timelock Bypass, Integer Overflow, Unprotected Proxy, Delegatecall Attack, Selfdestruct Force, tx.origin Attack, Fallback Hijack, Missing Access Control, Zero Address, Unsafe Approve, Unchecked Return, Storage Collision, Selector Clash, Cross-chain Race, Assembly Corruption, Invariant Violation.

---

## 🛠 Технические навыки

| Навык | Уровень | Инструменты |
|---|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ | VS Code, Foundry |
| Foundry Fuzzing | ⭐⭐⭐⭐⭐ | forge test --fuzz-runs 10000 |
| Invariant Testing (Echidna-style) | ⭐⭐⭐⭐⭐ | 256 seq / 128K calls |
| CTF-разработка | ⭐⭐⭐⭐⭐ | 21-уровневый CTF, GitHub Pages |
| Assembly / Yul анализ | ⭐⭐⭐⭐ | grep, regex, ручной анализ |
| Storage Collision Detection | ⭐⭐⭐⭐ | Python-скрипты |
| Diamond / Facet Selectors | ⭐⭐⭐⭐ | keccak256 анализ |
| Cross-chain Security | ⭐⭐⭐⭐ | LayerZero, Wormhole |
| DeFi-атаки (Flash Loans, AMM) | ⭐⭐⭐⭐ | Damn Vulnerable DeFi |
| Ethernaut CTF | ⭐⭐⭐⭐ | 14 уровней пройдено |
| MEV / Front-running | ⭐⭐⭐ | Sandwich, Arbitrage |
| Oracle Manipulation | ⭐⭐⭐ | Spot, TWAP, Chainlink, Pyth |
| Rust / Solana Audit | ⭐⭐⭐ | Anchor, SPL Token |

---

## 🔬 Foundry Invariant Testing

Методология: инварианты протокола → invariant_* функции → случайные действия → fuzz-runs 5000-10000 → авто-поиск нарушений.

| Тест | Инвариант | Результат |
|---|---|---|
| Bank.sol | totalDeposits - totalWithdrawals == sum(balances) | ❌ Нарушен |
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

**Lido DAO** (24 находки) · **Paxos** (24 находки) · **Wormhole** (10 находок) · **Aave V4** (20 находок) · **Metric DEX** · **DRE App** · **LayerZero Stellar** · **Phantom**

---

## 📜 Обучение

| Ресурс | Прогресс |
|---|---|
| 🎯 Собственный CTF | 21 уровень — [открыть](https://werety16451645.github.io/ctf-playground) |
| 🎮 Ethernaut CTF | 14 уровней |
| 🔴 Damn Vulnerable DeFi | 12 уровней |
| 📋 Code4rena | LayerZero Stellar |
| 🔍 Sherlock | 3 отчёта |
| 🧪 Fuzzing | 10,000+ прогонов |
| 🔬 Invariant Testing | 128,000+ вызовов |
| 🦀 Rust/Solana | minter-controller |

---

## 🎯 План

- [x] 145+ уязвимостей
- [x] 10 Critical
- [x] 39+ отчётов
- [x] Собственный CTF (21 уровень)
- [x] GitHub Pages
- [ ] Первая выплата (Aave V4)

---

## 📞 Контакты

| Платформа | Контакт |
|---|---|
| **GitHub** | [@Werety16451645](https://github.com/Werety16451645) |
| **CTF Playground** | [werety16451645.github.io/ctf-playground](https://werety16451645.github.io/ctf-playground) |
| **Sherlock** | @delayed |
| **Immunefi** | @Delayed |
| **Email** | werety1645@gmail.com |

---

*Обновлено: 17 июля 2026 — CTF Playground live на GitHub Pages*
