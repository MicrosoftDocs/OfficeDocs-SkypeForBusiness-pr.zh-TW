---
title: Lync Server 2013：監控的部署檢查清單
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
ms.openlocfilehash: f6cf28170044b7580fd07321b081e9366b056cd1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522760"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="21cd3-102">Lync Server 2013 中監控的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="21cd3-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21cd3-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="21cd3-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="21cd3-104">雖然已在每一部前端伺服器上安裝並啟用監視，但您必須先執行幾個步驟，才能實際收集 Microsoft Lync Server 2013 的監控資料。</span><span class="sxs-lookup"><span data-stu-id="21cd3-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="21cd3-105">這些步驟如下面的檢查清單所述：</span><span class="sxs-lookup"><span data-stu-id="21cd3-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21cd3-106">階段</span><span class="sxs-lookup"><span data-stu-id="21cd3-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="21cd3-107">步驟</span><span class="sxs-lookup"><span data-stu-id="21cd3-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="21cd3-108">角色與群組成員資格</span><span class="sxs-lookup"><span data-stu-id="21cd3-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="21cd3-109">文件</span><span class="sxs-lookup"><span data-stu-id="21cd3-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21cd3-110"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="21cd3-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="21cd3-111">在要作為監控之用的後端資料存放區的電腦上，安裝支援的 Microsoft SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="21cd3-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="21cd3-112">同時也是本機系統管理員群組成員的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="21cd3-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="21cd3-113">支援指南中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援硬體</a></span><span class="sxs-lookup"><span data-stu-id="21cd3-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="21cd3-114">支援指南<a href="lync-server-2013-server-software-and-infrastructure-support.md">中的 Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="21cd3-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21cd3-115"><strong>[建立適當的內部拓撲以支援監控]</strong></span><span class="sxs-lookup"><span data-stu-id="21cd3-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="21cd3-116">使用 Lync Server 2013 拓撲產生器將監控資料庫新增至拓撲，然後發佈更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="21cd3-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="21cd3-117">如果要定義拓樸，屬於本機使用者群組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="21cd3-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="21cd3-118">如果要發行拓樸，屬於網域管理員群組和 RTCUniversalServerAdmins 群組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="21cd3-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="21cd3-119">在部署指南中，使<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">監控存放區與 Lync Server 2013 中的前端集區產生關聯</a></span><span class="sxs-lookup"><span data-stu-id="21cd3-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21cd3-120"><strong>啟用適當的監控設定</strong></span><span class="sxs-lookup"><span data-stu-id="21cd3-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="21cd3-121">啟用全域範圍和/或網站範圍的詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 監控。</span><span class="sxs-lookup"><span data-stu-id="21cd3-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="21cd3-122">屬於 RTCUniversalServerAdmins 群組成員的使用者，或被指派提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 存取權的 RBAC 角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="21cd3-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="21cd3-123">在作業指南中<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">設定 Lync Server 2013 中的詳細通話記錄及經驗品質設定</a></span><span class="sxs-lookup"><span data-stu-id="21cd3-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

