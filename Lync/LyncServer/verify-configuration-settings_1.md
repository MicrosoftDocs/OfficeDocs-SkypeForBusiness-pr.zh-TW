---
title: 確認組態設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7655547ff4f3e528b3948a537bbd5e85f351ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="fc55d-102">確認組態設定</span><span class="sxs-lookup"><span data-stu-id="fc55d-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc55d-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="fc55d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fc55d-104">在合併拓撲，並執行**Import-cslegacyconfiguration** cmdlet 之後，請確認您的 Office Communications Server 2007 R2 原則和設定都已匯入到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fc55d-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="fc55d-105">下表列出您應確認的原則及設定。</span><span class="sxs-lookup"><span data-stu-id="fc55d-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="fc55d-106">移轉後所需檢查的原則與設定</span><span class="sxs-lookup"><span data-stu-id="fc55d-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc55d-107">若是使用此工作量：</span><span class="sxs-lookup"><span data-stu-id="fc55d-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="fc55d-108">檢查下列原則與設定：</span><span class="sxs-lookup"><span data-stu-id="fc55d-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-109">立即訊息 (IM) 和會議</span><span class="sxs-lookup"><span data-stu-id="fc55d-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="fc55d-110">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-110">Presence policy</span></span></p>
<p><span data-ttu-id="fc55d-111">會議原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-112">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="fc55d-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="fc55d-113">撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="fc55d-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="fc55d-114">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="fc55d-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="fc55d-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="fc55d-116">語音原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-116">Voice policy</span></span></p>
<p><span data-ttu-id="fc55d-117">語音路由</span><span class="sxs-lookup"><span data-stu-id="fc55d-117">Voice routes</span></span></p>
<p><span data-ttu-id="fc55d-118">撥號計劃</span><span class="sxs-lookup"><span data-stu-id="fc55d-118">Dial plans</span></span></p>
<p><span data-ttu-id="fc55d-119">PSTN 使用方式設定</span><span class="sxs-lookup"><span data-stu-id="fc55d-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="fc55d-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="fc55d-121">簡單 URL</span><span class="sxs-lookup"><span data-stu-id="fc55d-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-122">外部使用者</span><span class="sxs-lookup"><span data-stu-id="fc55d-122">External users</span></span></p></td>
<td><p><span data-ttu-id="fc55d-123">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-124">封存</span><span class="sxs-lookup"><span data-stu-id="fc55d-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="fc55d-125">封存原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="fc55d-126">驗證原則與設定</span><span class="sxs-lookup"><span data-stu-id="fc55d-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="fc55d-127">在 Office Communications Server 2007 R2 環境中，記下撥號對應表的名稱 （以前稱為位置設定檔），列出撥入存取號碼 （會議服務員存取電話號碼和地區）、 語音路由和原則上表中，除了 Communicator Web Access 所用的 Url。</span><span class="sxs-lookup"><span data-stu-id="fc55d-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="fc55d-128">在 Lync Server 2013 前端伺服器上，開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="fc55d-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="fc55d-129">若要驗證匯入的會議原則，請在左窗格中，按一下 [**會議**]、 按一下 [**會議原則**]，然後確認 Office Communications Server 2007 R2 環境中的所有會議原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc55d-130">從舊版 Office Communications Server 的<STRONG>會議</STRONG>原則現在稱為 Lync Server 2013 中的會議原則。</span><span class="sxs-lookup"><span data-stu-id="fc55d-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="fc55d-131">此外，從舊版 Office Communications Server 的 [<STRONG>匿名參與者會</STRONG>設定現在是在 Lync Server 2013 會議原則設定。</span><span class="sxs-lookup"><span data-stu-id="fc55d-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc55d-132">在 [Office Communications Server 2007 R2，如果會議原則未設為<STRONG>每位使用者使用</STRONG>，僅全域原則設定會匯入。</span><span class="sxs-lookup"><span data-stu-id="fc55d-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="fc55d-133">在此情況下，將不會匯入其他的會議原則。</span><span class="sxs-lookup"><span data-stu-id="fc55d-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc55d-134">如果<STRONG>匿名參與者</STRONG>] 若是設為 [<STRONG>強制每位使用者</STRONG>Office Communications Server 2007 R2 會議原則中，會在移轉時建立兩個會議原則： <STRONG>allowanonymousparticipantsinmeetings</STRONG>設定為<STRONG>True</STRONG> ，且<STRONG>allowanonymousparticipantsinmeetings</STRONG>設定設<STRONG>為 False</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="fc55d-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="fc55d-135">若要驗證匯入的撥號對應表，請依序按一下 **[語音路由]** 與 **[撥號對應表]**，然後驗證您 Office Communicator 2007 R2 環境的所有撥號對應表都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc55d-136">在 Lync Server 2013 中，<STRONG>位置設定檔</STRONG>現在稱為<STRONG>撥號對應表計劃</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="fc55d-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="fc55d-137">若要驗證匯入的語音原則，請依序按一下 **[語音路由]** 與 **[語音原則]**，然後驗證您 Office Communicator 2007 R2 環境的所有語音原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc55d-138">如果語音原則未設為 [Office Communications Server 2007 R2 環境中的 [<STRONG>每位使用者使用</STRONG>，會匯入僅全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="fc55d-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="fc55d-139">在此情況下，將不會匯入其他的語音原則。</span><span class="sxs-lookup"><span data-stu-id="fc55d-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="fc55d-140">若要驗證匯入的語音路由，請依序按一下 **[語音路由]** 及 **[路由]**，然後驗證您 Office Communicator 2007 R2 環境中的所有語音路由都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="fc55d-141">若要驗證匯入的 PSTN 使用方式設定，請依序按一下 **[語音路由]** 及 **[PSTN 使用方式]**，然後驗證您 Office Communicator 2007 R2 環境中的 PSTN 使用方式設定包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="fc55d-142">若要驗證匯入的外部存取原則，請依序按一下 **[同盟與外部存取]** 及 **[外部存取原則]**，然後驗證您 Office Communicator 2007 R2 環境中的所有外部存取原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="fc55d-143">若要檢查封存原則，按一下 [**監控和封存**] 及 [**封存原則]**，然後確認 [Office Communications Server 2007 R2 環境中的所有封存原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="fc55d-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="fc55d-144">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fc55d-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="fc55d-145">若要驗證命令列的顯示狀態原則，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="fc55d-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="fc55d-146">透過查看**Identity**參數中的名稱，請確認 Office Communications Server 2007 R2 環境中的所有目前狀態原則都已匯入。</span><span class="sxs-lookup"><span data-stu-id="fc55d-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="fc55d-147">使用 Cmdlet 檢查原則與設定</span><span class="sxs-lookup"><span data-stu-id="fc55d-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="fc55d-148">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fc55d-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="fc55d-149">執行下表中的 Cmdlet，可以檢查原則及設定。</span><span class="sxs-lookup"><span data-stu-id="fc55d-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="fc55d-150">這些 Cmdlet 的語法會類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="fc55d-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="fc55d-151">如需這些 Cmdlet 的詳細資料，請執行：</span><span class="sxs-lookup"><span data-stu-id="fc55d-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc55d-152">若為下列原則或設定：</span><span class="sxs-lookup"><span data-stu-id="fc55d-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="fc55d-153">請使用此 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fc55d-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-154">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="fc55d-155"><strong>Get-cspresencepolicy</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-156">會議原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="fc55d-157"><strong>Get-csconferencingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-158">撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="fc55d-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="fc55d-159"><strong>Get-csdialinconferencingaccessnumber</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-160">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="fc55d-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="fc55d-161"><strong>Get-csdialplan</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-162">語音原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="fc55d-163"><strong>Get-csvoicepolicy</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-164">語音路由</span><span class="sxs-lookup"><span data-stu-id="fc55d-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="fc55d-165"><strong>Get-csvoiceroute</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-166">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="fc55d-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="fc55d-167"><strong>Get-cspstnusage</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-168">URL</span><span class="sxs-lookup"><span data-stu-id="fc55d-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="fc55d-169"><strong>Get-cssimpleurlconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55d-170">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="fc55d-171"><strong>Get-csexternalaccesspolicy</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55d-172">封存原則</span><span class="sxs-lookup"><span data-stu-id="fc55d-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="fc55d-173"><strong>Get-csarchivingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="fc55d-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

