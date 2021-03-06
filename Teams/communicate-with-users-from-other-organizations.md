---
title: 使用來賓存取和外部存取與組織外的人員共同作業
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
ms.openlocfilehash: 10ce0e7f89872a7fda842871d17f8bd06481193f
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461043"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a><span data-ttu-id="01039-103">使用來賓存取和外部存取與組織外的人員共同作業</span><span class="sxs-lookup"><span data-stu-id="01039-103">Use guest access and external access to collaborate with people outside your organization</span></span>

<span data-ttu-id="01039-104">當您需要與組織外部的人員通訊和共同作業時，Microsoft Teams 提供您兩個選項：</span><span class="sxs-lookup"><span data-stu-id="01039-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="01039-105">**外部存取** - 一種同盟類型，可讓使用者尋找、通話及與其他組織中的人員聊天。</span><span class="sxs-lookup"><span data-stu-id="01039-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="01039-106">除非他們受邀成為來賓，否則無法將這些人新增至小組。</span><span class="sxs-lookup"><span data-stu-id="01039-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="01039-107">**來賓存取** - 來賓存取可讓您邀請組織外部的人員加入小組。</span><span class="sxs-lookup"><span data-stu-id="01039-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="01039-108">受邀的人員會在 Azure Active Directory 中取得一個來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="01039-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="01039-109">請注意，Teams 允許您邀請組織外部的人員參加會議。</span><span class="sxs-lookup"><span data-stu-id="01039-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="01039-110">這不需要設定外部或來賓存取。</span><span class="sxs-lookup"><span data-stu-id="01039-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="01039-111">外部存取 (同盟)</span><span class="sxs-lookup"><span data-stu-id="01039-111">External access (federation)</span></span>

<span data-ttu-id="01039-112">如果您需要尋找、通話、聊天以及設定與使用 Teams、商務用 Skype (線上或內部部署) 或 Skype 的組織外部人員的會議，請設定外部存取。</span><span class="sxs-lookup"><span data-stu-id="01039-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="01039-113">預設會對所有網域啟用外部存取。</span><span class="sxs-lookup"><span data-stu-id="01039-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="01039-114">您可以透過允許或封鎖特定網域來限制外部存取，或將它關閉。</span><span class="sxs-lookup"><span data-stu-id="01039-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![外部存取設定的螢幕擷取畫面](media/external-access-federation-settings.png)

