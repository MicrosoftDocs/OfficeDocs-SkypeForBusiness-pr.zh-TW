---
title: 商務用 Skype Server 中的會議位置基礎路由
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
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 在商務用 Skype Server Enterprise Voice 中規劃會議的位置基礎路由（包括諮詢通話轉移）。
ms.openlocfilehash: f2a44c1f3275dd0cc9e1205d60ba26e01429ea51
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690579"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>商務用 Skype Server 中的會議位置基礎路由

在商務用 Skype Server Enterprise Voice 中規劃會議的位置基礎路由（包括諮詢通話轉移）。

以位置為基礎的路由可根據通話中各方的位置，限制 VoIP 端點和 PSTN 端點之間通話的路由。 以位置為基礎的會議路由可讓您強制會議上的位置基礎路由規則（即會議），以避免 PSTN 免付費旁路。 應用程式會監視作用中的會議，並根據參與的使用者位置，強制執行以位置為基礎的路由限制。 會議應用程式的位置基礎路由，此外也可將位置基礎路由限制強制加入與 PSTN 端點相關的顧問式轉接。

以位置為基礎的路由會議應用程式為商務用 Skype 會議提供一種防護 PSTN 收費旁路的機制。 應用程式會監控使用中的會議，並根據參與商務用 Skype 使用者的地點，強制執行以位置為基礎的路由限制。

以位置為基礎的路由會議應用程式會在符合下列準則時，決定是否要在商務用 Skype 會議上強制執行位置基礎路由：

- 已啟用會議召集人以進行位置基礎的路由。 以位置為基礎的路由限制，只適用于已啟用位置基礎路由之使用者所組織的會議。

- 至少有一個會議參與者為 PSTN 端點。 以位置為基礎的路由限制只適用于包括 PSTN 端點的會議。

- PSTN 閘道用來將會議加入 PSTN 的網路網站，以及召集人和參與者連線所在的網路網站。

會議應用程式的位置基礎路由，可防止將商務用 Skype 使用者和 PSTN 端點從不同的網路網站加入相同的會議。 如果已啟用會議召集人的位置基礎路由，會議應用程式會強制執行下列限制：

- 可以加入商務用 Skype 會議的端點取決於已加入會議的端點，而且此限制會調整為加入會議的端點，而且會將新的端點加入會議。 如果召集人和參與者從相同的網路網站加入商務用 Skype 會議，則來自相同網路網站的另一位參與者，允許來自不同網路網站或來自未知網路網站之參與者的另一位參與者加入。

- 如果召集人和參與者從不同或未知的網路網站加入會議，則不允許 PSTN 端點加入會議，如果 PSTN 呼叫從啟用位置路由的 SIP 主幹 ingresses。

- 如果召集人和參與者全都從相同的網路網站加入會議，且有參與者加入來自 PSTN 的相同會議，則不允許來自不同網路網站的商務用 Skype 端點加入會議。

下表摘要說明這些會議位置基礎路由限制。

| |

|**在任何指定點的會議中的使用者**|**允許使用者加入會議**|**不允許使用者加入會議**|
|:-----|:-----|:-----|
|商務用 Skype VoIP 用戶端使用者從單一網路網站  <br/> |商務用 Skype VoIP 來自相同網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自不同網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> 從 PSTN 端點加入的使用者  <br/> |無  <br/> |
|商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> |商務用 Skype VoIP 任何網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> |透過 PSTN 端點加入使用者  <br/> |
|商務用 Skype VoIP 來自不同網路網站的用戶端使用者  <br/> |商務用 Skype VoIP 任何網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> |透過 PSTN 端點加入使用者  <br/> |
|商務用 Skype VoIP 用戶端使用者從單一網路網站與從 PSTN 端點加入的使用者  <br/> |商務用 Skype VoIP 來自相同網路網站的用戶端使用者  <br/> |商務用 Skype VoIP 來自不同網路網站的用戶端使用者  <br/> 商務用 Skype VoIP 來自未知網路網站的用戶端使用者  <br/> 同盟商務用 Skype VoIP 用戶端使用者  <br/> |

以下是適用于會議應用程式之位置基礎路由的其他特性：

- 當使用者不允許加入以特定位置為基礎的路由限制的會議時，會議呼叫會遭到拒絕，而商務用 Skype 用戶端將會報告呼叫未完成或已經結束。

- 當端點透過未啟用位置路由的主幹加入會議時，將不會限制加入以位置為基礎之路由 enforcements 之會議的 PSTN 端點。

