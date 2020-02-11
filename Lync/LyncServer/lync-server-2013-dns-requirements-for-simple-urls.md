---
title: Lync Server 2013：簡單 URL 的 DNS 需求
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
ms.openlocfilehash: 2a05b5e5afc645c9219d02c8a551e4c0af9d93b0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 中簡單 URL 的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

Lync Server 2013 支援簡單的 Url，讓您的使用者更容易加入會議，並讓您能更輕鬆地進入 Lync Server 管理工具給您的系統管理員。 如需簡單 Url 的詳細資料，請參閱[規劃 Lync Server 2013 中的簡單 url](lync-server-2013-planning-for-simple-urls.md)。

Lync Server 支援下列三個簡單的 Url： [開會]、[撥入] 和 [管理員]。您必須設定適用于 [開會及撥入] 的簡單 Url，且 [管理員簡易 URL] 是選擇性的。 您需要支援簡單 Url 的網域名稱系統（DNS）記錄，取決於您如何定義這些簡單的 Url，以及是否要支援簡單 Url 的災害復原。

<div>

## <a name="simple-url-option-1"></a>簡單的 URL 選項1

在選項1中，您為每個簡單的 URL 建立新的基 URL。

<div class="">


> [!NOTE]  
> 當使用者按一下簡單的 URL 會議連結時，DNS A 記錄所解析的伺服器會決定要啟動的正確用戶端軟體。 用戶端軟體啟動之後，就會自動與該會議的主機池進行通訊。 如此一來，無論簡單的 URL DNS A 記錄解析到哪個伺服器或池中，使用者都會被導向會議內容的適當伺服器。



</div>

### <a name="simple-url-option-1"></a>簡單的 URL 選項1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡單的 URL</strong></p></td>
<td><p><strong>範例</strong></p></td>
</tr>
<tr class="even">
<td><p>符合</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.com等等（針對貴組織中的每個 SIP 網域一個）</p></td>
</tr>
<tr class="odd">
<td><p>撥入</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>管理員</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


如果您使用選項1，您必須定義下列各項：

  - 針對每個符合簡單的 URL，您需要一個 DNS A 記錄，將 URL 解析為主管的 IP 位址（如果您已部署）。 否則，它應該解析為前端池負載平衡器的 IP 位址。 如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。
    
    如果您的組織中有多個 SIP 網域，且您使用這個選項，您必須為每個 SIP 網域建立符合簡單的 Url，且您需要每個符合簡單 URL 的 DNS A 記錄。 例如，如果您同時擁有 contoso.com 和 fabrikam.com，您將會建立https://meet.contoso.com與https://meet.fabrikam.com的 DNS A 記錄。
    
    或者，如果您有多個 SIP 網域，而且想要將這些簡單 Url 的 DNS 記錄與證書需求減到最小，請使用 Option 3，如本主題稍後所述。

  - 若是撥入式簡易 URL，您需要 DNS A 記錄，將 URL 解析為主管的 IP 位址（如果您已部署的話）。 否則，它應該解析為前端池負載平衡器的 IP 位址。 如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。

  - [管理員] 簡單 URL 僅限內部版本。 它需要一個 DNS A 記錄，將 URL 解析為主管的 IP 位址（如果您已部署）。 否則，它應該解析為前端池負載平衡器的 IP 位址。 如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。

</div>

<div>

## <a name="simple-url-option-2"></a>簡單的 URL 選項2

有了選項2、[開會]、[撥入] 和 [系統管理] 的簡單 Url，都有共同的基底 URL，例如 lync.contoso.com。 因此，對於這些簡單的 Url，只需要一個 DNS A 記錄，即可將 lync.contoso.com 解析為主管池或頂層端池的 IP 位址。 如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。

