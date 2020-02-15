---
title: Lync Server 2013： 的通話許可控制的部署檢查表
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
ms.openlocfilehash: d68f13c636b24729db989f25da7055333968cbbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-08_

若要有效規劃通話許可控制 (CAC)，您必須考量下列事項：

  - 部署 CAC 的先決條件

  - 部署 CAC 所需的資訊，以及您必須做出的組態決策，以便在開始部署時就有完整的必要資訊可供使用。

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>部署通話許可控制的先決條件

在部署通話許可控制之前，您必須已部署 Lync Server 2013 內部伺服器，包括前端集區或 Standard Edition server。

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>通話許可控制的資訊需求

下表摘要說明部署通話許可控制所需的資訊。

### <a name="information-requirements-for-call-admission-control-deployment"></a>部署通話許可控制的資訊需求

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Information</th>
<th>必要資訊的摘要</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>您組織所需的 Lync Server 功能</p></td>
<td><ul>
<li><p>您組織要支援的功能</p></li>
<li><p>要為個別使用者啟用的功能</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">定義 Lync Server 2013 中的 [通話許可控制需求</a></p></td>
</tr>
<tr class="even">
<td><p>要部署的拓撲和元件</p></td>
<td><ul>
<li><p>CAC 相關元件會自動安裝 Lync Server 2013 的一部分</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">定義 Lync Server 2013 中的 [通話許可控制需求</a></p></td>
</tr>
<tr class="odd">
<td><p>系統需求</p></td>
<td><ul>
<li><p>硬體需求</p></li>
<li><p>軟體需求</p></li>
<li><p>組合需求</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">決定您的 Lync Server 2013 的系統需求</a></p></td>
</tr>
<tr class="even">
<td><p>基礎結構需求</p></td>
<td><ul>
<li><p>CAC 不需要特定的基礎結構需求</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中的通話許可控制的基礎結構需求</a></p></td>
</tr>
<tr class="odd">
<td><p>網路介面需求</p></td>
<td><ul>
<li><p>內部與外部介面資訊</p></li>
<li><p>路由資訊 (包括 NextHop 部落格上的資訊<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>，Microsoft Lync Server 團隊的客戶回應管道)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">部署 Lync Server 2013 中的外部使用者存取</a></p></td>
</tr>
<tr class="even">
<td><p>部署策略</p></td>
<td><ul>
<li><p>部署順序</p></li>
<li><p>工作群組或網域</p></li>
<li><p>安全性</p></li>
<li><p>監控和稽核</p></li>
<li><p>硬體考量</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中的通話許可控制的最佳做法</a></p></td>
</tr>
<tr class="odd">
<td><p>部署程序</p></td>
<td><ul>
<li><p>必要條件</p></li>
<li><p>資訊需求</p></li>
<li><p>處理和程序</p></li>
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

