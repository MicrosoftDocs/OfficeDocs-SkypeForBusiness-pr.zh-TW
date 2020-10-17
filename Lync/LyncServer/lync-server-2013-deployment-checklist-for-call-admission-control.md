---
title: Lync Server 2013：通話許可控制的部署檢查清單
description: Lync Server 2013：通話許可控制的部署檢查清單。
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
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557689"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="ef347-103">Lync Server 2013 中的通話許可控制的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="ef347-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef347-104">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="ef347-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="ef347-105">若要有效規劃通話許可控制 (CAC)，您必須考量下列事項：</span><span class="sxs-lookup"><span data-stu-id="ef347-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="ef347-106">部署 CAC 的先決條件</span><span class="sxs-lookup"><span data-stu-id="ef347-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="ef347-107">部署 CAC 所需的資訊，以及您必須做出的組態決策，以便在開始部署時就有完整的必要資訊可供使用。</span><span class="sxs-lookup"><span data-stu-id="ef347-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="ef347-108">部署通話許可控制的先決條件</span><span class="sxs-lookup"><span data-stu-id="ef347-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="ef347-109">在您部署通話許可控制之前，您必須已部署 Lync Server 2013 內部伺服器，包括前端集區或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="ef347-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="ef347-110">通話許可控制的資訊需求</span><span class="sxs-lookup"><span data-stu-id="ef347-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="ef347-111">下表摘要說明部署通話許可控制所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="ef347-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="ef347-112">部署通話許可控制的資訊需求</span><span class="sxs-lookup"><span data-stu-id="ef347-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef347-113">資訊</span><span class="sxs-lookup"><span data-stu-id="ef347-113">Information</span></span></th>
<th><span data-ttu-id="ef347-114">必要資訊的摘要</span><span class="sxs-lookup"><span data-stu-id="ef347-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="ef347-115">文件</span><span class="sxs-lookup"><span data-stu-id="ef347-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef347-116">組織所需的 Lync Server 功能</span><span class="sxs-lookup"><span data-stu-id="ef347-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-117">您組織要支援的功能</span><span class="sxs-lookup"><span data-stu-id="ef347-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="ef347-118">要為個別使用者啟用的功能</span><span class="sxs-lookup"><span data-stu-id="ef347-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定義通話許可控制需求</a></span><span class="sxs-lookup"><span data-stu-id="ef347-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef347-120">要部署的拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="ef347-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-121">在 Lync Server 2013 中會自動安裝 CAC 相關元件</span><span class="sxs-lookup"><span data-stu-id="ef347-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定義通話許可控制需求</a></span><span class="sxs-lookup"><span data-stu-id="ef347-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef347-123">系統需求</span><span class="sxs-lookup"><span data-stu-id="ef347-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-124">硬體需求</span><span class="sxs-lookup"><span data-stu-id="ef347-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="ef347-125">軟體需求</span><span class="sxs-lookup"><span data-stu-id="ef347-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="ef347-126">組合需求</span><span class="sxs-lookup"><span data-stu-id="ef347-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-127"><a href="lync-server-2013-determining-your-system-requirements.md">決定 Lync Server 2013 的系統需求</a></span><span class="sxs-lookup"><span data-stu-id="ef347-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef347-128">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="ef347-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-129">CAC 不需要特定的基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="ef347-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中通話許可控制的基礎結構需求</a></span><span class="sxs-lookup"><span data-stu-id="ef347-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef347-131">網路介面需求</span><span class="sxs-lookup"><span data-stu-id="ef347-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-132">內部與外部介面資訊</span><span class="sxs-lookup"><span data-stu-id="ef347-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="ef347-133">路由資訊 (<a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> ，包含 Microsoft Lync Server 小組客戶回應通道中 NextHop 博客的資訊) </span><span class="sxs-lookup"><span data-stu-id="ef347-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-134"><a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部使用者存取</a></span><span class="sxs-lookup"><span data-stu-id="ef347-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef347-135">部署策略</span><span class="sxs-lookup"><span data-stu-id="ef347-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-136">部署順序</span><span class="sxs-lookup"><span data-stu-id="ef347-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="ef347-137">工作群組或網域</span><span class="sxs-lookup"><span data-stu-id="ef347-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="ef347-138">安全性</span><span class="sxs-lookup"><span data-stu-id="ef347-138">Security</span></span></p></li>
<li><p><span data-ttu-id="ef347-139">監控和稽核</span><span class="sxs-lookup"><span data-stu-id="ef347-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="ef347-140">硬體考量</span><span class="sxs-lookup"><span data-stu-id="ef347-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中通話許可控制的最佳作法</a></span><span class="sxs-lookup"><span data-stu-id="ef347-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef347-142">部署程序</span><span class="sxs-lookup"><span data-stu-id="ef347-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef347-143">先決條件</span><span class="sxs-lookup"><span data-stu-id="ef347-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="ef347-144">資訊需求</span><span class="sxs-lookup"><span data-stu-id="ef347-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="ef347-145">處理和程序</span><span class="sxs-lookup"><span data-stu-id="ef347-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ef347-146"><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中設定通話許可控制</a></span><span class="sxs-lookup"><span data-stu-id="ef347-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

