---
id: validator-staking-operations
title: Стейкинг на Polygon
description: Узнайте, как сделать ставку в качестве валидатора в Polygon Network
keywords:
  - docs
  - matic
  - polygon
  - stake
  - claim
  - unstake
slug: validator-staking-operations
image: https://wiki.polygon.technology/img/polygon-wiki.png
---
import useBaseUrl from '@docusaurus/useBaseUrl';

## Предварительные условия {#prerequisites}

### Установка полного нода {#full-node-set-up}

Ваш узел валидатора полностью настроен и синхронизирован. См. также:

* [Запустите узел валидатора](run-validator.md)
* [Запуск ноды валидатора с помощью Ansible](run-validator-ansible.md)
* [Запуск узла проверки с помощью двоичных файлов](run-validator-binaries.md)

### Настройка аккаунта {#account-setup}

На вашем вершине валидатора проверьте, что настроен аккаунт. Для этого выполните следующую команду **в узле проверки**:

```sh
    heimdalld show-account
```

В результате вы должны получить следующее:

```json
{
    "address": "0x6c468CF8c9879006E22EC4029696E005C2319C9D",
    "pub_key": "0x04b12d8b2f6e3d45a7ace12c4b2158f79b95e4c28ebe5ad54c439be9431d7fc9dc1164210bf6a5c3b8523528b931e772c86a307e8cff4b725e6b4a77d21417bf19"
}
```

Будет отображен ваш адрес и открытый ключ для узла проверки. Обратите внимание, что **этот адрес должен соответствовать вашему адресу подписанта в Ethereum**.

### Отображение закрытого ключа {#show-private-key}

Это необязательное действие.

На вашем вершине валидатора проверьте, что приватный ключ был верен. Для этого выполните следующую команду **в узле проверки**:

```sh
heimdalld show-privatekey
```

В результате вы должны получить следующее:

```json
{
    "priv_key": "0x********************************************************"
}
```

## Стейкинг на Polygon {#stake-on-polygon}

Размещать средства в стейкинге на Polygon можно с помощью [дашборда валидатора](https://staking.polygon.technology/validators/).

### Стейкинг с помощью дашборда стейкинга {#stake-using-the-staking-dashboard}

1. Перейдите в [дашборд валидатора](https://staking.polygon.technology/validators/).
2. Войдите в кошелек. MetaMask — это рекомендуемый кошелек. Вам необходимо убедиться, что вы авторизуетесь с помощью того же адреса, где присутствуют ваши токены MATIC.
3. Нажмите **кнопку Стать валидатором**. Вам будет предложено настроить свой узел. Это обязательное действие. В противном случае при попытке разместить средства в стейкинге появится сообщение об ошибке.
4. На следующем экране добавьте данные валидатора, размер комиссии и количество средств, размещаемых в стейкинге.
5. Нажмите **Stake Now** (разместить в стейкинге).

После завершения транзакции средства будут размещены в стейкинге, и вы сможете стать валидатором. Вас попросят подтвердить транзакцию три раза.

* Approve Transaction (одобрить транзакцию) — одобрение транзакции стейкинга.
* Stake (разместить в стейкинге) — подтверждение транзакции стейкинга.
* Save (сохранить) — сохранение ваших данных валидатора.

:::note

Чтобы изменения отразились на [дашборде стейкинга](https://staking.polygon.technology/account), требуется дождаться 12 подтверждений блоков.

:::

### Проверка остатка средств {#check-the-balance}

Чтобы проверить остаток средств на вашем адресе, выполните следующую команду:

```sh
heimdallcli query auth account SIGNER_ADDRESS --chain-id CHAIN_ID
```

где

* SIGNER_ADDRESS — ваш [адрес подписанта](/docs/maintain/glossary.md#validator).
* CHAIN_ID — идентификатор цепочки Polygon mainnet с клиентским префиксом: `heimdall-137`.

В результате вы должны получить следующее:

```json
address: 0x6c468cf8c9879006e22ec4029696e005c2319c9d
coins:
- denom: matic
amount:
    i: "1000000000000000000000"
accountnumber: 0
sequence: 0
```

### Получение наград валидатора {#claim-rewards-as-a-validator}

Установив нод и разместив средства в стейкинге, вы начнете получать награды за выполнение обязанностей валидатора. Награды предоставляются за их добросовестное выполнение.

Чтобы получить награды, перейдите на [дашборд валидатора](https://staking.polygon.technology/account).

В профиле вы увидите две кнопки:

* Withdraw Reward (вывести награды)
* Restake Reward (добавить награды в стейкинг)

#### Withdraw Reward (вывести награды) {#withdraw-reward}

Как валидатор, вы получаете награды, если корректно выполняете свои обязанности.

После нажатия **Withdraw Reward** (вывести награды) награды поступят в ваш кошелек.

Дашборд обновится после 12 подтверждений блоков.

#### Restake Reward (добавить награды в стейкинг) {#restake-reward}

Добавление наград в стейкинг — это простой способ для валидатора увеличить свой стейк.

Нажав **Restake Reward** (добавить награды в стейкинг), вы добавите награды в стейкинг и увеличите свой стейк.

Дашборд обновится после 12 подтверждений блоков.
