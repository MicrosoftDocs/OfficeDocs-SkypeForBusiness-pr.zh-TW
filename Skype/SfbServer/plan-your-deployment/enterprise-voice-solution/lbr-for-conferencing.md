---
title: 在商務用 Skype Server 中 Location-Based 會議路由
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
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 在商務用 Skype Server Enterprise Voice 中規劃會議的位置基礎路由（包括諮詢通話轉移）。
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825573"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中 Location-Based 會議路由

在商務用 Skype Server Enterprise Voice 中規劃會議的位置基礎路由（包括諮詢通話轉移）。

Location-Based 路由可讓您根據通話中各方的位置，限制 VoIP 端點和 PSTN 端點之間通話的路由。 Location-Based 的會議路由功能可讓您在會議上強制執行 Location-Based 的路由規則 (亦即會議) 以避免 PSTN 免付費旁路。 應用程式會監視作用中的會議，並根據參與的使用者位置，強制執行 Location-Based 路由限制。 會議應用程式的 Location-Based 路由，另外也可強制執行 Location-Based 路由限制，以進行涉及 PSTN 端點的顧問式轉接。

Location-Based 路由會議應用程式為商務用 Skype 會議提供一種防護 PSTN 免付費旁路的機制。 應用程式會根據參與商務用 Skype 使用者的位置，監控使用中的會議並強制執行 Location-Based 路由限制。

Location-Based 路由會議應用程式會決定在符合下列準則時，是否要在商務用 Skype 會議上強制執行 Location-Based 路由：

- 已啟用會議召集人的 Location-Based 路由。 Location-Based 路由限制只會套用至已啟用 Location-Based 路由之使用者所組織的會議。

- 至少有一個會議參與者為 PSTN 端點。 Location-Based 路由限制只適用于包括 PSTN 端點的會議。

- PSTN 閘道用來將會議加入 PSTN 的網路網站，以及召集人和參與者連線所在的網路網站。

會議應用程式的 Location-Based 路由，可防止將商務用 Skype 使用者和 PSTN 端點從不同的網路網站加入相同的會議。 如果為 Location-Based 路由啟用會議召集人，會議應用程式會強制執行下列限制：

- 可以加入商務用 Skype 會議的端點取決於已加入會議的端點，而且此限制會調整為加入會議的端點，而且會將新的端點加入會議。 如果召集人和參與者從相同的網路網站加入商務用 Skype 會議，則來自相同網路網站的另一位參與者，允許來自不同網路網站或來自未知網路網站之參與者的另一位參與者加入。

- 如果召集人和參與者從不同或未知的網路網站加入會議，則不允許 PSTN 端點加入會議（如果 PSTN 通話 ingresses 從為 Location-Based 路由啟用的 SIP 主幹）。

- 如果召集人和參與者全都從相同的網路網站加入會議，且有參與者加入來自 PSTN 的相同會議，則不允許來自不同網路網站的商務用 Skype 端點加入會議。

下表摘要說明這些會議 Location-Based 路由限制。

|在會議中，任何指定點的使用者 (s) |允許加入會議的使用者 (s) |不允許使用者 (s) 加入會議|
|:-----|:-----|:-----|
|商務用 Skype VoIP 用戶端使用者 (s) 從單一網路網站  <br/> |商務用 Skype VoIP 來自相同網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自不同網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> 從 PSTN 端點加入的使用者  <br/> |無  <br/> |
|商務用 Skype VoIP 用戶端使用者 (s) 從未知的網路網站  <br/> |商務用 Skype VoIP 任何網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> |透過 PSTN 端點加入使用者  <br/> |
|商務用 Skype VoIP 來自不同網路網站的用戶端使用者  <br/> |商務用 Skype VoIP 任何網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> |透過 PSTN 端點加入使用者  <br/> |
|商務用 Skype VoIP 用戶端使用者 (s) 從單一網路網站，以及從 PSTN 端點加入的使用者  <br/> |商務用 Skype VoIP 來自相同網路網站的用戶端使用者  <br/> |商務用 Skype VoIP 來自不同網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> |

下列為會議應用程式的 Location-Based 路由的其他特性：

- 當使用者因 Location-Based 路由限制而不允許加入會議時，會拒絕對會議的呼叫，並且商務用 Skype 用戶端將會報告通話未完成或已經結束。

- 在加入具有 Location-Based 路由 enforcements 之會議的 PSTN 端點時，如果端點透過未啟用 Location-Based 路由的主幹加入，則不會限制加入會議的狀態。

