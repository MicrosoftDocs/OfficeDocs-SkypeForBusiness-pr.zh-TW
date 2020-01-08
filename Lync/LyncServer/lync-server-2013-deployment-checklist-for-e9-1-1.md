---
title: Lync Server 2013： E9 的部署檢查清單-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="463bb-102">Lync Server 2013 的 E9 部署檢查清單-1-1</span><span class="sxs-lookup"><span data-stu-id="463bb-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="463bb-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="463bb-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="463bb-104">若要有效地規劃增強型9-1-1 （E9-1-1），請務必包含下列部署需求：</span><span class="sxs-lookup"><span data-stu-id="463bb-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="463bb-105">部署 E9 的先決條件-1-1。</span><span class="sxs-lookup"><span data-stu-id="463bb-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="463bb-106">部署 E9 所需的步驟-1-1。</span><span class="sxs-lookup"><span data-stu-id="463bb-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="463bb-107">E9 的部署必備元件-1-1</span><span class="sxs-lookup"><span data-stu-id="463bb-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="463bb-108">在您部署 E9-1-1 之前，您必須已部署 Lync Server 內部伺服器，包括中央管理儲存體、前端池或標準版伺服器、一或多個轉送伺服器或轉送伺服器池，以及 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="463bb-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="463bb-109">此外，E9 部署需要將 SIP 主幹轉至合格的 E9-1 服務提供者，或緊急位置識別號碼（ELIN）閘道到您的公用交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="463bb-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="463bb-110">Lync Server 僅支援在美國境內使用 E9-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="463bb-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="463bb-111">部署程式</span><span class="sxs-lookup"><span data-stu-id="463bb-111">Deployment Process</span></span>

<span data-ttu-id="463bb-112">下表提供 E9-1-1 1 部署程式的概覽。</span><span class="sxs-lookup"><span data-stu-id="463bb-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="463bb-113">如需部署步驟的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [設定增強型 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md) ]。</span><span class="sxs-lookup"><span data-stu-id="463bb-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="463bb-114">分</span><span class="sxs-lookup"><span data-stu-id="463bb-114">Phase</span></span></th>
<th><span data-ttu-id="463bb-115">步驟</span><span class="sxs-lookup"><span data-stu-id="463bb-115">Steps</span></span></th>
<th><span data-ttu-id="463bb-116">角色</span><span class="sxs-lookup"><span data-stu-id="463bb-116">Roles</span></span></th>
<th><span data-ttu-id="463bb-117">部署檔</span><span class="sxs-lookup"><span data-stu-id="463bb-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="463bb-118">設定語音使用方式、路由和主幹設定</span><span class="sxs-lookup"><span data-stu-id="463bb-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="463bb-119">建立新的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="463bb-119">Create a new PSTN usage record.</span></span> <span data-ttu-id="463bb-120">這與位置原則中用於<strong>PSTN 使用</strong>設定的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="463bb-120">This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="463bb-121">建立或指派語音路由至在上一個步驟建立的 PSTN 使用記錄，然後將閘道屬性指向 E9-1-1 SIP 幹線或 ELIN 閘道。</span><span class="sxs-lookup"><span data-stu-id="463bb-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="463bb-122">針對 SIP 幹線 E9-1 服務提供者，請設定要透過 SIP 處理 E9-1-1 呼叫的幹線，以使用<strong>set-EnablePIDFLOSupport</strong> Cmdlet 來傳送 PIDF-LO 資料。</span><span class="sxs-lookup"><span data-stu-id="463bb-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="463bb-123">您也可以選擇針對 SIP 幹線 E9-1 服務提供者，為不是由 E9-1-1 服務提供者 SIP 幹線處理的呼叫建立或指派本機 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="463bb-123">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="463bb-124">如果無法連線至 E9-1-1 服務提供者，就會使用這個路由。</span><span class="sxs-lookup"><span data-stu-id="463bb-124">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> <span data-ttu-id="463bb-125">如果您的 E9-1 服務提供者支援，請將幹線設定規則指派給閘道，將911撥號字串轉換為國內/地區緊急電話回應中心（ECRC）的直接向內撥號（已發出）號碼。</span><span class="sxs-lookup"><span data-stu-id="463bb-125">If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="463bb-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="463bb-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="463bb-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">在 Lync Server 2013 中設定 E9-1-1 的語音路由</a></span><span class="sxs-lookup"><span data-stu-id="463bb-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-128">建立位置原則並將其指派給使用者和子網</span><span class="sxs-lookup"><span data-stu-id="463bb-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="463bb-129">查看全域位置原則。</span><span class="sxs-lookup"><span data-stu-id="463bb-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="463bb-130">建立具有使用者層級範圍的位置原則;或者，如果組織有一個以上的網站有不同的緊急用途，請建立具有網路層級範圍的位置原則。</span><span class="sxs-lookup"><span data-stu-id="463bb-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="463bb-131">將位置原則指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="463bb-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="463bb-132">將適當的子網新增至網路網站。</span><span class="sxs-lookup"><span data-stu-id="463bb-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="463bb-133">可選將位置原則指派給使用者原則。</span><span class="sxs-lookup"><span data-stu-id="463bb-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="463bb-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="463bb-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="463bb-135">CSLocationAdmin （建立位置原則除外）</span><span class="sxs-lookup"><span data-stu-id="463bb-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="463bb-136"><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中建立位置原則</a></span><span class="sxs-lookup"><span data-stu-id="463bb-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="463bb-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">在 Lync Server 2013 的網路網站中新增位置原則</a></span><span class="sxs-lookup"><span data-stu-id="463bb-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="463bb-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">在 Lync Server 2013 中將子網與網路網站進行 E9-1-1</a></span><span class="sxs-lookup"><span data-stu-id="463bb-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463bb-139">設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="463bb-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="463bb-140">使用網路元素對應至位置來填入資料庫。</span><span class="sxs-lookup"><span data-stu-id="463bb-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="463bb-141">針對 ELIN 閘道，將 ELINs 新增至&lt;[&gt;公司名稱] 資料行。</span><span class="sxs-lookup"><span data-stu-id="463bb-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="463bb-142">設定連線至 E9-1 服務提供者，以驗證位址。</span><span class="sxs-lookup"><span data-stu-id="463bb-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="463bb-143">使用 E9-1 服務提供者驗證位址。</span><span class="sxs-lookup"><span data-stu-id="463bb-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="463bb-144">發佈更新後的資料庫。</span><span class="sxs-lookup"><span data-stu-id="463bb-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="463bb-145">若是 ELIN 閘道，請將 ELINs 上傳到 PSTN 載波的自動位置識別（阿裡）資料庫。</span><span class="sxs-lookup"><span data-stu-id="463bb-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="463bb-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="463bb-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="463bb-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="463bb-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="463bb-148"><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中設定位置資料庫</a></span><span class="sxs-lookup"><span data-stu-id="463bb-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463bb-149">設定高級功能（選用）</span><span class="sxs-lookup"><span data-stu-id="463bb-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="463bb-150">設定 SNMP 應用程式的 URL。</span><span class="sxs-lookup"><span data-stu-id="463bb-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="463bb-151">設定次要位置資訊服務之位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="463bb-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="463bb-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="463bb-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="463bb-153"><a href="lync-server-2013-configure-an-snmp-application.md">在 Lync Server 2013 中設定 SNMP 應用程式</a></span><span class="sxs-lookup"><span data-stu-id="463bb-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="463bb-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中設定次要位置資訊服務</a></span><span class="sxs-lookup"><span data-stu-id="463bb-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

