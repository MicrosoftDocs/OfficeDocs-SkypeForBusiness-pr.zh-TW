---
title: 與其他組織的使用者通話與聊天
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用外部存取 (同盟) 和來賓存取在 Microsoft Teams 中與組織外的使用者通話、聊天以及尋找和新增使用者。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031809"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a><span data-ttu-id="43a37-103">在 Microsoft Teams 中與其他組織的使用者通話和聊天</span><span class="sxs-lookup"><span data-stu-id="43a37-103">Call and chat with users from other organizations in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="43a37-p101">當您需要與組織外的人員通訊和共同作業時，Microsoft Teams 提供您兩種不同的方式。第一個： **外部存取** (同盟) - 可讓您尋找、通話並與其他網域 (如 contoso.com) 中的使用者聊天。第二個： **來賓存取** - 可讓您使用對方的電子郵件地址，將其新增到您的團隊。您可以像與組織中的任何其他使用者一樣與來賓共同作業。</span><span class="sxs-lookup"><span data-stu-id="43a37-p101">When you need to communicate and collaborate with people outside your organization, Microsoft Teams gives you two different ways to make that happen. The first – **external access** (federation) – lets  you find, call, and chat with users in other domains (for example, contoso.com). The second – **guest access** – lets you add individuals to your teams, as guests, using their email address. You can collaborate with guests as you would with any other users in your organization.</span></span>

<span data-ttu-id="43a37-108">如有需要，您可以同時使用外部存取和來賓存取，兩者不互相牴觸。</span><span class="sxs-lookup"><span data-stu-id="43a37-108">You can use both external access and guest access if you want - one doesn't preclude the other.</span></span>

