---
title: 使用通話分析來疑難排解通話品質不佳的問題
ms.author: serdars
author: SerdarSoysal
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
description: 使用每個使用者的通話分析詳細資料，瞭解裝置、網路和連接能力，以疑難排解使用者Microsoft Teams通話和會議的問題。
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760558"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="91109-103">使用通話分析來疑難排解通話品質不佳的問題</span><span class="sxs-lookup"><span data-stu-id="91109-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="91109-104">本文說明如何使用通話分析來疑難排解個別Microsoft Teams使用者通話或會議品質不佳的問題，Teams或通訊支援專家Teams工程師。</span><span class="sxs-lookup"><span data-stu-id="91109-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>

## <a name="call-analytics-permissions"></a><span data-ttu-id="91109-105">通話分析許可權</span><span class="sxs-lookup"><span data-stu-id="91109-105">Call Analytics permissions</span></span>

<span data-ttu-id="91109-106">本文假設您已經設定通話分析。</span><span class="sxs-lookup"><span data-stu-id="91109-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="91109-107">如果沒有，請參閱[設定通話分析Teams。](set-up-call-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="91109-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="91109-108">通話分析簡介</span><span class="sxs-lookup"><span data-stu-id="91109-108">Introduction to call analytics</span></span>

<span data-ttu-id="91109-109">通話分析會顯示您Teams中每個使用者的通話和會議Office 365詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="91109-110">它包含裝置、網路、連接和通話品質 (任何一項資訊都可能是導致通話或會議品質不佳) 。</span><span class="sxs-lookup"><span data-stu-id="91109-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="91109-111">如果您上傳建築物、網站和租使用者資訊，也會針對每一個通話和會議顯示此資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="91109-112">使用通話分析來説明您瞭解使用者為何通話或會議體驗不佳。</span><span class="sxs-lookup"><span data-stu-id="91109-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="91109-113">通話分析會顯示通話或會議的每一個區段 ，例如，從一個參與者到另一個參與者。</span><span class="sxs-lookup"><span data-stu-id="91109-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="91109-114">您可以分析這些詳細資料，Teams管理員可以隔離問題區域，並找出品質不佳的根本原因。</span><span class="sxs-lookup"><span data-stu-id="91109-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>

