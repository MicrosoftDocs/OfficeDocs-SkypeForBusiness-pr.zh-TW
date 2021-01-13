---
title: 商務用 Skype Server 中簡易 URLs 的 DNS 需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在為商務用 Skype Server 實施 DNS 記錄之前，請參閱本主題中的簡易 URL 考慮。
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834583"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>商務用 Skype Server 中簡易 URLs 的 DNS 需求

**摘要：** 在為商務用 Skype Server 實施 DNS 記錄之前，請參閱本主題中的簡易 URL 考慮。

簡單 URLs 使您的使用者加入會議變得更容易，並讓系統管理員更輕鬆取得商務用 Skype Server 的系統管理工具。 簡易 URLs 會使用自己的網域，而不能比對任何您定義的 SIP 網域。 

商務用 Skype 伺服器支援下列三個簡單 URLs：「開會」、「Dial-In」和「系統管理」。您必須設定「符合」和「Dial-In」的簡易 URLs，且 Admin 簡易 URL 是選用的。 需要用來支援簡單 URL 的網域名稱系統 (DNS) 記錄，視您定義這些簡單 URL 的方式而定，以及是否要支援簡單 URL 的災害復原。 

## <a name="simple-url-scope"></a>簡單 URL 範圍

您可以將您的簡易 URLs 設定為具有全域範圍，也可以為組織中的每個中央網站指定不同的簡單 URLs。 如果同時指定全域簡單 URL 和網站簡易 url，則網站簡易 URL 具有優先權。 

在大多數情況下，我們建議您只在全域層級設定簡單 URLs，如此一來，如果使用者的符合簡易 URL 從一個網站移動到另一個網站，就不會變更。 例外狀況是組織必須針對不同網站上的撥入使用者使用不同的電話號碼。 請注意，如果您設定一個簡易 URL (例如，將網站上的撥入簡易 URL) 設定為網站層級的簡易 URL，您也必須將該網站上的其他簡單 URLs 也設定為網站層級。

您可以在拓撲產生器中設定全域簡單的 URLs。 若要在網站層級設定簡單 URL，請使用 Set-CsSimpleURLConfiguration Cmdlet。

定義簡單 URL 時，也需要在您的 DNS 設定中設定 A 和/或 AAAA 記錄。

## <a name="simple-url-naming-and-validation-rules"></a>簡單 URL 命名和驗證規則
<a name="BK_Valid"> </a>

拓撲產生器和商務用 Skype Server 管理命令介面指令程式會針對您的簡易 URLs 執行數種驗證規則。 您必須為符合和撥入設定簡單的 URLs，但為 Admin 設定一個是選用的。 每個 SIP 網域都必須有個別的符合簡單 URL，但是您只需要一個撥入簡易 URL 和一個系統管理員簡易 URL 給整個組織。

