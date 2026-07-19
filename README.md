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

## 🦀 HUNTER v3.0 — GOD Mode (Rust)

Собственный профессиональный bug bounty toolkit. 16 модулей, многопоточность, прогресс-бары.

| Модуль | Назначение | Потоков |
|---|---|---|
| `cors` | CORS сканер | 1 |
| `raw` | GET с игнором сертификатов | 1 |
| `subs` | Поддомены через crt.sh | 1 |
| `load` | Загрузка JSON поддоменов | — |
| `check` | Проверка списка хостов | 50 |
| `idor` | IDOR перебор | 50 |
| `xss` | XSS сканер | 1 |
| `fuzz` | Фаззинг параметров | 50 |
| `rce` | RCE Deep Scan (4 стадии) | 1 |
| `llm` | LLM Prompt Injection | 1 |
| `race` | Race Condition тестер | 10 |
| `graphql` | GraphQL introspection | 1 |
| `jwt` | JWT анализ (alg none, expiry) | 1 |
| `cache` | Cache Poisoning | 1 |
| `ssti` | SSTI сканер | 1 |
| `smuggle` | HTTP Request Smuggling | 1 |

**Стек:** Rust, tokio (async), reqwest, colored, indicatif, base64

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

Aave V4: initialize() без защиты (4). Paxos: initialize() без защиты (2) · upgradeTo(address(0)). Lido: initialize() без защиты (3). Pachca.com: CORS. Яндекс: OAuth Open Redirect + CRLF · OAuth redirect_uri (3 контура) · Внутренний OAuth yandex-team.ru.

---

## 🟠 HIGH находки (7)

Aave V4: delegatecall Assembly · Unsafe approve. Paxos: delegatecall Assembly. Lido: delegatecall Assembly · Unsafe approve (2). Яндекс.Маркет: Reflected XSS.

---

## 🟡 MEDIUM находки (35+)

Aave V4 (7) · Lido (6) · Paxos (8) · Wormhole (5) · Яндекс.Диск: Information Disclosure · Яндекс.Путешествия: API без авторизации · Ozon: Open Redirect (3) · Сбер: Sentry DSN · Яндекс: тестовые контуры (rc/test) · VK/RuStore: Open Redirect.

---

## 🔵 LOW / INFO (100+)

Missing Input Validation (50+) · Конфликты селекторов (30+) · Missing zero-address (10+) · nonce без проверок (40+) · Яндекс: Open Redirect (4 сервиса) · Сбер: отсутствие CSP/HSTS · Яндекс: 1659 поддоменов.

---

## 🛠 Технические навыки

| Навык | Уровень |
|---|---|
| Ручной аудит Solidity | ⭐⭐⭐⭐⭐ |
| Web-пентест (XSS, CORS, IDOR, OAuth, CRLF) | ⭐⭐⭐⭐⭐ |
| Foundry Fuzzing + Invariant Testing | ⭐⭐⭐⭐⭐ |
| Rust — Bug Bounty Toolkit (16 модулей) | ⭐⭐⭐⭐⭐ |
| CTF-разработка (21 уровень) | ⭐⭐⭐⭐⭐ |
| Assembly / Yul анализ | ⭐⭐⭐⭐ |
| Subdomain enumeration (crt.sh) | ⭐⭐⭐⭐⭐ |
| GraphQL / JWT / Cache / SSTI / Smuggling | ⭐⭐⭐⭐ |
| Cross-chain Security | ⭐⭐⭐⭐ |
| DeFi-атаки (Damn Vulnerable DeFi 12 ур.) | ⭐⭐⭐⭐ |
| Ethernaut CTF (14 уровней) | ⭐⭐⭐⭐ |
| OAuth / Open Redirect / CRLF | ⭐⭐⭐⭐ |
| Rust / Solana Audit | ⭐⭐⭐ |
| MEV / Front-running | ⭐⭐⭐ |
| Oracle Manipulation | ⭐⭐⭐ |

---

## 📜 Обучение

| Ресурс | Прогресс |
|---|---|
| 🦀 HUNTER v3.0 — собственный тулкит | 16 модулей |
| 🎯 Собственный CTF | 21 уровень |
| 🎮 Ethernaut CTF | 14 уровней |
| 🔴 Damn Vulnerable DeFi | 12 уровней |
| 📋 Code4rena | LayerZero Stellar |
| 🔍 Sherlock | 3 отчёта |
| 🧪 Foundry Fuzzing | 10,000+ прогонов |
| 🔬 Invariant Testing | 128,000+ вызовов |
| 🌐 Web-пентест | 8 типов атак |
| 🔑 OAuth Security | Account Takeover, 3 контура |

---

## 🎯 План

- [x] 157+ уязвимостей
- [x] 13 Critical
- [x] 47+ отчётов
- [x] 8 отчётов отправлено
- [x] Собственный CTF
- [x] HUNTER v3.0 — 16 модулей
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

*Обновлено: 19 июля 2026 — HUNTER v3.0 GOD Mode (16 модулей)*
