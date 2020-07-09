---
title: 使用呼叫分析來排查不佳的通話品質問題
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用針對裝置、網路和連線的每個使用者呼叫分析詳細資料，以解決 Microsoft 團隊通話和會議的使用者問題。
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085319"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="8762a-103">使用呼叫分析來排查不佳的通話品質問題</span><span class="sxs-lookup"><span data-stu-id="8762a-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="8762a-104">本文說明如何使用呼叫分析來針對個別使用者進行較差的 Microsoft 團隊通話或會議品質（如果您是團隊管理員或團隊溝通支援專家或工程師）。</span><span class="sxs-lookup"><span data-stu-id="8762a-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>


  
## <a name="call-analytics-permissions"></a><span data-ttu-id="8762a-105">呼叫分析許可權</span><span class="sxs-lookup"><span data-stu-id="8762a-105">Call Analytics permissions</span></span>

<span data-ttu-id="8762a-106">本文假設您已設定通話分析。</span><span class="sxs-lookup"><span data-stu-id="8762a-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="8762a-107">如果您還沒有，請閱讀[設定小組的呼叫分析](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="8762a-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="8762a-108">通話分析簡介</span><span class="sxs-lookup"><span data-stu-id="8762a-108">Introduction to call analytics</span></span>

<span data-ttu-id="8762a-109">[通話分析] 會顯示針對您 Office 365 帳戶中每位使用者的小組通話與會議的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8762a-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="8762a-110">它包含有關裝置、網路、連線及通話品質的資訊（這些都可能是不佳通話或會議品質的一個因素）。</span><span class="sxs-lookup"><span data-stu-id="8762a-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="8762a-111">如果您上傳的是建築物、網站和租使用者資訊，也會針對每個通話和會議顯示此資訊。</span><span class="sxs-lookup"><span data-stu-id="8762a-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="8762a-112">使用呼叫分析，協助您找出使用者為何通話或會議體驗不佳的原因。</span><span class="sxs-lookup"><span data-stu-id="8762a-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="8762a-113">[通話分析] 會顯示通話或會議的每個腿，例如，從一個參與者到第二個參與者。</span><span class="sxs-lookup"><span data-stu-id="8762a-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="8762a-114">透過分析這些詳細資料，團隊管理員可以隔離問題區域並找出品質欠佳的根本原因。</span><span class="sxs-lookup"><span data-stu-id="8762a-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>
   
