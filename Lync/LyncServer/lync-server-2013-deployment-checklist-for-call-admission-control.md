---
title: Lync Server 2013：通話許可控制的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="9e2a2-102">Lync Server 2013 中的通話許可控制的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="9e2a2-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e2a2-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="9e2a2-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="9e2a2-104">若要有效地規劃通話許可控制（CAC），您需要考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="9e2a2-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="9e2a2-105">部署 CAC 所需的先決條件。</span><span class="sxs-lookup"><span data-stu-id="9e2a2-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="9e2a2-106">您必須在部署之前進行的 CAC 與設定決策所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="9e2a2-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="9e2a2-107">呼叫許可控制的部署先決條件</span><span class="sxs-lookup"><span data-stu-id="9e2a2-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="9e2a2-108">您必須先部署 Lync Server 2013 內部伺服器（包括前端池或標準版伺服器），才能部署呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="9e2a2-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="9e2a2-109">通話許可控制的資訊需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="9e2a2-110">下表摘要列出部署通話許可控制所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="9e2a2-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="9e2a2-111">呼叫許可控制部署的資訊需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e2a2-112">錯誤資訊</span><span class="sxs-lookup"><span data-stu-id="9e2a2-112">Information</span></span></th>
<th><span data-ttu-id="9e2a2-113">所需資訊摘要</span><span class="sxs-lookup"><span data-stu-id="9e2a2-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="9e2a2-114">文件</span><span class="sxs-lookup"><span data-stu-id="9e2a2-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e2a2-115">貴組織所需的 Lync Server 功能</span><span class="sxs-lookup"><span data-stu-id="9e2a2-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-116">貴組織支援的功能</span><span class="sxs-lookup"><span data-stu-id="9e2a2-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-117">針對個別使用者啟用的功能</span><span class="sxs-lookup"><span data-stu-id="9e2a2-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定義通話許可控制需求</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e2a2-119">要部署的拓撲與元件</span><span class="sxs-lookup"><span data-stu-id="9e2a2-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-120">在 Lync Server 2013 中會自動安裝 CAC 相關元件</span><span class="sxs-lookup"><span data-stu-id="9e2a2-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定義通話許可控制需求</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e2a2-122">系統需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-123">硬體需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-124">軟體需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-125">Collocation 需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-126"><a href="lync-server-2013-determining-your-system-requirements.md">判定 Lync Server 2013 的系統需求</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e2a2-127">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-128">CAC 不需要任何特定的基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中的通話許可控制的基礎結構需求</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e2a2-130">網路介面需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-131">內部和外部介面資訊</span><span class="sxs-lookup"><span data-stu-id="9e2a2-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-132">路由資訊（包括來自 Microsoft Lync Server 團隊客戶<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>回應頻道之 NextHop 博客的相關資訊）</span><span class="sxs-lookup"><span data-stu-id="9e2a2-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-133"><a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e2a2-134">部署策略</span><span class="sxs-lookup"><span data-stu-id="9e2a2-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-135">部署順序</span><span class="sxs-lookup"><span data-stu-id="9e2a2-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-136">工作組或網域</span><span class="sxs-lookup"><span data-stu-id="9e2a2-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-137">安全性</span><span class="sxs-lookup"><span data-stu-id="9e2a2-137">Security</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-138">監控與審計</span><span class="sxs-lookup"><span data-stu-id="9e2a2-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-139">硬體考慮</span><span class="sxs-lookup"><span data-stu-id="9e2a2-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中通話許可控制的最佳做法</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e2a2-141">部署程式</span><span class="sxs-lookup"><span data-stu-id="9e2a2-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9e2a2-142">先決條件</span><span class="sxs-lookup"><span data-stu-id="9e2a2-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-143">資訊需求</span><span class="sxs-lookup"><span data-stu-id="9e2a2-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="9e2a2-144">程式與程式</span><span class="sxs-lookup"><span data-stu-id="9e2a2-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9e2a2-145"><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中設定通話許可控制</a></span><span class="sxs-lookup"><span data-stu-id="9e2a2-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

