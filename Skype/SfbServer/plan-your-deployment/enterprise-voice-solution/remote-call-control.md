---
title: 規劃商務用 Skype 中的遠端呼叫控制
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 遠端呼叫控制已在舊版的 Lync Server 啟用使用者控制 PBX 電話與 Lync Server 的功能。 Skype for Business Server，此功能已取代呼叫透過工作。 中用於商務用 Skype Server 2015 及移轉寄、 遠端通話的用戶端版本控制不再是可在用戶端設定，並使用已移除。
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982798"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>規劃商務用 Skype 中的遠端呼叫控制
 
遠端呼叫控制已在舊版的 Lync Server 啟用使用者控制 PBX 電話與 Lync Server 的功能。 Skype for Business Server，此功能已取代呼叫透過工作。  *中用於商務用 Skype Server 2015 及移轉寄、 遠端通話的用戶端版本控制不再是可在用戶端設定，並使用已移除。* 
  
 遠端呼叫控制您組織中的使用者位於前端伺服器執行 Lync Server 可以繼續使用遠端呼叫控制，即使它們使用 Skype 商務用戶端。 不過，任何使用者隸屬於 Skype for Business Server，如遠端呼叫控制不支援。 請參閱下表中的伺服器/用戶端組合，以及是否可以支援遠端呼叫控制或通話從公司撥號。
  
||**商務用戶端與 Skype UI 啟用商務用 Skype**|**商務用戶端與 Lync UI 啟用商務用 Skype**|**Skype 商務版 2016年用戶端**|**Lync 2013 用戶端**|**Lync 2010 用戶端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| 商務用 Skype Server <br/> |呼叫從公司撥號  <br/> |1  <br/> |呼叫從公司撥號  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |1  <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |
| Lync Server 2010 <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |1  <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |
   
1. 支援這兩個功能。
  
如需詳細資訊，請參閱 Lync Server 2013 文件中的[Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) 。
  
## <a name="see-also"></a>另請參閱

[計劃工時以 Skype for Business Server 透過呼叫](call-via-work.md)
  
[商務用 skype 桌面用戶端功能比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[請 Skype for Business 通話，但您 PBX 桌上電話用於音訊](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

