---
title: 確認組態設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2430fe82aa424571405def33139ba315677ffcc7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="5ff81-102">確認組態設定</span><span class="sxs-lookup"><span data-stu-id="5ff81-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ff81-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5ff81-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5ff81-104">在您合併拓撲並執行**Import-CsLegacyConfiguration** Cmdlet 後，請確認您的 Office 通訊伺服器 2007 R2 原則和設定已匯入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="5ff81-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="5ff81-105">下表列出您應確認的原則及設定。</span><span class="sxs-lookup"><span data-stu-id="5ff81-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="5ff81-106">移轉後所需檢查的原則與設定</span><span class="sxs-lookup"><span data-stu-id="5ff81-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ff81-107">若是使用此工作量：</span><span class="sxs-lookup"><span data-stu-id="5ff81-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="5ff81-108">檢查下列原則與設定：</span><span class="sxs-lookup"><span data-stu-id="5ff81-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-109">立即訊息 (IM) 和會議</span><span class="sxs-lookup"><span data-stu-id="5ff81-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="5ff81-110">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-110">Presence policy</span></span></p>
<p><span data-ttu-id="5ff81-111">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-112">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="5ff81-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="5ff81-113">撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="5ff81-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="5ff81-114">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="5ff81-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="5ff81-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="5ff81-116">語音原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-116">Voice policy</span></span></p>
<p><span data-ttu-id="5ff81-117">語音路由</span><span class="sxs-lookup"><span data-stu-id="5ff81-117">Voice routes</span></span></p>
<p><span data-ttu-id="5ff81-118">撥號計劃</span><span class="sxs-lookup"><span data-stu-id="5ff81-118">Dial plans</span></span></p>
<p><span data-ttu-id="5ff81-119">PSTN 使用方式設定</span><span class="sxs-lookup"><span data-stu-id="5ff81-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="5ff81-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="5ff81-121">簡單 URL</span><span class="sxs-lookup"><span data-stu-id="5ff81-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-122">外部使用者</span><span class="sxs-lookup"><span data-stu-id="5ff81-122">External users</span></span></p></td>
<td><p><span data-ttu-id="5ff81-123">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-124">封存</span><span class="sxs-lookup"><span data-stu-id="5ff81-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="5ff81-125">封存原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="5ff81-126">驗證原則與設定</span><span class="sxs-lookup"><span data-stu-id="5ff81-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="5ff81-127">在您的 Office 通訊伺服器 2007 R2 環境中，請記下撥號對應表（以前稱為位置設定檔）名稱、撥入存取號碼（會議應答存取電話號碼和地區）、語音路由以及上表所列的原則，以及用於 Communicator Web Access 的 URLs。</span><span class="sxs-lookup"><span data-stu-id="5ff81-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="5ff81-128">在 Lync Server 2013 前端伺服器上，開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="5ff81-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="5ff81-129">若要驗證匯入的會議原則，請在左窗格中，依序按一下 [**會議**]、[**會議原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有會議原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ff81-130">先前版本的 Office 通訊伺服器的<STRONG>會議</STRONG>原則現在稱為 Lync Server 2013 中的會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ff81-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="5ff81-131">此外，舊版 Office 通訊伺服器的<STRONG>匿名 Particpants</STRONG>設定現在是 Lync Server 2013 會議原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="5ff81-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ff81-132">在 Office 通訊伺服器 2007 R2 中，如果會議原則並未設定為 [<STRONG>每位使用者使用</STRONG>]，則只會匯入全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="5ff81-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="5ff81-133">在此情況下，將不會匯入其他的會議原則。</span><span class="sxs-lookup"><span data-stu-id="5ff81-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ff81-134">如果在您的 Office 通訊伺服器 2007 R2 會議原則中，將<STRONG>匿名參與者</STRONG>設定為<STRONG>針對每位使用者強制執行</STRONG>，則在遷移期間會建立兩個會議原則：其中一個<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>設定為 True，另一個<STRONG>則</STRONG>使用<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>設定為<STRONG>False</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="5ff81-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="5ff81-135">若要驗證匯入的撥號對應表，請依序按一下 **[語音路由]** 與 **[撥號對應表]**，然後驗證您 Office Communicator 2007 R2 環境的所有撥號對應表都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ff81-136">在 Lync Server 2013 中，<STRONG>位置設定檔</STRONG>現在稱為<STRONG>撥號</STRONG>對應表。</span><span class="sxs-lookup"><span data-stu-id="5ff81-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="5ff81-137">若要驗證匯入的語音原則，請依序按一下 **[語音路由]** 與 **[語音原則]**，然後驗證您 Office Communicator 2007 R2 環境的所有語音原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ff81-138">如果您的 Office 通訊伺服器 2007 R2 環境中的<STRONG>每位使用者</STRONG>未設定語音原則，則只會匯入全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="5ff81-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="5ff81-139">在此情況下，將不會匯入其他的語音原則。</span><span class="sxs-lookup"><span data-stu-id="5ff81-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="5ff81-140">若要驗證匯入的語音路由，請依序按一下 **[語音路由]** 及 **[路由]**，然後驗證您 Office Communicator 2007 R2 環境中的所有語音路由都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="5ff81-141">若要驗證匯入的 PSTN 使用方式設定，請依序按一下 **[語音路由]** 及 **[PSTN 使用方式]**，然後驗證您 Office Communicator 2007 R2 環境中的 PSTN 使用方式設定包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="5ff81-142">若要驗證匯入的外部存取原則，請依序按一下 **[同盟與外部存取]** 及 **[外部存取原則]**，然後驗證您 Office Communicator 2007 R2 環境中的所有外部存取原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="5ff81-143">若要驗證封存原則，請依序按一下 [**監視與**封存]、[封存**原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有封存原則都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="5ff81-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="5ff81-144">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5ff81-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="5ff81-145">若要驗證命令列的顯示狀態原則，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="5ff81-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="5ff81-146">透過查看**Identity**參數中的名稱，確認已匯入 Office 通訊伺服器 2007 R2 環境中的所有目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="5ff81-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="5ff81-147">使用 Cmdlet 檢查原則與設定</span><span class="sxs-lookup"><span data-stu-id="5ff81-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="5ff81-148">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5ff81-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="5ff81-149">執行下表中的 Cmdlet，可以檢查原則及設定。</span><span class="sxs-lookup"><span data-stu-id="5ff81-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="5ff81-150">這些 Cmdlet 的語法會類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="5ff81-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="5ff81-151">如需這些 Cmdlet 的詳細資料，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ff81-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ff81-152">若為下列原則或設定：</span><span class="sxs-lookup"><span data-stu-id="5ff81-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="5ff81-153">請使用此 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5ff81-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-154">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="5ff81-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-156">會議原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="5ff81-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-158">撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="5ff81-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="5ff81-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-160">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="5ff81-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="5ff81-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-162">語音原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="5ff81-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-164">語音路由</span><span class="sxs-lookup"><span data-stu-id="5ff81-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="5ff81-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-166">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="5ff81-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="5ff81-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-168">URL</span><span class="sxs-lookup"><span data-stu-id="5ff81-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="5ff81-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff81-170">外部存取原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="5ff81-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff81-172">封存原則</span><span class="sxs-lookup"><span data-stu-id="5ff81-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="5ff81-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ff81-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

