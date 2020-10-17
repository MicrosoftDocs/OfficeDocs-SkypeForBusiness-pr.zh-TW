---
title: Lync Server 2013：規劃簡易 URLs
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
ms.openlocfilehash: f7d5ae03267b266b1ef2abbacc2e3fce06e034ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513520"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中規劃簡易 URLs

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-12-11_

簡單 URLs 使您的使用者加入會議變得更容易，並讓系統管理員更輕鬆取得 Lync Server 系統管理工具。

Lync Server 支援三種簡單的 URLs：

  - 「**開會**」是網站或組織中所有會議的基礎 URL。 符合簡易 URL 的範例是 https://meet.contoso.com 。 特定會議的 URL 可能是 https://meet.contoso.com/ *username*/7322994。
    
    使用符合簡易 URL 時，加入會議的連結就很容易理解，而且易於進行通訊和發佈。

  - **撥入** 功能可讓您存取電話撥入式會議設定網頁。 此頁面會以其可用語言、指派會議資訊 (，也就是針對不需要排程) 的會議，以及在會議 DTMF 中的控制措施，以及支援管理個人識別碼) 的個人 (標識號，以及所指派的會議資訊。 撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。 撥入式簡易 URL 的範例是 https://dialin.contoso.com 。

  - 系統**管理員**可讓您快速存取 Lync Server [控制台]。 從組織防火牆內部的任何電腦，管理員都可以在瀏覽器中輸入系統管理員簡易 URL，以開啟 Lync Server 控制台。 系統管理員簡易 URL 是您組織內部。 管理員簡易 URL 的範例是 https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>簡單 URL 範圍

您可以將您的簡易 URLs 設定為具有全域範圍，也可以為組織中的每個中央網站指定不同的簡單 URLs。 如果同時指定全域範圍簡易 url 和網站範圍簡易 URL，則網站範圍的簡單 URL 具有優先權。

在大多數情況下，我們建議您只在全域層級設定簡單 URLs，如此一來，如果使用者的符合簡易 URL 從一個網站移動到另一個網站，就不會變更。 例外狀況是組織必須針對不同網站上的撥入使用者使用不同的電話號碼。 請注意，如果您設定一個簡易 URL (例如，將網站上的撥入簡易 URL) 設定為網站層級的簡易 URL，您也必須將該網站上的其他簡單 URLs 也設定為網站層級。

<div>


> [!NOTE]  
> 如果您選擇使用網站範圍的簡易 URLs，您的使用者將無法在不同網站中的 Front-End 集區間移動，除非使用者重新設定所有排程的會議，而不是讓會議簡單 URLs 在網站之間有所不同。 這包括容錯移轉案例，其中集區的備份關係位於不同的網站。 當您需要在部署網站範圍簡易 URLs 的網站之間進行容錯移轉時，使用者將無法加入其會議，因為 URL 的範圍。 如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>。



</div>

您可以在拓撲產生器中設定全域簡單的 URLs。 若要在網站層級設定簡單 URL，您必須使用 Set-CsSimpleURLConfiguration Cmdlet。

</div>

<div>

## <a name="naming-your-simple-urls"></a>命名您的簡易 URLs

有三個建議選項可用於命名您的簡易 URLs。 您選擇的哪個選項會影響您設定 DNS A 記錄的方式，以及支援簡易 URLs 的憑證。 在每個選項中，您必須為組織中的每個 SIP 網域設定一個符合簡易 URL 的功能。

在整個組織中，您永遠只需要一個簡易 URL，以進行撥入，一個用於管理，不論您有多少 SIP 網域。

如需必要的 DNS A 記錄和憑證的詳細資訊，請參閱規劃檔中的 Lync server 2013 中的 [簡易 URLs 的 dns 需求](lync-server-2013-dns-requirements-for-simple-urls.md) 和 [lync server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。

在選項1中，您可以為每個簡單 URL 建立新的 SIP 功能變數名稱。

如果您使用此選項，則每個簡單 URL 都必須有個別的 DNS A 記錄，而且每個符合簡易 URL 的憑證皆必須在您的憑證中命名。

### <a name="simple-url-naming-option-1"></a>簡單 URL 命名選項1

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


使用選項2，簡單 URLs 是以功能變數名稱 lync.contoso.com 為基礎。 因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 URLs。 此 DNS A 記錄參照 lync.contoso.com。 此外，您的組織中的其他 SIP 網域仍然需要不同的 DNS A 記錄。

### <a name="simple-url-naming-option-2"></a>簡單 URL 命名選項2

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


如果您有多個 SIP 網域，而您想要讓其具有個別的符合簡易 URLs，但想要將這些簡易 URLs 的 DNS 記錄和憑證需求降至最低，則選項3最為有用。

### <a name="simple-url-naming-option-3"></a>簡單 URL 命名選項3

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
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>系統管理員</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>簡單 URL 命名和驗證規則

拓撲產生器和 Lync Server 管理命令介面指令程式會針對您的簡易 URLs 執行數種驗證規則。 您必須為符合和撥入設定簡單的 URLs，但為 Admin 設定一個是選用的。 每個 SIP 網域都必須有個別的符合簡單 URL，但是您只需要一個撥入簡易 URL 和一個系統管理員簡易 URL 給整個組織。

組織中的每個簡易 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼 (例如，您無法將 lync.contoso.com/Meet 設定為您的 [lync.contoso.com/Meet/Dialin] 簡單 url，而為您的撥入簡易 URL) 。 簡單 URL 名稱不能包含任何集區的 FQDN，或任何埠資訊 (例如， https://FQDN:88/meet 不允許) 。 所有的簡單 URLs 都必須以 HTTPs://前置詞開頭。

簡單 URLs 只能包含字母數位字元 (即 a-z、A-Z、0-9 和句點 (。 ) 。 如果您使用其他字元，則簡單 URLs 可能無法如預期那樣運作。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>在部署後變更簡單 URLs

如果您在初始部署後變更簡單 URL，您必須注意變更會如何影響您的 DNS 記錄和憑證以取得簡易 URLs。 如果簡單 URL 的基底變更，您也必須變更 DNS 記錄和憑證。 例如，從 lync.contoso.com 變更 https://lync.contoso.com/Meet 為 https://meet.contoso.com meet.contoso.com 時，您必須變更 DNS 記錄和憑證，以參照 meet.contoso.com。 如果您已將簡易 URL 變更 https://lync.contoso.com/Meet 為 https://lync.contoso.com/Meetings ，lync.contoso.com 的基底 url 會保持不變，因此不需要任何 DNS 或憑證變更。

不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 **Enable-CsComputer** ，以註冊變更。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中簡易 URLs 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

