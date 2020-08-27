---
title: 深入了解通話線路識別碼和來電方名稱
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解為何您需要新增在您使用 [新的當地號碼埠順序] 嚮導時可以變更帳戶的授權人員。
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255396"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>深入了解通話線路識別碼和來電方名稱

CallerID （如通常所說的話），實際上是由兩個面向使用者的可識別區塊所組成：
    - 電話號碼 (通常稱為 CLID 或呼叫線路識別碼)  
    - 呼叫參與方名稱 (通常稱為 CNAM) ，最多可以長達15個字元。 

撥打電話時，會將 CLID (電話號碼) 路由到目的地的載波 (也稱為 [端接載波) ]。 通話的 CNAM 資訊可以與通話路由，也可能不會與電話進行路由，因為這會因國家/地區如何實現 CNAM (（如果所有) 都一樣）。 CNAM 傳送與通話的可靠性，會根據將呼叫作為中間和/或終止載波來處理通話的國家和運營商而有所不同。 

CLID & CNAM 傳輸是終止載波的責任，因為端接運營商必須支援 CLID & CNAM 功能，以及提供這兩個值的最新記錄。 Microsoft 可靠地在起源撥打電話時提供 CLID 值，但這些值在經過中間載波或終止載波後可能不會保持不變。 遺憾的是，如果 CLID 值已變更、由中間或終止載波省略或截斷，Microsoft 幾乎無法 recourse 在公用電話網絡中修正這些問題。

CNAM 中的不一致可能是由於中間或終止載波的延遲，在授權資料庫中重新整理 CNAM 資訊，就像在美國的情況下。 在沒有 CNAM 授權資料庫的國家/地區中，個別的運營商做法也可能會造成 CNAM 資訊與通話不完整的問題。 Microsoft 目前不支援美國以外的國家/地區的來源 CNAM 資訊。」

## <a name="related-topics"></a>相關主題


