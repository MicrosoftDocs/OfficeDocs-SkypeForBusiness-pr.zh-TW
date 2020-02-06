---
title: 商務用 Skype Server 中的會議位置式路由
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
description: 規劃商務用 Skype Server Enterprise Voice 中以位置為基礎的路由，包括諮詢式通話轉移。
ms.openlocfilehash: d03bab835556bf0cea4dffb33bcfbcc48ba7fa42
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802843"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>商務用 Skype Server 中的會議位置式路由

規劃商務用 Skype Server Enterprise Voice 中以位置為基礎的路由，包括諮詢式通話轉移。

以位置為基礎的路由可以根據通話中各方的位置，限制 VoIP 端點與 PSTN 端點之間的通話路由。 [以位置為基礎的會議路由] 可讓您在會議（亦即會議）上強制執行以位置為基礎的路由規則，以避免 PSTN 免付費旁路。 應用程式會監視作用中的會議，並根據參與的使用者位置強制執行以位置為基礎的路由限制。 [以位置為基礎的會議應用程式路由] 可讓您將以位置為基礎的路由限制實施到涉及 PSTN 端點的諮詢式轉移。

以位置為基礎的路由會議應用程式為商務用 Skype 會議提供一種防範 PSTN 免付費旁路的機制。 應用程式會監視作用中的會議，並根據參與的商務用 Skype 使用者的位置，強制執行以位置為基礎的路由限制。

如果符合下列條件，則以位置為基礎的路由會議應用程式決定是否要在商務用 Skype 會議上強制執行基於位置的路由：

- 會議召集人已啟用位置路由。 以位置為基礎的路由限制將只會套用至啟用位置式路由的使用者所組織的會議。

- 至少有一個會議參與者是 PSTN 端點。 以位置為基礎的路由限制只適用于包含 PSTN 端點的會議。

- PSTN 閘道用來將會議橋接至 PSTN 的網路網站，以及召集人與參與者的連線位置所在的網路網站。

會議應用程式的位置式路由可防止將商務用 Skype 使用者和 PSTN 端點從不同的網路網站加入相同的會議。 如果啟用會議召集人進行位置式路由，會議應用程式會強制執行下列限制：

- 可以加入商務用 Skype 會議的端點，取決於已加入會議的端點，而且這個限制會依連接端點離開，而新端點則會加入會議。 如果召集人與參與者是從相同的網路網站加入商務用 Skype 會議，則是 PSTN 端點，另一個參與者來自相同的網路網站，另一個參與者來自于來自未知網路網站的參與者[允許加入]。

- 如果召集人和參與者是從不同或未知的網路網站加入會議，但如果 PSTN 呼叫 ingresses 來自 SIP 主幹系，且已啟用位置路由，則不允許 PSTN 端點加入會議。

- 如果召集人與參與者都是從相同的網路網站加入會議，且有參與者加入來自 PSTN 的同一個會議，則不允許來自不同網路網站的商務用 Skype 端點加入會議。

下表摘要列出了這些會議位置的路由限制。

| |

|**在任何指定點的會議中的使用者**|**允許使用者加入會議**|**不允許使用者加入會議**|
|:-----|:-----|:-----|
|單一網路網站上的商務用 Skype VoIP 用戶端使用者  <br/> |同一網路網站上的商務用 Skype VoIP 用戶端使用者  <br/> 來自不同網路網站的商務用 Skype VoIP 用戶端使用者  <br/> 來自未知網路網站的商務用 Skype VoIP 用戶端使用者  <br/> 聯盟商務用 Skype VoIP 用戶端使用者  <br/> 從 PSTN 端點加入的使用者  <br/> |無  <br/> |
|來自未知網路網站的商務用 Skype VoIP 用戶端使用者  <br/> |來自任何網站的商務用 Skype VoIP 用戶端使用者  <br/> 來自未知網站的商務用 Skype VoIP 用戶端使用者  <br/> 聯盟商務用 Skype VoIP 用戶端使用者  <br/> |透過 PSTN 端點加入的使用者  <br/> |
|來自不同網路網站的商務用 Skype VoIP 用戶端使用者  <br/> |來自任何網路網站的商務用 Skype VoIP 用戶端使用者  <br/> 來自未知網路網站的商務用 Skype VoIP 用戶端使用者  <br/> 聯盟商務用 Skype VoIP 用戶端使用者  <br/> |透過 PSTN 端點加入的使用者  <br/> |
|從單一網路網站和從 PSTN 端點加入的使用者的商務用 Skype VoIP 用戶端使用者  <br/> |同一網路網站上的商務用 Skype VoIP 用戶端使用者  <br/> |來自不同網路網站的商務用 Skype VoIP 用戶端使用者  <br/> 來自未知網路網站的商務用 Skype VoIP 用戶端使用者  <br/> 聯盟商務用 Skype VoIP 用戶端使用者  <br/> |

以下是適用于會議應用程式之位置路由的其他特性：

- 如果使用者不允許加入會議指定的位置路由限制，會議呼叫將遭到拒絕，而商務用 Skype 用戶端將會報告通話未完成或已結束。

