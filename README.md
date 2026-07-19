# 🔐 Web3 Security Researcher Portfolio

**delayed** | Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-3_Reports_Submitted-blue)](https://audits.sherlock.xyz) [![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com) [![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com) [![Cantina](https://img.shields.io/badge/Cantina-Registered-orange)](https://cantina.xyz) [![CTF](https://img.shields.io/badge/CTF_Playground-Live-white)](https://werety16451645.github.io/ctf-playground)

---

## 📊 Общая статистика

| Категория | Количество |
|---|---|
| 🔴 Critical | 13 |
| 🟠 High | 7 |
| 🟡 Medium | 35+ |
| 🔵 Low / Info | 100+ |
| **Всего находок** | **157+** |
| Готовых отчётов | 47+ |
| **Отправлено на проверку** | **8** |
| Проектов проанализировано | 15+ |
| Платформ охвачено | 7 |

---

## 🛠 Технические навыки

| Навык | Уровень | Инструменты |
|---|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ | VS Code, Foundry |
| Web-пентест (XSS, CORS, IDOR, OAuth, CRLF) | ⭐⭐⭐⭐⭐ | Python, Burp Suite |
| Foundry Fuzzing | ⭐⭐⭐⭐⭐ | forge test --fuzz-runs 10000 |
| Invariant Testing (Echidna-style) | ⭐⭐⭐⭐⭐ | 256 seq / 128K calls |
| **Rust — bug bounty toolkit** | ⭐⭐⭐⭐⭐ | Hunter (6 tools, 50 threads) |
| CTF-разработка | ⭐⭐⭐⭐⭐ | HTML/CSS/JS, GitHub Pages |
| Subdomain enumeration | ⭐⭐⭐⭐⭐ | crt.sh, 1659 subs Yandex |
| Assembly / Yul анализ | ⭐⭐⭐⭐ | grep, regex |
| Storage Collision Detection | ⭐⭐⭐⭐ | Python-скрипты |
| Diamond / Facet Selectors | ⭐⭐⭐⭐ | keccak256 анализ |
| Cross-chain Security | ⭐⭐⭐⭐ | LayerZero, Wormhole |
| DeFi-атаки | ⭐⭐⭐⭐ | Damn Vulnerable DeFi |
| Ethernaut CTF | ⭐⭐⭐⭐ | 14 уровней |
| Rust / Solana Audit | ⭐⭐⭐ | Anchor, SPL Token |
| MEV / Front-running | ⭐⭐⭐ | Sandwich, Arbitrage |
| Oracle Manipulation | ⭐⭐⭐ | Spot, TWAP, Chainlink |

---

## 🦀 Hunter — Professional Bug Bounty Toolkit (Rust)

Собственный инструмент на Rust для профессионального пентеста:

| Команда | Назначение | Потоков |
|---|---|---|
| `hunter cors` | CORS сканер | 1 |
| `hunter subs` | Поиск поддоменов | 50 |
| `hunter check` | Проверка списка хостов | 50 |
| `hunter idor` | Перебор ID | 50 |
| `hunter xss` | Поиск XSS | 1 |
| `hunter fuzz` | Фаззинг параметров | 50 |
| `hunter load` | Загрузка JSON от crt.sh | — |
| `hunter raw` | Запрос без проверки сертификата | — |

Применён на Яндексе: найдено 1659 поддоменов, обнаружены тестовые контуры.

---

## 📤 Отправленные отчёты

| # | Платформа | Проект | Уязвимость | Severity | Статус |
|---|---|---|---|---|---|
| 1 | Sherlock | Aave V4 | Unbounded Loops (×2) | 🟡 Medium | ⏳ Ждём |
| 2 | Sherlock | Aave V4 | Unchecked permit | 🟡 Medium | ✅ У команды |
| 3 | Email | Pachca.com | CORS + открытые пути | 🔴 Critical | ❌ Отклонён |
| 4 | Яндекс | Маркет | Reflected XSS | 🟠 High | ⏳ Ждём |
| 5 | Яндекс | Диск | Information Disclosure | 🟡 Medium | ⏳ Ждём |
| 6 | Яндекс | Паспорт | OAuth Open Redirect + CRLF | 🔴 Critical | ⏳ Ждём |
| 7 | Яндекс | OAuth | redirect_uri не валидируется | 🔴 Critical | ⏳ Ждём |
| 8 | Email | yandex-team.ru | Внутренний OAuth + client_id | 🔴 Critical | 📤 Отправлен |

---

## 🔴 CRITICAL находки (13)

| # | Проект | Суть |
|---|---|---|
| 1-4 | Aave V4 | initialize() без защиты (Hub, Spoke, TokenizationSpoke, TreasurySpoke) |
| 5-6 | Paxos | initialize() без защиты (PAXG, PaxosToken) |
| 7-9 | Lido | initialize() без защиты (StakingRouter, WithdrawalQueue, NodeOperatorsRegistry) |
| 10 | Paxos | upgradeTo(address(0)) |
| 11 | Pachca.com | CORS + открытые пути |
| 12 | Яндекс.Паспорт | OAuth Open Redirect + CRLF Injection |
| 13 | Яндекс | OAuth redirect_uri на production + тест + внутренний |

---

## 🟠 HIGH находки (7)

Aave V4: delegatecall Assembly · Unsafe approve. Paxos: delegatecall Assembly. Lido: delegatecall Assembly · Unsafe approve (2). **Яндекс.Маркет: XSS**.

---

## 🟡 MEDIUM находки (35+)

Aave V4 (7) · Lido (6) · Paxos (8) · Wormhole (5) · Paxos Solana (2) · **Яндекс.Диск: Information Disclosure** · **Яндекс.Путешествия: API без авторизации** · **Ozon: Open Redirect (3)** · **Сбер: Sentry DSN** · **Яндекс: тестовые контуры**

---

## 🔵 LOW / INFO (100+)

Missing Input Validation (50+) · Конфликты селекторов (30+) · Missing zero-address (10+) · nonce без проверок (40+) · **Яндекс: Open Redirect (4 сервиса)** · **VK/RuStore: Open Redirect** · **Сбер: отсутствие CSP/HSTS** · **Яндекс: 1659 поддоменов**

---

## 📁 Проекты

**Яндекс** (12 находок: XSS, OAuth ×3, CSP, Open Redirect ×4, Тестовые контуры, 1659 поддоменов) · **Lido DAO** (24) · **Paxos** (24) · **Wormhole** (10) · **Aave V4** (20) · **Ozon** (4) · **Сбер** (3) · **Pachca.com** (2) · **VK/RuStore** (2) · Metric DEX · DRE App · LayerZero Stellar · Phantom · Nubank

---

## 📜 Обучение

| Ресурс | Прогресс |
|---|---|
| 🦀 Rust Bug Bounty Toolkit | 8 инструментов, 50 потоков |
| 🎯 Собственный CTF | 21 уровень |
| 🎮 Ethernaut CTF | 14 уровней |
| 🔴 Damn Vulnerable DeFi | 12 уровней |
| 📋 Code4rena | LayerZero Stellar |
| 🔍 Sherlock | 3 отчёта |
| 🧪 Fuzzing | 10,000+ прогонов |
| 🔬 Invariant Testing | 128,000+ вызовов |
| 🌐 Web-пентест | XSS, CORS, IDOR, OAuth, CRLF |
| 🔑 OAuth Security | Account Takeover, 3 контура |

---

## 🎯 План

- [x] 157+ уязвимостей
- [x] 13 Critical
- [x] 47+ отчётов
- [x] 8 отчётов отправлено
- [x] Собственный CTF
- [x] Rust Bug Bounty Toolkit
- [x] OAuth на 3 контурах Яндекса
- [x] 1659 поддоменов Яндекса
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

*Обновлено: 19 июля 2026 — Hunter Rust Toolkit, yandex-team.ru, 1659 поддоменов*
