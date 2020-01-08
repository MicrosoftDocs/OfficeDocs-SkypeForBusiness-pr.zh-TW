---
title: Lync Server 2013：通話寄存的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab02c8cfbf0f1ca71aff85c8a71a2bcb20ee3fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="3d3a1-102">Lync Server 2013 中通話駐留的部署程式</span><span class="sxs-lookup"><span data-stu-id="3d3a1-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d3a1-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="3d3a1-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3d3a1-104">本節概要說明部署通話駐留應用程式所涉及的步驟。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="3d3a1-105">您必須先使用企業語音部署企業版或標準版，才能設定通話駐留。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="3d3a1-106">當您部署企業語音時，系統會安裝並啟用通話駐留所需的元件。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="3d3a1-107">通話駐留部署程式</span><span class="sxs-lookup"><span data-stu-id="3d3a1-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d3a1-108">分</span><span class="sxs-lookup"><span data-stu-id="3d3a1-108">Phase</span></span></th>
<th><span data-ttu-id="3d3a1-109">步驟</span><span class="sxs-lookup"><span data-stu-id="3d3a1-109">Steps</span></span></th>
<th><span data-ttu-id="3d3a1-110">必要的群組和角色</span><span class="sxs-lookup"><span data-stu-id="3d3a1-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="3d3a1-111">部署檔</span><span class="sxs-lookup"><span data-stu-id="3d3a1-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d3a1-112">設定 [軌道] 表格中的 [通話駐留軌道] 範圍</span><span class="sxs-lookup"><span data-stu-id="3d3a1-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-113">使用 Lync Server [控制台] 或<strong>新的 CSCallParkOrbit</strong> Cmdlet，在 [通話駐留軌道] 表格中建立軌道範圍，並將它們與託管通話駐留應用程式的應用程式服務建立關聯。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3d3a1-114">若要與現有的撥號方案進行無縫整合，軌道範圍通常是設定為虛擬延伸的區塊。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-114">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="3d3a1-115">在 [通話駐留軌道] 表格中，將直向內撥（所做的）號碼指派為軌道編號，不受支援。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="3d3a1-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d3a1-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3d3a1-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中建立或修改通話駐留軌道的範圍</a></span><span class="sxs-lookup"><span data-stu-id="3d3a1-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d3a1-121">設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="3d3a1-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-122">使用<strong>CsCpsConfiguration</strong> Cmdlet 來設定 [通話駐留] 設定。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="3d3a1-123">我們建議您至少設定<strong>OnTimeoutURI</strong>選項，以設定在寄存通話超時時要使用的備用目的地。您也可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3d3a1-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="3d3a1-124">可選<strong>EnableMusicOnHold</strong>以啟用或停用音樂保留。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="3d3a1-125">可選<strong>MaxCallPickupAttempts</strong> ，決定在將來電轉接到回退統一資源識別項（URI）之前，寄存通話響鈴回到接聽電話的次數。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="3d3a1-126">可選<strong>CallPickupTimeoutThreshold</strong> ，決定通話在撥出到接聽通話的電話之前所經過的時間長度。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3d3a1-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d3a1-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3d3a1-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-131"><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中設定通話駐留設定</a></span><span class="sxs-lookup"><span data-stu-id="3d3a1-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d3a1-132">或者，您也可以自訂 [等候音樂]</span><span class="sxs-lookup"><span data-stu-id="3d3a1-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-133">如果您不想使用預設的音樂保留，請使用<strong>CsCallParkServiceMusicOnHoldFile</strong> Cmdlet 來自訂及上傳音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d3a1-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3d3a1-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自訂通話寄存音樂暫停</a></span><span class="sxs-lookup"><span data-stu-id="3d3a1-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d3a1-139">設定語音原則，為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="3d3a1-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-140">使用 Lync Server [控制台] 或<strong>CSVoicePolicy</strong> Cmdlet 與<strong>EnableCallPark</strong>選項，在語音原則中為使用者啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3d3a1-141">根據預設，會停用所有使用者的 [通話駐留]。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="3d3a1-142">如果您有多個語音原則，請務必針對每個語音原則設定 EnableCallPark 屬性，而不只是針對預設原則。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="3d3a1-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d3a1-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3d3a1-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-147"><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中為使用者啟用通話駐留</a></span><span class="sxs-lookup"><span data-stu-id="3d3a1-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d3a1-148">驗證通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="3d3a1-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-149">通話駐留軌道式一定不能正常化。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-149">Call park orbits must not be normalized.</span></span> <span data-ttu-id="3d3a1-150">確認您的正常化規則不包含任何您的軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-150">Verify that your normalization rules do not include any of your orbit ranges.</span></span> <span data-ttu-id="3d3a1-151">如有需要，請建立其他正常化規則，以避免讓軌道式成為正常化的。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-151">If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d3a1-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3d3a1-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3d3a1-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d3a1-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中驗證通話寄存的正常化規則</a></span><span class="sxs-lookup"><span data-stu-id="3d3a1-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d3a1-157">確認您的電話寄存部署</span><span class="sxs-lookup"><span data-stu-id="3d3a1-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="3d3a1-158">測試停用和檢索通話，以確保您的設定如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="3d3a1-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3d3a1-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">可選在 Lync Server 2013 中確認通話駐留部署</a></span><span class="sxs-lookup"><span data-stu-id="3d3a1-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

