---
title: Lync Server 2013： 的通話許可控制的部署檢查表
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
ms.openlocfilehash: d68f13c636b24729db989f25da7055333968cbbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="60ef7-102">Lync Server 2013 中的通話許可控制的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="60ef7-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60ef7-103">_**主題上次修改日期：** 2012年-10-08_</span><span class="sxs-lookup"><span data-stu-id="60ef7-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="60ef7-104">若要有效規劃通話許可控制 (CAC)，您必須考量下列事項：</span><span class="sxs-lookup"><span data-stu-id="60ef7-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="60ef7-105">部署 CAC 的先決條件</span><span class="sxs-lookup"><span data-stu-id="60ef7-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="60ef7-106">部署 CAC 所需的資訊，以及您必須做出的組態決策，以便在開始部署時就有完整的必要資訊可供使用。</span><span class="sxs-lookup"><span data-stu-id="60ef7-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="60ef7-107">部署通話許可控制的先決條件</span><span class="sxs-lookup"><span data-stu-id="60ef7-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="60ef7-108">在部署通話許可控制之前，您必須已部署 Lync Server 2013 內部伺服器，包括前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="60ef7-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="60ef7-109">通話許可控制的資訊需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="60ef7-110">下表摘要說明部署通話許可控制所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="60ef7-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="60ef7-111">部署通話許可控制的資訊需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60ef7-112">Information</span><span class="sxs-lookup"><span data-stu-id="60ef7-112">Information</span></span></th>
<th><span data-ttu-id="60ef7-113">必要資訊的摘要</span><span class="sxs-lookup"><span data-stu-id="60ef7-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="60ef7-114">文件</span><span class="sxs-lookup"><span data-stu-id="60ef7-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60ef7-115">您組織所需的 Lync Server 功能</span><span class="sxs-lookup"><span data-stu-id="60ef7-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-116">您組織要支援的功能</span><span class="sxs-lookup"><span data-stu-id="60ef7-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="60ef7-117">要為個別使用者啟用的功能</span><span class="sxs-lookup"><span data-stu-id="60ef7-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">定義 Lync Server 2013 中的 [通話許可控制需求</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ef7-119">要部署的拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="60ef7-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-120">CAC 相關元件會自動安裝 Lync Server 2013 的一部分</span><span class="sxs-lookup"><span data-stu-id="60ef7-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">定義 Lync Server 2013 中的 [通話許可控制需求</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ef7-122">系統需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-123">硬體需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="60ef7-124">軟體需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="60ef7-125">組合需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-126"><a href="lync-server-2013-determining-your-system-requirements.md">決定您的 Lync Server 2013 的系統需求</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ef7-127">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-128">CAC 不需要特定的基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中的通話許可控制的基礎結構需求</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ef7-130">網路介面需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-131">內部與外部介面資訊</span><span class="sxs-lookup"><span data-stu-id="60ef7-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="60ef7-132">路由資訊 (包括 NextHop 部落格上的資訊<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>，Microsoft Lync Server 團隊的客戶回應管道)</span><span class="sxs-lookup"><span data-stu-id="60ef7-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-133"><a href="lync-server-2013-deploying-external-user-access.md">部署 Lync Server 2013 中的外部使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60ef7-134">部署策略</span><span class="sxs-lookup"><span data-stu-id="60ef7-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-135">部署順序</span><span class="sxs-lookup"><span data-stu-id="60ef7-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="60ef7-136">工作群組或網域</span><span class="sxs-lookup"><span data-stu-id="60ef7-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="60ef7-137">安全性</span><span class="sxs-lookup"><span data-stu-id="60ef7-137">Security</span></span></p></li>
<li><p><span data-ttu-id="60ef7-138">監控和稽核</span><span class="sxs-lookup"><span data-stu-id="60ef7-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="60ef7-139">硬體考量</span><span class="sxs-lookup"><span data-stu-id="60ef7-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中的通話許可控制的最佳做法</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60ef7-141">部署程序</span><span class="sxs-lookup"><span data-stu-id="60ef7-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="60ef7-142">必要條件</span><span class="sxs-lookup"><span data-stu-id="60ef7-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="60ef7-143">資訊需求</span><span class="sxs-lookup"><span data-stu-id="60ef7-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="60ef7-144">處理和程序</span><span class="sxs-lookup"><span data-stu-id="60ef7-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="60ef7-145"><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中設定通話許可控制</a></span><span class="sxs-lookup"><span data-stu-id="60ef7-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

