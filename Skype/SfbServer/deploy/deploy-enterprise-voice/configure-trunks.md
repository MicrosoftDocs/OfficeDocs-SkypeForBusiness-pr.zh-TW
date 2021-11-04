---
title: 在商務用 Skype Server 中設定主幹
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要：瞭解如何在商務用 Skype Server 中的企業語音的轉送伺服器和對等間設定主幹。
ms.openlocfilehash: 128be18c31802787c173c8d180de80f5ae5a64fb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748889"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中設定主幹
 
**摘要：** 瞭解如何在商務用 Skype Server 中為企業語音設定轉送伺服器和對等間的主幹。
  
在企業語音部署的過程中，您可以設定轉送伺服器與一或多個下列對等之間的主幹，以為組織中的企業語音用戶端和裝置提供公用交換電話網路 (PSTN) 連線能力：
  
- 網際網路電話語音服務提供者 (ITSP) 的 SIP 主幹連線
    
- PSTN 閘道
    
- 專用交換機 (Private branch exchange，PBX)
    
如需詳細資訊，請參閱[Plan for PSTN connectivity in 商務用 Skype Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
商務用 Skype Server 功能支援閘道和轉送伺服器之間的多重關聯。 這些關聯是透過定義主幹（轉送伺服器集區和公用交換電話網路 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP-PBX）進行。 使用拓撲產生器，將閘道與轉送伺服器相關聯 (也就是說，主幹) 。
  
- 若要在商務用 Skype Server 中指派或移除主幹，您必須先在拓撲產生器中定義主幹。 主幹包含下列關聯：轉送伺服器的完整功能變數名稱 (FQDN) 、轉送伺服器接聽埠、閘道 FQDN 及閘道聆聽埠。
    
- 若要設定多個主幹，您可以在同一個閘道和轉送伺服器之間建立多個關聯。 這為企業語音基礎結構提供額外的復原能力，尤其適用于私人 exchange (PBX) interoperational 案例中。 
    
定義主幹時，它必須與路由相關聯。 若要將主幹關聯至路由，您可以在拓撲產生器中定義主幹的簡易名稱。 這個簡易名稱是在商務用 Skype Server 控制台中做為主幹名稱，主幹可以與路由相關聯。 簡易主幹名稱會當做商務用 Skype Server 管理命令介面中的閘道名稱使用。 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理員必須選取與轉送伺服器相關聯的預設主幹。 在 [拓撲產生器] 中，以滑鼠右鍵按一下關聯的轉送伺服器，然後按一下 [ **屬性**]。 指定轉送伺服器的預設閘道。 
  

