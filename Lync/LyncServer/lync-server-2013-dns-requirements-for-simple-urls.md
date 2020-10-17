---
title: Lync Server 2013：簡易 URLs 的 DNS 需求
description: Lync Server 2013：簡易 URLs 的 DNS 需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564959"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 中簡易 URLs 的 DNS 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

Lync Server 2013 支援簡單的 URLs，讓使用者加入會議變得更容易，並讓系統管理員更輕鬆取得 Lync Server 系統管理工具。 如需簡單 URLs 的詳細資訊，請參閱 [在 Lync Server 2013 中規劃簡易 URLs](lync-server-2013-planning-for-simple-urls.md)。

Lync Server 支援下列三個簡單 URLs：「開會」、「Dial-In」和「系統管理」。您必須設定「符合」和「Dial-In」的簡易 URLs，且 Admin 簡易 URL 是選用的。 需要用來支援簡單 URL 的網域名稱系統 (DNS) 記錄，視您定義這些簡單 URL 的方式而定，以及是否要支援簡單 URL 的災害復原。

<div>

## <a name="simple-url-option-1"></a>簡單 URL 選項 1

在選項 1 中，您為每個簡單 URL 各建立一個新的基底 URL。

<div class="">


> [!NOTE]  
> 當使用者按一下簡單 URL 會議連結時，DNS A 記錄解析為的伺服器會判斷要啟動的正確用戶端軟體。用戶端軟體啟動後，便會自動與裝載會議的集區進行通訊。透過這個方式，無論簡單 URL DNS A 記錄是解析為哪個伺服器或集區，都會將使用者導向至包含會議內容的正確伺服器。



</div>

### <a name="simple-url-option-1"></a>簡單 URL 選項 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡單 URL</strong></p></td>
<td><p><strong>範例</strong></p></td>
</tr>
<tr class="even">
<td><p>滿足</p></td>
<td><p>https://meet.contoso.com、等等 https://meet.fabrikam.com 等等 (組織中的每個 SIP 網域) </p></td>
</tr>
<tr class="odd">
<td><p>撥入</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>系統管理員</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


如果使用選項 1，您必須定義下列項目：

  - 對於每個 Meet 簡單 URL，如果您已部署 Director，則需要有一筆 DNS A 記錄，並讓其將 URL 解析為 Director 的 IP 位址。否則，即應解析為前端集區的負載平衡器的 IP 位址。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。
    
    如果組織中有多個 SIP 網域而您使用此選項，您必須為每個 SIP 網域建立 Meet 簡單 URL，且每個 Meet 簡單 URL 各需有一筆 DNS A 記錄。 例如，如果您同時有 contoso.com 和 fabrikam.com，您會同時為和建立 DNS A 記錄 https://meet.contoso.com https://meet.fabrikam.com 。
    
    或者，如果您有多個 SIP 網域且想減少這些簡單 URL 的 DNS 記錄和憑證需求，請使用本主題稍後所述的選項 3。

  - 對於 Dial-in 簡單 URL，如果您已部署 Director，則需要有一筆 DNS A 記錄，並讓其將 URL 解析為 Director 的 IP 位址。否則，即應解析為前端集區的負載平衡器的 IP 位址。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。

  - Admin 簡單 URL 僅限內部使用。如果您已部署 Director，則需要有一筆 DNS A 記錄，並讓其將 URL 解析為 Director 的 IP 位址。否則，即應解析為前端集區的負載平衡器的 IP 位址。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。

</div>

<div>

## <a name="simple-url-option-2"></a>簡單 URL 選項 2

在選項 2 中，Meet、Dial-in 和 Admin 簡單 URL 全都使用同一個基底 URL，例如 lync.contoso.com。因此，這些簡單 URL 只需要有一筆 DNS A 記錄，並讓其將 lync.contoso.com 解析為 Director 集區或前端集區的 IP 位址即可。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。

請注意，如果組織中有多個 SIP 網域，您仍必須為每個 SIP 網域建立 Meet 簡單 URL，且每個 Meet 簡單 URL 各需有一筆 DNS A 記錄。 在此範例中，除了有三個全都以 lync.contoso.com 為基礎的簡單 URL 外，還有一個針對 fabrikam.com 所設定，使用不同基底 URL 的 Meet 簡單 URL。 在此範例中，您必須建立和的 DNS A https://lync.contoso.com 記錄 https://lync.fabrikam.com 。 簡單 URL 選項 3 顯示當有多個 SIP 網域時，另一個處理命名和 DNS A 記錄的方式。

### <a name="simple-url-option-2"></a>簡單 URL 選項 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡單 URL</strong></p></td>
<td><p><strong>範例</strong></p></td>
</tr>
<tr class="even">
<td><p>滿足</p></td>
<td><p>https://lync.contoso.com/Meet、等等 https://lync.fabrikam.com/Meet 等等 (組織中的每個 SIP 網域) </p></td>
</tr>
<tr class="odd">
<td><p>撥入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>系統管理員</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>簡單 URL 選項 3

如果您有許多 SIP 網域，且想要每個網域各有不同的簡單 URL，但想要減少這些簡單 URL 的 DNS 記錄和憑證需求，則採用選項 3 最適合。在此範例中，您僅需要有一筆 DNS A 記錄，並讓其將 lync.contoso.com 解析為 Director 集區或前端集區的 IP 位址。

### <a name="simple-url-option-3"></a>簡單 URL 選項 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡單 URL</strong></p></td>
<td><p><strong>範例</strong></p></td>
</tr>
<tr class="even">
<td><p>滿足</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>撥入</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>系統管理員</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>簡單 URL 的災害復原選項

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

<div class="">


> [!NOTE]  
> 如果網路使用<EM>「髮夾」</EM> (將所有簡單 URL 流量透過外部連結路由，包括來自組織內的流量)，則可僅設定外部 GeoDNS 位址，並將 Meet 簡單 URL 僅解析為該外部位址。



</div>

使用此方法時，可設定每個 GeoDNS 位址使用循環配置資源方法來散發要求至兩個集區，或者主要連線至一個集區 (例如地理位置上較近的集區)，然後僅在連線失敗時才使用另一個集區。

針對 Dial-In 簡單 URL 也可以設定相同的組態。 若要這麼做，請建立如先前範例中的其他記錄，並以 `dialin` `meet` DNS 記錄取代。 針對 Admin 簡單 URL，請使用本節中先前列出的三個選項。

此組態一旦設定，就必須使用監控應用程式，設定 HTTP 監控以監看失敗。 若要進行外部存取，請確定 HTTPS 對兩個集區的外部 web FQDN 或負載平衡器 IP 位址的 HTTPS GET 自動探索要求成功。 例如，下列要求不得包含任何 **ACCEPT** 標頭且必須傳回 **200 OK**。

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

針對內部存取，則必須監控該兩個集區之內部 Web FQDN 或負載平衡器 IP 位址的連接埠 5061。如果偵測到任何連線失敗，這些集區的 VIP 必須關閉連接埠 80、443 及 444。

</div>

</div>

<span> </span>

</div>

</div>

</div>