<span data-ttu-id="8762a-115">就像團隊管理員一樣，您可以完全存取每位使用者的所有呼叫分析資料。</span><span class="sxs-lookup"><span data-stu-id="8762a-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="8762a-116">此外，您也可以將 Azure Active Directory 角色指派給支援人員。</span><span class="sxs-lookup"><span data-stu-id="8762a-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="8762a-117">若要深入瞭解這些角色，請參閱[提供支援和技術人員的許可權](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。</span><span class="sxs-lookup"><span data-stu-id="8762a-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="8762a-118">不要錯過[每個團隊是否支援 role？](#what-does-each-teams-support-role-do)在下方。</span><span class="sxs-lookup"><span data-stu-id="8762a-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="8762a-119">尋找每個使用者的呼叫分析的位置</span><span class="sxs-lookup"><span data-stu-id="8762a-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="8762a-120">若要查看使用者的所有呼叫資訊和資料，請移至[團隊系統管理中心](https://admin.teams.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="8762a-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="8762a-121">在 [**使用者**] 底下，選取使用者，然後在使用者的設定檔頁面面上開啟 [**通話記錄**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8762a-121">Under **Users**, select a user and then open the **Call History** tab on the user's profile page.</span></span> <span data-ttu-id="8762a-122">您可以在這裡找到該使用者在過去30天內的所有通話與會議。</span><span class="sxs-lookup"><span data-stu-id="8762a-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![所有分析使用者資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="8762a-124">若要取得指定會話的其他資訊，包括詳細的媒體和網路統計資料，請按一下某個會話以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8762a-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![呼叫分析使用者會話資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="8762a-126">每個團隊支援角色的功能是什麼？</span><span class="sxs-lookup"><span data-stu-id="8762a-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="8762a-127">**團隊通訊支援專家**（第1層支援）會處理基本的通話品質問題。</span><span class="sxs-lookup"><span data-stu-id="8762a-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="8762a-128">他們不會調查會議的問題。</span><span class="sxs-lookup"><span data-stu-id="8762a-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="8762a-129">相反地，他們會收集相關資訊，然後升級至通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="8762a-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span> 

<span data-ttu-id="8762a-130">**團隊通訊支援工程師**（第2層支援）會查看小組通訊支援專家隱藏的詳細通話記錄中的資訊。</span><span class="sxs-lookup"><span data-stu-id="8762a-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="8762a-131">下表列出每個小組通訊支援角色所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8762a-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="8762a-132">下表說明每個使用者資訊可供每個通訊支援角色使用。</span><span class="sxs-lookup"><span data-stu-id="8762a-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="8762a-133">**活動**</span><span class="sxs-lookup"><span data-stu-id="8762a-133">**Activity**</span></span>|<span data-ttu-id="8762a-134">**錯誤資訊**</span><span class="sxs-lookup"><span data-stu-id="8762a-134">**Information**</span></span>|<span data-ttu-id="8762a-135">溝通支援**專家**所能看到的內容</span><span class="sxs-lookup"><span data-stu-id="8762a-135">What the communications support **specialist** sees</span></span>|<span data-ttu-id="8762a-136">溝通支援**工程師**所能看到的內容</span><span class="sxs-lookup"><span data-stu-id="8762a-136">What the communications support **engineer** sees</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8762a-137">**撥**</span><span class="sxs-lookup"><span data-stu-id="8762a-137">**Calls**</span></span> <br/> |<span data-ttu-id="8762a-138">來電者名稱</span><span class="sxs-lookup"><span data-stu-id="8762a-138">Caller name</span></span>  <br/> |<span data-ttu-id="8762a-139">僅限代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="8762a-139">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="8762a-140">[使用者名稱]。</span><span class="sxs-lookup"><span data-stu-id="8762a-140">User name.</span></span>  <br/> |
||<span data-ttu-id="8762a-141">收件者名稱</span><span class="sxs-lookup"><span data-stu-id="8762a-141">Recipient name</span></span>  <br/> |<span data-ttu-id="8762a-142">顯示為內部使用者或外部使用者。</span><span class="sxs-lookup"><span data-stu-id="8762a-142">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="8762a-143">收件者名稱。</span><span class="sxs-lookup"><span data-stu-id="8762a-143">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="8762a-144">來電者電話號碼</span><span class="sxs-lookup"><span data-stu-id="8762a-144">Caller phone number</span></span>  <br/> |<span data-ttu-id="8762a-145">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="8762a-145">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="8762a-146">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8762a-146">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="8762a-147">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="8762a-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="8762a-148">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8762a-148">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="8762a-149">收件者電話號碼</span><span class="sxs-lookup"><span data-stu-id="8762a-149">Recipient phone number</span></span>  <br/> |<span data-ttu-id="8762a-150">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="8762a-150">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="8762a-151">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8762a-151">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="8762a-152">除後三位數以外的整個電話號碼都會以星號符號加以混淆。</span><span class="sxs-lookup"><span data-stu-id="8762a-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="8762a-153">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8762a-153">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="8762a-154">**通話詳細資料**  > [**高級**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="8762a-154">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="8762a-155">未顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="8762a-155">Information not shown.</span></span>  <br/> |<span data-ttu-id="8762a-156">顯示所有的詳細資料，例如裝置名稱、IP 位址、子網對應等。</span><span class="sxs-lookup"><span data-stu-id="8762a-156">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="8762a-157">**通話詳細資料**  > [**高級**  >  ][**調試**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="8762a-157">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="8762a-158">未顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="8762a-158">Information not shown.</span></span>  <br/> |<span data-ttu-id="8762a-159">顯示所有的詳細資料，例如 DNS 尾碼和 SSID。</span><span class="sxs-lookup"><span data-stu-id="8762a-159">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="8762a-160">**會議**</span><span class="sxs-lookup"><span data-stu-id="8762a-160">**Meetings**</span></span> <br/> |<span data-ttu-id="8762a-161">參與者名稱</span><span class="sxs-lookup"><span data-stu-id="8762a-161">Participant names</span></span>  <br/> |<span data-ttu-id="8762a-162">僅限代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="8762a-162">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="8762a-163">已識別為內部使用者或外部使用者的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="8762a-163">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="8762a-164">顯示所有名稱。</span><span class="sxs-lookup"><span data-stu-id="8762a-164">All names shown.</span></span>  <br/> |
||<span data-ttu-id="8762a-165">參與者計數</span><span class="sxs-lookup"><span data-stu-id="8762a-165">Participant count</span></span>  <br/> |<span data-ttu-id="8762a-166">參與者數目。</span><span class="sxs-lookup"><span data-stu-id="8762a-166">Number of participants.</span></span>  <br/> |<span data-ttu-id="8762a-167">參與者數目。</span><span class="sxs-lookup"><span data-stu-id="8762a-167">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="8762a-168">會話詳細資料</span><span class="sxs-lookup"><span data-stu-id="8762a-168">Session details</span></span>  <br/> |<span data-ttu-id="8762a-169">顯示的會話詳細資料（含例外狀況）。</span><span class="sxs-lookup"><span data-stu-id="8762a-169">Session details shown with exceptions.</span></span> <span data-ttu-id="8762a-170">只顯示代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="8762a-170">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="8762a-171">已識別為內部使用者或外部使用者的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="8762a-171">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="8762a-172">以星號符號加以混淆之電話號碼的後三位數。</span><span class="sxs-lookup"><span data-stu-id="8762a-172">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="8762a-173">顯示 [會話詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="8762a-173">Session details shown.</span></span> <span data-ttu-id="8762a-174">顯示 [使用者名稱] 和 [會話詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="8762a-174">User names and session details shown.</span></span> <span data-ttu-id="8762a-175">以星號符號加以混淆之電話號碼的後三位數。</span><span class="sxs-lookup"><span data-stu-id="8762a-175">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="8762a-176">疑難排解使用者通話品質問題</span><span class="sxs-lookup"><span data-stu-id="8762a-176">Troubleshoot user call quality problems</span></span> 

1. <span data-ttu-id="8762a-177">開啟 [團隊系統管理中心] （ https://admin.teams.microsoft.com) 並以您的小組通訊支援或團隊管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="8762a-177">Open the Teams admin center (https://admin.teams.microsoft.com) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="8762a-178">在**儀表板**上的 [**使用者搜尋**] 中，開始輸入您想要排查其通話問題之使用者的名稱或 SIP 位址，或選取 [**查看使用者**] 來查看使用者清單。</span><span class="sxs-lookup"><span data-stu-id="8762a-178">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="8762a-179">從清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="8762a-179">Select the user from the list.</span></span>

4. <span data-ttu-id="8762a-180">選取 [**通話記錄**]，然後選取您想要疑難排解的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="8762a-180">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
5. <span data-ttu-id="8762a-181">選取 [**高級**] 索引標籤，然後尋找黃色和紅色專案，指出通話品質或連線問題不佳。</span><span class="sxs-lookup"><span data-stu-id="8762a-181">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="8762a-182">在每個通話或會議的 [會話詳細資料] 中，次要問題會以黃色顯示。</span><span class="sxs-lookup"><span data-stu-id="8762a-182">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="8762a-183">如果有黃色，則它不在正常範圍之內，可能會造成問題，但不太可能是問題的主要原因。</span><span class="sxs-lookup"><span data-stu-id="8762a-183">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="8762a-184">如果有紅色，這是一個很重要的問題，這可能是這個會話的通話品質不佳的主要原因。</span><span class="sxs-lookup"><span data-stu-id="8762a-184">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
      
<span data-ttu-id="8762a-185">在少數情況下，音訊會話的體驗資料品質不會收到。</span><span class="sxs-lookup"><span data-stu-id="8762a-185">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="8762a-186">這通常是由中斷的通話或與用戶端的連線所導致。</span><span class="sxs-lookup"><span data-stu-id="8762a-186">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="8762a-187">發生這種情況時，**無法使用**[會議評等]。</span><span class="sxs-lookup"><span data-stu-id="8762a-187">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="8762a-188">對於有經驗品質（QoE）資料的音訊會話，下表說明將會話限制為**不良**的主要問題。</span><span class="sxs-lookup"><span data-stu-id="8762a-188">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="8762a-189">**問題**</span><span class="sxs-lookup"><span data-stu-id="8762a-189">**Issue**</span></span>|<span data-ttu-id="8762a-190">**圖**</span><span class="sxs-lookup"><span data-stu-id="8762a-190">**Area**</span></span>|<span data-ttu-id="8762a-191">**描述**</span><span class="sxs-lookup"><span data-stu-id="8762a-191">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8762a-192">撥號設定</span><span class="sxs-lookup"><span data-stu-id="8762a-192">Call setup</span></span>  <br/> |<span data-ttu-id="8762a-193">工作階段</span><span class="sxs-lookup"><span data-stu-id="8762a-193">Session</span></span>  <br/> |<span data-ttu-id="8762a-194">錯誤碼 Ms-診斷程式20-29 指出通話設定失敗。</span><span class="sxs-lookup"><span data-stu-id="8762a-194">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="8762a-195">使用者無法加入通話或會議。</span><span class="sxs-lookup"><span data-stu-id="8762a-195">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="8762a-196">音訊網路分類不佳通話</span><span class="sxs-lookup"><span data-stu-id="8762a-196">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="8762a-197">工作階段</span><span class="sxs-lookup"><span data-stu-id="8762a-197">Session</span></span>  <br/> |<span data-ttu-id="8762a-198">遇到網路品質問題（例如資料包遺失、抖動、NMOS 下降、RTT 或隱藏比率）。</span><span class="sxs-lookup"><span data-stu-id="8762a-198">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>  <br/> |
|<span data-ttu-id="8762a-199">裝置無法運作</span><span class="sxs-lookup"><span data-stu-id="8762a-199">Device not functioning</span></span>  <br/> |<span data-ttu-id="8762a-200">裝置</span><span class="sxs-lookup"><span data-stu-id="8762a-200">Device</span></span>  <br/> | <span data-ttu-id="8762a-201">裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="8762a-201">A device isn't functioning correctly.</span></span> <span data-ttu-id="8762a-202">裝置的運作比例如下：</span><span class="sxs-lookup"><span data-stu-id="8762a-202">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="8762a-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="8762a-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="8762a-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="8762a-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="8762a-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="8762a-205">Related topics</span></span>

[<span data-ttu-id="8762a-206">設定每個使用者的呼叫分析</span><span class="sxs-lookup"><span data-stu-id="8762a-206">Set up per-user call analytics</span></span>](set-up-call-analytics.md)



  
 
