---
title: 位置型路由 skype 會議的企業伺服器
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
description: 規劃商務 Server Enterprise Voice 的 skype 會議的位置型路由，包括諮詢呼叫傳輸。
ms.openlocfilehash: decfe8117b3b47c5de4db8a7d0963eca587d0da1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42130176"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>位置型路由 skype 會議的企業伺服器

規劃商務 Server Enterprise Voice 的 skype 會議的位置型路由，包括諮詢呼叫傳輸。

位置型的路由可讓您可以限制的 VoIP 端點與位置的呼叫方為基礎的 PSTN 端點之間的通話路由傳送。 位置型會議的路由可讓您在上強制執行位置型的路由規則可防止 PSTN 會議 （亦即會議） 的免付費電話略過。 應用程式監視作用中的會議，並強制執行的位置型路由限制根據使用者參與的位置。 此外，位置型路由會議應用程式可讓諮詢轉接涉及 PSTN 端點以位置為主的路由限制強制執行。

位置型路由會議應用程式提供 skype 商務會議的 PSTN 通話費防護機制略過。 應用程式監視作用中的會議，並強制執行的商務使用者參與 Skype 位置為基礎的位置型路由限制。

位置型路由會議應用程式會決定是否是如果符合下列準則，則會強制執行上 Skype 會議位置型的路由：

- 會議召集人會啟用位置型的路由。 位置型路由限制將會是只套用至由位置型路由已啟用的使用者安排的會議。

- 至少一位會議參與者是 PSTN 端點。 位置型路由限制將僅適用於包含 PSTN 端點的會議。

- 用來橋接至 PSTN 會議的 PSTN 閘道的所在位置以及從何處網際網路連接參與者與召集人的網路站台的網路網站。

位置型路由會議應用程式，可防止商務使用者和來自不同網路網站的 PSTN 端點，才能在同一場會議參與的 Skype。 如果會議的召集人啟用位置型的路由，會議應用程式強制執行下列限制：

- 可加入 Skype 會議的端點取決於已加入會議的端點這項限制會調整以加入的端點離開和新端點加入會議。 如果召集人與參與者加入 Skype 會議從相同的網路網站，然後 PSTN 端點、 從相同網路網站的其他參與者、 從不同的網路網站的其他參與者或未知的網路網站的參與者允許加入。

