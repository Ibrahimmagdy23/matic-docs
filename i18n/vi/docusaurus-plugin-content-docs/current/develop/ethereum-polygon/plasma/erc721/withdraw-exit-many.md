---
id: withdraw-exit-many
title: withdrawExitMany
keywords:
- 'plasma client, erc721, withdrawExitMany, polygon, sdk'
description: 'Bắt đầu sử dụng maticjs'
---

# withdrawExitMany {#withdrawexitmany}

Có thể sử dụng phương pháp `withdrawExitMany` để phê duyệt tất cả token.

```
const erc721RootToken = plasmaClient.erc721(<root token address>, true);

const approveResult = await erc721RootToken.withdrawExitMany(<burn tx hash>);

const txHash = await approveResult.getTransactionHash();

const txReceipt = await approveResult.getReceipt();

```