---
title: Lync Server 2013： E9-1-1 的部署檢查清單
description: Lync Server 2013： E9-1-1 的部署檢查清單。
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
ms.openlocfilehash: 0c93762e2acef5e065249ced17bfa0eab2f159e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568349"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="70fca-103">Lync Server 2013 中的 E9-1-1 的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="70fca-103">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70fca-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="70fca-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="70fca-105">若要有效規劃增強型 9-1-1 (E9-1-1) ，請務必包含下列部署需求：</span><span class="sxs-lookup"><span data-stu-id="70fca-105">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="70fca-106">部署 E9-1-1 的必要條件。</span><span class="sxs-lookup"><span data-stu-id="70fca-106">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="70fca-107">部署 E9-1-1 所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="70fca-107">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="70fca-108">E9-1-1 的部署必要條件</span><span class="sxs-lookup"><span data-stu-id="70fca-108">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="70fca-109">在您部署 E9-1-1 之前，您必須已部署 Lync Server 內部伺服器，包括中央管理存放區、前端集區或 Standard Edition Server、一或多部轉送伺服器或轉送伺服器集區，以及 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="70fca-109">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="70fca-110">此外，E9-1-1 部署需要 SIP 主幹給合格的 E9-1-1 服務提供者或緊急位置識別號碼 (ELIN) 閘道至您公用交換電話網路 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="70fca-110">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="70fca-111">Lync Server 僅支援在美國內使用 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="70fca-111">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="70fca-112">部署程式</span><span class="sxs-lookup"><span data-stu-id="70fca-112">Deployment Process</span></span>

<span data-ttu-id="70fca-113">下表提供 E9-1-1 部署程式的概述。</span><span class="sxs-lookup"><span data-stu-id="70fca-113">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="70fca-114">如需部署步驟的詳細資訊，請參閱部署檔中的 [Configure The Lync Server 2013 中的 Configure 增強 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md) 。</span><span class="sxs-lookup"><span data-stu-id="70fca-114">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70fca-115">階段</span><span class="sxs-lookup"><span data-stu-id="70fca-115">Phase</span></span></th>
<th><span data-ttu-id="70fca-116">步驟</span><span class="sxs-lookup"><span data-stu-id="70fca-116">Steps</span></span></th>
<th><span data-ttu-id="70fca-117">角色</span><span class="sxs-lookup"><span data-stu-id="70fca-117">Roles</span></span></th>
<th><span data-ttu-id="70fca-118">部署文件</span><span class="sxs-lookup"><span data-stu-id="70fca-118">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70fca-119">設定語音使用方式、路由和主幹設定</span><span class="sxs-lookup"><span data-stu-id="70fca-119">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="70fca-120">建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="70fca-120">Create a new PSTN usage record.</span></span> <span data-ttu-id="70fca-121">這與位置原則中用於 <strong>PSTN 使用狀況</strong> 設定的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="70fca-121">This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="70fca-122">建立或指派語音路由至上一個步驟中建立的 PSTN 使用方式記錄，然後將閘道屬性指向 E9-1-1 SIP 主幹或 ELIN 閘道。</span><span class="sxs-lookup"><span data-stu-id="70fca-122">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="70fca-123">若為 SIP 主幹 E9-1-1 服務提供者，請設定主幹以透過 SIP 處理 E9-1-1 呼叫以透過使用 <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> Cmdlet 來傳遞 PIDF-LO 資料。</span><span class="sxs-lookup"><span data-stu-id="70fca-123">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="70fca-124">（選用）對於 SIP 主幹 E9-1-1 服務提供者，針對未由 E9-1-1 服務提供者的 SIP 主幹處理的呼叫建立或指派本機 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="70fca-124">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="70fca-125">如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。</span><span class="sxs-lookup"><span data-stu-id="70fca-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> <span data-ttu-id="70fca-126">如果您的 E9-1-1 服務提供者支援，請將主幹設定規則指派給將911撥號字串轉譯成直接向內撥號 (已) 國家/地區緊急通話回應中心 (ECRC) 的號碼。</span><span class="sxs-lookup"><span data-stu-id="70fca-126">If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="70fca-127">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="70fca-127">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="70fca-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">在 Lync Server 2013 中設定 E9-1-1 語音路由</a></span><span class="sxs-lookup"><span data-stu-id="70fca-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70fca-129">建立位置原則並將其指派給使用者和子網</span><span class="sxs-lookup"><span data-stu-id="70fca-129">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="70fca-130">複查全域位置原則。</span><span class="sxs-lookup"><span data-stu-id="70fca-130">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="70fca-131">建立具有使用者層級範圍的位置原則;或者，如果組織有多個具有不同緊急用途的網站，請使用網路層級範圍建立一個位置原則。</span><span class="sxs-lookup"><span data-stu-id="70fca-131">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="70fca-132">將位置原則指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="70fca-132">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="70fca-133">將適當的子網新增至網路網站。</span><span class="sxs-lookup"><span data-stu-id="70fca-133">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="70fca-134"> (選用) 指派位置原則給使用者原則。</span><span class="sxs-lookup"><span data-stu-id="70fca-134">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="70fca-135">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="70fca-135">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="70fca-136">CSLocationAdmin (除了建立位置原則) </span><span class="sxs-lookup"><span data-stu-id="70fca-136">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="70fca-137"><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中建立位置原則</a></span><span class="sxs-lookup"><span data-stu-id="70fca-137"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="70fca-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">在 Lync Server 2013 中將位置原則新增至網路網站</a></span><span class="sxs-lookup"><span data-stu-id="70fca-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="70fca-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">將子網與 E9-1-1 在 Lync Server 2013 中的網站產生關聯</a></span><span class="sxs-lookup"><span data-stu-id="70fca-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70fca-140">設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="70fca-140">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="70fca-141">以網元對應至位置，填入資料庫。</span><span class="sxs-lookup"><span data-stu-id="70fca-141">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="70fca-142">針對 ELIN 閘道，將 Elin 新增至 [ &lt; CompanyName] &gt; 欄中。</span><span class="sxs-lookup"><span data-stu-id="70fca-142">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="70fca-143">設定 E9-1-1 服務提供者的連線以驗證位址。</span><span class="sxs-lookup"><span data-stu-id="70fca-143">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="70fca-144">使用 E9-1-1 服務提供者驗證位址。</span><span class="sxs-lookup"><span data-stu-id="70fca-144">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="70fca-145">發佈更新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="70fca-145">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="70fca-146">針對 ELIN 閘道，將 Elin 上傳至您的 PSTN 載體的自動位置識別 (阿裡) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="70fca-146">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="70fca-147">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="70fca-147">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="70fca-148">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="70fca-148">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="70fca-149"><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中設定位置資料庫</a></span><span class="sxs-lookup"><span data-stu-id="70fca-149"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70fca-150">設定高級功能 (選用) </span><span class="sxs-lookup"><span data-stu-id="70fca-150">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="70fca-151">設定 SNMP 應用程式的 URL。</span><span class="sxs-lookup"><span data-stu-id="70fca-151">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="70fca-152">設定次要位置資訊服務之位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="70fca-152">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="70fca-153">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="70fca-153">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="70fca-154"><a href="lync-server-2013-configure-an-snmp-application.md">在 Lync Server 2013 中設定 SNMP 應用程式</a></span><span class="sxs-lookup"><span data-stu-id="70fca-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="70fca-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中設定次要位置資訊服務</a></span><span class="sxs-lookup"><span data-stu-id="70fca-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

