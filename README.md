Имя: [Дмитрий]
Специализация: Web3 / Smart Contract Security
Опыт: 2+ недели активного поиска уязвимостей
Платформы: Sherlock, Immunefi, Cantina, Code4rena
📊 Статистика
Показатель	Значение
Проанализировано проектов	7
Найдено уязвимостей	12+
Отправлено отчётов	2 (ожидают решения)
Платформ охвачено	5
🔍 Проекты и находки
1. Aave V4 (Sherlock) — ⏳ На рассмотрении
#	Находка	Severity	Файл
1	Unbounded Loop в setUserPositionManagers()	Medium	Spoke.sol L450
2	Unbounded Loop в _calculateLiquidationAmounts()	Medium	Spoke.sol L795

Описание: Обнаружены циклы без ограничения длины массива, позволяющие атакующему вызвать gas exhaustion и заблокировать работу функций.

Навыки: Анализ Solidity-кода, поиск DoS-уязвимостей, написание PoC на Foundry.
2. Wormhole (Immunefi) — 🔍 Анализ завершён
#	Находка	Severity	Файл
1	Missing Input Validation в submitContractUpgrade()	Low	Governance.sol
2	Missing Event в upgradeImplementation()	Low	Governance.sol
3	Centralization Risk — 13/19 guardian'ов контролируют все активы	Medium	Governance.sol

Описание: Полный анализ Governance-контрактов Wormhole. Найдены проблемы с валидацией входных данных и centralization-риски.

Навыки: Анализ мостов, governance-механизмов, кросс-чейн протоколов.
3. Paxos (Cantina) — 🔍 Анализ завершён
#	Находка	Severity	Файл
1	Integer Overflow — компилятор 0.4.24 без SafeMath	Medium	PAXGImplementation.sol
2	Integer Overflow — AddressUtils.sol без SafeMath	Medium	AddressUtils.sol
3	TODO в production-коде	Low	AddressUtils.sol

Описание: Анализ семи репозиториев Paxos. Найдены контракты с устаревшим компилятором без защиты от переполнений.

Навыки: Анализ стейблкоинов, ERC-20 токенов, прокси-контрактов.
4. Lido DAO (Immunefi) — 🔍 Анализ завершён
#	Находка	Severity	Файл
1	Missing Input Validation в 50+ функциях	Low	StakingRouter.sol, Dashboard.sol

Описание: Обнаружено отсутствие проверки длины входных данных в governance-функциях Lido.

Навыки: Анализ LSD-протоколов, governance-механизмов.
5. Metric DEX (Sherlock) — 🔍 Анализ завершён

Описание: Изучены смарт-контракты oracle-based DEX. Выявлены потенциальные проблемы с округлениями и staleness-проверками оракулов.

Навыки: Анализ DEX, оракулов, ценовых механизмов.
6. DRE App / dreUSD (Sherlock) — 🔍 Анализ завершён

Описание: Проанализирован стейблкоин-протокол с кросс-чейн мостами. Изучены ERC-4626 vault, withdrawal NFT, кросс-чейн compliance.

Навыки: ERC-4626, LayerZero OFT, compliance-механизмы.
7. LayerZero Stellar (Code4rena) — 🔍 Анализ завершён

Описание: Изучена Rust-реализация LayerZero V2 на Soroban (Stellar). Анализ TTL-хранения, кросс-чейн сообщений.

Навыки: Rust, Soroban, кросс-чейн протоколы.
🛠 Технические навыки
Категория	Навыки
Языки	Solidity, Python, Rust (базовый)
Инструменты	Foundry, Git, VS Code
Блокчейны	Ethereum, Solana, Base, Arbitrum, Stellar
Уязвимости	Reentrancy, Integer Overflow, Access Control, DoS, Centralization, Missing Validation
Стандарты	ERC-20, ERC-721, ERC-4626, EIP-2612, UUPS
Протоколы	Aave, Wormhole, Lido, LayerZero, Paxos
📜 Сертификаты и обучение

    ✅ CTF: Ethernaut (в процессе)

    ✅ Code4rena: анализ LayerZero Stellar

    ✅ Sherlock: активный участник

🎯 Цели

    Получить первую выплату за bug bounty

    Выйти на Junior Security Researcher

    Освоить фаззинг (Echidna, Foundry fuzzing)

    Изучить формальную верификацию

📞 Контакты

    GitHub: [Werety16451645]

    Sherlock: [delayed]

    Immunefi: [Delayed]

    Email: [werety1645@gmail.com]

Портфолио создано 16 июля 2026 года. Обновляется по мере находок.
