---
title: 在商務用 Skype 中規劃遠端呼叫控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過公司來電」取代。 在商務用 Skype Server 2015 的用戶端版本中，繼續進行遠端呼叫控制，用戶端將無法再進行設定，已將其移除供使用。
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813513"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>在商務用 Skype 中規劃遠端呼叫控制
 
遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過公司來電」取代。  *在商務用 Skype Server 2015 的用戶端版本中，繼續進行遠端呼叫控制，用戶端將無法再進行設定，已將其移除供使用。* 
  
 遠端呼叫控制組織中執行 Lync Server 之前端伺服器的使用者，即使使用的是商務用 Skype 用戶端，仍然可以繼續使用遠端呼叫控制。 不過，對於位於商務用 Skype 伺服器上的任何使用者，都不支援遠端呼叫控制。 請參閱下表的伺服器/用戶端組合，以及是否可以支援遠端呼叫控制或透過工作呼叫。
  
||**啟用 Skype 使用者介面的商務用 skype 用戶端**|**已啟用 Lync 使用者的商務用 Skype 用戶端**|**商務用 Skype 2016 用戶端**|**Lync 2013 用戶端**|**Lync 2010 用戶端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| 商務用 Skype Server <br/> |從公司通話  <br/> |1  <br/> |從公司通話  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |1  <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |
| Lync Server 2010 <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |1  <br/> |遠端呼叫控制  <br/> |遠端呼叫控制  <br/> |
   
1. 這兩項功能都不受支援。
  
如需詳細資訊，請參閱 Lync Server 2013 檔中的 [遠端呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208) 。
  
## <a name="see-also"></a>另請參閱

[透過商務用 Skype Server 中的工作規劃通話](call-via-work.md)
  
[商務用 Skype 的桌面用戶端功能比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[進行商務用 Skype 通話，但使用您的 PBX 桌面電話進行音訊](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

