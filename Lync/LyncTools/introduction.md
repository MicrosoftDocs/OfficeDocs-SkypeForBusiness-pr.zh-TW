---
title: 簡介
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 893205127b6b1ccba958a0882c3aa0d1360a7c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>簡介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

Lync Server 2013 的應力和效能工具（稱為 LyncPerfTool）可以模擬使用者載入下列類型：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>立即訊息（IM）與目前狀態</p></td>
<td><p>音訊會議</p></td>
</tr>
<tr class="even">
<td><p>應用程式共用</p></td>
<td><p>[語音 over IP （VoIP）]，包括公用交換電話網絡（PSTN）模擬</p></td>
</tr>
<tr class="odd">
<td><p>Web Access 用戶端會議</p></td>
<td><p>Microsoft Lync 2013 助理</p></td>
</tr>
<tr class="even">
<td><p>回應群組</p></td>
<td><p>通訊群組清單展開</p></td>
</tr>
<tr class="odd">
<td><p>通訊錄下載與通訊錄查詢</p></td>
<td><p>增強型9-1-1 （E9-1）通話和位置設定檔（撥號方案）</p></td>
</tr>
<tr class="even">
<td><p>重視</p></td>
<td><p>從會議中查看多個資料流程</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Lync Server 2013 應力和效能工具僅支援透過高級設定進行跨池負載產生與同盟。

此工具也不會模擬下列用戶端的使用者負載：

  - Office Live Meeting 2007

  - Lync 2013 持續聊天

因此，Lync Server 2013 的應力和效能工具將不支援測試下列元件：

  - Lync 2013 持續聊天

  - Exchange 整合案例

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 應力和效能工具隨附的應用程式和檔案

Lync Server 2013 應力和效能工具組含下列應用程式：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>工具箱</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool</p></td>
<td><p>Lync Server 2013 使用者提供工具。 此工具可用來建立使用者和連絡人。</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator</p></td>
<td><p>Lync Server 2013 載入組態工具。 此工具可用來設定要模擬的使用者負載特性。</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool</p></td>
<td><p>Lync Server 2013 應力和效能工具。 LyncPerfTool 是類比使用者負載的工具。</p></td>
</tr>
<tr class="even">
<td><p>預設的 tmx</p></td>
<td><p>使用 Lync Server 2013 記錄工具時，必須使用預設的 tmx。</p></td>
</tr>
<tr class="odd">
<td><p>配置腳本範例</p></td>
<td><p>這些範例是用來根據特定案例來設定執行負載測試的拓朴</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

