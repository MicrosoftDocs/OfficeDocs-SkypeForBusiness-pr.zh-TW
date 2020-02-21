---
title: Lync Server 2013： 規劃簡單 Url
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
ms.openlocfilehash: c6bbbe8650ae1d7746c9b87ecf4518236f8b1575
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>規劃 Lync Server 2013 中的簡單 Url

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-12-11_

簡單 Url 加入會議更輕鬆地進行您的使用者，並讓 [Lync Server 系統管理工具更容易的取得您的系統管理員。

Lync Server 支援三個簡單 Url:

  - **符合**用於做為基底 URL 的網站或組織中的所有會議。 範例的 Meet 簡單 URL 是https://meet.contoso.com。 可能是特定會議 URL https://meet.contoso.com/ *username*/7322994。
    
    Meet 簡單 URL，來加入會議的連結有可更容易理解，且更容易溝通與分送。

  - **撥號對應表中**啟用 [存取電話撥入式會議設定網頁。 此頁面會顯示會議撥入號碼與其可用的語言，指派會議資訊 (也就是不需要排定的會議)，在會議 DTMF 控制項，並支援管理個人識別號碼 （Pin 碼），並指派會議資訊。 撥入簡單 URL 包含所有會議邀請中，讓要撥入會議的使用者可以存取的必要的電話號碼及 pin 碼資訊。 撥入簡單 URL 的範例是https://dialin.contoso.com。

  - **系統管理員**可讓您快速存取 Lync Server Control Panel。 從您的組織防火牆內的任何電腦，系統管理員可以在瀏覽器中輸入 Admin 簡單 URL 開啟 Lync Server Control Panel。 Admin 簡單 URL 是您組織內部。 Admin 簡單 URL 的範例https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>簡單 URL 範圍

您可以設定進行全域範圍，簡單 Url，或您可以指定貴組織中的每個中央網站不同的簡單 Url。 如果指定全域範圍簡單 URL 及網站範圍簡單 URL，則網站範圍的簡單 URL 的優先順序。

在大多數情況下，我們建議您只在全域層級，設定簡單 Url，讓使用者的 Meet 簡單 URL 不會變更，如果他們從一個網站移至另一個。 例外狀況可能需要使用不同的電話號碼的電話撥入式使用者在不同站台的組織。 請注意，是否您是網站層級的簡單 URL 的網站在設定一個簡單 URL （例如 dial-in 簡單 URL)，您也必須設定其他簡單 Url，該網站也是網站層級。

<div>


> [!NOTE]  
> 如果您選擇使用網站範圍的簡單 Url，則您的使用者，將無法在不同的站台沒有為會議的簡單 Url 的不同站台之間所有其排程的會議： 這些使用者的前端集區之間移動。 這包括容錯移轉案例中的備份關係的集區，是在個別的網站。 當您要容錯移轉之間部署所在網站範圍設定簡單 Url 的網站，使用者將無法加入其會議因為 URL 的範圍。 如需詳細資訊，請檢查<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-cssimpleurlconfiguration</A>。



</div>

您可以在拓撲產生器設定通用簡單 Url。 若要在網站層級設定簡單 URL，您必須使用 Set CsSimpleURLConfiguration 指令程式。

</div>

<div>

## <a name="naming-your-simple-urls"></a>簡單 Url 命名

有三個簡單 Url 命名的建議的選項。 您選擇哪個選項具有影響您如何設定您的 DNS A 記錄和支援簡單 Url 的憑證。 在每個選項，您必須在組織中設定每個 SIP 網域的一個 Meet 簡單 URL。

您一律在整個組織的撥入與一個 Admin，無論您有多少的 SIP 網域需要只是一個簡單的 URL。

如需必要的 DNS A 記錄與憑證的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)和[Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

在選項 1 中，您可以建立新的 SIP 網域名稱的每個簡單 URL。

如果您使用此選項，您需要個別的 DNS A 記錄，針對每個簡單 URL，以及每個 Meet 簡單 URL 必須命名為在憑證中。

### <a name="simple-url-naming-option-1"></a>簡單 URL 命名選項 1

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
<td><p>符合</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.com等等 （一個組織中每個 SIP 網域）</p></td>
</tr>
<tr class="odd">
<td><p>電話撥入式</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>系統管理</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


選項 2 使用網域名稱 lync.contoso.com 根據簡單 Url。 因此，您必須只能有一個 DNS A 記錄可讓所有三種簡單 Url。 此 DNS A 記錄參照 lync.contoso.com。 此外，您仍然需要個別的 DNS A 記錄的其他 SIP 網域貴組織中。

### <a name="simple-url-naming-option-2"></a>簡單 URL 命名選項 2

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
<td><p>符合</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet等等 （一個組織中每個 SIP 網域）</p></td>
</tr>
<tr class="odd">
<td><p>電話撥入式</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>系統管理</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


選項 3 是最有用的如果您有許多 SIP 網域，且您想要有個別的 Meet 簡單 Url，但想要減少這些簡單 Url 的 DNS 記錄與憑證需求。

### <a name="simple-url-naming-option-3"></a>簡單 URL 命名選項 3

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
<td><p>符合</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>電話撥入式</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>系統管理</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>簡單 URL 命名與驗證規則

拓撲產生器和 Lync Server 管理命令介面指令程式強化簡單 Url 幾個驗證規則。 您需要設定簡單 Url 的 Meet 和 Dialin，但設定另一個適用於系統管理員是選擇性的。 每個 SIP 網域必須有個別的 Meet 簡單 URL，但必須只能有一個撥入簡單 URL 與一個 Admin 簡單 URL 為整個組織。

您組織中的每個簡單 URL 都必須有唯一名稱，且不能為另一個簡單 URL 的前置詞 （例如，您無法設定為將 Meet 簡單 URL 的 lync.contoso.com/Meet 和 lync.contoso.com/Meet/Dialin 做為您的撥入簡單 URL）。 簡單 URL 名稱不得包含任何集區，或任何連接埠資訊的 FQDN (例如，https://FQDN:88/meet不允許)。 所有簡單 Url 的開頭必須 https:// 前置詞。

簡單 Url 可以僅包含英數字元 （也就是 a 到 z、 A 到 Z、 0-9 和句點 （.）。 如果您使用其他字元，簡單 Url 可能無法如預期般運作。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>部署後變更簡單 Url

如果您變更簡單 URL 初始部署之後，您必須知道如何變更會影響您的 DNS 記錄和憑證簡單 url。 如果變更之基底的簡單 URL，然後您必須變更 DNS 記錄及憑證也。 例如，從變更https://lync.contoso.com/Meet以https://meet.contoso.com基底 URL 從變成 lync.contoso.com meet.contoso.com，所以您需要變更 DNS 記錄和憑證，以參照 meet.contoso.com。 如果您變更從簡單 URLhttps://lync.contoso.com/Meet以https://lync.contoso.com/Meetings、 lync.contoso.com 的基底 URL 保持不變，因此沒有 DNS 或需要憑證的變更。

每當您變更了簡單 URL 名稱，但是，您必須執行**Enable-cscomputer**上每個 Director 與前端伺服器，以登錄變更。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

