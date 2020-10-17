---
title: 電話撥入式會議的 Lync Server 2013 部署檢查清單
description: 電話撥入式會議的 Lync Server 2013 部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 743b5120bf011ab8467679bea9869a46231b0835
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568355"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="a5d0b-103">Lync Server 2013 中的電話撥入式會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="a5d0b-103">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5d0b-104">_**主題上次修改日期：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="a5d0b-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="a5d0b-105">當您部署會議工作負載時，會部署電話撥入式會議所需的元件。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-105">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="a5d0b-106">在設定電話撥入式會議之前，您需要部署 Enterprise Voice 或轉送伺服器，以及公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-106">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="a5d0b-107">在使用者可以從 PSTN 撥入以加入音訊/視訊會議之前，必須先執行下表中的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-107">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5d0b-108">如果您是從 Office 通訊伺服器 2007 R2 進行遷移，您必須在部署電話撥入式會議之前，將最新的更新套用至 Office 通訊伺服器 2007 R2 環境。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-108">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="a5d0b-109">電話撥入式會議部署程式</span><span class="sxs-lookup"><span data-stu-id="a5d0b-109">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5d0b-110">階段</span><span class="sxs-lookup"><span data-stu-id="a5d0b-110">Phase</span></span></th>
<th><span data-ttu-id="a5d0b-111">步驟</span><span class="sxs-lookup"><span data-stu-id="a5d0b-111">Steps</span></span></th>
<th><span data-ttu-id="a5d0b-112">權限</span><span class="sxs-lookup"><span data-stu-id="a5d0b-112">Permissions</span></span></th>
<th><span data-ttu-id="a5d0b-113">部署文件</span><span class="sxs-lookup"><span data-stu-id="a5d0b-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-114"><strong>建立包含會議工作負載的拓撲，包括轉送伺服器和 PSTN 閘道，以及部署前端集區或 Standard Edition Server</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-114"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a5d0b-115">執行拓撲產生器以設定拓撲。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-115">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="a5d0b-116">設定拓撲時，請選取 [電話撥入式會議] 選項。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-116">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="a5d0b-117">發行拓撲及部署前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-117">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="a5d0b-118">如有必要，請建立獨立的轉送伺服器，並將它與 PSTN 閘道建立關聯。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-118">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a5d0b-119">只有在您未部署 Enterprise Voice，而且不會組合具有 Enterprise EditionFront server 或 Standard Edition Server 的轉送伺服器時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-119">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="a5d0b-120">如果您部署企業語音，請在企業語音部署中安裝及設定轉送伺服器和 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-120">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="a5d0b-121">如果您組合轉送伺服器，請在前端集區或 Standard Edition Server 部署的一部分中安裝及設定轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-121">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="a5d0b-122">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-122">Domain Admins</span></span></p>
<p><span data-ttu-id="a5d0b-123">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-123">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-124">系統管理員</span><span class="sxs-lookup"><span data-stu-id="a5d0b-124">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a5d0b-125"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-125"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="a5d0b-126">若要建立獨立的轉送伺服器集區，請執行下列作業：<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">部署轉送伺服器並定義 Lync server 2013 中的對等</a>專案</span><span class="sxs-lookup"><span data-stu-id="a5d0b-126">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-127"><strong>設定撥號對應表</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-127"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-128">撥號對應表是一組電話號碼正規化規則，可將從特定位置撥打的電話號碼，轉譯成單一標準 () 格式，以進行電話授權和呼叫路由的目的。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-128">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="a5d0b-129">從不同位置撥打的相同電話號碼可以根據各自的撥號對應表，視各自的位置而定，解析為不同的 e.164 號碼。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-129">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="a5d0b-130">如果您部署企業語音，您可以將撥號對應表設定為該部署的一部分，而且您必須確定撥號對應表也能容納電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-130">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="a5d0b-131">如果您未部署企業語音，您必須設定電話撥入式會議的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-131">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="a5d0b-132">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定撥號對應表，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5d0b-132">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="a5d0b-133">建立一或多個用於路由撥入存取電話號碼的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-133">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="a5d0b-134">將預設的撥號對應表指派給每個集區。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-134">Assign a default dial plan to each pool.</span></span> <span data-ttu-id="a5d0b-135">將 <strong>電話撥入式會議地區</strong> 設定為套用撥號對應表的地理位置。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-135">Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies.</span></span> <span data-ttu-id="a5d0b-136">地區會將撥號對應表與電話撥入存取號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-136">The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a5d0b-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-142"><strong>請確定已將撥號對應表指派給地區</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-142"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-143">請執行 <strong>Get-CsDialPlan</strong> 和 <strong>Set-CsDialPlan</strong> Cmdlet，以確定所有撥號對應表均已指派地區。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-143">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-146">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-146">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">確定撥號對應表 Lync Server 2013 具有指派的區域</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-149"><strong> (選用) 驗證或修改使用者個人身分識別號碼 (PIN) 需求</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-149"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-150">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來查看或修改會議 <strong>PIN 原則</strong>。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-150">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="a5d0b-151">您可以指定最小 PIN 碼長度、登入嘗試次數上限、PIN 碼到期，以及是否允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-151">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md"> (選用) 驗證 Lync Server 2013 中的 PIN 原則設定</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-156"><strong>設定會議原則以支援電話撥入式會議</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-156"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-157">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定 <strong>會議原則</strong> 設定。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-157">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="a5d0b-158">指定：</span><span class="sxs-lookup"><span data-stu-id="a5d0b-158">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="a5d0b-159">已啟用 PSTN 會議撥入功能。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-159">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="a5d0b-160">使用者可以邀請匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-160">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="a5d0b-161">未驗證的使用者可以使用撥出 phoning 加入會議。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-161">Unauthenticated users can join a conference by using dial-out phoning.</span></span> <span data-ttu-id="a5d0b-162">透過撥出 phoning，會議服務器呼叫使用者，而使用者接聽電話以加入會議。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-162">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a5d0b-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-164">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-164">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-165">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-165">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中設定電話撥入式會議原則</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-167"><strong>設定撥入存取號碼</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-167"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-168">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定使用者撥打至會議的撥入存取號碼，並指定與適當撥號對應表相關聯之存取號碼的地區。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-168">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="a5d0b-169">召集人的撥號對應表所指定之區域的前三個存取號碼會包含在會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-169">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="a5d0b-170">[電話撥入式會議設定] 頁面上提供所有的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-170">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a5d0b-171">建立撥入存取號碼之後，您可以使用 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> Cmdlet 來修改 Active Directory 連絡人物件的顯示名稱，這樣使用者就能更輕鬆地識別正確的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-171">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="a5d0b-172">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-172">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-173">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-173">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-174">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-174">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中設定電話撥入式會議存取號碼</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-176"><strong> (選用) 驗證電話撥入式會議設定</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-176"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-177">使用 <strong>Get-CsDialinConferencingAccessNumber</strong> 指令程式來搜尋撥號對應表，其中含有未獲任何存取號碼及未指派任何區域之電話撥入式會議區域的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-177">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-178">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-178">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-179">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-179">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-180">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-180">CsAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-181">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-181">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-182">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="a5d0b-182">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議設定</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-184"><strong> (選用) Modify DTMF 命令的按鍵對應</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-184"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-185">您可以使用 <strong>Set-CsDialinConferencingDtmfConfiguration</strong> Cmdlet，修改雙音訊式訊號 (DTMF) 命令所用的按鍵，以供參與者用來控制會議設定 (例如靜音和取消靜音或鎖定和解除鎖定) 。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-185">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-187">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-187">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-188">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-188">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md"> (選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-190"><strong> (選用) Modify 會議加入和離開宣告行為</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-190"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-191">使用 <strong>Set-CsDialinConferencingConfiguration</strong> 變更參與者加入和離開會議時的宣告運作方式。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-191">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-192">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-192">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-193">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-193">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-194">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-194">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md"> (選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-196"><strong> (選用) 驗證電話撥入式會議</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-196"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-197">使用 <strong>Test-CsDialInConferencing</strong> Cmdlet 來測試指定集區的存取號碼是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-197">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-198">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-198">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-199">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-199">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-200">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-200">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-202"><strong>部署 Lync 2013 的線上會議增益集</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-202"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-203">部署 Lync 2013 的線上會議增益集，讓使用者可以排程支援電話撥入式會議的會議。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-203">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="a5d0b-204">當您安裝 Lync 2013 時，會自動安裝 Lync 2013 的線上會議增益集。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-204">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-205">系統管理員</span><span class="sxs-lookup"><span data-stu-id="a5d0b-205">Administrators</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的線上會議增益集</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-207"><strong>設定使用者帳戶設定</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-207"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-208">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面，將電話語音列 <strong>URI</strong> 設定為唯一且正規化的電話號碼 (例如電話： + 14255550200) 。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-208">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a5d0b-210">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-210">CsAdministrator</span></span></p>
<p><span data-ttu-id="a5d0b-211">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="a5d0b-211">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-212"><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中設定使用者帳戶設定</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-212"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d0b-213"> (建議) 設定會議目錄</span><span class="sxs-lookup"><span data-stu-id="a5d0b-213">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-214">使用 <strong>New-CsConferenceDirectory</strong> Cmdlet 為集區中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-214">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-215">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-215">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</a> <a href="recommended-create-conference-directories.md"> (建議) 建立會議目錄</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d0b-217"><strong> (選用) 歡迎使用者的電話撥入式會議和設定初始 PIN 碼</strong></span><span class="sxs-lookup"><span data-stu-id="a5d0b-217"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d0b-218">使用 <strong>Set-CsPinSendCAWelcomeMail</strong> 腳本來設定使用者的初始 pin，並傳送包含初始 PIN 的歡迎使用電子郵件，以及電話撥入式會議設定頁面的連結。</span><span class="sxs-lookup"><span data-stu-id="a5d0b-218">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-219">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a5d0b-219">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a5d0b-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md"> 在 Lync Server 2013 中 (選用) 歡迎使用者撥入式會議</a></span><span class="sxs-lookup"><span data-stu-id="a5d0b-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

