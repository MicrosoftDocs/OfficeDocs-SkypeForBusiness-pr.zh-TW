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
ms.openlocfilehash: 8e455cb06c6890bb8925bc35a8d5f4c6775288f8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="f0664-102">在 Lync Server 2013 中監視的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="f0664-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0664-103">_**主題上次修改日期：** 2012年-09-05_</span><span class="sxs-lookup"><span data-stu-id="f0664-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="f0664-104">雖然監視是已安裝，並在每一部前端伺服器上啟動，仍有幾個步驟，您必須進行您可以實際正在收集監視資料的 Microsoft Lync Server 2013 之前。</span><span class="sxs-lookup"><span data-stu-id="f0664-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f0664-105">這些步驟如下面的檢查清單所述：</span><span class="sxs-lookup"><span data-stu-id="f0664-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0664-106">階段</span><span class="sxs-lookup"><span data-stu-id="f0664-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="f0664-107">步驟</span><span class="sxs-lookup"><span data-stu-id="f0664-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="f0664-108">角色與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="f0664-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="f0664-109">文件</span><span class="sxs-lookup"><span data-stu-id="f0664-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0664-110"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="f0664-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="f0664-111">在要作為監控之用的後端資料存放區的電腦上，安裝支援的 Microsoft SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="f0664-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="f0664-112">同時也是本機系統管理員群組成員的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="f0664-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="f0664-113">支援能力指南 》 中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a></span><span class="sxs-lookup"><span data-stu-id="f0664-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="f0664-114">支援能力指南 》 中的 [ <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="f0664-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0664-115"><strong>[建立適當的內部拓撲以支援監控]</strong></span><span class="sxs-lookup"><span data-stu-id="f0664-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="f0664-116">使用 Lync Server 2013 拓撲產生器將監控資料庫至拓撲，然後發佈更新過的拓撲。</span><span class="sxs-lookup"><span data-stu-id="f0664-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="f0664-117">如果要定義拓樸，屬於本機使用者群組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="f0664-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="f0664-118">如果要發行拓樸，屬於網域管理員群組和 RTCUniversalServerAdmins 群組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="f0664-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="f0664-119">部署指南 》 中的 [<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">建立監控儲存區與 Lync Server 2013 中的前端集區的關聯</a></span><span class="sxs-lookup"><span data-stu-id="f0664-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0664-120"><strong>啟用適當的監控設定</strong></span><span class="sxs-lookup"><span data-stu-id="f0664-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="f0664-121">啟用全域範圍和/或網站範圍的詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 監控。</span><span class="sxs-lookup"><span data-stu-id="f0664-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="f0664-122">屬於 RTCUniversalServerAdmins 群組成員的使用者，或被指派提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 存取權的 RBAC 角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="f0664-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="f0664-123">作業指南 》 中的<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">通話詳細記錄及經驗品質設定 Lync Server 2013 中的設定</a></span><span class="sxs-lookup"><span data-stu-id="f0664-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

