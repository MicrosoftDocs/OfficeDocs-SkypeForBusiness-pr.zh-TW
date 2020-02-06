---
title: 在商務用 Skype Server 中規劃 PSTN 連通性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 在商務用 Skype Server 的企業語音中規劃 PSTN 連線。
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802543"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃 PSTN 連通性
 
在商務用 Skype Server 的企業語音中規劃 PSTN 連線。
  
企業級 VoIP 解決方案必須提供呼叫及從公開的交換電話網絡（PSTN）撥打電話，而不會拒絕服務品質（QoS）。 撥打及接聽來電的使用者不應該知道基礎技術：從使用者的角度來看，企業語音結構和 PSTN 之間的通話看起來就像是另一個電話撥。
  
商務用 Skype 伺服器可透過使用下列選項，提供可靠且可伸縮的 PSTN 連線：
  
- **SIP trunks**至網際網路電話服務提供者（ITSP）
    
- **直接將 SIP**連線至 PSTN 閘道
    
- **直接將 SIP**連線至 PBX
    
根據其大小、地理覆蓋及現有的語音基礎結構，企業可能會在不同的位置使用其中一個、兩個以上的選項。 如需這些選項的詳細資訊，請參閱下列各節。
  
## <a name="in-this-section"></a>本節內容

- [商務用 Skype Server 中的 SIP 中繼](sip-trunking.md)
    
- [商務用 Skype Server 中的直接 SIP 連線](direct-sip.md)
    
- [商務用 Skype Server 中的 M:N 幹線](m-n-trunk.md)
    
- [商務用 Skype Server 中的翻譯規則](translation-rules.md)
    
- [在商務用 Skype Server 中規劃出站語音路由](outbound-voice-routing.md)
    

