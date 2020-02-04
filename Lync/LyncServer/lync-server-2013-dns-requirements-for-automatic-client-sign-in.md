---
title: Lync Server 2013：自動用戶端登入的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>在 Lync Server 2013 中自動用戶端登入的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

本節說明自動用戶端登入所需的網域名稱系統（DNS）記錄。 當您部署標準版 server 或前端池時，您可以將用戶端設定為使用自動探索來登入適當的標準版 server 或前端池。 如果您打算要求用戶端手動連線至 Lync Server 2013，您可以略過本主題。

若要支援自動用戶端登入，您必須：

  - 指派單一伺服器或池來發佈及驗證用戶端登入要求。 這可以是貴組織中託管使用者的現有伺服器或池，或者，您也可以指定專用伺服器或池來主持沒有使用者的目的。 為了提供高可用性，建議您指定此函數的前端池。

  - 建立內部 DNS SRV 記錄，以支援此伺服器或池的自動用戶端登入。
    
    <div>
    

    > [!NOTE]  
    > 在下列記錄需求中，SIP 網域是指指派給使用者的 SIP Uri 的主機部分。 例如，如果 SIP Uri 的形式是 * @contoso .com，則 contoso.com 是 SIP 網域。 SIP 網域通常與內部 Active Directory 網域不同。 組織也可以支援多個 SIP 網域。

    
    </div>

若要為您的用戶端啟用自動設定，您必須建立內部 DNS SRV 記錄，將下列其中一個記錄對應至前端池或標準版伺服器的完整功能變數名稱（FQDN），以從 Lync 分發登入要求台

  - \_sipinternaltls.\_tcp。\<網域\> -內部 TLS 連線

您只需要為前端池或標準版伺服器建立單一 SRV 記錄，或將發佈登入要求。

下表顯示虛構公司 Contoso 所需的一些範例記錄，這些案例支援 contoso.com 和 retail.contoso.com 的 SIP 網域。

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>使用多個 SIP 網域自動進行用戶端登入所需的 DNS 記錄範例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用來散佈登入要求的前端池 FQDN</th>
<th>SIP 網域</th>
<th>DNS SRV 記錄</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>在 pool01.contoso.com 的埠5061上，_tcp contoso 網域 _sipinternaltls 的 SRV 記錄</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>在 pool01.contoso.com 的埠5061上，將 _sipinternaltls. _tcp retail 網域的 SRV 記錄。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 根據預設，DNS 記錄的查詢會在使用者名稱和 SRV 記錄中的網域之間，遵循嚴格的功能變數名稱相符。 如果您希望用戶端 DNS 查詢改為使用尾碼相符，您可以設定 DisableStrictDNSNaming 組原則。 如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的用戶端和裝置規劃</A>。



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>自動用戶端登入所需的憑證和 DNS 記錄範例

這個範例在前一個表格中使用相同的範例名稱。 Contoso 組織支援 contoso.com 和 retail.contoso.com 的 SIP 網域，且其所有使用者都有下列其中一種形式的 SIP URI：

  - \<使用者\>@retail contoso.com

  - \<使用者\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

