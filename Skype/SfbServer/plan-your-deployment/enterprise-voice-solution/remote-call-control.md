---
title: 在商務用 Skype 中規劃遠端通話控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: '[遠端通話控制] 是舊版 Lync Server 中的功能, 可讓使用者使用 Lync Server 控制其 PBX 手機。 在商務用 Skype Server 中, 此功能已由 [透過工作通話] 取代。 在商務用 Skype Server 2015 的用戶端版本中, 繼續進行, 用戶端的遠端通話控制已不再提供, 且已移除供使用。'
ms.openlocfilehash: e98bcbd7e1feb91b31994d2ece2770c911547882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187573"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>在商務用 Skype 中規劃遠端通話控制
 
[遠端通話控制] 是舊版 Lync Server 中的功能, 可讓使用者使用 Lync Server 控制其 PBX 手機。 在商務用 Skype Server 中, 此功能已由 [透過工作通話] 取代。  *在商務用 Skype Server 2015 的用戶端版本中, 繼續進行, 用戶端的遠端通話控制已不再提供, 且已移除供使用。* 
  
 如果您組織中的遠端通話控制使用者是駐留在執行 Lync Server 的前端伺服器上, 即使他們使用的是商務用 Skype 用戶端, 也可以繼續使用遠端通話控制。 不過, 任何駐留在商務用 Skype Server 上的使用者, 都不支援遠端通話控制。 請參閱下表以取得伺服器/用戶端組合, 以及他們是否能支援遠端通話控制或透過工作通話。
  
||**已啟用 Skype UI 的商務用 skype 用戶端**|**已啟用 Lync UI 的商務用 Skype 用戶端**|**商務用 Skype 2016 用戶端**|**Lync 2013 用戶端**|**Lync 2010 用戶端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| 商務用 Skype 伺服器 <br/> |透過公司通話  <br/> |sr-1 <br/> |透過公司通話  <br/> |sr-1 <br/> |sr-1 <br/> |
| Lync Server 2013 <br/> |遠端通話控制  <br/> |遠端通話控制  <br/> |sr-1 <br/> |遠端通話控制  <br/> |遠端通話控制  <br/> |
| Lync Server 2010 <br/> |遠端通話控制  <br/> |遠端通話控制  <br/> |sr-1 <br/> |遠端通話控制  <br/> |遠端通話控制  <br/> |
   
1. 這兩個功能都不受支援。
  
如需詳細資訊, 請參閱 Lync Server 2013 檔中的[遠端通話控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。
  
## <a name="see-also"></a>另請參閱

[透過商務用 Skype Server 中的工作規劃通話](call-via-work.md)
  
[商務用 Skype 的桌面用戶端功能比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[撥打商務用 Skype 電話, 但使用您的 PBX 電話進行音訊](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

