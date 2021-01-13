---
title: 在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 摘要：瞭解如何在商務用 Skype Server 中查看有關 SIP 主幹的資訊。
ms.openlocfilehash: 29a5a025589f4df7d99b8bf708bf8bd67d0f138f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830523"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊
 
**摘要：** 瞭解如何在商務用 Skype Server 中查看有關 SIP 主幹的資訊。
  
SIP 主幹是用來將商務用 Skype Server Voice over IP phone 網路與公用交換電話網路 (PSTN) 連線。 在舊版本的產品中，主幹是用來將撥出電話從轉送伺服器路由傳送至 PSTN 閘道，而每個閘道都限制為單一主幹。 因此，PSTN 閘道和 SIP 主幹本質上都相同。 針對系統管理員而言，只要查看相關聯的 PSTN 閘道的相關資訊，就可以查看個別 SIP 主幹的相關資訊。
  
不過，在商務用 Skype Server 中，多個主幹現在可以指派給單一 PSTN 閘道;這表示閘道和主幹不再是一個，也是相同的。 反過來，這表示系統管理員必須使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) Cmdlet，才能查看個別 SIP 主幹的相關資訊。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>若要查看所有 SIP 主幹的資訊

- 下列命令會傳回組織中使用之所有 SIP 主幹的資訊：
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>若要查看特定 SIP 主幹的資訊

- 這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看指派至集區之所有 SIP 主幹的資訊

- 在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
