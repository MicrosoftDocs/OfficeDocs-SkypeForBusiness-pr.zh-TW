---
title: 同盟路由設定展開工具
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 若要設定網站同盟路由指派，您必須先在 Edge Server 或 Edge Server 集區上啟用同盟。如果 Edge Server 或集區上未啟用同盟，則無法修改網站的同盟路由指派設定。
ms.openlocfilehash: 2cf088fbb95f6d4d7ed563313c332d5a9dd47dd4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833639"
---
# <a name="federation-route-settings-expander"></a>同盟路由設定展開工具
 
若要設定網站同盟路由指派，您必須先在 Edge Server 或 Edge Server 集區上啟用同盟。如果 Edge Server 或集區上未啟用同盟，則無法修改網站的同盟路由指派設定。

如果已設定 Edge Server 或集區上的同盟設定，則可以設定下列選項： 
  
- **允許對所有網站的同盟路由指派** 此設定會影響所有網站。 請確定您在此網站上設定的設定適用于所有網站。
    
- **啟用 SIP 同盟** 選取此選項可啟用 SIP 同盟路由，然後選取 Director 或 Edge 集區作為同盟路由。
    
- **啟用 XMPP 同盟** 選取此選項可啟用 XMPP 同盟路由，然後選取 Director 或 Edge 集區作為同盟路由。
- 
  > [!NOTE]
  > XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。
    

