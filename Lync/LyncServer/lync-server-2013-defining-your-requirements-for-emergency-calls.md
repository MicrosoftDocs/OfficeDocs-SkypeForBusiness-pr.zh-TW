---
title: Lync Server 2013：定義緊急通話需求
description: Lync Server 2013：定義緊急通話的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545399"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="96e34-103">在 Lync Server 2013 中定義緊急通話的需求</span><span class="sxs-lookup"><span data-stu-id="96e34-103">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e34-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="96e34-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="96e34-105">開始使用 Microsoft Lync Server 2013 E9-1-1 部署之前，您應該先回答下列各節所述的問題。</span><span class="sxs-lookup"><span data-stu-id="96e34-105">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="96e34-106">您需要執行的規劃視您選擇部署的 E9-1-1 解決方案類型— SIP 主幹 E9-1-1 服務提供者或緊急位置識別碼 (ELIN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="96e34-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="96e34-107">下表針對各個解決方案指出此規劃工作簿中您需要檢閱的章節。</span><span class="sxs-lookup"><span data-stu-id="96e34-107">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="96e34-108">規劃步驟 (依 E9-1-1 解決方案的類型)</span><span class="sxs-lookup"><span data-stu-id="96e34-108">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96e34-109">SIP 主幹服務提供者</span><span class="sxs-lookup"><span data-stu-id="96e34-109">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="96e34-110">ELIN 閘道</span><span class="sxs-lookup"><span data-stu-id="96e34-110">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96e34-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</a></span><span class="sxs-lookup"><span data-stu-id="96e34-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</a></span><span class="sxs-lookup"><span data-stu-id="96e34-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e34-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷 Lync Server 2013 中的位置的網路元素</a></span><span class="sxs-lookup"><span data-stu-id="96e34-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷 Lync Server 2013 中的位置的網路元素</a></span><span class="sxs-lookup"><span data-stu-id="96e34-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e34-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中啟用 E9-1-1 的使用者</a></span><span class="sxs-lookup"><span data-stu-id="96e34-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中啟用 E9-1-1 的使用者</a></span><span class="sxs-lookup"><span data-stu-id="96e34-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e34-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">在 Lync Server 2013 中管理 SIP 主幹服務提供者的位置</a></span><span class="sxs-lookup"><span data-stu-id="96e34-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">在 Lync Server 2013 中管理 ELIN 閘道的位置</a></span><span class="sxs-lookup"><span data-stu-id="96e34-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e34-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義在 Lync Server 2013 中手動取得位置的使用者體驗</a></span><span class="sxs-lookup"><span data-stu-id="96e34-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義在 Lync Server 2013 中手動取得位置的使用者體驗</a></span><span class="sxs-lookup"><span data-stu-id="96e34-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e34-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">在 Lync Server 2013 中設計 E9-1-1 的 SIP 主幹</a></span><span class="sxs-lookup"><span data-stu-id="96e34-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-122"><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包含安全性桌面</a></span><span class="sxs-lookup"><span data-stu-id="96e34-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e34-123"><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包含安全性桌面</a></span><span class="sxs-lookup"><span data-stu-id="96e34-123"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-124"><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></span><span class="sxs-lookup"><span data-stu-id="96e34-124"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e34-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">選擇 Lync Server 2013 的 E9-1-1 服務提供者</a></span><span class="sxs-lookup"><span data-stu-id="96e34-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="96e34-126"><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中指派位置原則範圍</a></span><span class="sxs-lookup"><span data-stu-id="96e34-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e34-127"><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></span><span class="sxs-lookup"><span data-stu-id="96e34-127"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e34-128"><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中指派位置原則範圍</a></span><span class="sxs-lookup"><span data-stu-id="96e34-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="96e34-129">本章節內容</span><span class="sxs-lookup"><span data-stu-id="96e34-129">In This Section</span></span>

  - [<span data-ttu-id="96e34-130">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="96e34-130">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="96e34-131">定義用來判斷 Lync Server 2013 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="96e34-131">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="96e34-132">在 Lync Server 2013 中啟用 E9-1-1 的使用者</span><span class="sxs-lookup"><span data-stu-id="96e34-132">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="96e34-133">在 Lync Server 2013 中管理 SIP 主幹服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="96e34-133">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="96e34-134">在 Lync Server 2013 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="96e34-134">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="96e34-135">定義在 Lync Server 2013 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="96e34-135">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="96e34-136">在 Lync Server 2013 中設計 E9-1-1 的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="96e34-136">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="96e34-137">在 Lync Server 2013 中包含安全性桌面</span><span class="sxs-lookup"><span data-stu-id="96e34-137">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="96e34-138">選擇 Lync Server 2013 的 E9-1-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="96e34-138">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="96e34-139">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="96e34-139">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="96e34-140">在 Lync Server 2013 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="96e34-140">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

