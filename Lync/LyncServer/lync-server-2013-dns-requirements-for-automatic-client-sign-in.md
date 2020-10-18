---
title: Lync Server 2013：自動用戶端登入的 DNS 需求
description: Lync Server 2013：自動用戶端登入的 DNS 需求。
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
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574369"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013 中自動用戶端登入的 DNS 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

本主題將說明自動用戶端登入所需的網域名稱系統 (DNS) 記錄。 當您部署自己的 Standard Edition Server 或前端集區時，可以設定用戶端使用自動探索功能來登入適當的 Standard Edition Server 或前端集區。 如果您打算要求用戶端手動連接至 Lync Server 2013，您可以略過此主題。

若要支援用戶端自動登入，您必須：

  - 指定單一伺服器或集區，以分送和驗證用戶端登入要求。這可以是您組織中裝載使用者的現有伺服器或集區，或者，您也可以指定不裝載任何使用者的專用伺服器或集區做為此用途。若要達到高可用性，建議您指定前端集區來執行此功能。

  - 建立內部 DNS SRV 記錄，以支援此伺服器或集區的自動用戶端登入。
    
    <div>
    

    > [!NOTE]  
    > 下列記錄需求中，SIP 網域是指已指派給使用者的 SIP URI 的主機部分。例如，如果 SIP URI 的格式為 *@contoso.com，則 contoso.com 為 SIP 網域。SIP 網域通常與內部 Active Directory 網域不同。組織也可以支援多個 SIP 網域。

    
    </div>

若要為您的用戶端啟用自動設定，您必須建立內部 DNS SRV 記錄，將下列其中一項記錄對應至前端集區或 Standard Edition server 的完整功能變數名稱 (FQDN) ，以從 Lync 用戶端分配登入要求：

  - \_sipinternaltls。 \_Tcp。\<domain\> -適用于內部 TLS 連接

您只需要為會分散登入要求的前端集區或 Standard Edition Server 建立單一 SRV 記錄。

下表顯示一些虛構公司 Contoso 所需的範例記錄，該公司支援 contoso.com 和 retail.contoso.com 這兩個 SIP 網域。

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>針對多個 SIP 網域進行自動用戶端登入所需之 DNS 記錄的範例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用來分送登入要求之前端集區的 FQDN</th>
<th>SIP 網域</th>
<th>DNS SRV 記錄</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>_sipinternaltls._tcp.contoso.com 網域 (透過連接埠 5061) 的 SRV 記錄，對應到 pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>_sipinternaltls._tcp.retail.contoso.com 網域 (透過連接埠 5061) 的 SRV 記錄，對應到 pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 根據預設，DNS 記錄的查詢符合使用者名稱中的網域與 SRV 記錄之間的嚴格網域名稱比對。 如果您想要讓用戶端 DNS 查詢改用尾碼比對，可以設定 DisableStrictDNSNaming 群組原則。 如需詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-clients-and-devices.md">規劃 Lync Server 2013 中的用戶端和裝置</A> 。



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>用戶端自動登入所需之憑證和 DNS 記錄的範例

此範例使用前面表格中的相同範例名稱。Contoso 組織支援 contoso.com 以及 retail.contoso.com 這兩個 SIP 網域，而且其所有的使用者都具有下列其中一種格式的 SIP URI：

  - \<user\>@retail。 contoso.com

  - \<user\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

