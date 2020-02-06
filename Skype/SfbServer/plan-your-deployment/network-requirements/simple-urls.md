---
title: 商務用 Skype Server 中簡單 Url 的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在針對商務用 Skype Server 執行 DNS 記錄之前，請先查看本主題中的簡單 URL 考慮。
ms.openlocfilehash: 7eb734fb4a9005f833f27efd3b0d180593155f39
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815781"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>商務用 Skype Server 中簡單 Url 的 DNS 需求

**摘要：** 在針對商務用 Skype 伺服器執行 DNS 記錄之前，請先查看本主題中的簡單 URL 考慮。

簡單的 Url 能讓您的使用者更容易加入會議，以及讓系統管理員更容易取得商務用 Skype Server 管理工具。 簡單的 Url 會使用自己的網域，而不應與您定義的任何 SIP 網域相符。 

商務用 Skype 伺服器支援下列三個簡單的 Url： [開會]、[撥入] 和 [管理員]。您必須設定適用于 [開會及撥入] 的簡單 Url，且 [管理員簡易 URL] 是選擇性的。 您需要支援簡單 Url 的網域名稱系統（DNS）記錄，取決於您如何定義這些簡單的 Url，以及是否要支援簡單 Url 的災害復原。 

## <a name="simple-url-scope"></a>簡單的 URL 範圍

您可以將簡單的 Url 設定為擁有全域範圍，或者您可以為組織中的每個中心網站指定不同的簡單 Url。 如果同時指定全域簡單 URL 和網站簡單的 URL，則網站簡單的 URL 具有優先權。 

在大部分的情況下，建議您只在全域層級設定簡單的 Url，讓使用者的 [符合簡單 URL] 不會隨著從某個網站移至另一個網站而變更。 例外情況是，組織必須在不同的網站上為撥入使用者使用不同的電話號碼。 請注意，如果您在網站上將一個簡單的 URL （例如撥入式簡易 URL）設定為網站層級的簡單 URL，您也必須將該網站上的其他簡單 Url 設定為網站層級。

您可以在拓撲產生器中設定全域簡單的 Url。 若要在網站層級設定簡單的 URL，請使用 CsSimpleURLConfiguration Cmdlet。

定義簡單的 URL 時，也必須在您的 DNS 設定中設定 A 和/或 AAAA 記錄。

## <a name="simple-url-naming-and-validation-rules"></a>簡單的 URL 命名與驗證規則
<a name="BK_Valid"> </a>

[拓撲建立器] 和 [商務用 Skype 伺服器管理 Shell] Cmdlet 會針對您的簡單 Url 強制執行數個驗證規則。 您必須將簡單的 Url 設定為 [符合] 或 [撥入]，但為 [管理員] 設定一個則是選擇性的。 每個 SIP 網域都必須有一個單獨的 [符合簡單 URL]，但您只需要一個簡單的 URL，而且只有一個系統管理員就能為整個組織提供簡單的 URL。

貴組織中的每個簡單 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼（例如，您無法將 SfB2015.contoso.com/Meet 設為您的 [您的內輟] 簡單 url，而 SfB2015.contoso.com/Meet/Dialin 為您的撥入簡易 URL）。 簡單的 URL 名稱不能包含任何一個池的 FQDN，或任何埠資訊（例如， https://FQDN:88/meet不允許）。 所有簡單的 Url 都必須以 HTTPs://首碼開頭。 

簡單的 Url 只能包含字母數位字元（即 a-z、A-Z、0-9 及句號（.）。 如果您使用其他字元，則簡單的 Url 可能無法如期運作。

## <a name="changing-simple-urls-after-deployment"></a>在部署之後變更簡單的 Url
<a name="BK_Valid"> </a>

如果您在初始部署之後變更簡單的 URL，您必須知道變更對您的 DNS 記錄及簡單 Url 的憑證有何影響。 如果簡單 URL 的基底發生變更，則您也必須變更 DNS 記錄和憑證。 例如，從https://SfB2015.contoso.com/Meet SfB2015.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL，因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。 如果您將簡單的 URL 改https://SfB2015.contoso.com/Meet為https://SfB2015.contoso.com/Meetings[寄件者]，則 SFB2015.CONTOSO.COM 的基底 url 會保持不變，因此不需要變更 DNS 或憑證。

不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行**Enable-CsComputer** ，以登錄變更。

