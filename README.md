# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-3_Reports_Submitted-blue)](https://audits.sherlock.xyz) [![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com) [![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com) [![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz) [![CTF](https://img.shields.io/badge/CTF_Playground-Live-white)](https://werety16451645.github.io/ctf-playground)

---

## 📊 Общая статистика

| Категория | Количество |
|---|---|
| 🔴 Critical | 11 |
| 🟠 High | 7 |
| 🟡 Medium | 32+ |
| 🔵 Low / Info | 100+ |
| **Всего находок** | **150+** |
| Готовых отчётов | 42+ |
| **Отправлено на проверку** | **5** |
| Проектов проанализировано | 12+ |
| Платформ охвачено | 7 |

---

## 🎯 CTF Playground — собственный проект

🌐 **[werety16451645.github.io/ctf-playground](https://werety16451645.github.io/ctf-playground)**

21 уровень · 21 категория уязвимостей · English/Русский · Обучение на каждом шагу

---

## 🛠 Технические навыки

| Навык | Уровень | Инструменты |
|---|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ | VS Code, Foundry |
| Web-пентест (XSS, CORS, IDOR) | ⭐⭐⭐⭐⭐ | Python, Burp Suite |
| Foundry Fuzzing | ⭐⭐⭐⭐⭐ | forge test --fuzz-runs 10000 |
| Invariant Testing (Echidna-style) | ⭐⭐⭐⭐⭐ | 256 seq / 128K calls |
| CTF-разработка | ⭐⭐⭐⭐⭐ | HTML/CSS/JS, GitHub Pages |
| Assembly / Yul анализ | ⭐⭐⭐⭐ | grep, regex |
| Storage Collision Detection | ⭐⭐⭐⭐ | Python-скрипты |
| Diamond / Facet Selectors | ⭐⭐⭐⭐ | keccak256 анализ |
| Cross-chain Security | ⭐⭐⭐⭐ | LayerZero, Wormhole |
| DeFi-атаки (Flash Loans, AMM) | ⭐⭐⭐⭐ | Damn Vulnerable DeFi |
| Ethernaut CTF | ⭐⭐⭐⭐ | 14 уровней |
| MEV / Front-running | ⭐⭐⭐ | Sandwich, Arbitrage |
| Oracle Manipulation | ⭐⭐⭐ | Spot, TWAP, Chainlink |
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

Статистика: 10,000+ прогонов · 128,000+ вызовов · 2 инварианта нарушено · ~13 сек

---

## 📤 Отправленные отчёты

| # | Платформа | Проект | Уязвимость | Severity | Статус |
|---|---|---|---|---|---|
| 1 | Sherlock | Aave V4 | Unbounded Loops (×2) | 🟡 Medium | ⏳ Ждём |
| 2 | Sherlock | Aave V4 | Unchecked permit | 🟡 Medium | ✅ У команды |
| 3 | Email | Pachca.com | CORS + открытые пути | 🔴 Critical | 📤 Отправлен |
| 4 | Яндекс | Диск | Information Disclosure | 🟡 Medium | 📤 Отправлен |
| 5 | Яндекс | Маркет | Reflected XSS | 🟠 High | 📤 Отправлен |

---

## 🔴 CRITICAL находки (11)

| # | Проект | Суть | Файл |
|---|---|---|---|
| 1 | Aave V4 | initialize() без защиты | Hub.sol |
| 2 | Aave V4 | initialize() без защиты | Spoke.sol |
| 3 | Aave V4 | initialize() без защиты | TokenizationSpoke.sol |
| 4 | Aave V4 | initialize() без защиты | TreasurySpoke.sol |
| 5 | Paxos | initialize() без защиты | PAXGImplementation.sol |
| 6 | Paxos | initialize() без защиты | PaxosToken.sol |
| 7 | Lido | initialize() без защиты | StakingRouter.sol |
| 8 | Lido | initialize() без защиты | WithdrawalQueue.sol |
| 9 | Lido | initialize() без защиты | NodeOperatorsRegistry.sol |
| 10 | Paxos | upgradeTo(address(0)) | AdminUpgradeabilityProxy.sol |
| 11 | Pachca.com | CORS + открытые пути | api.pachca.com |

---

## 🟠 HIGH находки (7)

Aave V4: delegatecall в Assembly. Paxos: delegatecall в Assembly. Lido: delegatecall в Assembly, Unsafe approve (2). Aave V4: Unsafe approve. **Яндекс.Маркет: отражённый XSS.**

---

## 🟡 MEDIUM находки (32+)

Aave V4 (7): Unbounded Loops (2), Unchecked permit (2), sstore без Guard, Invariant violations (2). Lido (6): Integer Overflow (4), Assembly sstore (2). Paxos (8): Integer Overflow (3), Centralization (2), Solana admin, Solana timelock, Assembly sstore (2). Wormhole (5): Centralization 13/19, .transfer() gas (2), sstore без Guard, Re-entrancy. Paxos Solana (2). **Яндекс.Диск: Information Disclosure. Ozon: Open Redirect (3). Сбер: Sentry DSN.**

---

## 🔵 LOW / INFO находки (100+)

Missing Input Validation (50+) · Missing Events · TODO в production · Конфликты селекторов (30+) · Missing zero-address checks (10+) · .transfer() gas limit · nonce без проверок (40+) · mstore без 0x40 · **Яндекс: Open Redirect (2). Сбер: отсутствие CSP/HSTS.**

---

## 📁 Проекты

**Lido DAO** (24) · **Paxos** (24) · **Wormhole** (10) · **Aave V4** (20) · **Яндекс** (5) · **Ozon** (4) · **Сбер** (3) · **Pachca.com** (2) · Metric DEX · DRE App · LayerZero Stellar · Phantom · Nubank

---

## 📜 Обучение

| Ресурс | Прогресс |
|---|---|
| 🎯 Собственный CTF | 21 уровень |
| 🎮 Ethernaut CTF | 14 уровней |
| 🔴 Damn Vulnerable DeFi | 12 уровней |
| 📋 Code4rena | LayerZero Stellar |
| 🔍 Sherlock | 3 отчёта |
| 🧪 Fuzzing | 10,000+ прогонов |
| 🔬 Invariant Testing | 128,000+ вызовов |
| 🌐 Web-пентест | XSS, CORS, IDOR, Open Redirect |

---

## 🎯 План

- [x] 150+ уязвимостей
- [x] 11 Critical
- [x] 42+ отчётов
- [x] 5 отчётов отправлено
- [x] Собственный CTF (21 уровень)
- [x] GitHub Pages
- [x] Web-пентест (Яндекс, Ozon, Сбер, Pachca)
- [ ] Первая выплата

---

## 📞 Контакты

| Платформа | Контакт |
|---|---|
| **GitHub** | [@Werety16451645](https://github.com/Werety16451645) |
| **CTF** | [ctf-playground](https://werety16451645.github.io/ctf-playground) |
| **Sherlock** | @delayed |
| **Immunefi** | @Delayed |
| **Email** | werety1645@gmail.com |

---

*Обновлено: 17 июля 2026 — добавлены отчёты по Яндексу, Ozon, Сберу, Pachca*
