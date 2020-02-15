---
title: 監控的 Lync Server 2013： 部署檢查清單
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
ms.openlocfilehash: 26fd0c34d51445902e7f00439dd210ddfd64f392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中監視的部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-05_

雖然監視是已安裝，並在每一部前端伺服器上啟動，仍有幾個步驟，您必須進行您可以實際正在收集監視資料的 Microsoft Lync Server 2013 之前。 這些步驟如下面的檢查清單所述：


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
<td><p>支援能力指南 》 中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a></p>
<p>支援能力指南 》 中的 [ <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>[建立適當的內部拓撲以支援監控]</strong></p></td>
<td><p>使用 Lync Server 2013 拓撲產生器將監控資料庫至拓撲，然後發佈更新過的拓撲。</p></td>
<td><p>如果要定義拓樸，屬於本機使用者群組成員的使用者。</p>
<p>如果要發行拓樸，屬於網域管理員群組和 RTCUniversalServerAdmins 群組成員的使用者。</p></td>
<td><p>部署指南 》 中的 [<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">建立監控儲存區與 Lync Server 2013 中的前端集區的關聯</a></p></td>
</tr>
<tr class="even">
<td><p><strong>啟用適當的監控設定</strong></p></td>
<td><p>啟用全域範圍和/或網站範圍的詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 監控。</p></td>
<td><p>屬於 RTCUniversalServerAdmins 群組成員的使用者，或被指派提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 存取權的 RBAC 角色的使用者。</p></td>
<td><p>作業指南 》 中的<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">通話詳細記錄及經驗品質設定 Lync Server 2013 中的設定</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