- 如果召集人與參與者加入會議從不同] 或 [未知的網路網站，不允許加入會議，如果 PSTN 通話 ingresses 從啟用位置型路由的 SIP 主幹的 PSTN 端點。

- 如果召集人與參與者所有加入會議從相同網路網站，且沒有加入相同從 PSTN 會議的參與者，不允許從不同的網路網站的商務端點商務用 Skype 加入會議。

下表摘要說明這些會議位置型路由限制。

| |

|**在任何特定時間點會議中的使用者**|**允許加入會議的使用者**|**不允許加入會議的使用者**|
|:-----|:-----|:-----|
|從單一網路網站的商務 VoIP 用戶端使用者的商務用 Skype  <br/> |Skype 商務 VoIP 用戶端使用者從相同網路網站  <br/> Skype 商務 VoIP 用戶端使用者從不同的網路網站  <br/> Skype 商務 VoIP 用戶端使用者的未知的網路站台  <br/> 同盟的 Skype 商務 VoIP 用戶端使用者  <br/> 使用者加入從 PSTN 端點  <br/> |無  <br/> |
|Skype 商務 VoIP 用戶端使用者的未知的網路站台  <br/> |Skype 商務 VoIP 用戶端使用者從任何網站  <br/> Skype 商務 VoIP 用戶端使用者的未知的站台  <br/> 同盟的 Skype 商務 VoIP 用戶端使用者  <br/> |使用者加入透過 PSTN 端點  <br/> |
|Skype 商務 VoIP 用戶端使用者從不同的網路網站  <br/> |Skype 商務 VoIP 用戶端使用者從任何網路網站  <br/> Skype 商務 VoIP 用戶端使用者的未知的網路站台  <br/> 同盟的 Skype 商務 VoIP 用戶端使用者  <br/> |使用者加入透過 PSTN 端點  <br/> |
|Skype for Business VoIP 從單一網路網站的用戶端使用者和使用者加入從 PSTN 端點  <br/> |Skype 商務 VoIP 用戶端使用者從相同網路網站  <br/> |Skype 商務 VoIP 用戶端使用者從不同的網路網站  <br/> Skype 商務 VoIP 用戶端使用者的未知的網路站台  <br/> 同盟的 Skype 商務 VoIP 用戶端使用者  <br/> |

以下是依位置路由會議應用程式的其他特性：

- 時不允許使用者加入會議，指定位置型路由限制時，會拒絕會議的呼叫而 Skype 商務用戶端將報告，在呼叫未完成，或已經結束。

- 以位置為主的路由 enforcements 會議將不會限制為不論其狀態加入會議，如果將端點加入未啟用位置型路由主幹透過 PSTN 端點加入。

- 透過 SIP 主幹，不會不輸出至 PSTN 通話連線的中繼伺服器的 PBX 系統會有相同的商務使用者以 Skype enforcements 位於相同網路站台定義 SIP 主幹的位置。 例如，PSTN 端點將能夠加入 PBX 使用者與使用者商務用 Skype 會議，如果他們都位於相同的網路網站;否則，將不允許 PSTN 端點，如果 PBX 使用者位於不同的網路站台比 Skype 商務使用者加入會議。

> [!NOTE]
> 與累計更新 4 商務用 Skype，應遵守下列表格中的行為：

|**使用者**|**另一方**|**動作**|**結果**|
|:-----|:-----|:-----|:-----|
|Skype 商務行動電話  <br/> |PSTN  <br/> |Skype 商務行動是 PSTN 通話。 Skype 商務行動然後呈報通話至會議自動語音應答 (CAA)。  <br/> |通話會遭到封鎖，使用適當的錯誤訊息。  <br/> |
|Skype 商務行動電話  <br/> |Skype 商務用戶端或同盟的使用者  <br/> |同盟使用者的用戶端上 Skype Business Mobile Location-Based 路由的使用者，在 VoIP 呼叫，任一廠商逐層向上提報至 CAA。  <br/> |擴大呼叫會遭到封鎖，使用適當的錯誤訊息。  <br/> |

## <a name="consultative-call-transfers"></a>諮詢轉接

除了商務會議，強制執行 skype 位置型路由，位置型路由會議應用程式強制執行諮詢轉接，輸出至 PSTN 端點上的位置型路由限制。 諮詢的來電轉接是兩方的其中一方將通話轉接給新的使用者建立通話。 例如，PSTN 端點撥話給使用者 (Skype for Business 受話者)。 使用者的決定 PSTN 使用者應該轉寄給使用者 B (商務使用者商務用 Skype)。 按下以講話 PSTN 使用者同意 PSTN 使用者保留狀態，並呼叫使用者 B 使用者的呼叫使用者的位置。 使用者的轉接通話上-保留給使用者 b。

**諮詢的呼叫轉接通話流程**

![依位置路由會議圖表](../../media/LocationBasedRoutingForConferencing.jpg)

當使用者啟用位置型路由啟始諮詢來電轉接的 PSTN 端點 （如如上圖所示） 時，這會建立兩個作用中呼叫，一次呼叫之間 PSTN 使用者與 Skype 商務使用者 A，另一個商務用 Skype 之間位置型路由會議應用程式會強制執行商務使用者 A 與 Skype for Business 使用者 b 下列行為：

- 如果呼叫的 SIP 主幹路由 PSTN 重新路由傳送至網站 （亦即轉接的目標） 的 Skype for Business 使用者 B 位於、，然後將允許來電轉接; PSTN 通話授權否則請諮詢的來電轉接會被封鎖。 這項授權會根據傳送的方的位置路由至 PSTN 端點作用中的呼叫的 SIP 主幹與位於相同網路站台正在執行。

- 如果 SIP 主幹路由內送的 PSTN 通話無法將通話路由傳送至網站： 轉移的方 (Skype for Business 使用者 B) 位於或轉接的廠商位於不明的網路網站的權限，然後諮詢通話轉接至PSTN 端點 （亦即來電轉接的目標） 會被封鎖。

下表說明如何以位置為主的路由限制會套用的位置型路由諮詢轉接的會議應用程式。 雖然 PBX 端點不是直接與網路網站相關聯，PBX 連接至 SIP 主幹可被指派的網路網站。 因此，PBX 端點可以間接網路與網站產生關聯。


|**轉接的通話方的網路網站**|**來電轉接的目標的網路網站**|**行為**|
|:-----|:-----|:-----|
|PSTN 端點  <br/> |商務用 Skype 中相同的網路網站 （亦即網站 1） 的商務使用者  <br/> |將允許諮詢轉接  <br/> |
|PSTN 端點  <br/> |商務用 Skype 在不同的網路網站 (亦即 site 2) 中的商務使用者  <br/> |將不允許諮詢轉接  <br/> |
|PSTN 端點  <br/> |商務用 Skype 不明的網路網站中的商務使用者  <br/> |將不允許諮詢轉接  <br/> |
|PSTN 端點  <br/> |同盟的 Skype 商務使用者  <br/> |將不允許諮詢轉接  <br/> |
|PSTN 端點  <br/> |在相同的網站 （亦即網站 1） 的 PBX 端點  <br/> |將允許諮詢轉接  <br/> |
|PSTN 端點  <br/> |在不同的站台 (亦即 site 2) 的 PBX 端點  <br/> |將不允許諮詢轉接  <br/> |
|在相同的網站 （亦即網站 1） 的 PBX 端點  <br/> |PSTN 端點  <br/> |將允許諮詢轉接  <br/> |
|在不同的網站 (亦即 site 2) 的 PBX 端點  <br/> |PSTN 端點  <br/> |將不允許諮詢轉接  <br/> |
|站台中的 PBX 端點  <br/> |商務用 Skype 中相同的網路網站 （亦即網站 1） 的商務使用者  <br/> |將允許諮詢轉接  <br/> |
|站台中的 PBX 端點  <br/> |商務用 Skype 在不同的網路網站 (亦即 site 2) 中的商務使用者  <br/> |將允許諮詢轉接  <br/> |
|站台中的 PBX 端點  <br/> |商務用 Skype 不明的網路網站中的商務使用者  <br/> |將允許諮詢轉接  <br/> |
|站台中的 PBX 端點  <br/> |同盟的 Skype 商務使用者  <br/> |將允許諮詢轉接  <br/> |

## <a name="requirements"></a>需求

應用程式需要 Skype for Business Server 或 Lync Server 2013 累計更新 2年上所有的前端集區和 Standard Edition 伺服器，在您的拓撲中部署的會議位置型的路由。 如果您的拓樸某些伺服器上未安裝這些伺服器版本，位置型路由限制無法完全強制在會議和諮詢呼叫傳輸。

下表列出伺服器角色和支援位置型路由的版本的組合。


|**前端集區版本**|**中繼伺服器版本**|**支援**|
|:-----|:-----|:-----|
|Skype for Business Server 或 Lync Server 2013 累計更新 2  <br/> |Skype for Business Server 或 Lync Server 2013 累計更新 2  <br/> |是  <br/> |
|Lync Server 2013 累計更新 2  <br/> |Lync Server 2013 累計更新 1  <br/> |否  <br/> |
|Lync Server 2013 累計更新 2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累計更新 2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累計更新 1  <br/> |任何  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任何  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任何  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>會議位置型路由組態

位置型路由會議應用程式依賴位置型路由的組態。 主要的設定如下所示：

- 參與者加入會議的位置取決於其網站。 網站和其相關聯的網路子網路必須定義在 Skype for Business Server 以強制執行位置型的路由。

- 若要強制的會議位置型路由，Skype for Business 參與者必須啟用位置型的路由。

- 若要強制位置型路由的加入會議的 PSTN 端點，用來連線的 PSTN 端點 SIP 主幹必須針對位置型的路由。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>啟用電話撥入會議位置型路由

預設會停用應用程式的會議位置型的路由。 之前啟用此應用程式，您必須決定要指派給應用程式的正確優先順序。 若要判斷此優先順序，請執行下列 cmdlet skype for Business Server 管理命令介面：

Get-csserverapplication-Identity Service: Registrar:<Pool FQDN>此指令程式，\<集區 FQDN\>是啟用位置型路由會議應用程式集區。

此 cmdlet 會傳回給個別使用者裝載由 Skype 商務伺服器及優先順序值的應用程式的清單。 位置型路由會議應用程式必須被指派大於 「 UdcAgent 」 應用程式且小於 「 DefaultRouting 」、 「 ExumRouting 」 及 「 OutboundRouting 」 應用程式的優先順序值。 我們建議您指派位置型路由會議應用程式是一個點的優先順序值高於 「 UdcAgent 」 應用程式的優先順序值。

例如，如果 「 UdcAgent 」 應用程式都有優先順序值為"2"，「 DefaultRouting 」 應用程式都有優先順序值為"8"、 「 ExumRouting 」 應用程式都有優先順序值為"9"且 「 OutboundRouting 」 應用程式優先順序值為"10"然後您應該指派位置型路由會議應用程式的優先順序值為"3"。 這樣會將應用程式的優先順序，依下列順序： 其他應用程式 (優先順序： 0 到 1)，「 UdcAgent 」 (優先順序： 2)、 位置型路由會議應用程式 (優先順序： 3)，其他應用程式 (優先順序： 4 到 8)，」DefaultRouting 」 (Priority: 9)，「 ExumRouting 」 (優先順序： 10) 和 「 OutboundRouting 」 (優先順序： 11)。

您尋找正確的優先順序值的位置型路由會議應用程式後，請輸入每個前端集區或 Standard Edition Server 主控的使用者啟用位置型路由的下列 cmdlet:

New-csserverapplication-Identity Service: Registrar:`<Pool FQDN`>/LBRouting-優先順序\<應用程式的優先順序\>-啟用 $true-重要 $true Uri<https://www.microsoft.com/LCS/LBRouting> 

例如：

New-csserverapplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-優先順序 3-啟用的 $true-重要 $true Urihttps://www.microsoft.com/LCS/LBRouting 

使用此 cmdlet 之後, 重新啟動集區或 Standard Edition 伺服器已啟用位置型路由會議應用程式中的所有前端伺服器。

> [!IMPORTANT]
> 會議或諮詢轉接位置型路由 enforcements 不會強制執行直到所有前端伺服器中適用的集區或 Standard Edition 伺服器重新啟動。 如果您設定 **-重要**為 **$true**上述指令程式中，您 Skype for Business Server 服務將會立即重新啟動。 如果您不想要立即重新啟動這些服務，請設定 [ **-重要**以 **$false**現在，，然後使用**組 CsServerApplication**若要變更的 **-重要**為 **$true**更新版本中，已重新啟動服務之後。

一旦成功啟用位置型路由會議應用程式及所有適用的伺服器重新啟動後，將可防止監視召集的所有會議 Skype 商務使用者啟用位置型的路由PSTN 通話費略過


