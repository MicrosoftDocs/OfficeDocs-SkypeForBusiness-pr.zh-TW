---
title: Lync Server 2013：定義緊急通話需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53543d815519dc440ba038999e5fc531173551f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="e8d2e-102">在 Lync Server 2013 中定義緊急通話需求</span><span class="sxs-lookup"><span data-stu-id="e8d2e-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8d2e-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e8d2e-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e8d2e-104">在您開始使用 Microsoft Lync Server 2013 E9-1-1 1 之前，您應該先能夠回答下列各節所述的問題。</span><span class="sxs-lookup"><span data-stu-id="e8d2e-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="e8d2e-105">您需要執行的規劃取決於您選擇部署的 E9-1-1 解決方案類型，即 SIP 幹線 E9-1 服務提供者，或緊急位置識別號碼（ELIN）閘道。</span><span class="sxs-lookup"><span data-stu-id="e8d2e-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="e8d2e-106">下表說明本規劃活頁簿中您需要針對每個方案進行審查的章節。</span><span class="sxs-lookup"><span data-stu-id="e8d2e-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="e8d2e-107">依 E9 類型（1-1-1）方案規劃步驟</span><span class="sxs-lookup"><span data-stu-id="e8d2e-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8d2e-108">SIP 中繼服務提供者</span><span class="sxs-lookup"><span data-stu-id="e8d2e-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="e8d2e-109">ELIN 閘道</span><span class="sxs-lookup"><span data-stu-id="e8d2e-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8d2e-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d2e-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷 Lync Server 2013 中的位置的網路元素</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定義用來判斷 Lync Server 2013 中的位置的網路元素</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8d2e-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中啟用 E9-1-1 的使用者</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中啟用 E9-1-1 的使用者</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d2e-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">在 Lync Server 2013 中管理 SIP 中繼服務提供者的位置</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">在 Lync Server 2013 中管理 ELIN 閘道的位置</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8d2e-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義在 Lync Server 2013 中手動取得位置的使用者體驗</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定義在 Lync Server 2013 中手動取得位置的使用者體驗</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d2e-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">在 Lync Server 2013 中針對 E9-1-1 設計 SIP 主幹</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-121"><a href="lync-server-2013-including-the-security-desk.md">包括 Lync Server 2013 中的安全服務台</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8d2e-122"><a href="lync-server-2013-including-the-security-desk.md">包括 Lync Server 2013 中的安全服務台</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-123"><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d2e-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">選擇 Lync Server 2013 的 E9-1 服務提供者</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8d2e-125"><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中指派位置原則範圍</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8d2e-126"><a href="lync-server-2013-defining-the-location-policy.md">定義 Lync Server 2013 的位置原則</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8d2e-127"><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中指派位置原則範圍</a></span><span class="sxs-lookup"><span data-stu-id="e8d2e-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="e8d2e-128">本節內容</span><span class="sxs-lookup"><span data-stu-id="e8d2e-128">In This Section</span></span>

  - [<span data-ttu-id="e8d2e-129">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="e8d2e-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="e8d2e-130">定義用來判斷 Lync Server 2013 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="e8d2e-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="e8d2e-131">在 Lync Server 2013 中啟用 E9-1-1 的使用者</span><span class="sxs-lookup"><span data-stu-id="e8d2e-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="e8d2e-132">在 Lync Server 2013 中管理 SIP 中繼服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="e8d2e-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="e8d2e-133">在 Lync Server 2013 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="e8d2e-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="e8d2e-134">定義在 Lync Server 2013 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="e8d2e-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="e8d2e-135">在 Lync Server 2013 中針對 E9-1-1 設計 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="e8d2e-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="e8d2e-136">包括 Lync Server 2013 中的安全服務台</span><span class="sxs-lookup"><span data-stu-id="e8d2e-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="e8d2e-137">選擇 Lync Server 2013 的 E9-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="e8d2e-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="e8d2e-138">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="e8d2e-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="e8d2e-139">在 Lync Server 2013 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="e8d2e-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

