---
title: 'Lync Server 2013: E9-1-1 的部署檢查清單'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a8bc7072cb1faa197f733d01eb545a964ed6612
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="063d6-102">E9-1-1 Lync Server 2013 中的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="063d6-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="063d6-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="063d6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="063d6-104">若要有效規劃的增強型 9-1-1 (E9-1-1)，請務必包含下列部署需求：</span><span class="sxs-lookup"><span data-stu-id="063d6-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="063d6-105">部署 E9-1-1 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="063d6-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="063d6-106">部署 E9-1-1 所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="063d6-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="063d6-107">E9-1-1 的部署先決條件</span><span class="sxs-lookup"><span data-stu-id="063d6-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="063d6-108">部署 E9-1-1 之前，您必須已部署 Lync Server 內部伺服器，包括中央管理存放區、 前端集區或 Standard Edition server、 一或多個中繼伺服器或中繼伺服器集區] 中，與 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="063d6-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="063d6-109">此外，E9-1-1 部署需要合格的 E9-1-1 服務提供者的 SIP 主幹或公用交換的電話網路 (PSTN) 緊急位置識別號碼 (ELIN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="063d6-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="063d6-110">Lync Server 支援使用 E9-1-1 服務提供者，僅在美國境內內部。</span><span class="sxs-lookup"><span data-stu-id="063d6-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="063d6-111">部署程序</span><span class="sxs-lookup"><span data-stu-id="063d6-111">Deployment Process</span></span>

<span data-ttu-id="063d6-112">下表提供 E9-1-1 部署程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="063d6-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="063d6-113">如需部署步驟的詳細資訊，請參閱部署文件中的[設定增強型 9-1-1 Lync Server 2013 中](lync-server-2013-configure-enhanced-9-1-1.md)。</span><span class="sxs-lookup"><span data-stu-id="063d6-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="063d6-114">階段</span><span class="sxs-lookup"><span data-stu-id="063d6-114">Phase</span></span></th>
<th><span data-ttu-id="063d6-115">步驟</span><span class="sxs-lookup"><span data-stu-id="063d6-115">Steps</span></span></th>
<th><span data-ttu-id="063d6-116">角色</span><span class="sxs-lookup"><span data-stu-id="063d6-116">Roles</span></span></th>
<th><span data-ttu-id="063d6-117">部署文件</span><span class="sxs-lookup"><span data-stu-id="063d6-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="063d6-118">設定語音使用方式、 路由和主幹組態</span><span class="sxs-lookup"><span data-stu-id="063d6-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="063d6-119">建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="063d6-119">Create a new PSTN usage record.</span></span> <span data-ttu-id="063d6-120">這是相同的名稱，用於位置原則中的<strong>PSTN 使用方式</strong>設定。</span><span class="sxs-lookup"><span data-stu-id="063d6-120">This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="063d6-121">建立或指派語音路由給在上一個步驟中建立的 PSTN 使用方式記錄，然後閘道屬性指向 [E9-1-1 SIP 主幹或 ELIN 閘道。</span><span class="sxs-lookup"><span data-stu-id="063d6-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="063d6-122">SIP 主幹 E9-1-1 服務提供者，設定主幹來透過 SIP 傳遞 PIDF-LO 資料使用<strong>Set-cstrunkconfiguration – EnablePIDFLOSupport</strong> cmdlet 將會處理 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="063d6-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="063d6-123">（選用） 的 SIP 主幹 E9-1-1 服務提供者，建立或指派本機 PSTN 路由不由 E9-1-1 服務提供者的 SIP 主幹處理的通話。</span><span class="sxs-lookup"><span data-stu-id="063d6-123">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="063d6-124">如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。</span><span class="sxs-lookup"><span data-stu-id="063d6-124">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> <span data-ttu-id="063d6-125">如果您的 E9-1-1 服務提供者支援，將主幹組態規則指派給將 911 撥號字串轉譯成的國家/區域緊急通話回應中心 (ECRC) 直接向內撥號 (DID) 號碼的閘道。</span><span class="sxs-lookup"><span data-stu-id="063d6-125">If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="063d6-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="063d6-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="063d6-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013 中設定 E9-1-1 語音路由</a></span><span class="sxs-lookup"><span data-stu-id="063d6-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="063d6-128">建立位置原則，並將它們指派給使用者和子網路</span><span class="sxs-lookup"><span data-stu-id="063d6-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="063d6-129">檢閱全域位置原則。</span><span class="sxs-lookup"><span data-stu-id="063d6-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="063d6-130">使用者層級範圍; 建立位置原則或者，如果組織有多個具有不同緊急使用方式的網站，建立位置原則具有網路層級範圍。</span><span class="sxs-lookup"><span data-stu-id="063d6-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="063d6-131">將位置原則指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="063d6-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="063d6-132">將適當的子網路新增至網站。</span><span class="sxs-lookup"><span data-stu-id="063d6-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="063d6-133">（選用）將位置原則指派給使用者原則。</span><span class="sxs-lookup"><span data-stu-id="063d6-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="063d6-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="063d6-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="063d6-135">CSLocationAdmin （建立位置原則除外）</span><span class="sxs-lookup"><span data-stu-id="063d6-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="063d6-136"><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中建立位置原則</a></span><span class="sxs-lookup"><span data-stu-id="063d6-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="063d6-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">將位置原則新增至 Lync Server 2013 中的網路網站</a></span><span class="sxs-lookup"><span data-stu-id="063d6-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="063d6-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">關聯子網路與 E9-1-1 Lync Server 2013 中的網站</a></span><span class="sxs-lookup"><span data-stu-id="063d6-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="063d6-139">設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="063d6-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="063d6-140">填入網路元素與位置的對應資料庫。</span><span class="sxs-lookup"><span data-stu-id="063d6-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="063d6-141">對於 ELIN 閘道，請新增 Elin 至&lt;CompanyName&gt;資料行。</span><span class="sxs-lookup"><span data-stu-id="063d6-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="063d6-142">設定 E9-1-1 服務提供者的連線驗證地址。</span><span class="sxs-lookup"><span data-stu-id="063d6-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="063d6-143">驗證與 E9-1-1 服務提供者的地址。</span><span class="sxs-lookup"><span data-stu-id="063d6-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="063d6-144">發佈更新過的資料庫。</span><span class="sxs-lookup"><span data-stu-id="063d6-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="063d6-145">為 ELIN 閘道，將 Elin 上傳至您 PSTN 業者的自動位置識別 (ALI) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="063d6-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="063d6-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="063d6-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="063d6-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="063d6-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="063d6-148"><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中設定位置資料庫</a></span><span class="sxs-lookup"><span data-stu-id="063d6-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="063d6-149">設定進階功能 （選用）</span><span class="sxs-lookup"><span data-stu-id="063d6-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="063d6-150">設定 SNMP 應用程式的 URL。</span><span class="sxs-lookup"><span data-stu-id="063d6-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="063d6-151">設定次要位置資訊服務的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="063d6-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="063d6-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="063d6-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="063d6-153"><a href="lync-server-2013-configure-an-snmp-application.md">在 Lync Server 2013 中設定 SNMP 應用程式</a></span><span class="sxs-lookup"><span data-stu-id="063d6-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="063d6-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中設定次要位置資訊服務</a></span><span class="sxs-lookup"><span data-stu-id="063d6-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

