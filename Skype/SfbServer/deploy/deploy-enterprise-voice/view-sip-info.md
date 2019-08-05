---
title: 在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '摘要: 瞭解如何在商務用 Skype Server 中查看有關 SIP trunks 的資訊。'
ms.openlocfilehash: a8cb5559b1431987adeef7c50b7810b7e9b4adc7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193258"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊
 
**摘要:** 瞭解如何在商務用 Skype Server 中查看有關 SIP trunks 的資訊。
  
SIP trunks 是用來連接商務用 Skype Server Voice over IP 電話網絡 (PSTN)。 在早期版本的產品中, trunks 是用來將撥出電話從中繼伺服器傳送到 PSTN 閘道, 而每個閘道都限制在單一干線中。 因此, PSTN 閘道與 SIP 幹線本質上完全相同。 針對管理員而言, 這表示只要查看關聯 PSTN 閘道的相關資訊, 就能查看個別 SIP 主幹的相關資訊。
  
在商務用 Skype Server 中, 您現在可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 已不再是相同的。 因此, 這表示系統管理員必須使用新的[CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) Cmdlet, 才能查看個別 SIP 幹線的相關資訊。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>若要查看所有 SIP trunks 的相關資訊

- 下列命令會傳回貴組織中使用的所有 SIP trunks 資訊:
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>若要查看特定 SIP 主幹的資訊

- 這個命令只會傳回具有身分識別 PstnGateway 的 SIP 幹線資訊: 192.168.0.240:
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看指派給某個池之所有 SIP trunks 的相關資訊

- 在這個範例中, 會針對指派給 pool atl-cs-001.litwareinc.com 的所有 SIP trunks 傳回信息:
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
