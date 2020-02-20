---
title: Lync Server 2013： 部署程序的通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ff40921e75eb9b2a48c591f3f5df2ba09891627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="d9e40-102">Lync Server 2013 中的通話駐留的部署程序</span><span class="sxs-lookup"><span data-stu-id="d9e40-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e40-103">_**上次修改主題：** 2013年-02-25_</span><span class="sxs-lookup"><span data-stu-id="d9e40-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d9e40-104">本節提供部署通話駐留應用程式的相關步驟的概觀。</span><span class="sxs-lookup"><span data-stu-id="d9e40-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="d9e40-105">設定通話駐留之前，您必須部署 Enterprise Edition 或 Standard Edition 與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="d9e40-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="d9e40-106">通話駐留所需的元件會安裝並啟用當您部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="d9e40-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="d9e40-107">通話駐留部署程序</span><span class="sxs-lookup"><span data-stu-id="d9e40-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9e40-108">階段</span><span class="sxs-lookup"><span data-stu-id="d9e40-108">Phase</span></span></th>
<th><span data-ttu-id="d9e40-109">步驟</span><span class="sxs-lookup"><span data-stu-id="d9e40-109">Steps</span></span></th>
<th><span data-ttu-id="d9e40-110">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="d9e40-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="d9e40-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="d9e40-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9e40-112">設定軌道表中的通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="d9e40-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="d9e40-113">使用 Lync Server Control Panel 或<strong>New-cscallparkorbit</strong> cmdlet 以通話駐留軌道表建立的軌道範圍，以及其關聯的應用程式服務主控的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="d9e40-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d9e40-114">與現有的撥號對應表計劃的緊密整合，針對軌道範圍通常設定為虛擬分機區塊。</span><span class="sxs-lookup"><span data-stu-id="d9e40-114">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="d9e40-115">不支援將直接向內撥號 (DID) 號碼指派為通話駐留軌道表中的軌道數字。</span><span class="sxs-lookup"><span data-stu-id="d9e40-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="d9e40-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d9e40-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d9e40-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d9e40-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">建立或修改通話駐留軌道範圍在 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d9e40-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e40-121">設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="d9e40-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="d9e40-122">使用<strong>Set-cscpsconfiguration</strong> cmdlet 進行通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="d9e40-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="d9e40-123">在最低限度下，我們建議您設定來設定使用駐留的通話逾時的後援目的地<strong>OnTimeoutURI</strong>選項。您也可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d9e40-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="d9e40-124">（選用）<strong>EnableMusicOnHold</strong>可啟用或停用等候音樂。</span><span class="sxs-lookup"><span data-stu-id="d9e40-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="d9e40-125">（選用）若要判斷次數駐留的通話週期回來接聽電話之前轉接至後援統一資源識別項 (URI) <strong>MaxCallPickupAttempts</strong> 。</span><span class="sxs-lookup"><span data-stu-id="d9e40-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="d9e40-126">（選用）<strong>CallPickupTimeoutThreshold</strong>決定駐留通話回接聽來電的電話之前經過的時間量。</span><span class="sxs-lookup"><span data-stu-id="d9e40-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d9e40-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d9e40-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d9e40-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d9e40-131"><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中設定通話駐留設定</a></span><span class="sxs-lookup"><span data-stu-id="d9e40-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9e40-132">（選用） 自訂等候音樂</span><span class="sxs-lookup"><span data-stu-id="d9e40-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="d9e40-133">若要自訂及上傳音訊檔案，如果您不想要使用預設的等候音樂上保留使用<strong>Set-cscallparkservicemusiconholdfile</strong> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9e40-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="d9e40-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d9e40-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d9e40-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d9e40-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">自訂通話駐留等候音樂 Lync Server 2013 中</a></span><span class="sxs-lookup"><span data-stu-id="d9e40-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e40-139">設定語音原則，為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="d9e40-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="d9e40-140">使用 Lync Server Control Panel 或<strong>Set-csvoicepolicy</strong> cmdlet 搭配<strong>EnableCallPark</strong>選項來啟用通話駐留的語音原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="d9e40-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d9e40-141">根據預設，通話駐留已停用所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d9e40-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="d9e40-142">如果您有多個語音原則，請確定每個語音原則，而不只是預設的原則設定 EnableCallPark 屬性。</span><span class="sxs-lookup"><span data-stu-id="d9e40-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="d9e40-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d9e40-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d9e40-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d9e40-147"><a href="lync-server-2013-enable-call-park-for-users.md">啟用 Lync Server 2013 中的使用者的通話駐留</a></span><span class="sxs-lookup"><span data-stu-id="d9e40-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9e40-148">確認通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="d9e40-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="d9e40-149">通話駐留軌道必須不會被正規化。</span><span class="sxs-lookup"><span data-stu-id="d9e40-149">Call park orbits must not be normalized.</span></span> <span data-ttu-id="d9e40-150">確認的正規化規則不包含任何的軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="d9e40-150">Verify that your normalization rules do not include any of your orbit ranges.</span></span> <span data-ttu-id="d9e40-151">如有必要，建立額外的正規化規則，以避免軌道要正規化。</span><span class="sxs-lookup"><span data-stu-id="d9e40-151">If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="d9e40-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d9e40-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d9e40-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d9e40-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9e40-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d9e40-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">確認 Lync Server 2013 中的通話駐留的正規化規則</a></span><span class="sxs-lookup"><span data-stu-id="d9e40-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e40-157">確認通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="d9e40-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="d9e40-158">測試駐留並擷取通話，請確定您的設定如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="d9e40-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="d9e40-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">（選用）確認 Lync Server 2013 中的通話駐留部署</a></span><span class="sxs-lookup"><span data-stu-id="d9e40-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

