---
title: 驗證組態設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="f316e-102">驗證組態設定</span><span class="sxs-lookup"><span data-stu-id="f316e-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f316e-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f316e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f316e-104">在您合併拓朴並執行**CsLegacyConfiguration** Cmdlet 之後，請確認您的 Office 通訊伺服器 2007 R2 原則和設定已匯入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f316e-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="f316e-105">下表列出您應該驗證的原則和設定。</span><span class="sxs-lookup"><span data-stu-id="f316e-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="f316e-106">遷移之後要驗證的原則和設定</span><span class="sxs-lookup"><span data-stu-id="f316e-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f316e-107">如果您使用此工作負載：</span><span class="sxs-lookup"><span data-stu-id="f316e-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="f316e-108">驗證這些原則與設定：</span><span class="sxs-lookup"><span data-stu-id="f316e-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f316e-109">立即訊息（IM）與會議</span><span class="sxs-lookup"><span data-stu-id="f316e-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="f316e-110">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="f316e-110">Presence policy</span></span></p>
<p><span data-ttu-id="f316e-111">會議原則</span><span class="sxs-lookup"><span data-stu-id="f316e-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-112">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="f316e-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="f316e-113">撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="f316e-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="f316e-114">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="f316e-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f316e-115">企業語音</span><span class="sxs-lookup"><span data-stu-id="f316e-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f316e-116">語音原則</span><span class="sxs-lookup"><span data-stu-id="f316e-116">Voice policy</span></span></p>
<p><span data-ttu-id="f316e-117">語音路由</span><span class="sxs-lookup"><span data-stu-id="f316e-117">Voice routes</span></span></p>
<p><span data-ttu-id="f316e-118">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="f316e-118">Dial plans</span></span></p>
<p><span data-ttu-id="f316e-119">PSTN 使用量設定</span><span class="sxs-lookup"><span data-stu-id="f316e-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="f316e-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="f316e-121">簡單 URL</span><span class="sxs-lookup"><span data-stu-id="f316e-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f316e-122">外部使用者</span><span class="sxs-lookup"><span data-stu-id="f316e-122">External users</span></span></p></td>
<td><p><span data-ttu-id="f316e-123">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f316e-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-124">封存</span><span class="sxs-lookup"><span data-stu-id="f316e-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="f316e-125">存檔原則</span><span class="sxs-lookup"><span data-stu-id="f316e-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="f316e-126">驗證原則與設定</span><span class="sxs-lookup"><span data-stu-id="f316e-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="f316e-127">在您的 Office 通訊伺服器 2007 R2 環境中，記下撥號方案的名稱（先前稱為位置設定檔）、撥入存取號碼（會議助理存取電話號碼和區域）、語音路由，以及本文中所列的原則。[前一張表格]，除了用於 Communicator Web Access 的 Url 之外。</span><span class="sxs-lookup"><span data-stu-id="f316e-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="f316e-128">在 Lync Server 2013 前端伺服器上，開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="f316e-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f316e-129">若要驗證已匯入的會議原則，請在左窗格中，按一下 [**會議**]，按一下 [**會議原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有會議原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f316e-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f316e-130">舊版 Office 通訊伺服器的<STRONG>會議</STRONG>原則現在稱為 Lync Server 2013 中的會議原則。</span><span class="sxs-lookup"><span data-stu-id="f316e-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="f316e-131">此外，舊版 Office 通訊伺服器的<STRONG>匿名 Particpants</STRONG>設定現在已成為 Lync Server 2013 會議原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="f316e-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f316e-132">在 Office 通訊伺服器 2007 R2 中，如果會議原則未設定為 [<STRONG>針對每位使用者使用</STRONG>]，則只會匯入全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="f316e-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="f316e-133">在這種情況下，不會匯入任何其他會議原則。</span><span class="sxs-lookup"><span data-stu-id="f316e-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f316e-134">如果您在 Office 通訊伺服器的 2007 R2 會議原則中，將<STRONG>匿名參與者</STRONG>設定為 [<STRONG>針對每位使用者強制執行</STRONG>]，則會在遷移期間建立兩個會議原則：一個使用<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>設定為<STRONG>True</STRONG> ，另一個<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>設為<STRONG>False</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f316e-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="f316e-135">若要驗證已匯入的撥號方案，請按一下 [**語音路由**]，按一下 [**撥號方案**]，然後確認您的 Office Communicator 2007 R2 環境中的所有撥號方案都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f316e-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f316e-136">在 Lync Server 2013 中，<STRONG>位置設定檔</STRONG>現在稱為<STRONG>撥號計畫</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f316e-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="f316e-137">若要驗證已匯入的語音原則，請按一下 [**語音路由**]，按一下 [**語音原則**]，然後確認您的 Office Communicator 2007 R2 環境中的所有語音原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f316e-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f316e-138">如果您未將語音原則設定為在您的 Office 通訊伺服器 2007 R2 環境中<STRONG>使用每位使用者</STRONG>，則只會匯入全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="f316e-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="f316e-139">在這種情況下，不會匯入任何其他語音原則。</span><span class="sxs-lookup"><span data-stu-id="f316e-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="f316e-140">若要驗證已匯入的語音路由，請按一下 [**語音路由**]，按一下 [**路由**]，然後確認您的 Office Communicator 2007 R2 環境中的所有語音路由都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f316e-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="f316e-141">若要確認已匯入 PSTN 使用設定，請按一下 [**語音路由**]，按一下 [ **PSTN 使用狀況**]，然後確認清單中包含您的 Office Communicator 2007 R2 環境中的 PSTN 使用狀況設定。</span><span class="sxs-lookup"><span data-stu-id="f316e-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="f316e-142">若要驗證已匯入的外部存取原則，請按一下 [**同盟及外部存取**]，按一下 [**外部存取原則**]，然後確認您的 Office Communicator 2007 R2 環境中的所有外部存取原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f316e-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="f316e-143">若要驗證歸檔原則，請按一下 [**監視及**封存]，按一下 [封存**原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有存檔原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f316e-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="f316e-144">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="f316e-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="f316e-145">若要驗證目前狀態原則，請在命令列輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="f316e-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="f316e-146">透過在身分**識別**參數中查看名稱，確認您的 Office 通訊伺服器 2007 R2 環境中的所有目前狀態原則都已匯入。</span><span class="sxs-lookup"><span data-stu-id="f316e-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="f316e-147">使用 Cmdlet 驗證原則和設定</span><span class="sxs-lookup"><span data-stu-id="f316e-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="f316e-148">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="f316e-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f316e-149">執行下表中的 Cmdlet，以驗證原則與設定。</span><span class="sxs-lookup"><span data-stu-id="f316e-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="f316e-150">這些 Cmdlet 的語法就像下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="f316e-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="f316e-151">如需這些 Cmdlet 的詳細資訊，請執行：</span><span class="sxs-lookup"><span data-stu-id="f316e-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f316e-152">針對此原則或設定：</span><span class="sxs-lookup"><span data-stu-id="f316e-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="f316e-153">使用此 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f316e-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f316e-154">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="f316e-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="f316e-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-156">會議原則</span><span class="sxs-lookup"><span data-stu-id="f316e-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="f316e-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f316e-158">撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="f316e-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="f316e-159"><strong>CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-160">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="f316e-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="f316e-161"><strong>CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f316e-162">語音原則</span><span class="sxs-lookup"><span data-stu-id="f316e-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="f316e-163"><strong>CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-164">語音路由</span><span class="sxs-lookup"><span data-stu-id="f316e-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="f316e-165"><strong>CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f316e-166">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="f316e-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="f316e-167"><strong>CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-168">Url</span><span class="sxs-lookup"><span data-stu-id="f316e-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="f316e-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f316e-170">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f316e-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="f316e-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f316e-172">存檔原則</span><span class="sxs-lookup"><span data-stu-id="f316e-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="f316e-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f316e-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

