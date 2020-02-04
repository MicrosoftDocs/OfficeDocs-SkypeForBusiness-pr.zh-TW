---
title: Lync Server 2013：規劃簡單 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中規劃簡單 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-12-11_

簡單的 Url 可讓您更輕鬆地加入會議，並讓您的系統管理員更輕鬆地進入 Lync Server 管理工具。

Lync Server 支援三個簡單的 Url：

  - [**開會**] 是用來做為網站或組織中所有會議的基底 URL。 [符合簡單 URL] 的範例是https://meet.contoso.com。 特定會議的 URL 可能是https://meet.contoso.com/[使用者*名稱*/7322994]。
    
    使用 [符合簡單的 URL]，加入會議的連結就很容易理解，且易於溝通及發佈。

  - [**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。 此頁面會以其可用語言、指派的會議資訊（也就是不需要排程的會議）及會議中的 DTMF 控制來顯示會議撥入號碼，並支援個人身分識別號碼的管理（PIN）及指派的會議資訊。 [撥入] 簡單 URL 包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。 電話撥入式簡單 URL 的範例是https://dialin.contoso.com。

  - [系統**管理**] 可讓您快速存取 Lync Server [控制台]。 從組織防火牆內的任何電腦，管理員都可以在瀏覽器中輸入 [管理員] 簡單 URL，以開啟 Lync Server [控制台]。 系統管理員簡易 URL 是貴組織的內部。 系統管理簡單 URL 的範例https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>簡單的 URL 範圍

您可以將簡單的 Url 設定為擁有全域範圍，或者您可以為組織中的每個中心網站指定不同的簡單 Url。 如果全域範圍簡單 URL 和網站範圍的簡單 URL 都已指定，則網站範圍簡單 URL 就會有優先順序。

在大部分的情況下，建議您只在全域層級設定簡單的 Url，讓使用者的 [符合簡單 URL] 不會隨著從某個網站移至另一個網站而變更。 例外情況是，組織必須在不同的網站上為撥入使用者使用不同的電話號碼。 請注意，如果您在網站上將一個簡單的 URL （例如撥入式簡易 URL）設定為網站層級的簡單 URL，您也必須將該網站上的其他簡單 Url 設定為網站層級。

<div>


> [!NOTE]  
> 如果您選擇使用網站範圍簡單的 Url，您的使用者將無法在不同網站中的前端池間移動，而不會讓這些使用者重新排定所有排程會議，因為網站之間的會議簡單 Url 是不一樣的。 這包括容錯移轉案例，其中，備份關係中的池位於不同的網站中。 如果您需要在網站設定簡單 Url 的網站之間進行容錯移轉，使用者將無法加入其會議，因為 URL 的範圍。 如需進一步資訊，請核<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">取 CsSimpleUrlConfiguration</A>。



</div>

您可以在拓撲產生器中設定全域簡單的 Url。 若要在網站層級設定簡單的 URL，您必須使用 CsSimpleURLConfiguration Cmdlet。

</div>

<div>

## <a name="naming-your-simple-urls"></a>命名您的簡單 Url

有三個建議選項可用於命名您的簡單 Url。 您選擇的選項會對您設定 DNS A 記錄的方式，以及支援簡易 Url 的憑證有何影響。 在每個選項中，您必須針對組織中的每個 SIP 網域設定一個 [符合簡單 URL]。

您永遠只需要在整個組織中使用一個簡單的 URL 進行撥入，另一個用於管理員，不論您有多少 SIP 網域。

如需有關必要 DNS A 記錄和憑證的詳細資料，請參閱規劃檔中的 lync [server 2013 簡單 url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)和[lync server 2013 中的內部伺服器憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

在選項1中，您為每個簡單的 URL 建立新的 SIP 功能變數名稱。

如果您使用這個選項，則每個簡單的 URL 都需要一個單獨的 DNS A 記錄，而且每個符合簡單 URL 的名稱都必須在您的憑證中命名。

### <a name="simple-url-naming-option-1"></a>簡單 URL 命名選項1

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


有了選項2，簡單的 Url 就會以功能變數名稱 lync.contoso.com 為基礎。 因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 Url。 這個 DNS A 記錄參照 lync.contoso.com。 此外，貴組織中的其他 SIP 網域，您仍然需要獨立的 DNS A 記錄。

### <a name="simple-url-naming-option-2"></a>簡單 URL 命名選項2

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


如果您有多個 SIP 網域，而您想要將它們放在不同的基本 Url 中，但想要將這些簡單 Url 的 DNS 記錄與證書需求降至最低，選項3是最實用的。

### <a name="simple-url-naming-option-3"></a>簡單 URL 命名選項3

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
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理員</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>簡單的 URL 命名與驗證規則

拓撲建立器和 Lync Server 管理命令介面 Cmdlet 會針對您的簡單 Url 強制執行數個驗證規則。 您必須將簡單的 Url 設定為 [符合] 或 [撥入]，但為 [管理員] 設定一個則是選擇性的。 每個 SIP 網域都必須有一個單獨的 [符合簡單 URL]，但您只需要一個簡單的 URL，而且只有一個系統管理員就能為整個組織提供簡單的 URL。

貴組織中的每個簡單 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼（例如，您無法將 lync.contoso.com/Meet 設為您的 [您的內輟] 簡單 url，而 lync.contoso.com/Meet/Dialin 為您的撥入簡易 URL）。 簡單的 URL 名稱不能包含任何一個池的 FQDN，或任何埠資訊（例如， https://FQDN:88/meet不允許）。 所有簡單的 Url 都必須以 HTTPs://首碼開頭。

簡單的 Url 只能包含字母數位字元（即 a-z、A-Z、0-9 及句號（.）。 如果您使用其他字元，則簡單的 Url 可能無法如期運作。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>在部署之後變更簡單的 Url

如果您在初始部署之後變更簡單的 URL，您必須知道變更對您的 DNS 記錄及簡單 Url 的憑證有何影響。 如果簡單 URL 的基底發生變更，則您也必須變更 DNS 記錄和憑證。 例如，從https://lync.contoso.com/Meet lync.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL，因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。 如果您將簡單的 URL 改https://lync.contoso.com/Meet為https://lync.contoso.com/Meetings[寄件者]，則 LYNC.CONTOSO.COM 的基底 url 會保持不變，因此不需要變更 DNS 或憑證。

不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行**Enable-CsComputer** ，以登錄變更。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中簡單 URL 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