- 使用以位置為基礎的路由 enforcements 加入會議的 PSTN 端點不會限制加入會議，無論端點是透過不是以位置式路由的幹線來連接。

- 透過不是出局撥出呼叫的 SIP 幹線連線到中繼伺服器的 PBX 系統，將會有與商務用 Skype 使用者相同的 enforcements，這些使用者位於已定義 SIP 幹線的同一個網路網站中。 例如，PSTN 端點可以使用 PBX 使用者與商務用 Skype 使用者（如果它們位於相同的網路網站上）加入會議;否則，如果 PBX 使用者與商務用 Skype 使用者位於不同的網路網站，則不允許 PSTN 端點加入會議。

> [!NOTE]
> 在商務用 Skype 累計更新4中，應遵循下清單格中的行為：

|**使用者**|**其他聚會**|**動作**|**所得**|
|:-----|:-----|:-----|:-----|
|商務用 Skype Mobile  <br/> |PSTN  <br/> |商務用 Skype Mobile 位於 PSTN 通話中。 商務用 Skype 行動裝置會將通話升級至會議自動語音應答（CAA）。  <br/> |通話遭到封鎖，並提供適當的錯誤訊息。  <br/> |
|商務用 Skype Mobile  <br/> |商務用 Skype 用戶端或同盟使用者  <br/> |用戶端或同盟使用者位於商務用 Skype Mobile 位置的 VoIP 通話中，且其中一個參與方升級至 CAA。  <br/> |會封鎖升級通話，並提供適當的錯誤訊息。  <br/> |

## <a name="consultative-call-transfers"></a>諮詢式通話轉移

除了強制將位置路由到商務用 Skype 會議之外，會議應用程式的位置路由在諮詢通話中強制執行以位置為基礎的路由限制，可將出局傳送到 PSTN 端點。 「諮詢式來電轉接」是雙方在其中一方傳送呼叫給新使用者的兩方之間所建立的通話。 例如，PSTN 端點會呼叫使用者 A （商務用 Skype 呼叫者）。 使用者 A 決定應將 PSTN 使用者轉寄到使用者 B （商務用 Skype 使用者）。 使用者 A 將呼叫與 PSTN 使用者保留通話，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。 使用者 A 將來電轉接到使用者 B。

**諮詢式通話轉移通話流程**

![會議圖表的以位置為基礎的路由](../../media/LocationBasedRoutingForConferencing.jpg)

當使用者啟用以位置為基礎的路由，啟動 PSTN 端點的諮詢式來電轉接時（如上圖所示），這會建立兩個作用中的通話、PSTN 使用者與商務用 Skype 使用者 A 之間的通話，以及 Skype 中的另一個通話商務使用者 A 和商務用 Skype 使用者 B。下列行為是由針對會議應用程式的位置式路由所強制執行的：

- 如果 SIP 中繼路由 PSTN 呼叫已獲授權，可以將 PSTN 呼叫重新路由到商務用 Skype 使用者 B （亦即，傳送目標）所在的網路網站，則允許來電轉接;否則，將會封鎖諮詢式來電轉接。 這項授權是依據已傳送的參與方的位置，而不是將作用中的呼叫路由至 PSTN 端點的 SIP 主幹來執行。

- 如果 SIP 中繼路由未獲授權將呼叫路由至傳送方（商務用 Skype 使用者 B）所在的網路網站，或轉移的參與方位於未知的網路網站中，請諮詢來電轉接至PSTN 端點（亦即來電轉接目標）將會被封鎖。

下表說明如何針對針對諮詢式來電轉接的會議應用程式以位置為基礎的路由限制套用位置式路由限制。 雖然 PBX 端點並不與網路網站直接關聯，但 PBX 的 SIP 幹線已連接至可指派網路網站。 因此，PBX 端點可以與網路網站間接關聯。


|**來電轉接方的網路網站**|**來電轉接目標的網路網站**|**行為**|
|:-----|:-----|:-----|
|PSTN 端點  <br/> |同一網路網站中的商務用 Skype 使用者（亦即網站1）  <br/> |允許使用顧問式轉接  <br/> |
|PSTN 端點  <br/> |不同網路網站中的商務用 Skype 使用者（亦即 site 2）  <br/> |不允許使用顧問式轉接  <br/> |
|PSTN 端點  <br/> |未知網路網站中的商務用 Skype 使用者  <br/> |不允許使用顧問式轉接  <br/> |
|PSTN 端點  <br/> |聯盟商務用 Skype 使用者  <br/> |不允許使用顧問式轉接  <br/> |
|PSTN 端點  <br/> |同一網站中的 PBX 端點（亦即 site 1）  <br/> |允許使用顧問式轉接  <br/> |
|PSTN 端點  <br/> |不同網站中的 PBX 端點（亦即 site 2）  <br/> |不允許使用顧問式轉接  <br/> |
|同一網站中的 PBX 端點（亦即 site 1）  <br/> |PSTN 端點  <br/> |允許使用顧問式轉接  <br/> |
|不同網站中的 PBX 端點（亦即 site 2）  <br/> |PSTN 端點  <br/> |不允許使用顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |同一網路網站中的商務用 Skype 使用者（亦即網站1）  <br/> |允許使用顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |不同網路網站中的商務用 Skype 使用者（亦即 site 2）  <br/> |允許使用顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |未知網路網站中的商務用 Skype 使用者  <br/> |允許使用顧問式轉接  <br/> |
|任何網站中的 PBX 端點  <br/> |聯盟商務用 Skype 使用者  <br/> |允許使用顧問式轉接  <br/> |