請注意，如果您的組織中有多個 SIP 網域，您仍然必須建立符合每個 SIP 網域的簡單 Url，而且您需要每個符合簡單 URL 的 DNS A 記錄。 在這個範例中，雖然三個簡單的 Url 都是以 lync.contoso.com 為基礎，但 fabrikam.com 的另一個基本 url 是以不同的基 URL 來設定。 在這個範例中，您必須同時為兩個和https://lync.contoso.com https://lync.fabrikam.com兩個都建立 DNS A 記錄。 如果您有多個 SIP 網域，則簡單的 URL 選項3會顯示另一個處理命名和 DNS A 記錄的方式。

### <a name="simple-url-option-2"></a>簡單的 URL 選項2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡單的 URL</strong></p></td>
<td><p><strong>範例</strong></p></td>
</tr>
<tr class="even">
<td><p>符合</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet等等（針對貴組織中的每個 SIP 網域一個）</p></td>
</tr>
<tr class="odd">
<td><p>撥入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理員</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>簡單的 URL 選項3

如果您有許多 SIP 網域，而您想要讓它們擁有不同的簡單 Url，但想要將這些簡單 Url 的 DNS 記錄與證書需求減至最少，選項3就是最實用的方法。 在這個範例中，您只需要一個 DNS A 記錄，該記錄會將 lync.contoso.com 解析為主管池或頂層端池的 IP 位址。

### <a name="simple-url-option-3"></a>簡單的 URL 選項3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡單的 URL</strong></p></td>
<td><p><strong>範例</strong></p></td>
</tr>
<tr class="even">
<td><p>符合</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>撥入</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理員</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>簡單 Url 的災害復原選項

如果您有多個包含前端池的網站，而且您的 DNS 提供者支援 GeoDNS，您可以針對簡單的 Url 設定您的 DNS 記錄，以支援災害復原，因此即使一個完整的前端池已停止，簡單的 URL 功能仍會繼續。 這個災害復原功能支援 [開會] 和 [撥入] 簡單的 Url。

若要設定這一點，請建立兩個 GeoDNS 位址。 每個位址都有兩個 DNS A 或 CNAME 記錄，可解析成成對組成的兩個池以進行災害復原。 一個 GeoDNS 位址用於內部存取，並解析為兩個池的內部網路 FQDN 或負載平衡器 IP 位址。 其他 GeoDNS 位址是用於外部存取，並解析為兩個池的外部 web FQDN 或負載平衡器 IP 位址。 下列是使用池之 Fqdn 的 [符合簡單 URL] 的範例。

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

然後建立可將您的符合簡單 URL （例如 meet.contoso.com）解析成兩個 GeoDNS 位址的 CNAME 記錄。

<div class="">


> [!NOTE]  
> 如果您的網路使用的是<EM>hairpinning</EM> （透過外部連結路由所有簡單的 URL 流量，包括來自貴組織內部的流量），則您可以只設定外部 GeoDNS 位址，並將您的 [符合簡單 url] 解析為僅限外部地址。



</div>

當您使用此方法時，您可以設定每個 GeoDNS 位址，以使用迴圈複用方法將要求發佈到兩個池，或主要連線到一個池（例如位於地理位置較近的池中），並使用其他池（例如連接失敗。

您可以針對撥入簡易 URL 設定相同的配置。 若要這樣做，請建立如先前範例中的其他記錄， `dialin`並`meet`在 DNS 記錄中取代。 針對系統管理員簡易 URL，請使用本節前面所列的三個選項之一。

設定此設定之後，您必須使用監視應用程式來設定 HTTP 監視來監視失敗。 針對外部存取，請務必確認 HTTPS 取得對外部網路 FQDN 的自動探索要求，或兩個池的負載平衡器 IP 位址成功。 例如，下列要求不能包含任何**ACCEPT**標頭，而且必須傳回**200 OK**。

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

針對內部存取，您必須在兩個池的內部網路 FQDN 或負載平衡器 IP 位址上，監視埠5061。 如果偵測到任何連線失敗，這些池的 VIP 必須關閉埠80、443和444。

</div>

</div>

<span> </span>

</div>

</div>

</div>

