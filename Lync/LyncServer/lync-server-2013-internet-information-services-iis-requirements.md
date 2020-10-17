---
title: Lync Server 2013： Internet Information Services (IIS) 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b0c1c9966945554af6d1d9cec02a17dd884a857
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498480"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Lync Server 2013 中的網際網路資訊服務 (IIS) 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

有些 Lync Server 2013 元件需要 Internet Information Services (IIS) 。 本主題說明支援 Lync Server 所需的特定 IIS 功能。 本節中的主題則說明 IIS 特定元件的需求。

當 Windows Server 2008 上啟用 Web 伺服器 (IIS) 角色時，預設會安裝各種角色服務。下表說明當 Windows Server 2008 上啟用 Web 伺服器 (IIS) 角色時，必須安裝的其他角色服務。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>角色服務</th>
<th>功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>一般 HTTP 功能</p></td>
<td><p>HTTP 重新導向</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>.NET 擴充性</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 擴充程式</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 篩選器</p></td>
</tr>
<tr class="even">
<td><p>健康情況及診斷</p></td>
<td><p>記錄工具</p></td>
</tr>
<tr class="odd">
<td><p>健康情況及診斷</p></td>
<td><p>跟蹤</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>基本驗證</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>Windows 驗證</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理指令碼及工具</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 6 管理相容性</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全性附注：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>如果您在 Windows Server 2008 作業系統上使用 IIS 7.0，Lync Server 安裝程式會在 IIS 中停用核心模式驗證。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中前端集區與 Standard Edition server 的 IIS 需求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

