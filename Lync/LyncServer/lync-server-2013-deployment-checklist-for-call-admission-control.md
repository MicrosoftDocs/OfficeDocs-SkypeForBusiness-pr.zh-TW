---
title: Lync Server 2013：通話許可控制的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制的部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

若要有效地規劃通話許可控制（CAC），您需要考慮下列事項：

  - 部署 CAC 所需的先決條件。

  - 您必須在部署之前進行的 CAC 與設定決策所需的資訊。

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>呼叫許可控制的部署先決條件

您必須先部署 Lync Server 2013 內部伺服器（包括前端池或標準版伺服器），才能部署呼叫許可控制。

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>通話許可控制的資訊需求

下表摘要列出部署通話許可控制所需的資訊。

### <a name="information-requirements-for-call-admission-control-deployment"></a>呼叫許可控制部署的資訊需求

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>錯誤資訊</th>
<th>所需資訊摘要</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>貴組織所需的 Lync Server 功能</p></td>
<td><ul>
<li><p>貴組織支援的功能</p></li>
<li><p>針對個別使用者啟用的功能</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定義通話許可控制需求</a></p></td>
</tr>
<tr class="even">
<td><p>要部署的拓撲與元件</p></td>
<td><ul>
<li><p>在 Lync Server 2013 中會自動安裝 CAC 相關元件</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定義通話許可控制需求</a></p></td>
</tr>
<tr class="odd">
<td><p>系統需求</p></td>
<td><ul>
<li><p>硬體需求</p></li>
<li><p>軟體需求</p></li>
<li><p>Collocation 需求</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">判定 Lync Server 2013 的系統需求</a></p></td>
</tr>
<tr class="even">
<td><p>基礎結構需求</p></td>
<td><ul>
<li><p>CAC 不需要任何特定的基礎結構需求</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中的通話許可控制的基礎結構需求</a></p></td>
</tr>
<tr class="odd">
<td><p>網路介面需求</p></td>
<td><ul>
<li><p>內部和外部介面資訊</p></li>
<li><p>路由資訊（包括來自 Microsoft Lync Server 團隊客戶<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>回應頻道之 NextHop 博客的相關資訊）</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部使用者存取</a></p></td>
</tr>
<tr class="even">
<td><p>部署策略</p></td>
<td><ul>
<li><p>部署順序</p></li>
<li><p>工作組或網域</p></li>
<li><p>安全性</p></li>
<li><p>監控與審計</p></li>
<li><p>硬體考慮</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中通話許可控制的最佳做法</a></p></td>
</tr>
<tr class="odd">
<td><p>部署程式</p></td>
<td><ul>
<li><p>先決條件</p></li>
<li><p>資訊需求</p></li>
<li><p>程式與程式</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中設定通話許可控制</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