- 透過 SIP 主幹（透過非出局來電）連接到轉送伺服器的 PBX 系統，將會與商務用 Skype 使用者具有相同的 enforcements，而這些使用者位於與 SIP 主幹定義相同的網路網站中。 例如，PSTN 端點可以加入具有 PBX 使用者的會議，以及商務用 Skype 使用者（如果它們位於相同的網路網站中）; 否則為商務用 Skype 使用者。否則，如果 PBX 使用者與商務用 Skype 使用者位於不同的網路網站，將不允許 PSTN 端點加入會議。

> [!NOTE]
> 使用商務用 Skype 累計更新4時，應遵循下清單格中的行為：

|使用者|其他聚會|動作|結果|
|:-----|:-----|:-----|:-----|
|商務用 Skype Mobile  <br/> |Pstn  <br/> |商務用 Skype Mobile 位於 PSTN 通話中。 商務用 Skype Mobile 會將通話 (CAA) 升級為會議自動語音應答。  <br/> |通話遭到封鎖，並顯示適當的錯誤訊息。  <br/> |
|商務用 Skype Mobile  <br/> |商務用 Skype 用戶端或同盟使用者  <br/> |用戶端或同盟使用者位於 VoIP 呼叫商務用 Skype Mobile Location-Based 路由使用者，而每一方都升級至 CAA。  <br/> |會封鎖呈報通話，並顯示適當的錯誤訊息。  <br/> |

## <a name="consultative-call-transfers"></a>顧問式來電轉接

除了強制執行 Location-Based 路由傳送至商務用 Skype 會議之外，會議應用程式的 Location-Based 路由，還會強制對 PSTN 端點出口的諮詢來電轉接 Location-Based 路由限制。 「諮詢通話轉移」是兩方間所建立的呼叫，其中一個團體會將來電轉接給新的使用者。 例如，PSTN 端點會呼叫使用者 A (商務用 Skype) 。 使用者 A 判斷 PSTN 使用者應轉寄給使用者 B (商務用 Skype 使用者) 。 使用者 A 通話為 PSTN 使用者保留，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。 使用者 A 將來電轉接至使用者 B。

**諮詢通話轉接通話流程**

![會議圖表的位置基礎路由](../../media/LocationBasedRoutingForConferencing.jpg)

當啟用 Location-Based 路由的使用者啟動對 PSTN 端點的諮詢來電轉接時 (如前面的圖所示) 所示，這會建立兩個使用中的呼叫、PSTN 使用者和商務用 Skype 使用者 A 之間的呼叫，以及商務用 Skype 使用者 a 和商務用 Skype 使用者 B 之間的呼叫。下列行為是由 Location-Based 路由會議應用程式強制執行：

- 若 SIP 主幹路由 PSTN 呼叫已獲授權，可將 PSTN 呼叫重新路由至網路網站（商務用 Skype 使用者 B (亦即，轉接目標) 所在的位置），則會允許通話轉移;否則，將會封鎖「諮詢來電轉接」。 這種授權是根據傳送方的位置，而不是以將使用中通話路由傳送至 PSTN 端點的 SIP 主幹所在的相同網路網站執行。

- 若 SIP 主幹路由輸入 PSTN 來電未獲授權，無法將來電路由傳送至已傳送方 (商務用 Skype 使用者 B) 或轉讓的當事方位於未知的網路網站，則諮詢來電轉接至 PSTN 端點 (亦即會封鎖來電轉接目標) 。

下表說明會議應用程式的 Location-Based 路由傳送限制如何套用 Location-Based 路由限制以進行諮詢來電轉接。 雖然 PBX 端點不會直接與網路產生關聯，但 PBX 的 SIP 主幹可被指派為網路網站。 因此，PBX 端點可以與網路網站間接關聯。


|通話轉移方的網路網站|來電轉接目標的網路網站|行為|
|:-----|:-----|:-----|
|PSTN 端點  <br/> |相同網路網站中的商務用 Skype 使用者 (亦即網站 1)   <br/> |允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |不同網路網站中的商務用 Skype 使用者 (亦即，site 2)   <br/> |不允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |未知網路網站中的商務用 Skype 使用者  <br/> |不允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |同盟商務用 Skype 使用者  <br/> |不允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |同一個網站中的 PBX 端點 (亦即，site 1)   <br/> |允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |不同網站中的 PBX 端點 (亦即，site 2)   <br/> |不允許顧問式轉接  <br/> |
|同一個網站中的 PBX 端點 (亦即，site 1)   <br/> |PSTN 端點  <br/> |允許顧問式轉接  <br/> |
|不同網站中的 PBX 端點 (亦即，site 2)   <br/> |PSTN 端點  <br/> |不允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |相同網路網站中的商務用 Skype 使用者 (亦即網站 1)   <br/> |允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |不同網路網站中的商務用 Skype 使用者 (亦即，site 2)   <br/> |允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |未知網路網站中的商務用 Skype 使用者  <br/> |允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |同盟商務用 Skype 使用者  <br/> |允許顧問式轉接  <br/> |