## <a name="requirements"></a>需求

[以位置為基礎的會議] 應用程式必須在拓撲中的所有前端池和標準版伺服器上部署 [商務用 Skype Server] 或 [Lync Server 2013 累計更新 2]。 如果您在拓撲中的部分伺服器上沒有安裝這些伺服器版本，則無法在會議和諮詢式通話轉移上完全強制執行以位置為基礎的路由限制。

下表列出支援位置路由的伺服器角色與版本組合。


|**前端池版本**|**中繼伺服器版本**|**受**|
|:-----|:-----|:-----|
|商務用 Skype Server 或 Lync Server 2013 累計更新2  <br/> |商務用 Skype Server 或 Lync Server 2013 累計更新2  <br/> |是  <br/> |
|Lync Server 2013 累計更新2  <br/> |Lync Server 2013 累計更新1  <br/> |否  <br/> |
|Lync Server 2013 累計更新2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累計更新2  <br/> |Office 通訊伺服器 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累計更新1  <br/> |每  <br/> |否  <br/> |
|Lync Server 2010  <br/> |每  <br/> |否  <br/> |
|Office 通訊伺服器 2007 R2  <br/> |每  <br/> |否  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>針對會議進行位置式路由的設定

會議應用程式的位置路由，取決於以位置為基礎的路由配置。 主要配置如下所示：

- 加入會議的參與者位置是根據其網路網站來決定。 您必須在商務用 Skype Server 中定義網路網站及其關聯的網路子網，才能強制執行位置路由。

- 若要強制進行依位置路由的會議，必須為商務用 Skype 參與者啟用位置路由。

- 若要強制對 PSTN 端點的位置路由加入會議，必須針對以位置為基礎的路由設定用來連接 PSTN 端點的 SIP 幹線。

## <a name="enabling-the-location-based-routing-for-conferencing"></a>啟用會議的位置路由

依預設停用會議應用程式的位置式路由。 啟用此應用程式之前，您必須先決定指派給應用程式的正確優先順序。 若要判斷這個優先順序，請在商務用 Skype Server Management Shell 中執行下列 Cmdlet：

CsServerApplication 身分識別服務：註冊機構：<Pool FQDN>在這個 Cmdlet 中， \<[池\> FQDN] 是在其中啟用會議應用程式之位置式路由的池。

這個 Cmdlet 會傳回商務用 Skype Server 託管的應用程式清單，以及每個應用程式的優先順序值。 需要將 [UdcAgent] 應用程式的 [位置] 路由，指派優先順序值大於 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 應用程式。 我們建議您指派會議應用程式的位置路由，此優先順序值比「UdcAgent」應用程式的優先順序值高1點。

例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，則您應該為會議應用程式指派以位置為基礎的路由，優先順序值為 "3"。 如此一來，就會按照下列順序來放置應用程式的優先順序：其他應用程式（優先順序：0到1）、"UdcAgent" （優先順序：2）、以位置為基礎的路由會議應用程式（優先順序：4到8），"DefaultRouting "（Priority：9），" ExumRouting "（優先順序：10）和" OutboundRouting "（優先順序：11）。

在您找到適用于 [會議] 應用程式的位置式路由的正確優先順序值之後，請針對每個主機使用者啟用位置路由的 [前端] 池或標準版伺服器輸入下列 Cmdlet：

新-CsServerApplication 身分識別服務：註冊機構`<Pool FQDN` ：>/Lbrouting- \<優先順序應用\>程式優先順序-已啟用 $true 關鍵型 $true Uri<http://www.microsoft.com/LCS/LBRouting> 

例如：

新的-CsServerApplication 身分識別服務:Registrar:LS2013CU2LBRPool/LBRouting 優先順序 3-啟用的 $true-關鍵性 $true Urihttp://www.microsoft.com/LCS/LBRouting 

使用這個 Cmdlet 之後，請重新開機該資源庫中的所有前端伺服器或標準版伺服器（在其中已啟用以位置為基礎的會議應用程式）。

> [!IMPORTANT]
> 在重新開機適用的池中的所有前端伺服器或標準版伺服器之後，才會強制執行針對會議或顧問式傳送的位置式路由 enforcements。 如果您設定為在前面的 Cmdlet 中 **$true** ，您的商務用 Skype Server**服務將會**立即重新開機。 如果您不想要讓這些服務立即重新開機，請 **$false**將 CsServerApplication 設定為 [立即]，然後在重新開機服務**** 之後，使用 [**設定** **] 變更為** **$true** 。

一旦已成功啟用並重新啟動會議應用程式的位置式路由，且已重新開機所有適用的伺服器之後，系統就會監視所有啟用了以位置路由的商務用 Skype 使用者組織的會議，以防PSTN 免付費旁路


