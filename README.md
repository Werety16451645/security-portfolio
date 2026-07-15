# 🔐 Web3 Security Researcher Portfolio

**Дмитрий** | Junior Smart Contract Security Researcher

[![Sherlock](https://img.shields.io/badge/Sherlock-Active-blue)](https://audits.sherlock.xyz)
[![Immunefi](https://img.shields.io/badge/Immunefi-Registered-green)](https://immunefi.com)
[![Code4rena](https://img.shields.io/badge/Code4rena-Participant-purple)](https://code4rena.com)

---

## 📊 Статистика

| Метрика | Значение |
|---|---|
| Проектов проанализировано | 7 |
| Уязвимостей найдено | 12+ |
| Отчётов на рассмотрении | 2 (Medium) |
| Охвачено платформ | 5 |

---

## 🏆 Отчёты на рассмотрении

### Aave V4 — Sherlock (⏳ ожидание)

| # | Уязвимость | Severity | Контракт |
|---|---|---|---|
| 1 | Unbounded Loop в `setUserPositionManagers()` | Medium | `Spoke.sol:450` |
| 2 | Unbounded Loop в `_calculateLiquidationAmounts()` | Medium | `Spoke.sol:795` |

**Impact:** Gas exhaustion через неограниченные циклы, блокировка ликвидаций.

**PoC:** Foundry-тесты с демонстрацией линейного роста газа.

---

## 🔍 Завершённые исследования

### Wormhole (Immunefi)
- `submitContractUpgrade()` — Missing Input Validation (Low)
- `upgradeImplementation()` — Missing Event Emission (Low)
- Guardian Set — Centralization Risk (Medium)

### Paxos (Cantina)
- `PAXGImplementation.sol` — Integer Overflow 0.4.24 без SafeMath (Medium)
- `AddressUtils.sol` — Integer Overflow без SafeMath (Medium)
- TODO в production-коде (Low)

### Lido DAO (Immunefi)
- 50+ функций без валидации входных данных (Low)

### Metric DEX (Sherlock)
- Анализ округлений и staleness-проверок оракулов

### DRE App / dreUSD (Sherlock)
- ERC-4626 vault, withdrawal NFT, LayerZero кросс-чейн compliance

### LayerZero Stellar (Code4rena)
- Rust/Soroban реализация, TTL-хранение, кросс-чейн сообщения

---

## 🛠 Технический стек

| Категория | Технологии |
|---|---|
| **Языки** | Solidity, Python, Rust (basics) |
| **Фреймворки** | Foundry, Hardhat |
| **Блокчейны** | Ethereum, Solana, Base, Arbitrum, Stellar |
| **Стандарты** | ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS |
| **Протоколы** | Aave V4, Wormhole, Lido, LayerZero, Paxos |

**Типы уязвимостей:**
- DoS (Gas Exhaustion, Unbounded Loops)
- Integer Overflow/Underflow
- Access Control / Centralization
- Missing Input Validation
- Missing Events

---

## 📜 Обучение

- 🎮 **Ethernaut CTF** — в процессе
- 📋 **Code4rena** — LayerZero Stellar contest
- 🔍 **Sherlock** — активный участник

---

## 🎯 План развития

- [ ] Получить первую выплату (Aave V4 — на рассмотрении)
- [ ] Junior Security Researcher
- [ ] Освоить Echidna / Foundry fuzzing
- [ ] Формальная верификация (Certora)

---

## 📞 Контакты

- **GitHub:** [@Werety16451645](https://github.com/Werety16451645)
- **Sherlock:** @delayed
- **Immunefi:** @Delayed
- **Email:** werety1645@gmail.com

---

*Последнее обновление: 16 июля 2026*
