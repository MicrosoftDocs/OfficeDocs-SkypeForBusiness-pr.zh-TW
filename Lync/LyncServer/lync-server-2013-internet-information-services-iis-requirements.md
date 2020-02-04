---
title: Lync Server 2013：Internet Information Services (IIS) 需求
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
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Lync Server 2013 中的 Internet Information Services (IIS) 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

幾個 Lync Server 2013 元件需要網際網路資訊服務（IIS）。 本主題描述支援 Lync Server 所需的特定 IIS 功能。 本節中的主題描述 IIS 特定元件的需求。

在 Windows Server 2008 上啟用 Web 服務器（IIS）角色時，系統會預設安裝各種角色服務。 下表說明在 Windows Server 2008 上啟用 Web 服務器（IIS）角色時，必須安裝的其他角色服務。


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
<td><p>常見的 HTTP 功能</p></td>
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
<td><p>ISAPI 延伸</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 篩選</p></td>
</tr>
<tr class="even">
<td><p>健康與診斷</p></td>
<td><p>記錄工具</p></td>
</tr>
<tr class="odd">
<td><p>健康與診斷</p></td>
<td><p>診斷</p></td>
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
<td><p>IIS 管理腳本與工具</p></td>
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
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性注意事項：</th>
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

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的前端集區與 Standard Edition Server 的 IIS 需求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

