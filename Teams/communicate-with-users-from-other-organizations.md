---
title: 與其他組織的使用者通話與聊天
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: 了解如何使用外部存取 (同盟) 和來賓存取在 Microsoft Teams 中通話、聊天、尋找和新增來自組織外部的使用者。
ms.openlocfilehash: 5c5eecf5ceb2228f981a7cd06b52f3b5a1b787d7
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145832"
---
# <a name="call-chat-and-collaborate-with-people-outside-your-organization-in-microsoft-teams"></a><span data-ttu-id="8cda7-103">在 Microsoft Teams 中與來自組織外部的人員通話、聊天和共同作業</span><span class="sxs-lookup"><span data-stu-id="8cda7-103">Call, chat, and collaborate with people outside your organization in Microsoft Teams</span></span>

<span data-ttu-id="8cda7-104">當您需要與組織外部的人員通訊和共同作業時，Microsoft Teams 提供您兩個選項：</span><span class="sxs-lookup"><span data-stu-id="8cda7-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="8cda7-105">**外部存取** - 一種同盟類型，可讓使用者尋找、通話及與其他組織中的人員聊天。</span><span class="sxs-lookup"><span data-stu-id="8cda7-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="8cda7-106">除非他們受邀成為來賓，否則無法將這些人新增至小組。</span><span class="sxs-lookup"><span data-stu-id="8cda7-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="8cda7-107">**來賓存取** - 來賓存取可讓您邀請組織外部的人員加入小組。</span><span class="sxs-lookup"><span data-stu-id="8cda7-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="8cda7-108">受邀的人員會在 Azure Active Directory 中取得一個來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="8cda7-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="8cda7-109">請注意，Teams 允許您邀請組織外部的人員參加會議。</span><span class="sxs-lookup"><span data-stu-id="8cda7-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="8cda7-110">這不需要設定外部或來賓存取。</span><span class="sxs-lookup"><span data-stu-id="8cda7-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="8cda7-111">外部存取 (同盟)</span><span class="sxs-lookup"><span data-stu-id="8cda7-111">External access (federation)</span></span>

<span data-ttu-id="8cda7-112">如果您需要尋找、通話、聊天以及設定與使用 Teams、商務用 Skype (線上或內部部署) 或 Skype 的組織外部人員的會議，請設定外部存取。</span><span class="sxs-lookup"><span data-stu-id="8cda7-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="8cda7-113">預設會對所有網域啟用外部存取。</span><span class="sxs-lookup"><span data-stu-id="8cda7-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="8cda7-114">您可以透過允許或封鎖特定網域來限制外部存取，或將它關閉。</span><span class="sxs-lookup"><span data-stu-id="8cda7-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![外部存取設定的螢幕擷取畫面](media/external-access-federation-settings.png)

