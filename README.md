# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-3_Reports_Submitted-blue)](https://audits.sherlock.xyz) [![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com) [![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com) [![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz) [![CTF](https://img.shields.io/badge/CTF_Playground-Live-white)](https://werety16451645.github.io/ctf-playground)

---

## 📊 Общая статистика

| Категория | Количество |
|---|---|
| 🔴 Critical | 13 |
| 🟠 High | 8 |
| 🟡 Medium | 36+ |
| 🔵 Low / Info | 100+ |
| **Всего находок** | **160+** |
| Готовых отчётов | 48+ |
| **Отправлено на проверку** | **7** |
| Принято | 0 |
| Отклонено | 1 (Pachca) |
| Проектов проанализировано | 16+ |
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
| Web-пентест (XSS, CORS, IDOR, OAuth, CRLF) | ⭐⭐⭐⭐⭐ | Python, Burp Suite |
| Системный анализ (паттерны уязвимостей) | ⭐⭐⭐⭐⭐ | Python, cURL |
| Foundry Fuzzing | ⭐⭐⭐⭐⭐ | forge test --fuzz-runs 10000 |
| Invariant Testing (Echidna-style) | ⭐⭐⭐⭐⭐ | 256 seq / 128K calls |
| CTF-разработка | ⭐⭐⭐⭐⭐ | HTML/CSS/JS, GitHub Pages |
| Assembly / Yul анализ | ⭐⭐⭐⭐ | grep, regex |
| Storage Collision Detection | ⭐⭐⭐⭐ | Python-скрипты |
| Diamond / Facet Selectors | ⭐⭐⭐⭐ | keccak256 анализ |
| Cross-chain Security | ⭐⭐⭐⭐ | LayerZero, Wormhole |
| DeFi-атаки (Flash Loans, AMM) | ⭐⭐⭐⭐ | Damn Vulnerable DeFi |
| Ethernaut CTF | ⭐⭐⭐⭐ | 14 уровней |
| Rust / Solana Audit | ⭐⭐⭐ | Anchor, SPL Token |
| MEV / Front-running | ⭐⭐⭐ | Sandwich, Arbitrage |
| Oracle Manipulation | ⭐⭐⭐ | Spot, TWAP, Chainlink |

---

## 🔬 Foundry Invariant Testing

| Тест | Инвариант | Результат |
|---|---|---|
| Bank.sol | totalDeposits - totalWithdrawals == sum(balances) | ❌ Нарушен |
| Aave V4 | Курс обмена > 0 | ❌ Нарушен |
| Aave V4 | Баланс не отрицательный | ❌ Нарушен |

10,000+ прогонов · 128,000+ вызовов · 2 инварианта нарушено

---

## 📤 Отправленные отчёты

| # | Платформа | Проект | Уязвимость | Severity | Статус |
|---|---|---|---|---|---|
| 1 | Sherlock | Aave V4 | Unbounded Loops (×2) | 🟡 Medium | ⏳ Ждём |
| 2 | Sherlock | Aave V4 | Unchecked permit | 🟡 Medium | ⏳ Ждём |
| 3 | Email | Pachca.com | CORS + открытые пути | 🔴 Critical | ❌ Отклонён |
| 4 | Яндекс | Маркет | Reflected XSS | 🟠 High | ⏳ Ждём |
| 5 | Яндекс | Диск | Information Disclosure (CSP) | 🟡 Medium | ⏳ Ждём |
| 6 | Яндекс | Паспорт | OAuth Open Redirect + CRLF | 🔴 Critical | ⏳ Ждём |
| 7 | **Яндекс** | **10 сервисов** | **Системный Open Redirect (110 комбинаций)** | **🔴 Critical** | ⏳ Ждём |

---

## 🔴 CRITICAL находки (13)

| # | Проект | Суть |
|---|---|---|
| 1-4 | Aave V4 | initialize() без защиты (Hub, Spoke, TokenizationSpoke, TreasurySpoke) |
| 5-6 | Paxos | initialize() без защиты (PAXG, PaxosToken) |
| 7-9 | Lido | initialize() без защиты (StakingRouter, WithdrawalQueue, NodeOperatorsRegistry) |
| 10 | Paxos | upgradeTo(address(0)) — вечная блокировка |
| 11 | Pachca.com | CORS + открытые пути (отклонён) |
| 12 | Яндекс.Паспорт | OAuth Open Redirect + CRLF Injection (5 обходов) |
| 13 | **Яндекс (10 сервисов)** | **Системный Open Redirect — 110 комбинаций** |

---

## 🟠 HIGH находки (8)

Aave V4: delegatecall Assembly · Unsafe approve. Paxos: delegatecall Assembly. Lido: delegatecall Assembly · Unsafe approve (2). **Яндекс.Маркет: XSS**. **Яндекс: системный паттерн редиректов**.

---

## 🟡 MEDIUM находки (36+)

Aave V4 (7) · Lido (6) · Paxos (8) · Wormhole (5) · Paxos Solana (2) · Яндекс.Диск: Information Disclosure · Яндекс.Путешествия: API без авторизации · Ozon: Open Redirect (3) · Сбер: Sentry DSN · VK/RuStore: Open Redirect

---

## 🔵 LOW / INFO (100+)

Missing Input Validation (50+) · Missing Events · Конфликты селекторов (30+) · Missing zero-address (10+) · nonce без проверок (40+) · Open Redirect (7 сервисов Яндекса) · Сбер: CSP/HSTS

---

## 📁 Проекты

**Яндекс** (12 находок: XSS, CSP, системный редирект ×10 сервисов, OAuth CRLF) · **Lido DAO** (24) · **Paxos** (24) · **Aave V4** (20) · **Wormhole** (10) · **Ozon** (4) · **Сбер** (3) · **Pachca.com** (2) · **VK/RuStore** (2) · Metric DEX · DRE App · LayerZero Stellar · Phantom · Nubank

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
| 🌐 Web-пентест | XSS, CORS, IDOR, OAuth, CRLF |
| 🔍 Системный анализ | Паттерны уязвимостей в экосистемах |

---

## 🎯 План

- [x] 160+ уязвимостей
- [x] 13 Critical
- [x] 48+ отчётов
- [x] 7 отчётов отправлено
- [x] Системный паттерн на 10 сервисах Яндекса
- [x] Собственный CTF
- [ ] Первая выплата 💰

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

*Обновлено: 18 июля 2026 — системный паттерн редиректов Яндекса, 7 отчётов отправлено*
