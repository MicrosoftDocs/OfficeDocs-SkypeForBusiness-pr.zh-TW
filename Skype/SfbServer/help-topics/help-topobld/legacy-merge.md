---
title: 舊版合併
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: '[Web 會議外部 FQDN] 允許外部使用者加入內部會議。請輸入舊有 Edge Server 之 Web 會議外部介面的完整網域名稱 (FQDN)。'
ms.openlocfilehash: 0ca61fdb9312cf2265666cd383fc517006d7e83c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847566"
---
# <a name="legacy-merge"></a>舊版合併

[Web 會議外部 FQDN] 允許外部使用者加入內部會議。請輸入舊有 Edge Server 之 Web 會議外部介面的完整網域名稱 (FQDN)。

[外部 Web 會議外部連接埠] 值 443 為針對會議用戶端所預設的傳輸控制通訊協定 (TCP) 工作階段初始通訊協定 (SIP) 連接埠。如果系統未使用預設值，請更新 [外部 Web 會議外部連接埠] 的值。

如果您打算使用這部 Edge Server 進行同盟，則選取 [此 Edge 集區是用於同盟和公用 IM 連線] 核取方塊。如果您已部署多部 Edge Server，當中只有一部會啟用同盟功能。如果您並未勾選此方塊，而是決定稍後再啟用同盟，則您必須再次執行 [拓撲產生器合併精靈] 並發行拓撲。如需詳細資訊，請參閱＜[Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)＞。