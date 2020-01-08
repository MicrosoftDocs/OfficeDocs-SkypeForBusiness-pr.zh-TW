---
title: Lync Server 2013：監控的部署檢查表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cbf14920ef0103f2d6e8aa6088a2c0b35e17654
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中監控的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

雖然已在每個前端伺服器上安裝並啟用監視，但您仍必須採取幾個步驟，才能實際收集 Microsoft Lync Server 2013 的監視資料。 以下是下列檢查清單中所述的步驟：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>分</p></td>
<td><p>步驟</p></td>
<td><p>角色與群組成員資格</p></td>
<td><p>文件</p></td>
</tr>
<tr class="even">
<td><p><strong>安裝必備的硬體和軟體</strong></p></td>
<td><p>在電腦上安裝受支援的 Microsoft SQL Server 版本，該電腦將充當要監視的後端資料存放區。</p></td>
<td><p>同時也是本機管理員群組成員的網域使用者。</p></td>
<td><p>支援指南中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></p>
<p>支援指南中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>建立適當的內部拓朴以支援監視</strong></p></td>
<td><p>使用 Lync Server 2013 拓撲建立器新增監視資料庫至拓撲結構，然後發佈更新後的拓撲。</p></td>
<td><p>若要定義拓撲，該使用者是 [本機使用者] 群組的成員。</p>
<p>如果是 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組，則會發佈拓撲（屬於成員的使用者）。</p></td>
<td><p>在部署指南的<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013 中，將監視存放與前端池關聯</a></p></td>
</tr>
<tr class="even">
<td><p><strong>啟用適當的監視設定</strong></p></td>
<td><p>啟用 [呼叫詳細資料錄製（CDR）] 和/或 [（QoE）] 在全域及/或網站範圍內進行監控。</p></td>
<td><p>是 RTCUniversalServerAdmins 群組成員的使用者，或已被指派 RBAC 角色的使用者，可提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 的存取權。</p></td>
<td><p>在 [作業指南] 中<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">設定 Lync Server 2013 的通話詳細資料錄製和經驗品質設定</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

