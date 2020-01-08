---
title: Lync Server 2013 電話撥入式會議的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="32539-102">Lync Server 2013 中的電話撥入式會議的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="32539-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32539-103">_**主題上次修改日期：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="32539-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="32539-104">當您部署會議工作負載時，會部署電話撥入式會議所需的元件。</span><span class="sxs-lookup"><span data-stu-id="32539-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="32539-105">在您可以設定電話撥入式會議之前，您必須先部署企業語音或中繼伺服器以及公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="32539-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="32539-106">您必須先執行下表中的所有步驟，才能讓使用者從 PSTN 撥入以加入音訊/視訊會議。</span><span class="sxs-lookup"><span data-stu-id="32539-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32539-107">如果您是從 Office 通訊伺服器 2007 R2 進行遷移，您必須在部署電話撥入式會議之前，將最新的更新套用到您的 Office 通訊伺服器 2007 R2 環境。</span><span class="sxs-lookup"><span data-stu-id="32539-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="32539-108">電話撥入式會議部署程式</span><span class="sxs-lookup"><span data-stu-id="32539-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32539-109">分</span><span class="sxs-lookup"><span data-stu-id="32539-109">Phase</span></span></th>
<th><span data-ttu-id="32539-110">步驟</span><span class="sxs-lookup"><span data-stu-id="32539-110">Steps</span></span></th>
<th><span data-ttu-id="32539-111">許可權</span><span class="sxs-lookup"><span data-stu-id="32539-111">Permissions</span></span></th>
<th><span data-ttu-id="32539-112">部署檔</span><span class="sxs-lookup"><span data-stu-id="32539-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32539-113"><strong>建立包含會議工作負載的拓撲，包括轉送伺服器和 PSTN 閘道，以及部署前端池或標準版伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="32539-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="32539-114">執行拓撲產生器以設定您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="32539-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="32539-115">配置拓撲時，請選取 [電話撥入式會議] 選項。</span><span class="sxs-lookup"><span data-stu-id="32539-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="32539-116">發佈拓撲並部署前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="32539-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="32539-117">如有需要，請建立獨立的中繼伺服器，並將它與 PSTN 閘道建立關聯。</span><span class="sxs-lookup"><span data-stu-id="32539-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="32539-118">只有在您不部署企業語音且沒有 collocate 企業 EditionFront 端伺服器或標準版伺服器的中繼伺服器時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="32539-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="32539-119">如果您要部署企業語音，您必須安裝並設定轉送伺服器和 PSTN 閘道，做為企業語音部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="32539-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="32539-120">如果您 collocate 的是中繼伺服器，您可以在前端池或標準版伺服器部署中安裝並設定中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="32539-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="32539-121">網域管理員</span><span class="sxs-lookup"><span data-stu-id="32539-121">Domain Admins</span></span></p>
<p><span data-ttu-id="32539-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-123">許可權</span><span class="sxs-lookup"><span data-stu-id="32539-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="32539-124"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="32539-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="32539-125">若要建立獨立的中繼伺服器池：<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">在 Lync server 2013 中部署轉送伺服器和定義對等</a>專案</span><span class="sxs-lookup"><span data-stu-id="32539-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-126"><strong>設定撥號方案</strong></span><span class="sxs-lookup"><span data-stu-id="32539-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-127">撥號方案是一組電話號碼正規化規則，可將從特定位置撥打電話的電話號碼轉換為單一標準（e. 164）格式，以用於手機授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="32539-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="32539-128">根據各自的撥號方案，從不同位置撥打電話的電話號碼，視每個地點適當地解析成不同的 e. 164 號碼。</span><span class="sxs-lookup"><span data-stu-id="32539-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="32539-129">如果您要部署企業語音，請將撥號方案設定為該部署的一部分，而且您必須確認撥號方案也能容納電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="32539-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="32539-130">如果您沒有部署企業語音，您必須為電話撥入式會議設定撥號方案。</span><span class="sxs-lookup"><span data-stu-id="32539-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="32539-131">使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來設定撥號方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32539-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="32539-132">建立一或多個用來傳送撥入存取電話號碼的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="32539-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="32539-133">將預設的撥號方案指派給每個文件庫。</span><span class="sxs-lookup"><span data-stu-id="32539-133">Assign a default dial plan to each pool.</span></span> <span data-ttu-id="32539-134">將<strong>電話撥入式會議區域</strong>設定為要套用撥號計畫的地理位置。</span><span class="sxs-lookup"><span data-stu-id="32539-134">Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies.</span></span> <span data-ttu-id="32539-135">該區域會將撥號方案與撥入存取號碼進行關聯。</span><span class="sxs-lookup"><span data-stu-id="32539-135">The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="32539-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="32539-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</a></span><span class="sxs-lookup"><span data-stu-id="32539-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32539-141"><strong>確定撥號方案是指派的區域</strong></span><span class="sxs-lookup"><span data-stu-id="32539-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-142">執行<strong>CsDialPlan</strong>和<strong>CsDialPlan</strong> Cmdlet，以確定所有撥號方案都已指派區域。</span><span class="sxs-lookup"><span data-stu-id="32539-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="32539-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="32539-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">確認 Lync Server 2013 已指派地區的撥號方案</a></span><span class="sxs-lookup"><span data-stu-id="32539-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-148"><strong>可選驗證或修改使用者個人識別碼（PIN）需求</strong></span><span class="sxs-lookup"><span data-stu-id="32539-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-149">使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來查看或修改會議<strong>PIN 原則</strong>。</span><span class="sxs-lookup"><span data-stu-id="32539-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="32539-150">您可以指定最小 PIN 長度、最大登入嘗試次數、PIN 到期日，以及是否允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="32539-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="32539-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(選用) 在 Lync Server 2013 中驗證 PIN 原則設定</a></span><span class="sxs-lookup"><span data-stu-id="32539-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32539-155"><strong>設定會議原則以支援電話撥入式會議</strong></span><span class="sxs-lookup"><span data-stu-id="32539-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-156">使用 Lync Server 2013 [控制台] 或 [Lync Server 管理命令介面] 來設定<strong>會議原則</strong>設定。</span><span class="sxs-lookup"><span data-stu-id="32539-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="32539-157">指定是否：</span><span class="sxs-lookup"><span data-stu-id="32539-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="32539-158">已啟用 PSTN 會議撥入。</span><span class="sxs-lookup"><span data-stu-id="32539-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="32539-159">使用者可以邀請匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="32539-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="32539-160">未經驗證的使用者可以使用撥出 phoning 加入會議。</span><span class="sxs-lookup"><span data-stu-id="32539-160">Unauthenticated users can join a conference by using dial-out phoning.</span></span> <span data-ttu-id="32539-161">使用撥出 phoning，會議服務器就會呼叫使用者，而使用者會接聽電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="32539-161">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="32539-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中設定電話撥入式會議的會議原則</a></span><span class="sxs-lookup"><span data-stu-id="32539-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-166"><strong>設定撥入存取號碼</strong></span><span class="sxs-lookup"><span data-stu-id="32539-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-167">使用 Lync Server 2013 [控制台] 或 [Lync Server 管理命令介面] 來設定使用者撥入會議所撥打的撥入號碼，並指定將存取號碼與適當的撥號方案相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="32539-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="32539-168">召集人撥號計畫所指定之區域的前三個存取號碼包含在會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="32539-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="32539-169">[電話撥入式會議設定] 頁面上提供所有存取號碼。</span><span class="sxs-lookup"><span data-stu-id="32539-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="32539-170">在您建立撥入存取號碼之後，您可以使用<STRONG>CsDialInConferencingAccessNumber</STRONG> Cmdlet 來修改 Active Directory 連絡人物件的顯示名稱，讓使用者能更輕鬆地識別正確的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="32539-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="32539-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中設定電話撥入式會議存取號碼</a></span><span class="sxs-lookup"><span data-stu-id="32539-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32539-175"><strong>(選用) 驗證電話撥入式會議設定</strong></span><span class="sxs-lookup"><span data-stu-id="32539-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-176">使用<strong>CsDialinConferencingAccessNumber</strong> Cmdlet 來搜尋具有電話撥入式會議區域的撥號方案，這些方案不是由任何存取號碼和沒有指派區域的存取號碼所使用。</span><span class="sxs-lookup"><span data-stu-id="32539-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="32539-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="32539-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="32539-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="32539-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="32539-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(選用) 在 Lync Server 2013 中驗證電話撥入式會議設定</a></span><span class="sxs-lookup"><span data-stu-id="32539-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-183"><strong>可選修改 DTMF 命令的金鑰組應</strong></span><span class="sxs-lookup"><span data-stu-id="32539-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-184">使用<strong>CsDialinConferencingDtmfConfiguration</strong> Cmdlet 來修改雙色調 MULTIFREQUENCY （DTMF）命令使用的金鑰，這些參與者可以用來控制會議設定（例如靜音和取消靜音，或鎖定與解除鎖定）。</span><span class="sxs-lookup"><span data-stu-id="32539-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="32539-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</a></span><span class="sxs-lookup"><span data-stu-id="32539-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32539-189"><strong>可選修改會議加入並離開宣告行為</strong></span><span class="sxs-lookup"><span data-stu-id="32539-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-190">使用<strong>CsDialinConferencingConfiguration</strong>變更參與者加入與離開會議時的宣告運作方式。</span><span class="sxs-lookup"><span data-stu-id="32539-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="32539-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</a></span><span class="sxs-lookup"><span data-stu-id="32539-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-195"><strong>(選用) 驗證電話撥入式會議</strong></span><span class="sxs-lookup"><span data-stu-id="32539-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-196">使用<strong>CsDialInConferencing</strong> Cmdlet 來測試指定池的存取號碼是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="32539-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="32539-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="32539-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Lync Server 2013 中的 (選用) 驗證電話撥入式會議</a></span><span class="sxs-lookup"><span data-stu-id="32539-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32539-201"><strong>部署 Lync 2013 的線上會議增益集</strong></span><span class="sxs-lookup"><span data-stu-id="32539-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-202">部署 Lync 2013 的線上會議增益集，讓使用者能夠排程支援電話撥入式會議的會議。</span><span class="sxs-lookup"><span data-stu-id="32539-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="32539-203">當您安裝 Lync 2013 時，系統會自動安裝 Lync 2013 的線上會議增益集。</span><span class="sxs-lookup"><span data-stu-id="32539-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="32539-204">人員</span><span class="sxs-lookup"><span data-stu-id="32539-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="32539-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的線上會議增益集</a></span><span class="sxs-lookup"><span data-stu-id="32539-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-206"><strong>設定使用者帳戶設定</strong></span><span class="sxs-lookup"><span data-stu-id="32539-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-207">使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面]，將電話<strong>線路 URI</strong>設定為唯一、標準化的電話號碼（例如電話： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="32539-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="32539-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="32539-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="32539-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="32539-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="32539-211"><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中設定使用者帳戶設定</a></span><span class="sxs-lookup"><span data-stu-id="32539-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32539-212">採用設定會議目錄</span><span class="sxs-lookup"><span data-stu-id="32539-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="32539-213">使用<strong>CsConferenceDirectory</strong> Cmdlet 為池中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="32539-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="32539-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="32539-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</a> <a href="recommended-create-conference-directories.md">（建議使用）建立會議目錄</a></span><span class="sxs-lookup"><span data-stu-id="32539-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32539-216"><strong>可選歡迎使用者撥入式會議及設定初始 PIN</strong></span><span class="sxs-lookup"><span data-stu-id="32539-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="32539-217">使用<strong>CsPinSendCAWelcomeMail</strong>腳本來設定使用者的初始 pin，並傳送包含初始 PIN 的歡迎電子郵件，以及 [電話撥入式會議設定] 頁面的連結。</span><span class="sxs-lookup"><span data-stu-id="32539-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="32539-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32539-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="32539-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(選用) 在 Lync Server 2013 中歡迎使用者使用電話撥入式會議</a></span><span class="sxs-lookup"><span data-stu-id="32539-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

