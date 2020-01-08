---
title: Lync Server 2013：定義緊急通話需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53543d815519dc440ba038999e5fc531173551f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>在 Lync Server 2013 中定義緊急通話需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

在您開始使用 Microsoft Lync Server 2013 E9-1-1 1 之前，您應該先能夠回答下列各節所述的問題。 您需要執行的規劃取決於您選擇部署的 E9-1-1 解決方案類型，即 SIP 幹線 E9-1 服務提供者，或緊急位置識別號碼（ELIN）閘道。 下表說明本規劃活頁簿中您需要針對每個方案進行審查的章節。

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>依 E9 類型（1-1-1）方案規劃步驟

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP 中繼服務提供者</th>
<th>ELIN 閘道</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷 Lync Server 2013 中的位置的網路元素</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷 Lync Server 2013 中的位置的網路元素</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中啟用 E9-1-1 的使用者</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中啟用 E9-1-1 的使用者</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">在 Lync Server 2013 中管理 SIP 中繼服務提供者的位置</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">在 Lync Server 2013 中管理 ELIN 閘道的位置</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義在 Lync Server 2013 中手動取得位置的使用者體驗</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義在 Lync Server 2013 中手動取得位置的使用者體驗</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">在 Lync Server 2013 中針對 E9-1-1 設計 SIP 主幹</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">包括 Lync Server 2013 中的安全服務台</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">包括 Lync Server 2013 中的安全服務台</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">選擇 Lync Server 2013 的 E9-1 服務提供者</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中指派位置原則範圍</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中指派位置原則範圍</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中定義 E9-1-1 部署的範圍](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [定義用來判斷 Lync Server 2013 中的位置的網路元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [在 Lync Server 2013 中啟用 E9-1-1 的使用者](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [在 Lync Server 2013 中管理 SIP 中繼服務提供者的位置](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [在 Lync Server 2013 中管理 ELIN 閘道的位置](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [定義在 Lync Server 2013 中手動取得位置的使用者體驗](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [在 Lync Server 2013 中針對 E9-1-1 設計 SIP 主幹](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [包括 Lync Server 2013 中的安全服務台](lync-server-2013-including-the-security-desk.md)

  - [選擇 Lync Server 2013 的 E9-1 服務提供者](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)

  - [在 Lync Server 2013 中指派位置原則範圍](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

