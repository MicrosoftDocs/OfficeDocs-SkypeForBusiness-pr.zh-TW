---
title: Lync Server 2013：群組呼叫收取的部署程式
description: Lync Server 2013：群組呼叫收取的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552489"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中群組呼叫收取的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

本節提供部署群組呼叫收取相關步驟的概述。 您必須先部署 Enterprise Edition 或 Standard Edition 搭配 Enterprise Voice，才能設定群組呼叫收取。 當您部署企業語音時，會安裝及啟用群組通話收取所需的元件。

### <a name="group-call-pickup-deployment-process"></a>群組呼叫收取部署程式

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>所需群組和角色</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>啟用拓撲中的 SEFAUtil resource 工具組工具</p></td>
<td><ol>
<li><p>使用 <strong>New-CsTrustedApplicationPool</strong> Cmdlet 來建立新的受信任應用程式集區。</p></li>
<li><p>使用 <strong>New-CsTrustedApplication</strong> Cmdlet，將 SEFAUtil 工具指定為信任的應用程式。</p></li>
<li><p>執行 <strong>Enable-CsTopology</strong> Cmdlet 以啟用拓撲。</p></li>
<li><p>在步驟1中建立的受信任應用程式集區中的前端伺服器上安裝資源工具組工具。</p></li>
<li><p>執行該 SEFAUtil 以在部署中顯示使用者的「來電轉接」設定，以確認是否正常運作。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">在 Lync Server 2013 中部署 SEFAUtil 工具</a></p></td>
</tr>
<tr class="even">
<td><p>設定通話駐留軌道表格中的呼叫收取號碼範圍</p></td>
<td><p>使用 <strong>New-CSCallParkOrbit</strong> Cmdlet 來建立通話駐留軌道表格中的呼叫收取號碼範圍，並將類型 GroupPickup 指派給電話收取範圍。</p>
<div>

> [!NOTE]  
> 您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看通話駐留軌道表格中的群組呼叫收取號碼範圍。 在 Lync Server 控制台中無法使用群組呼叫收取號碼範圍。


</div>
<div>

> [!NOTE]  
> 為了與現有撥號對應表無縫整合，號碼範圍通常會設定為虛擬擴充區塊。 指派直接向內撥號 (，不支援通話駐留軌道表格中的範圍編號) 數位。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中設定呼叫收取群組號碼</a></p></td>
</tr>
<tr class="odd">
<td><p>將來電收取號碼指派給使用者，並為使用者啟用群組呼叫收取功能</p></td>
<td><p>使用 SEFAUtil resource 成套工具中的/enablegrouppickup 參數，啟用群組呼叫收取，並為使用者指派呼叫收取號碼。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">為 Lync Server 2013 中的使用者啟用群組呼叫收取，並指派群組號碼</a></p></td>
</tr>
<tr class="even">
<td><p>通知使用者他們所指派的來電收取號碼和其他相關數目</p></td>
<td><p>由於任何使用者都可以取回對群組呼叫收取使用者所撥打的電話，因此使用者可能會想要監視一個以上的群組。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">在 Lync Server 2013 中通訊群組呼叫收取指派給使用者</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證群組是否呼叫收取部署</p></td>
<td><p>測試放入和取回通話，以確保您的設定如預期般運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md"> (選用) 驗證 Lync Server 2013 中的群組呼叫收取部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