組織中的每個簡易 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼 (例如，您無法將 SfB2015.contoso.com/Meet 設定為您的 [SfB2015.contoso.com/Meet/Dialin] 簡單 url，而為您的撥入簡易 URL) 。 簡單 URL 名稱不能包含任何集區的 FQDN，或任何埠資訊 (例如， https://FQDN:88/meet 不允許) 。 所有的簡單 URLs 都必須以 HTTPs://前置詞開頭。 

簡單 URLs 只能包含字母數位字元 (即 a-z、A-Z、0-9 和句點 (。 ) 。 如果您使用其他字元，則簡單 URLs 可能無法如預期那樣運作。

## <a name="changing-simple-urls-after-deployment"></a>在部署後變更簡單 URLs
<a name="BK_Valid"> </a>

如果您在初始部署後變更簡單 URL，您必須注意變更會如何影響您的 DNS 記錄和憑證以取得簡易 URLs。 如果簡單 URL 的基底變更，您也必須變更 DNS 記錄和憑證。 例如，從 SfB2015.contoso.com 變更 https://SfB2015.contoso.com/Meet 為 https://meet.contoso.com meet.contoso.com 時，您必須變更 DNS 記錄和憑證，以參照 meet.contoso.com。 如果您已將簡易 URL 變更 https://SfB2015.contoso.com/Meet 為 https://SfB2015.contoso.com/Meetings ，SfB2015.contoso.com 的基底 url 會保持不變，因此不需要任何 DNS 或憑證變更。

不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 **Enable-CsComputer** ，以註冊變更。

## <a name="naming-examples-for-simple-urls"></a>簡單 URLs 的命名範例
<a name="BK_Valid"> </a>

有三個建議選項可用於命名您的簡易 URLs。 您選擇的哪個選項會影響您設定 DNS A 記錄的方式，以及支援簡易 URLs 的憑證。 在每個選項中，您必須為組織中的每個 SIP 網域設定一個符合簡易 URL 的功能。 

在整個組織中，您永遠只需要一個簡易 URL，以進行撥入，一個用於管理，不論您有多少 SIP 網域。

在選項1中，您可以為每個簡單 URL 建立新的 SIP 功能變數名稱。

如果您使用此選項，則每個簡單 URL 都必須有個別的 DNS A 記錄，而且每個符合簡易 URL 的憑證皆必須在您的憑證中命名。

**簡單 URL 命名選項1**


| **簡單 URL** <br/> | **範例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| 滿足  <br/>          | https://meet.contoso.com、等等 https://meet.fabrikam.com 等等 (組織中的每個 SIP 網域)   <br/> |
| 撥入  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 系統管理員  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

使用選項2，簡單 URLs 是以功能變數名稱 SfB2015.contoso.com 為基礎。 因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 URLs。 此 DNS A 記錄參照 SfB2015.contoso.com。 此外，您的組織中的其他 SIP 網域仍然需要不同的 DNS A 記錄。 

**簡單 URL 命名選項2**


| **簡單 URL** <br/> | **範例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 滿足  <br/>          | https://SfB2015.contoso.com/Meet、等等 https://SfB2015.fabrikam.com/Meet 等等 (組織中的每個 SIP 網域)   <br/> |
| 撥入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 系統管理員  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

如果您有多個 SIP 網域，而您想要讓其具有個別的符合簡易 URLs，但想要將這些簡易 URLs 的 DNS 記錄和憑證需求降至最低，則選項3最為有用。 

**簡單 URL 命名選項3**


| **簡單 URL** <br/> | **範例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| 滿足  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| 撥入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 系統管理員  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>簡易 URLs 的嚴重損壞修復選項
<a name="BK_Valid"> </a>

如果您有多個網站包含前端集區，而您的 DNS 提供者支援 GeoDNS，您可以設定您的 DNS 記錄以進行簡單的 URLs 以支援嚴重損壞修復，這樣一來，即使一部整個前端集區已停機，也能繼續簡易 URL 功能。 此災害復原功能支援 Meet 及 Dial-In 簡單 URL。

如要如此設定，請建立兩個 GeoDNS 位址。每個位址都包含兩個 DNS A 或 CNAME 記錄，這兩個記錄會解析為針對災害復原目的而配對的兩個集區。一個 GeoDNS 位址用於內部存取，並解析為該兩個集區的內部 Web FQDN 或負載平衡器 IP 位址。另一個 GeoDNS 位址用於外部存取，並解析為該兩個集區的外部 Web FQDN 或負載平衡器 IP 位址。下列範例針對 Meet 簡單 URL，並使用集區的 FQDN。 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

然後建立 CNAME 記錄，其中會將 Meet 簡單 URL (例如 meet.contoso.com) 解析為兩個 GeoDNS 位址。

> [!NOTE]
> 如果網路使用「髮夾」 (將所有簡單 URL 流量透過外部連結路由，包括來自組織內的流量)，則可僅設定外部 GeoDNS 位址，並將 Meet 簡單 URL 僅解析為該外部位址。

使用此方法時，可設定每個 GeoDNS 位址使用循環配置資源方法來散發要求至兩個集區，或者主要連線至一個集區 (例如地理位置上較近的集區)，然後僅在連線失敗時才使用另一個集區。 

針對 Dial-In 簡單 URL 也可以設定相同的組態。 若要這麼做，請建立如先前範例中的其他記錄，並以  `dialin` `meet` DNS 記錄取代。 針對 Admin 簡單 URL，請使用本節中先前列出的三個選項。

此組態一旦設定，就必須使用監控應用程式，設定 HTTP 監控以監看失敗。 若要進行外部存取，請確定 HTTPS 取得 lyncdiscover。<sipdomain> 兩個集區的外部 web FQDN 或負載平衡器 IP 位址要求都成功。 例如，下列要求不得包含任何 **ACCEPT** 標頭且必須傳回 **200 OK**。

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

針對內部存取，則必須監控該兩個集區之內部 Web FQDN 或負載平衡器 IP 位址的連接埠 5061。 如果偵測到任何連線失敗，這些集區的 VIP 必須關閉埠80、443及4443。


