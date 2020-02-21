---
title: Lync Server 2013 的電話撥入式會議的部署檢查表
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
ms.openlocfilehash: 084686c33482e4828378db76c2a5ca1c834bacf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5d450-102">Lync Server 2013 中的電話撥入式會議的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="5d450-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d450-103">_**上次修改主題：** 2014年-10-03_</span><span class="sxs-lookup"><span data-stu-id="5d450-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="5d450-104">當您部署會議工作負載時，會部署電話撥入式會議所需的元件。</span><span class="sxs-lookup"><span data-stu-id="5d450-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="5d450-105">您可以設定電話撥入式會議之前，您需要部署企業語音或中繼伺服器與公用交換的電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="5d450-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="5d450-106">使用者可以從 PSTN 加入音訊/視訊會議撥入之前，必須執行下表中的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="5d450-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d450-107">如果您從 Office Communications Server 2007 R2 移轉，您必須至少將最新更新套用至 Office Communications Server 2007 R2 環境，才能部署電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="5d450-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="5d450-108">電話撥入式會議部署程序</span><span class="sxs-lookup"><span data-stu-id="5d450-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d450-109">階段</span><span class="sxs-lookup"><span data-stu-id="5d450-109">Phase</span></span></th>
<th><span data-ttu-id="5d450-110">步驟</span><span class="sxs-lookup"><span data-stu-id="5d450-110">Steps</span></span></th>
<th><span data-ttu-id="5d450-111">權限</span><span class="sxs-lookup"><span data-stu-id="5d450-111">Permissions</span></span></th>
<th><span data-ttu-id="5d450-112">部署文件</span><span class="sxs-lookup"><span data-stu-id="5d450-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d450-113"><strong>建立包含會議工作負載，包括中繼伺服器和 PSTN 閘道、 拓撲及部署前端集區或 Standard Edition server</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5d450-114">執行拓撲產生器來設定您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="5d450-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="5d450-115">同時設定拓撲，請選取撥入式會議選項。</span><span class="sxs-lookup"><span data-stu-id="5d450-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="5d450-116">發行拓撲並部署前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="5d450-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="5d450-117">如有必要，建立獨立中繼伺服器，並將它與 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="5d450-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5d450-118">只有當您未部署 Enterprise Voice 且不組合的中繼伺服器與企業 EditionFront 端伺服器或 Standard Edition 伺服器，則需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="5d450-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="5d450-119">如果您部署企業語音時，安裝及設定中繼伺服器和 PSTN 閘道的 Enterprise Voice 部署過程。</span><span class="sxs-lookup"><span data-stu-id="5d450-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="5d450-120">如果您在組合的中繼伺服器，安裝及設定中繼伺服器的前端集區或 Standard Edition server 部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d450-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="5d450-121">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="5d450-121">Domain Admins</span></span></p>
<p><span data-ttu-id="5d450-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-123">系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d450-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5d450-124"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5d450-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="5d450-125">若要建立獨立的中繼伺服器集區： <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Lync Server 2013 中的定義同儕</a></span><span class="sxs-lookup"><span data-stu-id="5d450-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-126"><strong>設定撥號對應表</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-127">撥號對應表是一組的電話號碼正規化規則轉譯電話號碼撥打從特定位置的單一標準 (E.164) 格式，以便進行電話授權和來電路由。</span><span class="sxs-lookup"><span data-stu-id="5d450-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="5d450-128">從不同位置撥打的電話號碼相同可以根據各自的撥號對應表，解析為不同的 E.164 號碼，視每個位置。</span><span class="sxs-lookup"><span data-stu-id="5d450-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="5d450-129">如果您部署企業語音撥號對應表設定為該部署的一部分，您必須先確認撥號對應表也會配合撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="5d450-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="5d450-130">如果您不要部署 Enterprise Voice，您需要設定電話撥入式會議的撥號對應表計劃。</span><span class="sxs-lookup"><span data-stu-id="5d450-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="5d450-131">使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來設定撥號對應表，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d450-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="5d450-132">建立一或多個撥號對應表計劃路由傳送撥入存取電話號碼。</span><span class="sxs-lookup"><span data-stu-id="5d450-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="5d450-133">將預設撥號對應表指派給每個集區。</span><span class="sxs-lookup"><span data-stu-id="5d450-133">Assign a default dial plan to each pool.</span></span> <span data-ttu-id="5d450-134">設定<strong>電話撥入式會議地區</strong>為撥號對應表套用到的地理位置。</span><span class="sxs-lookup"><span data-stu-id="5d450-134">Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies.</span></span> <span data-ttu-id="5d450-135">與撥入存取號碼區域產生關聯的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="5d450-135">The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5d450-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5d450-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 中設定撥入式會議的撥號對應表計的劃</a></span><span class="sxs-lookup"><span data-stu-id="5d450-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d450-141"><strong>確定撥號對應表已被指派區域</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-142">執行<strong>Get-csdialplan</strong>和<strong>Set-csdialplan</strong> cmdlet，以確定所有撥號對應表計劃擁有指派的地區。</span><span class="sxs-lookup"><span data-stu-id="5d450-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="5d450-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5d450-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">確定撥號對應表 Lync Server 2013 已指派區域</a></span><span class="sxs-lookup"><span data-stu-id="5d450-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-148"><strong>（選用）確認或修改使用者個人識別碼號碼 (PIN) 需求</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-149">使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來檢視或修改會議<strong>的 pin 碼原則</strong>。</span><span class="sxs-lookup"><span data-stu-id="5d450-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="5d450-150">您可以指定最小 PIN 長度] 中，登入嘗試，PIN 到期的最大數目以及是否允許共同模式。</span><span class="sxs-lookup"><span data-stu-id="5d450-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="5d450-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">（選用）確認 Lync Server 2013 中的 pin 碼原則設定</a></span><span class="sxs-lookup"><span data-stu-id="5d450-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d450-155"><strong>設定會議原則以支援電話撥入式會議</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-156">使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來設定<strong>會議原則</strong>設定。</span><span class="sxs-lookup"><span data-stu-id="5d450-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="5d450-157">指定是否：</span><span class="sxs-lookup"><span data-stu-id="5d450-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="5d450-158">PSTN 會議撥號對應表中已啟用。</span><span class="sxs-lookup"><span data-stu-id="5d450-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="5d450-159">使用者可以邀請匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="5d450-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="5d450-160">未驗證的使用者可以使用電話撥出式打電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="5d450-160">Unauthenticated users can join a conference by using dial-out phoning.</span></span> <span data-ttu-id="5d450-161">電話撥出式打電話，會議伺服器會呼叫該使用者與使用者接聽電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="5d450-161">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d450-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中設定電話撥入式會議的原則</a></span><span class="sxs-lookup"><span data-stu-id="5d450-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-166"><strong>設定撥入存取號碼</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-167">使用 Lync Server 2013 Control Panel 或 Lync Server 管理命令介面來設定撥入會議，則使用者呼叫的撥入存取號碼，並指定適當的撥號對應表建立關聯的存取號碼的地區。</span><span class="sxs-lookup"><span data-stu-id="5d450-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="5d450-168">召集人的撥號對應表所指定的區域的第三個存取號碼會包含在會議邀請。</span><span class="sxs-lookup"><span data-stu-id="5d450-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="5d450-169">所有存取號碼都可在 [電話撥入式會議設定] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="5d450-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5d450-170">在建立撥入存取號碼後，您可以使用<STRONG>Set-csdialinconferencingaccessnumber</STRONG> cmdlet 修改的 Active Directory 連絡人物件的顯示名稱，以便使用者可以更輕鬆識別正確的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="5d450-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="5d450-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中設定電話撥入式會議存取號碼</a></span><span class="sxs-lookup"><span data-stu-id="5d450-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d450-175"><strong>（選用）驗證電話撥入式會議設定</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-176">使用<strong>Get-csdialinconferencingaccessnumber</strong> cmdlet 來搜尋有未由任何存取號碼撥入式會議地區的撥號對應表計劃和未指派區域的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="5d450-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="5d450-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="5d450-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="5d450-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="5d450-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="5d450-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">（選用）確認 Lync Server 2013 中的撥入式會議設定</a></span><span class="sxs-lookup"><span data-stu-id="5d450-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-183"><strong>（選用）修改 DTMF 命令的按鍵對應</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-184">使用<strong>Set-csdialinconferencingdtmfconfiguration</strong> cmdlet 來修改複頻式訊號 (DTMF) 命令，供參與者用來控制會議設定所使用的機碼 (例如靜音和取消靜音或鎖定和解除鎖定)。</span><span class="sxs-lookup"><span data-stu-id="5d450-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="5d450-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">（選用）修改 Lync Server 2013 中的 DTMF 命令的按鍵對應</a></span><span class="sxs-lookup"><span data-stu-id="5d450-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d450-189"><strong>（選用）修改會議加入和離開宣告行為</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-190">使用<strong>Set-csdialinconferencingconfiguration</strong>來變更參與者加入和離開會議時，宣告的運作方式。</span><span class="sxs-lookup"><span data-stu-id="5d450-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="5d450-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">（選用）啟用和停用會議加入和離開宣告在 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5d450-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-195"><strong>（選用）確認撥入式會議</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-196">使用<strong>Test-csdialinconferencing</strong> cmdlet 來測試指定的集區的存取號碼正確運作。</span><span class="sxs-lookup"><span data-stu-id="5d450-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="5d450-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d450-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">（選用）確認 Lync Server 2013 中的電話撥入式會議</a></span><span class="sxs-lookup"><span data-stu-id="5d450-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d450-201"><strong>部署 Online Meeting add-in for Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-202">部署的線上會議增益集 Lync 2013 讓使用者可以排程支援電話撥入式會議的會議。</span><span class="sxs-lookup"><span data-stu-id="5d450-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="5d450-203">線上會議增益集 for Lync 2013 會自動安裝當您安裝 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="5d450-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="5d450-204">系統管理員</span><span class="sxs-lookup"><span data-stu-id="5d450-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="5d450-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Online Meeting add-in for Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="5d450-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-206"><strong>設定使用者帳戶設定</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-207">使用 Lync Server 2013 Control Panel 或 Lync Server 管理命令介面來設定為唯一、 正規化的電話號碼的電話<strong>線路 URI</strong> (例如，tel: + 14255550200)。</span><span class="sxs-lookup"><span data-stu-id="5d450-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="5d450-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d450-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="5d450-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d450-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d450-211"><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中設定使用者帳戶設定</a></span><span class="sxs-lookup"><span data-stu-id="5d450-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d450-212">（建議使用）設定會議目錄</span><span class="sxs-lookup"><span data-stu-id="5d450-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="5d450-213">使用<strong>New-csconferencedirectory</strong> cmdlet 來建立一個的每個 999 使用者的會議目錄集區中。</span><span class="sxs-lookup"><span data-stu-id="5d450-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="5d450-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5d450-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">電話撥入式會議需求 Lync Server 2013 中的</a><a href="recommended-create-conference-directories.md">建立會議目錄 （建議使用）</a></span><span class="sxs-lookup"><span data-stu-id="5d450-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d450-216"><strong>（選用）歡迎使用者加入電話撥入式會議，並設定初始 PIN</strong></span><span class="sxs-lookup"><span data-stu-id="5d450-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="5d450-217">使用<strong>Set-cspinsendcawelcomemail</strong>指令碼來設定使用者的初始 Pin 並傳送歡迎電子郵件內含初始 PIN 和電話撥入式會議設定] 頁面的連結。</span><span class="sxs-lookup"><span data-stu-id="5d450-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="5d450-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d450-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5d450-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">（選用）歡迎使用者使用 Lync Server 2013 中的電話撥入式會議</a></span><span class="sxs-lookup"><span data-stu-id="5d450-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