## <a name="naming-examples-for-simple-urls"></a>簡單 Url 的命名範例
<a name="BK_Valid"> </a>

有三個建議選項可用於命名您的簡單 Url。 您選擇的選項會對您設定 DNS A 記錄的方式，以及支援簡易 Url 的憑證有何影響。 在每個選項中，您必須針對組織中的每個 SIP 網域設定一個 [符合簡單 URL]。 

您永遠只需要在整個組織中使用一個簡單的 URL 進行撥入，另一個用於管理員，不論您有多少 SIP 網域。

在選項1中，您為每個簡單的 URL 建立新的 SIP 功能變數名稱。

如果您使用這個選項，則每個簡單的 URL 都需要一個單獨的 DNS A 記錄，而且每個符合簡單 URL 的名稱都必須在您的憑證中命名。

**簡單 URL 命名選項1**


| **簡單的 URL** <br/> | **範例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| 符合  <br/>          | https://meet.contoso.comhttps://meet.fabrikam.com等等（針對貴組織中的每個 SIP 網域一個）  <br/> |
| 撥入  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 管理員  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

有了選項2，簡單的 Url 就會以功能變數名稱 SfB2015.contoso.com 為基礎。 因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 Url。 這個 DNS A 記錄參照 SfB2015.contoso.com。 此外，貴組織中的其他 SIP 網域，您仍然需要獨立的 DNS A 記錄。 

**簡單 URL 命名選項2**


| **簡單的 URL** <br/> | **範例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 符合  <br/>          | https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet等等（針對貴組織中的每個 SIP 網域一個）  <br/> |
| 撥入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 管理員  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

如果您有多個 SIP 網域，而您想要將它們放在不同的基本 Url 中，但想要將這些簡單 Url 的 DNS 記錄與證書需求降至最低，選項3是最實用的。 

**簡單 URL 命名選項3**


| **簡單的 URL** <br/> | **範例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| 符合  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| 撥入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 管理員  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>簡單 Url 的災害復原選項
<a name="BK_Valid"> </a>

如果您有多個包含前端池的網站，而且您的 DNS 提供者支援 GeoDNS，您可以針對簡單的 Url 設定您的 DNS 記錄，以支援災害復原，因此即使一個完整的前端池已停止，簡單的 URL 功能仍會繼續。 這個災害復原功能支援 [開會] 和 [撥入] 簡單的 Url。

若要設定這一點，請建立兩個 GeoDNS 位址。 每個位址都有兩個 DNS A 或 CNAME 記錄，可解析成成對組成的兩個池以進行災害復原。 一個 GeoDNS 位址用於內部存取，並解析為兩個池的內部網路 FQDN 或負載平衡器 IP 位址。 其他 GeoDNS 位址是用於外部存取，並解析為兩個池的外部 web FQDN 或負載平衡器 IP 位址。 下列是使用池之 Fqdn 的 [符合簡單 URL] 的範例。 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

然後建立可將您的符合簡單 URL （例如 meet.contoso.com）解析成兩個 GeoDNS 位址的 CNAME 記錄。

> [!NOTE]
> 如果您的網路使用的是 hairpinning （透過外部連結路由所有簡單的 URL 流量，包括來自貴組織內部的流量），則您只需設定外部 GeoDNS 位址，並將您的 [符合簡單 URL] 解析為僅限外部地址。

當您使用此方法時，您可以設定每個 GeoDNS 位址，以使用迴圈複用方法將要求發佈到兩個池，或主要連線到一個池（例如位於地理位置較近的池中），並使用其他池（例如連接失敗。 

您可以針對撥入簡易 URL 設定相同的配置。 若要這樣做，請建立如先前範例中的其他記錄， `dialin`並`meet`在 DNS 記錄中取代。 針對系統管理員簡易 URL，請使用本節前面所列的三個選項之一。

設定此設定之後，您必須使用監視應用程式來設定 HTTP 監視來監視失敗。 如果是外部存取，請在 [顯示器] 上確認 HTTPS： lyncdiscover。<sipdomain> 兩個池的外部 web FQDN 或負載平衡器 IP 位址要求成功。 例如，下列要求不能包含任何**ACCEPT**標頭，而且必須傳回**200 OK**。

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

針對內部存取，您必須在兩個池的內部網路 FQDN 或負載平衡器 IP 位址上，監視埠5061。 如果偵測到任何連線失敗，這些池的 VIP 必須關閉埠80、443和4443。