<span data-ttu-id="43a37-109">以下是更進階的選擇方法 (如需詳細比較，請跳至[比較外部與和來賓存取](#compare-external-and-guest-access))：</span><span class="sxs-lookup"><span data-stu-id="43a37-109">At a high level, here’s how to choose (for a detailed comparison, jump down to [Compare external and guest access](#compare-external-and-guest-access)):</span></span>

## <a name="external-access"></a><span data-ttu-id="43a37-110">外部存取</span><span class="sxs-lookup"><span data-stu-id="43a37-110">External access</span></span>

<span data-ttu-id="43a37-p102">當您需要可讓其他網域中的外部使用者尋找、通話、聊天和設定會議的解決方案時，可以使用 **外部存取** (同盟)。外部使用者不能存取您組織的團隊或團隊資源。當您要與仍然使用商務用 Skype (線上或內部部署) 或 Skype (2020 年年初推出) 的組織外部使用者通訊時，請選擇外部存取。</span><span class="sxs-lookup"><span data-stu-id="43a37-p102">Use **external access** (federation) when you need a solution that lets external users in other domains find, call, chat, and set up meetings with you. External users have no access to your organization's teams or team resources. Choose external access when you want to communicate with users outside your organization who are still on Skype for Business (online or on premises) or Skype (coming in early 2020).</span></span> 

<span data-ttu-id="43a37-p103">Teams 中預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。Teams 系統管理員可以將其關閉或指定要包含 (或排除) 的網域。若要深入了解，請閱讀[管理外部存取](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="43a37-p103">External access is turned on by default in Teams, which means your org can communicate with all external domains. The Teams admin can turn it off or specify which domains to include (or exclude). To learn more, read [Manage external access](manage-external-access.md).</span></span> 

<span data-ttu-id="43a37-117">如果您想讓外部使用者存取團隊和頻道，[來賓存取](#guest-access)可能是更好的作法。</span><span class="sxs-lookup"><span data-stu-id="43a37-117">If you want external users to have access to teams and channels, [guest access](#guest-access) might be a better way to go.</span></span> 


## <a name="guest-access"></a><span data-ttu-id="43a37-118">來賓存取</span><span class="sxs-lookup"><span data-stu-id="43a37-118">Guest access</span></span>

<span data-ttu-id="43a37-p104">使用 **來賓存取** 將個別使用者 (不論網域) 新增至團隊，讓他們可以使用 Microsoft 365 或 Office 365 應用程式 (例如 Word、Excel 或 PowerPoint) 來聊天、通話、開會及共同處理組織檔案 (儲存在 SharePoint 或商務用 OneDrive 中)。來賓使用者幾乎擁有與原生團隊成員相同的 Teams 功能。若要深入了解，請閱讀 [Teams 中的來賓存取](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="43a37-p104">Use **guest access** to add an individual user (regardless of domain) to a team, where they can chat, call, meet, and collaborate on organization files (stored in SharePoint or OneDrive for Business), using Microsoft 365 or Office 365 apps such as Word, Excel, or PowerPoint. A guest user can be given nearly all the same Teams capabilities as a native team member. To learn more, read [Guest access in Teams](guest-access.md).</span></span>

- <span data-ttu-id="43a37-122">來賓會新增至組織的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="43a37-122">Guests are added to your organization’s Active Directory.</span></span>
- <span data-ttu-id="43a37-p105">若要與來賓通訊，來賓必須使用其來賓帳戶登入 Teams。這表示來賓可能必須登出自己的 Teams 帳戶，才能登入您的 Teams 帳戶，或如果是相同帳戶，則切換組織。</span><span class="sxs-lookup"><span data-stu-id="43a37-p105">To communicate with a guest, the guest has to be signed in to Teams using their guest account. This means that a guest may have to sign out of their own Teams account to sign in to your Teams account, or switch organizations if it's the same account.</span></span>
- <span data-ttu-id="43a37-125">來賓使用者可以比外部存取 (同盟) 使用者存取 Teams 中的更多資源，例如檔案、團隊和頻道。</span><span class="sxs-lookup"><span data-stu-id="43a37-125">Guest users have access to more resources in Teams - such as files, teams, and channels - than external-access (federated) users.</span></span>
- <span data-ttu-id="43a37-p106">Teams 系統管理員會控制來賓可以 (或無法) 在 Teams 系統管理中心執行的所有動作。若要深入了解，請參閱[管理來賓存取](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="43a37-p106">The Teams admin controls everything that a guest can (or can’t) do in the Teams admin center. To learn more, read [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="43a37-128">如果您已在組織中開啟來賓存取，請從[在團隊中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)開始。</span><span class="sxs-lookup"><span data-stu-id="43a37-128">If you're ready to turn on guest access in your organization, start with the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>


## <a name="compare-external-and-guest-access"></a><span data-ttu-id="43a37-129">比較外部和來賓存取</span><span class="sxs-lookup"><span data-stu-id="43a37-129">Compare external and guest access</span></span>

| <span data-ttu-id="43a37-130">功能</span><span class="sxs-lookup"><span data-stu-id="43a37-130">Feature</span></span> | <span data-ttu-id="43a37-131">外部存取使用者</span><span class="sxs-lookup"><span data-stu-id="43a37-131">External access users</span></span> | <span data-ttu-id="43a37-132">來賓存取使用者</span><span class="sxs-lookup"><span data-stu-id="43a37-132">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="43a37-133">使用者可以與其他公司的人員聊天</span><span class="sxs-lookup"><span data-stu-id="43a37-133">User can chat with someone in another company</span></span> | <span data-ttu-id="43a37-134">是</span><span class="sxs-lookup"><span data-stu-id="43a37-134">Yes</span></span> |<span data-ttu-id="43a37-135">是</span><span class="sxs-lookup"><span data-stu-id="43a37-135">Yes</span></span> |
| <span data-ttu-id="43a37-136">使用者可以與其他公司的人員通話</span><span class="sxs-lookup"><span data-stu-id="43a37-136">User can call someone in another company</span></span> | <span data-ttu-id="43a37-137">是</span><span class="sxs-lookup"><span data-stu-id="43a37-137">Yes</span></span> | <span data-ttu-id="43a37-138">是</span><span class="sxs-lookup"><span data-stu-id="43a37-138">Yes</span></span> |
| <span data-ttu-id="43a37-139">使用者可以查看其他公司的人員是否可以通話或交談</span><span class="sxs-lookup"><span data-stu-id="43a37-139">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="43a37-140">是</span><span class="sxs-lookup"><span data-stu-id="43a37-140">Yes</span></span> | <span data-ttu-id="43a37-141">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-141">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="43a37-142">使用者可以在外部租用戶中搜尋使用者</span><span class="sxs-lookup"><span data-stu-id="43a37-142">User can search for users across external tenants</span></span> | <span data-ttu-id="43a37-143">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-143">Yes<sup>2</sup></span></span> | <span data-ttu-id="43a37-144">否</span><span class="sxs-lookup"><span data-stu-id="43a37-144">No</span></span> |
| <span data-ttu-id="43a37-145">使用者可以共用檔案</span><span class="sxs-lookup"><span data-stu-id="43a37-145">User can share files</span></span> | <span data-ttu-id="43a37-146">否</span><span class="sxs-lookup"><span data-stu-id="43a37-146">No</span></span> | <span data-ttu-id="43a37-147">是</span><span class="sxs-lookup"><span data-stu-id="43a37-147">Yes</span></span> |
| <span data-ttu-id="43a37-148">使用者可以存取 Teams 資源</span><span class="sxs-lookup"><span data-stu-id="43a37-148">User can access Teams resources</span></span> | <span data-ttu-id="43a37-149">否</span><span class="sxs-lookup"><span data-stu-id="43a37-149">No</span></span> | <span data-ttu-id="43a37-150">是</span><span class="sxs-lookup"><span data-stu-id="43a37-150">Yes</span></span> |
| <span data-ttu-id="43a37-151">可將使用者新增至群組聊天</span><span class="sxs-lookup"><span data-stu-id="43a37-151">User can be added to a group chat</span></span> | <span data-ttu-id="43a37-152">否</span><span class="sxs-lookup"><span data-stu-id="43a37-152">No</span></span> | <span data-ttu-id="43a37-153">是</span><span class="sxs-lookup"><span data-stu-id="43a37-153">Yes</span></span> |
| <span data-ttu-id="43a37-154">使用者可以受邀參加會議</span><span class="sxs-lookup"><span data-stu-id="43a37-154">User can be invited to a meeting</span></span> | <span data-ttu-id="43a37-155">是</span><span class="sxs-lookup"><span data-stu-id="43a37-155">Yes</span></span> | <span data-ttu-id="43a37-156">是</span><span class="sxs-lookup"><span data-stu-id="43a37-156">Yes</span></span> |
| <span data-ttu-id="43a37-157">可將其他使用者新增至與外部使用者的聊天</span><span class="sxs-lookup"><span data-stu-id="43a37-157">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="43a37-158">否<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-158">No<sup>3</sup></span></span> | <span data-ttu-id="43a37-159">不適用</span><span class="sxs-lookup"><span data-stu-id="43a37-159">N/A</span></span> |
| <span data-ttu-id="43a37-160">將使用者視為外部對象</span><span class="sxs-lookup"><span data-stu-id="43a37-160">User is identified as an external party</span></span> | <span data-ttu-id="43a37-161">是</span><span class="sxs-lookup"><span data-stu-id="43a37-161">Yes</span></span> | <span data-ttu-id="43a37-162">是</span><span class="sxs-lookup"><span data-stu-id="43a37-162">Yes</span></span> |
| <span data-ttu-id="43a37-163">會顯示目前狀態</span><span class="sxs-lookup"><span data-stu-id="43a37-163">Presence is displayed</span></span> | <span data-ttu-id="43a37-164">是</span><span class="sxs-lookup"><span data-stu-id="43a37-164">Yes</span></span> | <span data-ttu-id="43a37-165">是</span><span class="sxs-lookup"><span data-stu-id="43a37-165">Yes</span></span> |
| <span data-ttu-id="43a37-166">會顯示不在辦公室訊息</span><span class="sxs-lookup"><span data-stu-id="43a37-166">Out of office message is shown</span></span> | <span data-ttu-id="43a37-167">否</span><span class="sxs-lookup"><span data-stu-id="43a37-167">No</span></span> | <span data-ttu-id="43a37-168">是</span><span class="sxs-lookup"><span data-stu-id="43a37-168">Yes</span></span> |
| <span data-ttu-id="43a37-169">可以封鎖個別使用者</span><span class="sxs-lookup"><span data-stu-id="43a37-169">Individual user can be blocked</span></span> | <span data-ttu-id="43a37-170">否</span><span class="sxs-lookup"><span data-stu-id="43a37-170">No</span></span> | <span data-ttu-id="43a37-171">是</span><span class="sxs-lookup"><span data-stu-id="43a37-171">Yes</span></span> |
| <span data-ttu-id="43a37-172">支援以 @ 提及</span><span class="sxs-lookup"><span data-stu-id="43a37-172">@mentions are supported</span></span> | <span data-ttu-id="43a37-173">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-173">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-174">是</span><span class="sxs-lookup"><span data-stu-id="43a37-174">Yes</span></span> |
| <span data-ttu-id="43a37-175">可進行私人通話</span><span class="sxs-lookup"><span data-stu-id="43a37-175">Make private calls</span></span> | <span data-ttu-id="43a37-176">是</span><span class="sxs-lookup"><span data-stu-id="43a37-176">Yes</span></span> | <span data-ttu-id="43a37-177">是</span><span class="sxs-lookup"><span data-stu-id="43a37-177">Yes</span></span> |
| <span data-ttu-id="43a37-178">查看撥入會議參與者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="43a37-178">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="43a37-179">否<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-179">No<sup>5</sup></span></span> | <span data-ttu-id="43a37-180">是</span><span class="sxs-lookup"><span data-stu-id="43a37-180">Yes</span></span> |
| <span data-ttu-id="43a37-181">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="43a37-181">Allow IP video</span></span> | <span data-ttu-id="43a37-182">是</span><span class="sxs-lookup"><span data-stu-id="43a37-182">Yes</span></span> | <span data-ttu-id="43a37-183">是</span><span class="sxs-lookup"><span data-stu-id="43a37-183">Yes</span></span> |
| <span data-ttu-id="43a37-184">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="43a37-184">Screen sharing mode</span></span> | <span data-ttu-id="43a37-185">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-185">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-186">是</span><span class="sxs-lookup"><span data-stu-id="43a37-186">Yes</span></span> |
| <span data-ttu-id="43a37-187">允許立即開會</span><span class="sxs-lookup"><span data-stu-id="43a37-187">Allow meet now</span></span> | <span data-ttu-id="43a37-188">否</span><span class="sxs-lookup"><span data-stu-id="43a37-188">No</span></span> | <span data-ttu-id="43a37-189">是</span><span class="sxs-lookup"><span data-stu-id="43a37-189">Yes</span></span> |
| <span data-ttu-id="43a37-190">編輯已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="43a37-190">Edit sent messages</span></span> | <span data-ttu-id="43a37-191">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-191">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-192">是</span><span class="sxs-lookup"><span data-stu-id="43a37-192">Yes</span></span> |
| <span data-ttu-id="43a37-193">可以刪除已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="43a37-193">Can delete sent messages</span></span> | <span data-ttu-id="43a37-194">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-194">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-195">是</span><span class="sxs-lookup"><span data-stu-id="43a37-195">Yes</span></span> |
| <span data-ttu-id="43a37-196">在交談中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="43a37-196">Use Giphy in conversation</span></span> | <span data-ttu-id="43a37-197">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-197">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-198">是</span><span class="sxs-lookup"><span data-stu-id="43a37-198">Yes</span></span> |
| <span data-ttu-id="43a37-199">在交談中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="43a37-199">Use memes in conversation</span></span> | <span data-ttu-id="43a37-200">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-200">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-201">是</span><span class="sxs-lookup"><span data-stu-id="43a37-201">Yes</span></span> |
| <span data-ttu-id="43a37-202">在交談中使用貼圖</span><span class="sxs-lookup"><span data-stu-id="43a37-202">Use stickers in conversation</span></span> | <span data-ttu-id="43a37-203">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="43a37-203">Yes<sup>4</sup></span></span> | <span data-ttu-id="43a37-204">是</span><span class="sxs-lookup"><span data-stu-id="43a37-204">Yes</span></span> |
||||

<span data-ttu-id="43a37-205"><sup>1</sup>前提是已將使用者新增為來賓，且使用者以來賓身分登入來賓租用戶。</span><span class="sxs-lookup"><span data-stu-id="43a37-205"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="43a37-206"><sup>2</sup>僅透過電子郵件或工作階段初始通訊協定 (SIP) 位址。</span><span class="sxs-lookup"><span data-stu-id="43a37-206"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="43a37-207"><sup>3</sup>外部 (同盟) 聊天僅限一對一聊天。</span><span class="sxs-lookup"><span data-stu-id="43a37-207"><sup>3</sup> External (federated) chat is 1:1 only.</span></span><br>
<span data-ttu-id="43a37-208"><sup>4</sup> 支援來自兩個不同組織的僅 Teams 到僅 Teams 使用者的一對一聊天。</span><span class="sxs-lookup"><span data-stu-id="43a37-208"><sup>4</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="43a37-p107"><sup>5</sup> 依預設，外部參與者無法查看撥入的參與者電話號碼。如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型 **]** 的 [音調 **]** (這可避免 Teams 將號碼朗讀出來)。若要深入了解，請參閱 [開啟或關閉 Microsoft Teams 中會議的進入和退出宣告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="43a37-p107"><sup>5</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="43a37-212">相關主題</span><span class="sxs-lookup"><span data-stu-id="43a37-212">Related topics</span></span>

[<span data-ttu-id="43a37-213">Teams 中的外部存取</span><span class="sxs-lookup"><span data-stu-id="43a37-213">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="43a37-214">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="43a37-214">Guest access in Teams</span></span>](guest-access.md)

