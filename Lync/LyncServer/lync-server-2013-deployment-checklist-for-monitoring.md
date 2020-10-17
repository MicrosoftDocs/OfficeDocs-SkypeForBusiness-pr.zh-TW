---
title: Lync Server 2013：監控的部署檢查清單
description: Lync Server 2013：監控的部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568321"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中監控的部署檢查清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

雖然已在每一部前端伺服器上安裝並啟用監視，但您必須先執行幾個步驟，才能實際收集 Microsoft Lync Server 2013 的監控資料。 這些步驟如下面的檢查清單所述：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>階段</p></td>
<td><p>步驟</p></td>
<td><p>角色與群組成員資格</p></td>
<td><p>文件</p></td>
</tr>
<tr class="even">
<td><p><strong>安裝必備硬體和軟體</strong></p></td>
<td><p>在要作為監控之用的後端資料存放區的電腦上，安裝支援的 Microsoft SQL Server 版本。</p></td>
<td><p>同時也是本機系統管理員群組成員的網域使用者。</p></td>
<td><p>支援指南中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援硬體</a></p>
<p>支援指南<a href="lync-server-2013-server-software-and-infrastructure-support.md">中的 Lync server 2013 中的伺服器軟體和基礎結構支援</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>[建立適當的內部拓撲以支援監控]</strong></p></td>
<td><p>使用 Lync Server 2013 拓撲產生器將監控資料庫新增至拓撲，然後發佈更新的拓撲。</p></td>
<td><p>如果要定義拓樸，屬於本機使用者群組成員的使用者。</p>
<p>如果要發行拓樸，屬於網域管理員群組和 RTCUniversalServerAdmins 群組成員的使用者。</p></td>
<td><p>在部署指南中，使<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">監控存放區與 Lync Server 2013 中的前端集區產生關聯</a></p></td>
</tr>
<tr class="even">
<td><p><strong>啟用適當的監控設定</strong></p></td>
<td><p>啟用全域範圍和/或網站範圍的詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 監控。</p></td>
<td><p>屬於 RTCUniversalServerAdmins 群組成員的使用者，或被指派提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 存取權的 RBAC 角色的使用者。</p></td>
<td><p>在作業指南中<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">設定 Lync Server 2013 中的詳細通話記錄及經驗品質設定</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

