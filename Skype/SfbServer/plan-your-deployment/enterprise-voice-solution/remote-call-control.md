---
title: 在商務用 Skype 中規劃遠端呼叫控制
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過運作」的呼叫取代。 在商務用 Skype Server 2015 的用戶端版本中，接著向前，用戶端的遠端呼叫控制已無法在用戶端中進行設定，已將其移除，可供使用。
---

# <a name="plan-for-remote-call-control-in-skype-for-business"></a>在商務用 Skype 中規劃遠端呼叫控制
 
遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過運作」的呼叫取代。  *在商務用 Skype Server 2015 的用戶端版本中，接著向前，用戶端的遠端呼叫控制已無法在用戶端中進行設定，已將其移除，可供使用。* 
  
 遠端呼叫控制組織中執行 Lync Server 之前端伺服器的使用者，即使使用商務用 Skype 用戶端，仍然可以繼續使用遠端呼叫控制。 不過，對於位於商務用 Skype Server 的任何使用者，都不支援遠端呼叫控制。 請參閱下表的伺服器/用戶端組合，以及是否可以支援遠端呼叫控制或透過工作呼叫。
  
|&nbsp;|已啟用 Skype 使用者介面的商務用 Skype 用戶端|已啟用 Lync 使用者介面的商務用 Skype 用戶端|商務用 Skype 2016 用戶端|Lync 2013 用戶端|Lync 2010 用戶端|
|:-----|:-----|:-----|:-----|:-----|:-----|
| 商務用 Skype Server  |從公司通話   |1  |從公司通話   |1  |1  |
| Lync Server 2013  |遠端呼叫控制   |遠端呼叫控制   |1  |遠端呼叫控制   |遠端呼叫控制   |
| Lync Server 2010  |遠端呼叫控制   |遠端呼叫控制   |1  |遠端呼叫控制   |遠端呼叫控制   |
   
1. 這兩項功能都不受支援。
  
如需詳細資訊，請參閱 Lync Server 2013 檔中的 [遠端呼叫控制](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) 。
  
## <a name="see-also"></a>另請參閱

[規劃商務用 Skype Server 中的工作通話](call-via-work.md)
  
[商務用 Skype 的桌面用戶端功能比較](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[撥打商務用 Skype 電話，但使用您的 PBX 電話機進行音訊](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)