<span data-ttu-id="01039-116">若要設定外部存取，請參閱[管理外部存取](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="01039-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

>[!NOTE]
><span data-ttu-id="01039-117">Microsoft Teams 免費授權不支援外部存取。</span><span class="sxs-lookup"><span data-stu-id="01039-117">Microsoft Teams free licenses do not support external access.</span></span>

## <a name="guest-access"></a><span data-ttu-id="01039-118">來賓存取</span><span class="sxs-lookup"><span data-stu-id="01039-118">Guest access</span></span>

<span data-ttu-id="01039-119">使用來賓存取將來自組織外部的人員新增至小組，他們可在其中聊天、通話、開會及就檔案共同作業。</span><span class="sxs-lookup"><span data-stu-id="01039-119">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="01039-120">來賓幾乎擁有與原生小組成員相同的所有 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="01039-120">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="01039-121">來賓會以 B2B 使用者的身分新增至組織的 Azure Active Directory 中，且必須使用其來賓帳戶登入 Teams。</span><span class="sxs-lookup"><span data-stu-id="01039-121">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="01039-122">這表示他們可能必須登出自己的組織，才能登入您的組織。</span><span class="sxs-lookup"><span data-stu-id="01039-122">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="01039-123">若要為 Teams 設定來賓存取，請參閱[在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="01039-123">To configure guest access for Teams, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="01039-124">比較外部和來賓存取</span><span class="sxs-lookup"><span data-stu-id="01039-124">Compare external and guest access</span></span>

<span data-ttu-id="01039-125">下表顯示使用外部存取 (同盟) 和來賓之間的差異。</span><span class="sxs-lookup"><span data-stu-id="01039-125">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="01039-126">在這兩個情況下，系統會將組織外部的人員向您的使用者識別為外部。</span><span class="sxs-lookup"><span data-stu-id="01039-126">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="01039-127">您的使用者可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="01039-127">Things your users can do</span></span>

| <span data-ttu-id="01039-128">使用者可以</span><span class="sxs-lookup"><span data-stu-id="01039-128">Users can</span></span> | <span data-ttu-id="01039-129">外部存取使用者</span><span class="sxs-lookup"><span data-stu-id="01039-129">External access users</span></span> | <span data-ttu-id="01039-130">來賓</span><span class="sxs-lookup"><span data-stu-id="01039-130">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="01039-131">與其他組織中的人員聊天</span><span class="sxs-lookup"><span data-stu-id="01039-131">Chat with someone in another organization</span></span> | <span data-ttu-id="01039-132">是</span><span class="sxs-lookup"><span data-stu-id="01039-132">Yes</span></span> | <span data-ttu-id="01039-133">是</span><span class="sxs-lookup"><span data-stu-id="01039-133">Yes</span></span> |
| <span data-ttu-id="01039-134">與另一個組織中的人員通話</span><span class="sxs-lookup"><span data-stu-id="01039-134">Call someone in another organization</span></span> | <span data-ttu-id="01039-135">是</span><span class="sxs-lookup"><span data-stu-id="01039-135">Yes</span></span> | <span data-ttu-id="01039-136">是</span><span class="sxs-lookup"><span data-stu-id="01039-136">Yes</span></span> |
| <span data-ttu-id="01039-137">查看來自另一個組織的人員是否可以通話或聊天</span><span class="sxs-lookup"><span data-stu-id="01039-137">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="01039-138">是</span><span class="sxs-lookup"><span data-stu-id="01039-138">Yes</span></span> | <span data-ttu-id="01039-139">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="01039-139">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="01039-140">搜尋其他組織中的人員</span><span class="sxs-lookup"><span data-stu-id="01039-140">Search for people in other organizations</span></span> | <span data-ttu-id="01039-141">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="01039-141">Yes<sup>2</sup></span></span> | <span data-ttu-id="01039-142">否</span><span class="sxs-lookup"><span data-stu-id="01039-142">No</span></span> |
| <span data-ttu-id="01039-143">共用檔案</span><span class="sxs-lookup"><span data-stu-id="01039-143">Share files</span></span> | <span data-ttu-id="01039-144">否</span><span class="sxs-lookup"><span data-stu-id="01039-144">No</span></span> | <span data-ttu-id="01039-145">是</span><span class="sxs-lookup"><span data-stu-id="01039-145">Yes</span></span> |
| <span data-ttu-id="01039-146">查看另一個組織中某人的外出訊息</span><span class="sxs-lookup"><span data-stu-id="01039-146">See the out-of-office message of someone in another organization</span></span> | <span data-ttu-id="01039-147">否</span><span class="sxs-lookup"><span data-stu-id="01039-147">No</span></span> | <span data-ttu-id="01039-148">是</span><span class="sxs-lookup"><span data-stu-id="01039-148">Yes</span></span> |
| <span data-ttu-id="01039-149">封鎖另一個組織的某人</span><span class="sxs-lookup"><span data-stu-id="01039-149">Block someone in another organization</span></span>  | <span data-ttu-id="01039-150">否</span><span class="sxs-lookup"><span data-stu-id="01039-150">No</span></span> | <span data-ttu-id="01039-151">是</span><span class="sxs-lookup"><span data-stu-id="01039-151">Yes</span></span> |
| <span data-ttu-id="01039-152">使用 @ 提及</span><span class="sxs-lookup"><span data-stu-id="01039-152">Use @mentions</span></span> | <span data-ttu-id="01039-153">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-153">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-154">是</span><span class="sxs-lookup"><span data-stu-id="01039-154">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="01039-155">組織外部的人員可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="01039-155">Things people outside your organization can do</span></span>

| <span data-ttu-id="01039-156">組織外部的人員可以</span><span class="sxs-lookup"><span data-stu-id="01039-156">People outside your organization can</span></span> | <span data-ttu-id="01039-157">外部存取使用者</span><span class="sxs-lookup"><span data-stu-id="01039-157">External access users</span></span> | <span data-ttu-id="01039-158">來賓</span><span class="sxs-lookup"><span data-stu-id="01039-158">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="01039-159">存取 Teams 資源</span><span class="sxs-lookup"><span data-stu-id="01039-159">Access Teams resources</span></span> | <span data-ttu-id="01039-160">否</span><span class="sxs-lookup"><span data-stu-id="01039-160">No</span></span> | <span data-ttu-id="01039-161">是</span><span class="sxs-lookup"><span data-stu-id="01039-161">Yes</span></span> |
| <span data-ttu-id="01039-162">被新增至群組聊天</span><span class="sxs-lookup"><span data-stu-id="01039-162">Be added to a group chat</span></span> | <span data-ttu-id="01039-163">否</span><span class="sxs-lookup"><span data-stu-id="01039-163">No</span></span> | <span data-ttu-id="01039-164">是</span><span class="sxs-lookup"><span data-stu-id="01039-164">Yes</span></span> |
| <span data-ttu-id="01039-165">受邀參加會議</span><span class="sxs-lookup"><span data-stu-id="01039-165">Be invited to a meeting</span></span> | <span data-ttu-id="01039-166">是</span><span class="sxs-lookup"><span data-stu-id="01039-166">Yes</span></span> | <span data-ttu-id="01039-167">是</span><span class="sxs-lookup"><span data-stu-id="01039-167">Yes</span></span> |
| <span data-ttu-id="01039-168">可進行私人通話</span><span class="sxs-lookup"><span data-stu-id="01039-168">Make private calls</span></span> | <span data-ttu-id="01039-169">是</span><span class="sxs-lookup"><span data-stu-id="01039-169">Yes</span></span> | <span data-ttu-id="01039-170">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-170">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-171">檢視撥入會議參與者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="01039-171">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="01039-172">否<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="01039-172">No<sup>4</sup></span></span> | <span data-ttu-id="01039-173">是</span><span class="sxs-lookup"><span data-stu-id="01039-173">Yes</span></span> |
| <span data-ttu-id="01039-174">使用 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="01039-174">Use IP video</span></span> | <span data-ttu-id="01039-175">是</span><span class="sxs-lookup"><span data-stu-id="01039-175">Yes</span></span> | <span data-ttu-id="01039-176">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-176">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-177">使用螢幕畫面分享</span><span class="sxs-lookup"><span data-stu-id="01039-177">Use screen sharing</span></span> | <span data-ttu-id="01039-178">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-178">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-179">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-179">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-180">使用立即開會</span><span class="sxs-lookup"><span data-stu-id="01039-180">Use meet now</span></span> | <span data-ttu-id="01039-181">否</span><span class="sxs-lookup"><span data-stu-id="01039-181">No</span></span> | <span data-ttu-id="01039-182">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-182">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-183">編輯已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="01039-183">Edit sent messages</span></span> | <span data-ttu-id="01039-184">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-184">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-185">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-186">刪除已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="01039-186">Delete sent messages</span></span> | <span data-ttu-id="01039-187">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-187">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-188">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-188">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-189">在交談中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="01039-189">Use Giphy in conversation</span></span> | <span data-ttu-id="01039-190">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-190">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-191">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-191">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-192">在交談中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="01039-192">Use memes in conversation</span></span> | <span data-ttu-id="01039-193">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-193">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-194">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-194">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-195">在交談中使用貼圖</span><span class="sxs-lookup"><span data-stu-id="01039-195">Use stickers in conversation</span></span> | <span data-ttu-id="01039-196">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-196">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-197">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="01039-197">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="01039-198">會顯示目前狀態</span><span class="sxs-lookup"><span data-stu-id="01039-198">Presence is displayed</span></span> | <span data-ttu-id="01039-199">是</span><span class="sxs-lookup"><span data-stu-id="01039-199">Yes</span></span> | <span data-ttu-id="01039-200">是</span><span class="sxs-lookup"><span data-stu-id="01039-200">Yes</span></span> |
| <span data-ttu-id="01039-201">使用 @ 提及</span><span class="sxs-lookup"><span data-stu-id="01039-201">Use @mentions</span></span> | <span data-ttu-id="01039-202">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="01039-202">Yes<sup>3</sup></span></span> | <span data-ttu-id="01039-203">是</span><span class="sxs-lookup"><span data-stu-id="01039-203">Yes</span></span> |

<br>

<span data-ttu-id="01039-204"><sup>1</sup> 前提是已將使用者新增為來賓，並使用來賓帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="01039-204"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="01039-205"><sup>2</sup> 僅透過電子郵件或工作階段初始通訊協定 (SIP) 位址。</span><span class="sxs-lookup"><span data-stu-id="01039-205"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="01039-206"><sup>3</sup> 支援來自兩個不同組織的僅 Teams 到僅 Teams 使用者的一對一聊天。</span><span class="sxs-lookup"><span data-stu-id="01039-206"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="01039-207"><sup>4</sup> 依預設，外部參與者無法查看撥入參與者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="01039-207"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="01039-208">如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。</span><span class="sxs-lookup"><span data-stu-id="01039-208">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="01039-209">若要深入了解，請參閱[開啟或關閉 Microsoft Teams 中會議的進入和退出宣告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="01039-209">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="01039-210"><sup>5</sup> 預設會允許，但可以由 Teams 系統管理員關閉</span><span class="sxs-lookup"><span data-stu-id="01039-210"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="01039-211">相關主題</span><span class="sxs-lookup"><span data-stu-id="01039-211">Related topics</span></span>

[<span data-ttu-id="01039-212">Teams 中的外部存取</span><span class="sxs-lookup"><span data-stu-id="01039-212">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="01039-213">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="01039-213">Guest access in Teams</span></span>](guest-access.md)

