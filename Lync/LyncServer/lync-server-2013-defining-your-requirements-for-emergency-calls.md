---
title: Lync Server 2013： 定義緊急通話需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4455e7072e6bdb25fb2b2bc0cd4e7bc39f1f05d1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Lync Server 2013 中定義緊急通話需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-06_

開始 Microsoft Lync Server 2013 E9-1-1 部署之前，您應該先能夠回答下列各節中詳述的問題。 您需要執行的規劃視您選擇部署的 E9-1-1 解決方案類型— SIP 主幹 E9-1-1 服務提供者或緊急位置識別碼 (ELIN) 閘道。 下表針對各個解決方案指出此規劃工作簿中您需要檢閱的章節。

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>規劃步驟 (依 E9-1-1 解決方案的類型)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP 主幹服務提供者</th>
<th>ELIN 閘道</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 中定義 E9-1-1 部署的範圍</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 中定義 E9-1-1 部署的範圍</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷在 Lync Server 2013 中的位置的網路元素</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷在 Lync Server 2013 中的位置的網路元素</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">為使用者啟用 E9-1-1 在 Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">為使用者啟用 E9-1-1 在 Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">管理 Lync Server 2013 中的 SIP 主幹服務提供者的位置</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">管理 ELIN 閘道 Lync Server 2013 中的位置</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義手動取得位置 Lync Server 2013 中的使用者經驗</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義手動取得位置 Lync Server 2013 中的使用者經驗</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">針對 Lync Server 2013 中 E9-1-1 設計 SIP 主幹</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 中包括安全性桌面</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 中包括安全性桌面</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">選擇 [Lync Server 2013 的 E9-1-1 服務提供者</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">指派 Lync Server 2013 中的位置原則範圍</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">指派 Lync Server 2013 中的位置原則範圍</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中定義 E9-1-1 部署的範圍](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [定義用來判斷在 Lync Server 2013 中的位置的網路元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [為使用者啟用 E9-1-1 在 Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [管理 Lync Server 2013 中的 SIP 主幹服務提供者的位置](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [管理 ELIN 閘道 Lync Server 2013 中的位置](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [定義手動取得位置 Lync Server 2013 中的使用者經驗](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [針對 Lync Server 2013 中 E9-1-1 設計 SIP 主幹](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Lync Server 2013 中包括安全性桌面](lync-server-2013-including-the-security-desk.md)

  - [選擇 [Lync Server 2013 的 E9-1-1 服務提供者](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)

  - [指派 Lync Server 2013 中的位置原則範圍](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

