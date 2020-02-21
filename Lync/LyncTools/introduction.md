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
ms.openlocfilehash: 912c6a1704438106a3ffbb178d9f03a536489757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a>簡介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

Lync Server 2013 壓力及效能工具 （稱為 LyncPerfTool） 可以模擬下列類型的使用者負載：


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
<td><p>語音 over IP (VoIP)，包括公用交換的電話網路 (PSTN) 模擬</p></td>
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
<td><p>增強型 9-1-1 (E9-1-1) 呼叫和位置設定檔 （撥號對應表）</p></td>
</tr>
<tr class="even">
<td><p>MultiView</p></td>
<td><p>檢視從會議的多個資料流</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Lync Server 2013 壓力及效能工具支援跨集區負載產生和進階設定只透過同盟。

此工具也 generator 無法模擬使用者負載下的用戶端：

  - Office Live Meeting 2007

  - Lync 2013 常設聊天室

因此，[Lync Server 2013 壓力及效能工具將未支援測試下列元件：

  - Lync 2013 常設聊天室

  - Exchange 整合案例

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>應用程式及隨附的 Lync Server 2013 壓力及效能工具的檔案

在 [Lync Server 2013 壓力及效能工具包含下列應用程式：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>工具</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool.exe</p></td>
<td><p>Lync Server 2013 使用者佈建的工具。 這項工具用來建立使用者和連絡人。</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator.exe</p></td>
<td><p>為 Lync Server 2013 負載組態工具。 這項工具用來設定模擬的使用者負載的特性。</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool.exe</p></td>
<td><p>[Lync Server 2013 壓力及效能工具。 LyncPerfTool 是模擬的使用者負載的工具。</p></td>
</tr>
<tr class="even">
<td><p>Default.tmx</p></td>
<td><p>若要使用 Lync Server 2013 記錄工具，才 Default.tmx。</p></td>
</tr>
<tr class="odd">
<td><p>佈建指令碼的範例</p></td>
<td><p>下列範例會用來設定執行負載測試，根據特定案例的拓撲</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