- 透過 SIP 主幹（透過非出局來電）連接到轉送伺服器的 PBX 系統，將會與商務用 Skype 使用者具有相同的 enforcements，而這些使用者位於與 SIP 主幹定義相同的網路網站中。 例如，PSTN 端點可以加入具有 PBX 使用者的會議，以及商務用 Skype 使用者（如果它們位於相同的網路網站中）; 否則為商務用 Skype 使用者。否則，如果 PBX 使用者與商務用 Skype 使用者位於不同的網路網站，將不允許 PSTN 端點加入會議。

> [!NOTE]
> 使用商務用 Skype 累計更新4時，應遵循下清單格中的行為：

|**使用者**|**其他聚會**|**Action**|**結果**|
|:-----|:-----|:-----|:-----|
|商務用 Skype Mobile  <br/> |Pstn  <br/> |商務用 Skype Mobile 位於 PSTN 通話中。 商務用 Skype Mobile 會將通話升級為會議自動語音應答（CAA）。  <br/> |通話遭到封鎖，並顯示適當的錯誤訊息。  <br/> |
|商務用 Skype Mobile  <br/> |商務用 Skype 用戶端或同盟使用者  <br/> |用戶端或同盟使用者位於商務用 Skype Mobile 位置的 VoIP 呼叫，以及每一方升級至 CAA 的使用者。  <br/> |會封鎖呈報通話，並顯示適當的錯誤訊息。  <br/> |

## <a name="consultative-call-transfers"></a>顧問式來電轉接

除了對商務用 Skype 會議強制進行位置基礎的路由，會議應用程式的位置型路由功能會針對向 PSTN 端點出口的諮詢來電轉接強制進行位置基礎路由限制。 「諮詢通話轉移」是兩方間所建立的呼叫，其中一個團體會將來電轉接給新的使用者。 例如，PSTN 端點會呼叫使用者 A （商務用 Skype 呼叫者）。 使用者 A 判斷 PSTN 使用者應轉寄給使用者 B （商務用 Skype 使用者）。 使用者 A 通話為 PSTN 使用者保留，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。 使用者 A 將來電轉接至使用者 B。

**諮詢通話轉接通話流程**

![會議圖表的位置基礎路由](../../media/LocationBasedRoutingForConferencing.jpg)

當啟用位置基礎路由的使用者啟動 PSTN 端點的諮詢來電轉接時（如上圖所示），這會建立兩個作用中的呼叫、PSTN 使用者和商務用 Skype 使用者 A 之間的呼叫，以及商務用 Skype 使用者 A 和商務用 Skype 使用者 B 之間的呼叫。下列行為是由針對會議應用程式的位置型路由強制執行。:

- 如果您有權將 pstn 通話路由的 SIP 主幹路由，可將 PSTN 呼叫重新路由至網路網站（商務用 Skype 使用者 B （亦即傳輸目標）所在的網站，則會允許通話轉接;否則，將會封鎖「諮詢來電轉接」。 這種授權是根據傳送方的位置，而不是以將使用中通話路由傳送至 PSTN 端點的 SIP 主幹所在的相同網路網站執行。

- 若 SIP 主幹路由輸入 PSTN 呼叫未獲授權，無法將通話路由傳送至已傳送方（商務用 Skype 使用者 B）所在的網站，或傳送方位於未知的網路網站，則會封鎖諮詢來電轉接至 PSTN 端點（例如來電轉接目標）。

下表說明會議應用程式的位置基礎路由限制如何套用位置基礎路由限制，以進行諮詢通話轉移。 雖然 PBX 端點不會直接與網路產生關聯，但 PBX 的 SIP 主幹可被指派為網路網站。 因此，PBX 端點可以與網路網站間接關聯。


|**通話轉移方的網路網站**|**來電轉接目標的網路網站**|**行為**|
|:-----|:-----|:-----|
|PSTN 端點  <br/> |相同網路網站中的商務用 Skype 使用者（亦即網站1）  <br/> |允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |不同網路網站中的商務用 Skype 使用者（亦即網站2）  <br/> |不允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |未知網路網站中的商務用 Skype 使用者  <br/> |不允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |同盟商務用 Skype 使用者  <br/> |不允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |同一個網站中的 PBX 端點（亦即網站1）  <br/> |允許顧問式轉接  <br/> |
|PSTN 端點  <br/> |不同網站中的 PBX 端點（亦即 site 2）  <br/> |不允許顧問式轉接  <br/> |
|同一個網站中的 PBX 端點（亦即網站1）  <br/> |PSTN 端點  <br/> |允許顧問式轉接  <br/> |
|不同網站（亦即 site 2）中的 PBX 端點  <br/> |PSTN 端點  <br/> |不允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |相同網路網站中的商務用 Skype 使用者（亦即網站1）  <br/> |允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |不同網路網站中的商務用 Skype 使用者（亦即網站2）  <br/> |允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |未知網路網站中的商務用 Skype 使用者  <br/> |允許顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |同盟商務用 Skype 使用者  <br/> |允許顧問式轉接  <br/> |