<span data-ttu-id="8cda7-116">若要設定外部存取，請參閱[管理外部存取](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8cda7-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

## <a name="guest-access"></a><span data-ttu-id="8cda7-117">來賓存取</span><span class="sxs-lookup"><span data-stu-id="8cda7-117">Guest access</span></span>

<span data-ttu-id="8cda7-118">使用來賓存取將來自組織外部的人員新增至小組，他們可在其中聊天、通話、開會及就檔案共同作業。</span><span class="sxs-lookup"><span data-stu-id="8cda7-118">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="8cda7-119">來賓幾乎擁有與原生小組成員相同的所有 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="8cda7-119">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="8cda7-120">來賓會以 B2B 使用者的身分新增至組織的 Azure Active Directory 中，且必須使用其來賓帳戶登入 Teams。</span><span class="sxs-lookup"><span data-stu-id="8cda7-120">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="8cda7-121">這表示他們可能必須登出自己的組織，才能登入您的組織。</span><span class="sxs-lookup"><span data-stu-id="8cda7-121">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="8cda7-122">若要為 Teams 設定來賓存取，請參閱[在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="8cda7-122">To configure guest access for Teams, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="8cda7-123">比較外部和來賓存取</span><span class="sxs-lookup"><span data-stu-id="8cda7-123">Compare external and guest access</span></span>

<span data-ttu-id="8cda7-124">下表顯示使用外部存取 (同盟) 和來賓之間的差異。</span><span class="sxs-lookup"><span data-stu-id="8cda7-124">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="8cda7-125">在這兩個情況下，系統會將組織外部的人員向您的使用者識別為外部。</span><span class="sxs-lookup"><span data-stu-id="8cda7-125">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="8cda7-126">您的使用者可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="8cda7-126">Things your users can do</span></span>

| <span data-ttu-id="8cda7-127">使用者可以</span><span class="sxs-lookup"><span data-stu-id="8cda7-127">Users can</span></span> | <span data-ttu-id="8cda7-128">外部存取使用者</span><span class="sxs-lookup"><span data-stu-id="8cda7-128">External access users</span></span> | <span data-ttu-id="8cda7-129">來賓</span><span class="sxs-lookup"><span data-stu-id="8cda7-129">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="8cda7-130">與其他組織中的人員聊天</span><span class="sxs-lookup"><span data-stu-id="8cda7-130">Chat with someone in another organization</span></span> | <span data-ttu-id="8cda7-131">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-131">Yes</span></span> | <span data-ttu-id="8cda7-132">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-132">Yes</span></span> |
| <span data-ttu-id="8cda7-133">與另一個組織中的人員通話</span><span class="sxs-lookup"><span data-stu-id="8cda7-133">Call someone in another organization</span></span> | <span data-ttu-id="8cda7-134">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-134">Yes</span></span> | <span data-ttu-id="8cda7-135">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-135">Yes</span></span> |
| <span data-ttu-id="8cda7-136">查看來自另一個組織的人員是否可以通話或聊天</span><span class="sxs-lookup"><span data-stu-id="8cda7-136">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="8cda7-137">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-137">Yes</span></span> | <span data-ttu-id="8cda7-138">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-138">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="8cda7-139">搜尋其他組織中的人員</span><span class="sxs-lookup"><span data-stu-id="8cda7-139">Search for people in other organizations</span></span> | <span data-ttu-id="8cda7-140">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-140">Yes<sup>2</sup></span></span> | <span data-ttu-id="8cda7-141">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-141">No</span></span> |
| <span data-ttu-id="8cda7-142">共用檔案</span><span class="sxs-lookup"><span data-stu-id="8cda7-142">Share files</span></span> | <span data-ttu-id="8cda7-143">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-143">No</span></span> | <span data-ttu-id="8cda7-144">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-144">Yes</span></span> |
| <span data-ttu-id="8cda7-145">查看其不在辦公室訊息</span><span class="sxs-lookup"><span data-stu-id="8cda7-145">See the out-of-office message of</span></span> | <span data-ttu-id="8cda7-146">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-146">No</span></span> | <span data-ttu-id="8cda7-147">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-147">Yes</span></span> |
| <span data-ttu-id="8cda7-148">封鎖另一個組織中的人員</span><span class="sxs-lookup"><span data-stu-id="8cda7-148">Block someone in another organization someone in another organization</span></span> | <span data-ttu-id="8cda7-149">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-149">No</span></span> | <span data-ttu-id="8cda7-150">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-150">Yes</span></span> |
| <span data-ttu-id="8cda7-151">使用 @ 提及</span><span class="sxs-lookup"><span data-stu-id="8cda7-151">Use @mentions</span></span> | <span data-ttu-id="8cda7-152">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-152">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-153">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-153">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="8cda7-154">組織外部的人員可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="8cda7-154">Things people outside your organization can do</span></span>

| <span data-ttu-id="8cda7-155">組織外部的人員可以</span><span class="sxs-lookup"><span data-stu-id="8cda7-155">People outside your organization can</span></span> | <span data-ttu-id="8cda7-156">外部存取使用者</span><span class="sxs-lookup"><span data-stu-id="8cda7-156">External access users</span></span> | <span data-ttu-id="8cda7-157">來賓</span><span class="sxs-lookup"><span data-stu-id="8cda7-157">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="8cda7-158">存取 Teams 資源</span><span class="sxs-lookup"><span data-stu-id="8cda7-158">Access Teams resources</span></span> | <span data-ttu-id="8cda7-159">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-159">No</span></span> | <span data-ttu-id="8cda7-160">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-160">Yes</span></span> |
| <span data-ttu-id="8cda7-161">被新增至群組聊天</span><span class="sxs-lookup"><span data-stu-id="8cda7-161">Be added to a group chat</span></span> | <span data-ttu-id="8cda7-162">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-162">No</span></span> | <span data-ttu-id="8cda7-163">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-163">Yes</span></span> |
| <span data-ttu-id="8cda7-164">受邀參加會議</span><span class="sxs-lookup"><span data-stu-id="8cda7-164">Be invited to a meeting</span></span> | <span data-ttu-id="8cda7-165">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-165">Yes</span></span> | <span data-ttu-id="8cda7-166">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-166">Yes</span></span> |
| <span data-ttu-id="8cda7-167">可進行私人通話</span><span class="sxs-lookup"><span data-stu-id="8cda7-167">Make private calls</span></span> | <span data-ttu-id="8cda7-168">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-168">Yes</span></span> | <span data-ttu-id="8cda7-169">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-169">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-170">檢視撥入會議參與者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="8cda7-170">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="8cda7-171">否<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-171">No<sup>4</sup></span></span> | <span data-ttu-id="8cda7-172">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-172">Yes</span></span> |
| <span data-ttu-id="8cda7-173">使用 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="8cda7-173">Use IP video</span></span> | <span data-ttu-id="8cda7-174">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-174">Yes</span></span> | <span data-ttu-id="8cda7-175">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-175">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-176">使用螢幕畫面分享</span><span class="sxs-lookup"><span data-stu-id="8cda7-176">Use screen sharing</span></span> | <span data-ttu-id="8cda7-177">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-177">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-178">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-178">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-179">使用立即開會</span><span class="sxs-lookup"><span data-stu-id="8cda7-179">Use meet now</span></span> | <span data-ttu-id="8cda7-180">否</span><span class="sxs-lookup"><span data-stu-id="8cda7-180">No</span></span> | <span data-ttu-id="8cda7-181">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-181">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-182">編輯已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="8cda7-182">Edit sent messages</span></span> | <span data-ttu-id="8cda7-183">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-183">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-184">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-185">刪除已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="8cda7-185">Delete sent messages</span></span> | <span data-ttu-id="8cda7-186">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-186">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-187">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-188">在交談中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="8cda7-188">Use Giphy in conversation</span></span> | <span data-ttu-id="8cda7-189">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-189">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-190">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-191">在交談中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="8cda7-191">Use memes in conversation</span></span> | <span data-ttu-id="8cda7-192">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-192">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-193">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-193">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-194">在交談中使用貼圖</span><span class="sxs-lookup"><span data-stu-id="8cda7-194">Use stickers in conversation</span></span> | <span data-ttu-id="8cda7-195">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-195">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-196">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-196">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="8cda7-197">會顯示目前狀態</span><span class="sxs-lookup"><span data-stu-id="8cda7-197">Presence is displayed</span></span> | <span data-ttu-id="8cda7-198">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-198">Yes</span></span> | <span data-ttu-id="8cda7-199">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-199">Yes</span></span> |
| <span data-ttu-id="8cda7-200">使用 @ 提及</span><span class="sxs-lookup"><span data-stu-id="8cda7-200">Use @mentions</span></span> | <span data-ttu-id="8cda7-201">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8cda7-201">Yes<sup>3</sup></span></span> | <span data-ttu-id="8cda7-202">是</span><span class="sxs-lookup"><span data-stu-id="8cda7-202">Yes</span></span> |

<br>

<span data-ttu-id="8cda7-203"><sup>1</sup> 前提是已將使用者新增為來賓，並使用來賓帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="8cda7-203"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="8cda7-204"><sup>2</sup> 僅透過電子郵件或工作階段初始通訊協定 (SIP) 位址。</span><span class="sxs-lookup"><span data-stu-id="8cda7-204"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="8cda7-205"><sup>3</sup> 支援來自兩個不同組織的僅 Teams 到僅 Teams 使用者的一對一聊天。</span><span class="sxs-lookup"><span data-stu-id="8cda7-205"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="8cda7-206"><sup>4</sup> 依預設，外部參與者無法查看撥入參與者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8cda7-206"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="8cda7-207">如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。</span><span class="sxs-lookup"><span data-stu-id="8cda7-207">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="8cda7-208">若要深入了解，請參閱[開啟或關閉 Microsoft Teams 中會議的進入和退出宣告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8cda7-208">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="8cda7-209"><sup>5</sup> 預設會允許，但可以由 Teams 系統管理員關閉</span><span class="sxs-lookup"><span data-stu-id="8cda7-209"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="8cda7-210">相關主題</span><span class="sxs-lookup"><span data-stu-id="8cda7-210">Related topics</span></span>

[<span data-ttu-id="8cda7-211">Teams 中的外部存取</span><span class="sxs-lookup"><span data-stu-id="8cda7-211">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="8cda7-212">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="8cda7-212">Guest access in Teams</span></span>](guest-access.md)

