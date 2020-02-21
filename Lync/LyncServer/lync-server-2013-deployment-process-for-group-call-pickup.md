---
title: Lync Server 2013： 部署程序的群組來電接聽
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
ms.openlocfilehash: d0ed92300ae3445019b7b6fc0bba4d73b91c980e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>部署程序的 Lync Server 2013 中的 [群組來電接聽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-25_

本節提供部署群組來電接聽的相關步驟的概觀。 設定群組來電接聽之前，您必須部署 Enterprise Edition 或 Standard Edition 與 Enterprise Voice。 群組來電接聽所需的元件會安裝並啟用當您部署企業語音。

### <a name="group-call-pickup-deployment-process"></a>群組通話收取部署程序

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
<td><p>啟用拓撲的 SEFAUtil resource kit 工具</p></td>
<td><ol>
<li><p>使用<strong>New-cstrustedapplicationpool</strong> cmdlet 來建立新的受信任的應用程式集區。</p></li>
<li><p>若要指定 SEFAUtil 工具為信任的應用程式使用<strong>New-cstrustedapplication</strong> cmdlet。</p></li>
<li><p>執行<strong>Enable-cstopology</strong> cmdlet 來啟用拓撲。</p></li>
<li><p>在步驟 1 中建立信任的應用程式集區中以前端伺服器上安裝 resource kit 工具。</p></li>
<li><p>確認 SEFAUtil 正常執行藉由執行以顯示來電轉接的部署中的使用者設定。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">部署 Lync Server 2013 的 SEFAUtil 工具</a></p></td>
</tr>
<tr class="even">
<td><p>設定通話駐留軌道表中的呼叫收取的號碼範圍</p></td>
<td><p>使用<strong>New-cscallparkorbit</strong> cmdlet 來建立通話駐留軌道表中的通話收取] 目錄的數字範圍和指派通話收取範圍類型 GroupPickup。</p>
<div>

> [!NOTE]  
> 您必須使用 Lync Server 管理命令介面來建立、 修改、 移除和檢視通話駐留軌道表中的群組來電接聽的號碼範圍。 群組呼叫收取號碼範圍不在 Lync Server Control Panel 中使用。


</div>
<div>

> [!NOTE]  
> 與現有的撥號對應表計劃的緊密整合，針對號碼範圍通常設定為虛擬分機區塊。 不支援將直接向內撥號 (DID) 號碼指派為通話駐留軌道表中的 range 數字。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 中設定呼叫收取群組號碼</a></p></td>
</tr>
<tr class="odd">
<td><p>呼叫收取號碼指派給使用者，並為使用者啟用群組來電接聽</p></td>
<td><p>若要啟用群組來電接聽，並指派使用者的通話收取數字，SEFAUtil resource kit 工具中使用 /enablegrouppickup 參數。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">啟用群組來電接聽 Lync Server 2013 中的使用者並指派群組編號</a></p></td>
</tr>
<tr class="even">
<td><p>通知使用者其指派的通話收取] 目錄的數字和其他任何數字的利息</p></td>
<td><p>因為任何使用者可以擷取對群組來電接聽使用者的呼叫，使用者可能會想要監視多個群組。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">通訊群組來電接聽指派給 Lync Server 2013 中的使用者</a></p></td>
</tr>
<tr class="odd">
<td><p>確認群組來電接聽部署</p></td>
<td><p>測試放置，並擷取通話，請確定您的設定如預期般運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">（選用）確認 Lync Server 2013 中的群組來電接聽部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