## <a name="requirements"></a>需求

會議應用程式的位置基礎路由需要在拓撲中的所有前端集區和 Standard Edition server 上部署商務用 Skype 伺服器或 Lync Server 2013 累計更新2。 如果這些伺服器版本並未安裝在拓撲中的某些伺服器上，則無法在會議和諮詢來電轉接上充分強制使用以位置為基礎的路由限制。

下表識別伺服器角色與支援位置基礎路由的版本組合。


|**前端集區版本**|**轉送伺服器版本**|**支援**|
|:-----|:-----|:-----|
|商務用 Skype Server 或 Lync Server 2013 累計更新2  <br/> |商務用 Skype Server 或 Lync Server 2013 累計更新2  <br/> |是  <br/> |
|Lync Server 2013 累計更新2  <br/> |Lync Server 2013 累計更新1  <br/> |否  <br/> |
|Lync Server 2013 累計更新2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累計更新2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累計更新1  <br/> |任何  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任何  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任何  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>設定會議的位置基礎路由

會議應用程式的位置基礎路由，取決於位置基礎路由的設定。 主要設定如下：

- 加入會議的參與者位置是根據其網路網站來決定。 您必須在商務用 Skype Server 中定義網路網站及其相關聯的網路子網，才能強制進行位置基礎的路由傳送。

- 若要強制進行會議的位置型路由，必須啟用商務用 Skype 參與者，以進行位置基礎的路由。

- 若要強制執行 PSTN 端點的位置基礎路由加入會議，必須針對位置基礎路由設定用來連接 PSTN 端點的 SIP 主幹。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>啟用會議的位置基礎路由

依預設，會停用會議應用程式的位置型路由。 在啟用此應用程式之前，您必須決定指派給應用程式的正確優先順序。 若要決定此優先順序，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：

Get-CsServerApplication 身分識別服務：註冊機構： <Pool FQDN> 在此 Cmdlet 中， \<Pool FQDN\> 是要啟用會議應用程式之位置型路由的集區。

此 Cmdlet 會傳回由商務用 Skype Server 所主控的應用程式清單，以及每個應用程式的優先順序值。 需要為會議應用程式的位置基礎路由指派優先順序值，而不是 "UdcAgent" 應用程式，而且小於 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 應用程式。 建議您指派會議應用程式的位置型路由，優先順序值為比 "UdcAgent" 應用程式的優先順序值高一個點。

例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，則您應該為會議應用程式指派「3」優先順序值的位置基礎路由。 這樣做會依照下列順序進行應用程式的優先順序：其他應用程式（優先順序：0到1）、"UdcAgent" （Priority：2）、位置基礎路由會議應用程式（優先順序：3）、其他應用程式（優先順序：4到8）、"DefaultRouting" （優先順序：9）、"ExumRouting" （Priority：10）和 "OutboundRouting" （Priority：11）。

找到會議應用程式的位置基礎路由的正確優先順序值後，請為每個前端集區或 Standard Edition Server 輸入下列 Cmdlet，以供住宅使用者進行位置基礎路由的啟用：

New-CsServerApplication 身分識別服務：報名者： `<Pool FQDN`>/lbrouting- \<Application Priority\> 啟用優先順序的 $true 重要 $true Uri<http://www.microsoft.com/LCS/LBRouting>

例如：

New-CsServerApplication 身分識別服務:Registrar:LS2013CU2LBRPool LBRouting-Enabled Priority $true 關鍵型 $true Urihttp://www.microsoft.com/LCS/LBRouting

使用此 Cmdlet 後，請重新開機集區中的所有前端伺服器或 Standard Edition Server （已啟用會議應用程式的位置型路由）。

> [!IMPORTANT]
> 在重新開機適用的集區或 Standard Edition Server 中的所有前端伺服器之前，不會強制執行以位置為基礎的路由 enforcements 至會議或諮詢轉移。 如果您對上述 Cmdlet 中 **$true**設定**重要**，您的商務用 Skype Server 服務將立即重新開機。 如果您不想要立即重新開機這些服務，請**將 get-csserverapplication 設定為**[立即 **$false** ]，然後在重新開機服務之後，使用 [**設定**] 變更為 **$true**之後的**重要**事項。

當成功啟用已成功啟用會議應用程式的位置式路由，且已重新開機所有適用的伺服器後，系統會監控已啟用位置路由之商務用 Skype 使用者所組織的所有會議，以避免 PSTN 免付費旁路


