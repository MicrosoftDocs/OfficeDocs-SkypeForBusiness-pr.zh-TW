---
title: Lync Server 2013：通話駐留的部署程式
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
ms.openlocfilehash: 997097da30db000df82cba020b043748a1a5f62d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522630"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="0520a-102">Lync Server 2013 中通話駐留的部署程式</span><span class="sxs-lookup"><span data-stu-id="0520a-102">Deployment process for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0520a-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0520a-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0520a-104">本節概述部署通話駐留應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="0520a-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="0520a-105">您必須先部署 Enterprise Edition 或 Standard Edition 搭配 Enterprise Voice，才能設定通話駐留。</span><span class="sxs-lookup"><span data-stu-id="0520a-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="0520a-106">當您部署企業語音時，會安裝並啟用通話駐留所需的元件。</span><span class="sxs-lookup"><span data-stu-id="0520a-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="0520a-107">通話駐留部署程式</span><span class="sxs-lookup"><span data-stu-id="0520a-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0520a-108">階段</span><span class="sxs-lookup"><span data-stu-id="0520a-108">Phase</span></span></th>
<th><span data-ttu-id="0520a-109">步驟</span><span class="sxs-lookup"><span data-stu-id="0520a-109">Steps</span></span></th>
<th><span data-ttu-id="0520a-110">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="0520a-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="0520a-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="0520a-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0520a-112">在軌道表格中設定通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="0520a-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="0520a-113">使用 Lync Server 控制台或 <strong>New-CSCallParkOrbit</strong> Cmdlet 來建立通話駐留軌道表格中的軌道範圍，並將其關聯至主控通話駐留應用程式的應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="0520a-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0520a-114">為了與現有的撥號對應表進行無縫整合，軌道範圍通常會設定為虛擬擴充區塊。</span><span class="sxs-lookup"><span data-stu-id="0520a-114">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="0520a-115">指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。</span><span class="sxs-lookup"><span data-stu-id="0520a-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="0520a-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0520a-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0520a-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0520a-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0520a-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0520a-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</a></span><span class="sxs-lookup"><span data-stu-id="0520a-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0520a-121">設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="0520a-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="0520a-122">使用 <strong>Set-CsCpsConfiguration</strong> Cmdlet 來設定通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="0520a-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="0520a-123">建議您至少將 <strong>OnTimeoutURI</strong> 選項設定為設定要在寄存通話超時時使用的回退目的地。您也可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="0520a-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="0520a-124"> (選用) <strong>EnableMusicOnHold</strong> 啟用或停用等候的音樂。</span><span class="sxs-lookup"><span data-stu-id="0520a-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="0520a-125"> (選用) <strong>MaxCallPickupAttempts</strong> 決定寄存來電在將來電轉送至回復的備用資源識別元 (URI) 之前所用的次數。</span><span class="sxs-lookup"><span data-stu-id="0520a-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="0520a-126"> (選用) <strong>CallPickupTimeoutThreshold</strong> 可決定通話之後所經過的時間長度，超過此時間之後，它會在接聽來電的電話之前所經過的時間。</span><span class="sxs-lookup"><span data-stu-id="0520a-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0520a-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0520a-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0520a-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0520a-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0520a-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0520a-131"><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中設定通話駐留設定</a></span><span class="sxs-lookup"><span data-stu-id="0520a-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0520a-132">（選用）自訂等候音樂</span><span class="sxs-lookup"><span data-stu-id="0520a-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="0520a-133">如果您不想要使用預設的等候音樂，請使用 <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> Cmdlet 自訂和上傳音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="0520a-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="0520a-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0520a-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0520a-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0520a-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0520a-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0520a-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自訂通話駐留的等候音樂</a></span><span class="sxs-lookup"><span data-stu-id="0520a-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0520a-139">設定語音原則為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="0520a-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="0520a-140">使用 Lync Server 控制台或具有<strong>EnableCallPark</strong>選項的<strong>Set-CSVoicePolicy</strong> Cmdlet，為語音原則中的使用者啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="0520a-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0520a-141">預設會停用所有使用者的通話駐留。</span><span class="sxs-lookup"><span data-stu-id="0520a-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="0520a-142">如果您有多個語音原則，請確定針對每個語音原則設定 EnableCallPark 屬性，而不只是針對預設原則。</span><span class="sxs-lookup"><span data-stu-id="0520a-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="0520a-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0520a-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0520a-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0520a-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="0520a-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0520a-147"><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中為使用者啟用通話駐留</a></span><span class="sxs-lookup"><span data-stu-id="0520a-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0520a-148">驗證通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="0520a-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="0520a-149">通話駐留軌道不得正規化。</span><span class="sxs-lookup"><span data-stu-id="0520a-149">Call park orbits must not be normalized.</span></span> <span data-ttu-id="0520a-150">請確認您的正規化規則不包含任何軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="0520a-150">Verify that your normalization rules do not include any of your orbit ranges.</span></span> <span data-ttu-id="0520a-151">如有必要，請建立其他正規化規則，以防止軌道正規化。</span><span class="sxs-lookup"><span data-stu-id="0520a-151">If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="0520a-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0520a-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0520a-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0520a-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0520a-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0520a-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0520a-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中驗證通話駐留的正規化規則</a></span><span class="sxs-lookup"><span data-stu-id="0520a-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0520a-157">驗證通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="0520a-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="0520a-158">測試停車場和取回通話，以確保您的設定如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="0520a-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0520a-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md"> (選用) 在 Lync Server 2013 中驗證通話駐留部署</a></span><span class="sxs-lookup"><span data-stu-id="0520a-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

