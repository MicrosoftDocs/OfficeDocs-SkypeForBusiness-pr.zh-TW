---
title: Lync Server 2013：群組呼叫挑選的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中群組呼叫挑選的部署程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

本節概要說明部署群組呼叫挑選時所涉及的步驟。 您必須先使用企業語音部署企業版或標準版，才能設定群組呼叫挑選。 當您部署企業語音時，會安裝並啟用群組通話挑選所需的元件。

### <a name="group-call-pickup-deployment-process"></a>群組呼叫進行挑選部署程式

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>必要的群組和角色</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在拓撲中啟用 SEFAUtil 資源套件工具</p></td>
<td><ol>
<li><p>使用<strong>新的 CsTrustedApplicationPool</strong> Cmdlet 來建立新的受信任的應用程式池。</p></li>
<li><p>使用<strong>新的 CsTrustedApplication</strong> Cmdlet，將 SEFAUtil 工具指定為受信任的應用程式。</p></li>
<li><p>執行<strong>enable-CsTopology</strong> Cmdlet 來啟用拓撲。</p></li>
<li><p>在步驟1中建立的受信任的應用程式池中，在前端伺服器上安裝資源套件工具。</p></li>
<li><p>執行此程式以驗證 SEFAUtil 是否正常運作，只要執行它，即可在部署中顯示使用者的來電轉接設定。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">在 Lync Server 2013 中部署 SEFAUtil 工具</a></p></td>
</tr>
<tr class="even">
<td><p>在 [呼叫公園軌道軌道] 表格中設定呼叫挑選編號範圍</p></td>
<td><p>使用<strong>CSCallParkOrbit</strong> Cmdlet，在 [通話駐留軌道] 表格中建立呼叫挑選編號範圍，並將 [呼叫拾取] 範圍指派給 type GroupPickup。</p>
<div>

> [!NOTE]  
> 您必須使用 Lync Server 管理命令介面來建立、修改、移除及查看 [通話寄存軌道] 表格中的 [群組呼叫挑選號碼] 範圍。 在 Lync Server [控制台] 中無法使用 [群組呼叫挑選號碼] 範圍。


</div>
<div>

> [!NOTE]  
> 若要與現有的撥號方案進行無縫整合，數位範圍通常會設定為虛擬延伸區塊。 不支援在 [通話駐留軌道] 表格中，將直向內撥（已有）數位指派為範圍數位。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中設定呼叫挑選群組號碼</a></p></td>
</tr>
<tr class="odd">
<td><p>指派呼叫挑選號碼給使用者，並為使用者啟用群組呼叫分揀</p></td>
<td><p>在 SEFAUtil 資源套件工具中使用/enablegrouppickup 參數，以啟用群組通話分揀，並為使用者指派呼叫挑選號碼。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">在 Lync Server 2013 中為使用者啟用群組呼叫挑選，並指派群組號碼</a></p></td>
</tr>
<tr class="even">
<td><p>通知使用者已指派的電話提貨號碼和任何其他感興趣的號碼</p></td>
<td><p>因為任何使用者都可以撥打對群組呼叫使用者所做的通話，所以使用者可能想要監視一個以上的群組。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">在 Lync Server 2013 中將群組呼叫挑選指派給使用者</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證您的群組呼叫裝貨部署</p></td>
<td><p>測試放及檢索通話，以確保您的設定如預期的那樣正常運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">可選在 Lync Server 2013 中驗證群組呼叫裝貨部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