## <a name="requirements"></a>需求

會議應用程式的 Location-Based 路由，需要在拓撲中的所有 Front-End 集區和 Standard Edition server 上部署商務用 Skype Server 或 Lync Server 2013 累計更新2。 如果這些伺服器版本並未安裝在拓撲中的某些伺服器上，則無法在會議和諮詢來電轉接上充分執行 Location-Based 路由限制。

下表識別伺服器角色與支援 Location-Based 路由的版本的組合。


|Front-End 集區版本|轉送伺服器版本|支援|
|:-----|:-----|:-----|
|商務用 Skype Server 或 Lync Server 2013 累計更新2  <br/> |商務用 Skype Server 或 Lync Server 2013 累計更新2  <br/> |是  <br/> |
|Lync Server 2013 累計更新2  <br/> |Lync Server 2013 累計更新1  <br/> |否  <br/> |
|Lync Server 2013 累計更新2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累計更新2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累計更新1  <br/> |任何  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任何  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任何  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>會議的 Location-Based 路由設定

會議應用程式的 Location-Based 路由取決於 Location-Based 路由的設定。 主要設定如下：

- 加入會議的參與者位置是根據其網路網站來決定。 您必須在商務用 Skype Server 中定義網路網站及其相關聯的網路子網，才能強制執行 Location-Based 路由傳送。

- 若要強制執行 Location-Based 的會議，必須啟用商務用 Skype 參與者才能進行 Location-Based 路由傳送。

- 若要強制執行 Location-Based 路由加入會議，必須針對 Location-Based 路由設定用來連接 PSTN 端點的 SIP 主幹。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>啟用會議的 Location-Based 路由

預設會停用會議應用程式的 Location-Based 路由。 在啟用此應用程式之前，您必須決定指派給應用程式的正確優先順序。 若要決定此優先順序，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

在此 Cmdlet 中， \<Pool FQDN\> 是要啟用會議應用程式之 Location-Based 路由的集區。

此 Cmdlet 會傳回由商務用 Skype Server 所主控的應用程式清單，以及每個應用程式的優先順序值。 會議應用程式的 Location-Based 路由傳送的優先順序值必須大於 "UdcAgent" 應用程式，並小於 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 應用程式。 建議您指派會議應用程式的 Location-Based 路由，其優先順序值比 "UdcAgent" 應用程式的優先順序值高一個點。

例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，則您應該為會議應用程式指派「3」優先順序值的 Location-Based 路由。 這樣做會依照下列順序進行應用程式的優先順序：其他應用程式 (優先順序：0到 1) ，"UdcAgent" (優先順序： 2) ，Location-Based 路由會議應用程式 (優先順序： 3) ，其他應用程式 (優先順序：4到 8) ，"DefaultRouting" (優先順序： 9) ，"ExumRouting" (優先順序： 10) ，OutboundRouting " (Priority： 11) 。

在您為會議應用程式的 Location-Based 路由找到正確的優先順序值後，請針對每個 Front-End 集區或 Standard Edition Server 輸入下列 Cmdlet，以供住宅使用者啟用 Location-Based 路由：

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

例如：

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

使用此 Cmdlet 後，請重新開機集區中的所有前端伺服器或 Standard Edition Server （已啟用會議應用程式的 Location-Based 路由）。

> [!IMPORTANT]
> 在重新開機適用的集區或 Standard Edition Server 中的所有前端伺服器之前，不會強制執行 enforcements 到會議或諮詢傳遞的路由傳送。 Location-Based 如果您對上述 Cmdlet 中 **$true** 設定 **重要**，您的商務用 Skype Server 服務將立即重新開機。 如果您不想要立即重新開機這些服務，請 **將 get-csserverapplication 設定為**[立即 **$false** ]，然後在重新開機服務之後，使用 [**設定**] 變更為 **$true** 之後的 **重要** 事項。

當成功啟用會議應用程式的 Location-Based 路由，並重新啟動所有適用的伺服器後，系統會監控所有啟用 Location-Based 路由的商務用 Skype 使用者所組織的會議，以避免 PSTN 免付費旁路