<span data-ttu-id="91109-115">作為系統管理員Teams，您可以完全存取每個使用者的所有通話分析資料。</span><span class="sxs-lookup"><span data-stu-id="91109-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="91109-116">此外，您也可以將Azure Active Directory角色指派給支援人員。</span><span class="sxs-lookup"><span data-stu-id="91109-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="91109-117">若要深入瞭解這些角色，請參閱授予支援 [與支援服務人員的許可權](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。</span><span class="sxs-lookup"><span data-stu-id="91109-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="91109-118">請勿錯過每個支援[角色Teams的作用？](#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="91109-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="91109-119">在哪裡可以找到每個使用者的通話分析</span><span class="sxs-lookup"><span data-stu-id="91109-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="91109-120">若要查看使用者的所有通話資訊和資料，請前往系統管理Teams[中心](https://admin.teams.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="91109-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="91109-121">在 **使用者** 下，選取使用者，然後開啟&個人資料頁面上的會議與通話清單。</span><span class="sxs-lookup"><span data-stu-id="91109-121">Under **Users**, select a user and then open the **Meetings & Calls** tab on the user's profile page.</span></span> <span data-ttu-id="91109-122">您可以在這裡找到該使用者過去 30 天的所有通話和會議。</span><span class="sxs-lookup"><span data-stu-id="91109-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![所有分析使用者資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="91109-124">若要取得特定會話的其他資訊 ，包括詳細的媒體和網路統計資料，請按一下會話以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91109-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![通話分析使用者會話資料的螢幕擷取畫面](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="91109-126">每個支援Teams角色的作用是什麼？</span><span class="sxs-lookup"><span data-stu-id="91109-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="91109-127">第 **1 層** Teams通訊支援專家 (能) 基本通話品質問題。</span><span class="sxs-lookup"><span data-stu-id="91109-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="91109-128">他們不會調查會議的問題。</span><span class="sxs-lookup"><span data-stu-id="91109-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="91109-129">相反地，他們會收集相關資訊，然後升級為通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="91109-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span>

<span data-ttu-id="91109-130">第 **2 層** Teams通訊支援工程師 (第 2 層支援) 查看隱藏在通訊支援專家Teams通話記錄中的資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="91109-131">下表列出每個通訊支援角色Teams的資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="91109-132">下表告訴您每個通訊支援角色可用的每個使用者資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="91109-133">活動</span><span class="sxs-lookup"><span data-stu-id="91109-133">Activity</span></span>|<span data-ttu-id="91109-134">資訊</span><span class="sxs-lookup"><span data-stu-id="91109-134">Information</span></span>|<span data-ttu-id="91109-135">通訊內容</span><span class="sxs-lookup"><span data-stu-id="91109-135">What the communications</span></span><br><span data-ttu-id="91109-136">支援 *專家* 查看</span><span class="sxs-lookup"><span data-stu-id="91109-136">support *specialist* sees</span></span>|<span data-ttu-id="91109-137">通訊內容</span><span class="sxs-lookup"><span data-stu-id="91109-137">What the communications</span></span><br><span data-ttu-id="91109-138">支援 *工程師* 查看</span><span class="sxs-lookup"><span data-stu-id="91109-138">support *engineer* sees</span></span>|
|---|---|---|---|
|<span data-ttu-id="91109-139">**調用**</span><span class="sxs-lookup"><span data-stu-id="91109-139">**Calls**</span></span>|<span data-ttu-id="91109-140">來電者名稱</span><span class="sxs-lookup"><span data-stu-id="91109-140">Caller name</span></span>|<span data-ttu-id="91109-141">只有代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="91109-141">Only the name of the user for whom the agent searched.</span></span>|<span data-ttu-id="91109-142">使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="91109-142">User name.</span></span>|
||<span data-ttu-id="91109-143">收件者名稱</span><span class="sxs-lookup"><span data-stu-id="91109-143">Recipient name</span></span>|<span data-ttu-id="91109-144">以內部使用者或外部使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="91109-144">Shows as Internal User or External User.</span></span>|<span data-ttu-id="91109-145">收件者名稱。</span><span class="sxs-lookup"><span data-stu-id="91109-145">Recipient name.</span></span>|
||<span data-ttu-id="91109-146">來電者電話號碼</span><span class="sxs-lookup"><span data-stu-id="91109-146">Caller phone number</span></span>|<span data-ttu-id="91109-147">除了最後三位數以外，整個電話號碼會以星號符號混淆。</span><span class="sxs-lookup"><span data-stu-id="91109-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="91109-148">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="91109-148">For example, 15552823\*\*\*.</span></span>|<span data-ttu-id="91109-149">除了最後三位數以外，整個電話號碼會以星號符號混淆。</span><span class="sxs-lookup"><span data-stu-id="91109-149">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="91109-150">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="91109-150">For example, 15552823\*\*\*.</span></span>|
||<span data-ttu-id="91109-151">收件者電話號碼</span><span class="sxs-lookup"><span data-stu-id="91109-151">Recipient phone number</span></span>|<span data-ttu-id="91109-152">除了最後三位數以外，整個電話號碼會以星號符號混淆。</span><span class="sxs-lookup"><span data-stu-id="91109-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="91109-153">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="91109-153">For example, 15552823\*\*\*.</span></span>|<span data-ttu-id="91109-154">除了最後三位數以外，整個電話號碼會以星號符號混淆。</span><span class="sxs-lookup"><span data-stu-id="91109-154">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="91109-155">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="91109-155">For example, 15552823\*\*\*.</span></span>|
||<span data-ttu-id="91109-156">**通話詳細資料** \>**進位** 定位停駐點</span><span class="sxs-lookup"><span data-stu-id="91109-156">**Call Details** \> **Advanced** tab</span></span>|<span data-ttu-id="91109-157">未顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-157">Information not shown.</span></span>|<span data-ttu-id="91109-158">顯示的所有詳細資料，例如裝置名稱、IP 位址、子網映射等。</span><span class="sxs-lookup"><span data-stu-id="91109-158">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>|
||<span data-ttu-id="91109-159">**通話詳細資料** \>**進位** \>**調試** 鍵</span><span class="sxs-lookup"><span data-stu-id="91109-159">**Call Details** \> **Advanced** \> **Debug** tab</span></span>|<span data-ttu-id="91109-160">未顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="91109-160">Information not shown.</span></span>|<span data-ttu-id="91109-161">顯示的所有詳細資料，例如 DNS 尾碼和 SSID。</span><span class="sxs-lookup"><span data-stu-id="91109-161">All details shown, such as DNS suffix and SSID.</span></span>|
|<span data-ttu-id="91109-162">**會議**</span><span class="sxs-lookup"><span data-stu-id="91109-162">**Meetings**</span></span>|<span data-ttu-id="91109-163">參與者名稱</span><span class="sxs-lookup"><span data-stu-id="91109-163">Participant names</span></span>|<span data-ttu-id="91109-164">只有代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="91109-164">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="91109-165">識別為內部使用者或外部使用者的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="91109-165">Other participants identified as Internal User or External User.</span></span>|<span data-ttu-id="91109-166">顯示所有名稱。</span><span class="sxs-lookup"><span data-stu-id="91109-166">All names shown.</span></span>|
||<span data-ttu-id="91109-167">參與者計數</span><span class="sxs-lookup"><span data-stu-id="91109-167">Participant count</span></span>|<span data-ttu-id="91109-168">參與者人數。</span><span class="sxs-lookup"><span data-stu-id="91109-168">Number of participants.</span></span>|<span data-ttu-id="91109-169">參與者人數。</span><span class="sxs-lookup"><span data-stu-id="91109-169">Number of participants.</span></span>|
||<span data-ttu-id="91109-170">會話詳細資料</span><span class="sxs-lookup"><span data-stu-id="91109-170">Session details</span></span>|<span data-ttu-id="91109-171">會話詳細資料以例外顯示。</span><span class="sxs-lookup"><span data-stu-id="91109-171">Session details shown with exceptions.</span></span> <span data-ttu-id="91109-172">只會顯示代理程式搜尋的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="91109-172">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="91109-173">識別為內部使用者或外部使用者的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="91109-173">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="91109-174">電話號碼的最後三位數會以星號符號混淆。</span><span class="sxs-lookup"><span data-stu-id="91109-174">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>|<span data-ttu-id="91109-175">顯示會話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91109-175">Session details shown.</span></span> <span data-ttu-id="91109-176">顯示使用者名稱和會話詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91109-176">User names and session details shown.</span></span> <span data-ttu-id="91109-177">電話號碼的最後三位數會以星號符號混淆。</span><span class="sxs-lookup"><span data-stu-id="91109-177">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>|
||||

## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="91109-178">疑難排解使用者通話品質問題</span><span class="sxs-lookup"><span data-stu-id="91109-178">Troubleshoot user call quality problems</span></span>

1. <span data-ttu-id="91109-179">開啟 Teams系統管理中心 () ，然後使用您的 Teams 通訊支援或Teams <https://admin.teams.microsoft.com> 認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="91109-179">Open the Teams admin center (<https://admin.teams.microsoft.com>) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="91109-180">在儀表板 **的** 使用者 **搜尋** 中，開始輸入您想要進行疑難排解之通話之使用者的名稱或 SIP 位址，或選取查看使用者以查看使用者清單。</span><span class="sxs-lookup"><span data-stu-id="91109-180">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="91109-181">從清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="91109-181">Select the user from the list.</span></span>

4. <span data-ttu-id="91109-182">選取 **通話記錄**，然後選取您想要疑難排解的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="91109-182">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>

5. <span data-ttu-id="91109-183">選取進 **一頁** ，然後尋找黃色和紅色專案，指出通話品質不佳或連接問題。</span><span class="sxs-lookup"><span data-stu-id="91109-183">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>

   <span data-ttu-id="91109-184">在每個通話或會議的會議詳細資料中，次要問題會以黃色顯示。</span><span class="sxs-lookup"><span data-stu-id="91109-184">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="91109-185">如果某些專案是黃色，表示它超出正常範圍，而且可能會造成問題，但不太可能是問題的主要原因。</span><span class="sxs-lookup"><span data-stu-id="91109-185">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="91109-186">如果內容為紅色，這是一個嚴重的問題，而且可能是導致此會話通話品質不佳的主要原因。</span><span class="sxs-lookup"><span data-stu-id="91109-186">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span>

<span data-ttu-id="91109-187">在少數情況下，音訊會話不會收到體驗品質資料。</span><span class="sxs-lookup"><span data-stu-id="91109-187">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="91109-188">這通常是由中斷的通話或與用戶端的連線終止所導致。</span><span class="sxs-lookup"><span data-stu-id="91109-188">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="91109-189">發生此情況時，會話分級 **無法使用**。</span><span class="sxs-lookup"><span data-stu-id="91109-189">When this occurs, the session rating is **unavailable**.</span></span>

<span data-ttu-id="91109-190">如果音訊會話具有使用者體驗品質 (QoE) ，下表說明將會話視為不佳的主要 **問題**。</span><span class="sxs-lookup"><span data-stu-id="91109-190">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>

|<span data-ttu-id="91109-191">問題</span><span class="sxs-lookup"><span data-stu-id="91109-191">Issue</span></span>|<span data-ttu-id="91109-192">地區</span><span class="sxs-lookup"><span data-stu-id="91109-192">Area</span></span>|<span data-ttu-id="91109-193">描述</span><span class="sxs-lookup"><span data-stu-id="91109-193">Description</span></span>|
|---|---|---|
|<span data-ttu-id="91109-194">通話設定</span><span class="sxs-lookup"><span data-stu-id="91109-194">Call setup</span></span>|<span data-ttu-id="91109-195">會話</span><span class="sxs-lookup"><span data-stu-id="91109-195">Session</span></span>|<span data-ttu-id="91109-196">錯誤碼 Ms-diag 20-29 表示通話設定失敗。</span><span class="sxs-lookup"><span data-stu-id="91109-196">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="91109-197">使用者無法加入通話或會議。</span><span class="sxs-lookup"><span data-stu-id="91109-197">The user couldn't join the call or meeting.</span></span>|
|<span data-ttu-id="91109-198">音訊網路分類不良通話</span><span class="sxs-lookup"><span data-stu-id="91109-198">Audio network classified poor call</span></span>|<span data-ttu-id="91109-199">會話</span><span class="sxs-lookup"><span data-stu-id="91109-199">Session</span></span>|<span data-ttu-id="91109-200">網路品質問題 (例如封包遺失、抖動、核OS 降級、RTT 或隱藏比) 發生。</span><span class="sxs-lookup"><span data-stu-id="91109-200">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>|
|<span data-ttu-id="91109-201">裝置無法運作</span><span class="sxs-lookup"><span data-stu-id="91109-201">Device not functioning</span></span>|<span data-ttu-id="91109-202">裝置</span><span class="sxs-lookup"><span data-stu-id="91109-202">Device</span></span>|<span data-ttu-id="91109-203">裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="91109-203">A device isn't functioning correctly.</span></span> <span data-ttu-id="91109-204">裝置無法運作的比例為：</span><span class="sxs-lookup"><span data-stu-id="91109-204">Device not functioning ratios are:</span></span> <p> <span data-ttu-id="91109-205">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="91109-205">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br>  <span data-ttu-id="91109-206">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="91109-206">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span>|
||||

## <a name="related-topics"></a><span data-ttu-id="91109-207">相關主題</span><span class="sxs-lookup"><span data-stu-id="91109-207">Related topics</span></span>

[<span data-ttu-id="91109-208">設定每個使用者的通話分析</span><span class="sxs-lookup"><span data-stu-id="91109-208">Set up per-user call analytics</span></span>](set-up-call-analytics.md)
