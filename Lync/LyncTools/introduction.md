---
title: 簡介
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 354f28948578be528787928fd4e0874f6ff8e5fa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a>簡介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

Lync Server 2013 應力和效能工具（稱為 LyncPerfTool）可以模擬下列類型的使用者負載：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>立即訊息 (IM) 和目前狀態</p></td>
<td><p>音訊會議</p></td>
</tr>
<tr class="even">
<td><p>應用程式共用</p></td>
<td><p>Voice over IP （VoIP），包含公用交換電話網路（PSTN）類比</p></td>
</tr>
<tr class="odd">
<td><p>Web Access 用戶端會議</p></td>
<td><p>Microsoft Lync 2013 語音應答</p></td>
</tr>
<tr class="even">
<td><p>回應群組</p></td>
<td><p>通訊群組清單延伸</p></td>
</tr>
<tr class="odd">
<td><p>通訊錄下載和通訊錄查詢</p></td>
<td><p>增強型9-1-1 （E9-1-1）通話和位置設定檔（撥號對應表）</p></td>
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


Lync Server 2013 應力和效能工具僅支援透過高級設定進行跨集區的負載產生及同盟。

工具也不會為下列用戶端模擬使用者負載：

  - Office Live Meeting 2007

  - Lync 2013 持續聊天

因此，Lync Server 2013 的壓力和效能工具不支援測試下列元件：

  - Lync 2013 持續聊天

  - Exchange 整合案例

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 壓力和效能工具隨附的應用程式和檔案

Lync Server 2013 應力和效能工具組含下列應用程式：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>工具</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool.exe</p></td>
<td><p>Lync Server 2013 使用者布建工具。 此工具用來建立使用者和連絡人。</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator.exe</p></td>
<td><p>Lync Server 2013 載入設定工具。 此工具用來設定要模擬之使用者負載的特性。</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool.exe</p></td>
<td><p>Lync Server 2013 壓力和效能工具。 LyncPerfTool 是一種模擬使用者負載的工具。</p></td>
</tr>
<tr class="even">
<td><p>預設的 tmx</p></td>
<td><p>使用 Lync Server 2013 記錄工具時，必須使用預設 tmx。</p></td>
</tr>
<tr class="odd">
<td><p>範例布建腳本</p></td>
<td><p>這些範例是根據特定案例，用來設定執行負載測試的拓撲</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

