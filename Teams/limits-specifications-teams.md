---
title: Microsoft Teams 的限制和規格
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 本文說明套用到 Microsoft Teams 的限制、規格和其他需求。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7b66ce5095d194f937f3bceeef23d2666c51d518
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611467"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="1675b-103">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="1675b-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="1675b-104">本文說明一些套用到 Teams 的限制、規格和其他需求。</span><span class="sxs-lookup"><span data-stu-id="1675b-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="1675b-105">小組和頻道</span><span class="sxs-lookup"><span data-stu-id="1675b-105">Teams and channels</span></span>

|<span data-ttu-id="1675b-106">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-106">Feature</span></span>    | <span data-ttu-id="1675b-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="1675b-108">一位使用者可以建立的小組數目</span><span class="sxs-lookup"><span data-stu-id="1675b-108">Number of teams a user can create</span></span> | <span data-ttu-id="1675b-109">受限於 250 的物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="1675b-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="1675b-110">一位使用者可以加入成為成員的團隊數目</span><span class="sxs-lookup"><span data-stu-id="1675b-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="1675b-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="1675b-111">1,000&sup2;</span></span>|
|<span data-ttu-id="1675b-112">一個小組中的成員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-112">Number of members in a team</span></span> | <span data-ttu-id="1675b-113">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-113">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="1675b-114">每個小組擁有者人數</span><span class="sxs-lookup"><span data-stu-id="1675b-114">Number of owners per team</span></span> | <span data-ttu-id="1675b-115">100</span><span class="sxs-lookup"><span data-stu-id="1675b-115">100</span></span>   |
|<span data-ttu-id="1675b-116">一個租用戶中允許的全組織小組數目</span><span class="sxs-lookup"><span data-stu-id="1675b-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="1675b-117">5</span><span class="sxs-lookup"><span data-stu-id="1675b-117">5</span></span>     |
|<span data-ttu-id="1675b-118">一個[全組織小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="1675b-119">5,000</span><span class="sxs-lookup"><span data-stu-id="1675b-119">5,000</span></span>       |
|<span data-ttu-id="1675b-120">一位全域系統管理員可以建立的小組數目</span><span class="sxs-lookup"><span data-stu-id="1675b-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="1675b-121">500,000</span><span class="sxs-lookup"><span data-stu-id="1675b-121">500,000</span></span>   |
|<span data-ttu-id="1675b-122">一個 Microsoft 365 或 Office 365 組織可以擁有的小組數目</span><span class="sxs-lookup"><span data-stu-id="1675b-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="1675b-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="1675b-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="1675b-124">每個小組的頻道數目</span><span class="sxs-lookup"><span data-stu-id="1675b-124">Number of channels per team</span></span>    | <span data-ttu-id="1675b-125">200 (包含已刪除的頻道)&sup3;</span><span class="sxs-lookup"><span data-stu-id="1675b-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="1675b-126">每個小組的私人頻道數量</span><span class="sxs-lookup"><span data-stu-id="1675b-126">Number of Private channels per team</span></span>    |<span data-ttu-id="1675b-127">30</span><span class="sxs-lookup"><span data-stu-id="1675b-127">30</span></span>| <span data-ttu-id="1675b-128">(包含已刪除的頻道)&sup3;</span><span class="sxs-lookup"><span data-stu-id="1675b-128">(includes deleted channels)&sup3;</span></span>
|<span data-ttu-id="1675b-129">私人頻道中的成員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="1675b-130">250</span><span class="sxs-lookup"><span data-stu-id="1675b-130">250</span></span>|
|<span data-ttu-id="1675b-131">可匯入小組中的通訊群組清單、安全性群組或 Office 365 群組的大小上限</span><span class="sxs-lookup"><span data-stu-id="1675b-131">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="1675b-132">3,500</span><span class="sxs-lookup"><span data-stu-id="1675b-132">3,500</span></span>|
|<span data-ttu-id="1675b-133">Office 365 群組中可轉換成小組的成員數目上限</span><span class="sxs-lookup"><span data-stu-id="1675b-133">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="1675b-134">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-134">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="1675b-135">頻道交談貼文大小</span><span class="sxs-lookup"><span data-stu-id="1675b-135">Channel conversation post size</span></span> | <span data-ttu-id="1675b-136">每篇貼文約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-136">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="1675b-p101"><sup>1</sup> Azure Active Directory 中的任何目錄物件都會計入此限制。全域系統管理員會從此限制豁免，使用[應用程式權限](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式亦然。</span><span class="sxs-lookup"><span data-stu-id="1675b-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="1675b-139"><sup>2</sup> 此限制包含已封存的小組。</span><span class="sxs-lookup"><span data-stu-id="1675b-139"><sup>2</sup> This limit includes archived teams.</span></span> <span data-ttu-id="1675b-140">若要超出 Microsoft 365 或 Office 365 組織可以擁有的最大小組數，必須與Microsoft 支援部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="1675b-140">To go beyond the maximum number of teams a Microsoft 365 or Office 365 organization can have, you must contact Microsoft support.</span></span>

<span data-ttu-id="1675b-p103"><sup>3</sup> 已刪除的頻道可以在 30 天內還原。在這 30 天內，已刪除的頻道會持續計入每個小組 200 個頻道或 30 個私人頻道的限制。30 天後，已刪除的頻道及其內容會永久刪除，且該頻道不再會計入每個小組頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="1675b-p103"><sup>3</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="1675b-144"><sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。</span><span class="sxs-lookup"><span data-stu-id="1675b-144"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="1675b-145"><sup>5</sup> GCC 中的 Teams 只能容納 5,000 個成員，而 GCCH/DoD 中只能容納 2,500 個成員。</span><span class="sxs-lookup"><span data-stu-id="1675b-145"><sup>5</sup> Teams in GCC can only accommodate 5,000 members and teams in GCCH/DoD can only accommodate 2,500 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="1675b-146">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="1675b-146">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="1675b-147">聊天</span><span class="sxs-lookup"><span data-stu-id="1675b-147">Chat</span></span>

<span data-ttu-id="1675b-p104">參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留。(如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="1675b-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="1675b-154">Teams 的聊天是在 Microsoft Exchange 後端執行，因此 Exchange 的訊息限制會套用到 Teams 內的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="1675b-154">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="1675b-155">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-155">Feature</span></span>  | <span data-ttu-id="1675b-156">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-156">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="1675b-157">一個私人聊天中的人員數目<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-157">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="1675b-158">250</span><span class="sxs-lookup"><span data-stu-id="1675b-158">250</span></span> |
|<span data-ttu-id="1675b-159">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-159">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="1675b-160">20</span><span class="sxs-lookup"><span data-stu-id="1675b-160">20</span></span> |
|<span data-ttu-id="1675b-161">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-161">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="1675b-162">10</span><span class="sxs-lookup"><span data-stu-id="1675b-162">10</span></span>     |
|<span data-ttu-id="1675b-163">聊天大小</span><span class="sxs-lookup"><span data-stu-id="1675b-163">Chat size</span></span> | <span data-ttu-id="1675b-164">每篇貼文約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-164">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="1675b-p105"><sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息；輸入指示器；視訊和音訊通話；共用；讀取回條。當私人群組聊天包含超過 20 個成員時，也會移除 [設定傳遞選項] 按鈕 (!)。</span><span class="sxs-lookup"><span data-stu-id="1675b-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="1675b-167"><sup>2</sup> 如果附件數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="1675b-167"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="1675b-168"><sup>3</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及和回應。</span><span class="sxs-lookup"><span data-stu-id="1675b-168"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="1675b-169">傳送電子郵件到頻道</span><span class="sxs-lookup"><span data-stu-id="1675b-169">Emailing a channel</span></span>

 <span data-ttu-id="1675b-p106">如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。以下是一些傳送電子郵件到頻道時適用的限制。</span><span class="sxs-lookup"><span data-stu-id="1675b-p106">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="1675b-173">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-173">Feature</span></span>  | <span data-ttu-id="1675b-174">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-174">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="1675b-175">郵件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="1675b-175">Message size<sup>1<sup></span></span> | <span data-ttu-id="1675b-176">24 KB</span><span class="sxs-lookup"><span data-stu-id="1675b-176">24 KB</span></span> |
|<span data-ttu-id="1675b-177">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-177">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="1675b-178">20</span><span class="sxs-lookup"><span data-stu-id="1675b-178">20</span></span>     |
|<span data-ttu-id="1675b-179">每個檔案附件的大小</span><span class="sxs-lookup"><span data-stu-id="1675b-179">Size of each file attachment</span></span> | <span data-ttu-id="1675b-180">小於 10 MB</span><span class="sxs-lookup"><span data-stu-id="1675b-180">Less than 10 MB</span></span> |
|<span data-ttu-id="1675b-181">內嵌影像的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-181">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="1675b-182">50</span><span class="sxs-lookup"><span data-stu-id="1675b-182">50</span></span>   |

<span data-ttu-id="1675b-183"><sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1675b-183"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="1675b-184"><sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="1675b-184"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="1675b-185">如需詳細資訊，請參閱 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="1675b-185">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="1675b-p107">所有 Microsoft 365 和 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。在 Teams 中寄送電子郵件給頻道的功能不適用 Office GCC/GCCH/DOD 組織。</span><span class="sxs-lookup"><span data-stu-id="1675b-p107">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="1675b-188">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="1675b-188">Channel names</span></span>

<span data-ttu-id="1675b-189">頻道名稱不能包含下列字元或字詞：</span><span class="sxs-lookup"><span data-stu-id="1675b-189">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="1675b-190">類型</span><span class="sxs-lookup"><span data-stu-id="1675b-190">Type</span></span>|<span data-ttu-id="1675b-191">範例</span><span class="sxs-lookup"><span data-stu-id="1675b-191">Example</span></span>|
|---------|---------|
|<span data-ttu-id="1675b-192">字元</span><span class="sxs-lookup"><span data-stu-id="1675b-192">Characters</span></span>     | <span data-ttu-id="1675b-p108">~ # % & \* { } + / \ : < > ? &#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="1675b-p108">~ # % & \* { } + / \ : < > ? &#124; ' " , .</span></span>        |
|<span data-ttu-id="1675b-195">這些範圍內的字元</span><span class="sxs-lookup"><span data-stu-id="1675b-195">Characters in these ranges</span></span>    | <span data-ttu-id="1675b-196">0 至 1F</span><span class="sxs-lookup"><span data-stu-id="1675b-196">0 to 1F</span></span><br><span data-ttu-id="1675b-197">80 至 9F</span><span class="sxs-lookup"><span data-stu-id="1675b-197">80 to 9F</span></span>        |
|<span data-ttu-id="1675b-198">字詞</span><span class="sxs-lookup"><span data-stu-id="1675b-198">Words</span></span>     | <span data-ttu-id="1675b-199">forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="1675b-199">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="1675b-200">頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。</span><span class="sxs-lookup"><span data-stu-id="1675b-200">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="1675b-201">會議和通話</span><span class="sxs-lookup"><span data-stu-id="1675b-201">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1675b-202">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="1675b-202">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="1675b-203">**為了支援我們的客戶，直到 2021 年 1 月 1 日，針對 Teams、Stream 和 Yammer 中舉辦的即時活動，我們將會延長臨時的限制增加，其中包括**：</span><span class="sxs-lookup"><span data-stu-id="1675b-203">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for Live Events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="1675b-204">每個活動最多可有 20,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="1675b-204">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="1675b-205">每個 Teams 租用戶最多可同時舉行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="1675b-205">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="1675b-206">每個廣播最多 16 個小時</span><span class="sxs-lookup"><span data-stu-id="1675b-206">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="1675b-p109">此外，可透過 Microsoft 365 輔助計畫來規劃最多 10 萬位出席者參與的即時活動。小組會評估每個要求，並與您一起判斷可用的選項。[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。**2021 年 1 月 1 日之後，需要提高這些限制的客戶將需要購買 [進階通訊附加元件](teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="1675b-p109">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). **After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

|<span data-ttu-id="1675b-211">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-211">Feature</span></span>     | <span data-ttu-id="1675b-212">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-212">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="1675b-213">會議中的人數 (可以聊天和撥入)</span><span class="sxs-lookup"><span data-stu-id="1675b-213">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="1675b-214">350</span><span class="sxs-lookup"><span data-stu-id="1675b-214">350</span></span> |
|<span data-ttu-id="1675b-215">在聊天索引標籤上開始的聊天視訊或音訊通話中的人數</span><span class="sxs-lookup"><span data-stu-id="1675b-215">Number of people in a video or audio call started from the chat tab</span></span> | <span data-ttu-id="1675b-216">20</span><span class="sxs-lookup"><span data-stu-id="1675b-216">20</span></span> |
|<span data-ttu-id="1675b-217">PowerPoint 檔案大小的最大值</span><span class="sxs-lookup"><span data-stu-id="1675b-217">Max PowerPoint File Size</span></span> | <span data-ttu-id="1675b-218">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-218">2 GB</span></span>|
|<span data-ttu-id="1675b-219">Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載</span><span class="sxs-lookup"><span data-stu-id="1675b-219">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="1675b-220">20 天</span><span class="sxs-lookup"><span data-stu-id="1675b-220">20 days</span></span> |

>[!Note]
> <span data-ttu-id="1675b-p110">從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="1675b-p110">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="1675b-223">會議到期</span><span class="sxs-lookup"><span data-stu-id="1675b-223">Meeting expiration</span></span>

|<span data-ttu-id="1675b-224">會議類型</span><span class="sxs-lookup"><span data-stu-id="1675b-224">Meeting type</span></span>  |<span data-ttu-id="1675b-225">會議將在這些時間後到期</span><span class="sxs-lookup"><span data-stu-id="1675b-225">Meeting expires after this much time</span></span>  |<span data-ttu-id="1675b-226">每次您開始或更新會議，到期時間會延長這麼多時間</span><span class="sxs-lookup"><span data-stu-id="1675b-226">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="1675b-227">立即開會</span><span class="sxs-lookup"><span data-stu-id="1675b-227">Meet now</span></span>     |<span data-ttu-id="1675b-228">開始時間 + 8 小時</span><span class="sxs-lookup"><span data-stu-id="1675b-228">Start time + 8 hours</span></span>         |<span data-ttu-id="1675b-229">不適用</span><span class="sxs-lookup"><span data-stu-id="1675b-229">N/A</span></span>         |
|<span data-ttu-id="1675b-230">一般 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="1675b-230">Regular with no end time</span></span>     |<span data-ttu-id="1675b-231">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-231">Start time + 60 days</span></span>         | <span data-ttu-id="1675b-232">60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-232">60 days</span></span>        |
|<span data-ttu-id="1675b-233">一般 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="1675b-233">Regular with end time</span></span>     |<span data-ttu-id="1675b-234">結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-234">End time + 60 days</span></span>         |<span data-ttu-id="1675b-235">60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-235">60 days</span></span>         |
|<span data-ttu-id="1675b-236">週期性 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="1675b-236">Recurring with no end time</span></span>     |<span data-ttu-id="1675b-237">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-237">Start time + 60 days</span></span>         |<span data-ttu-id="1675b-238">60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-238">60 days</span></span>         |
|<span data-ttu-id="1675b-239">週期性 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="1675b-239">Recurring with end time</span></span>     |<span data-ttu-id="1675b-240">最後發生的結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-240">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="1675b-241">60 天</span><span class="sxs-lookup"><span data-stu-id="1675b-241">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="1675b-242">Microsoft Teams s會議的時間限制為 24 小時。</span><span class="sxs-lookup"><span data-stu-id="1675b-242">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="1675b-243">Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="1675b-243">Teams Live Events</span></span>

|<span data-ttu-id="1675b-244">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-244">Feature</span></span>     | <span data-ttu-id="1675b-245">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-245">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="1675b-246">對象數目</span><span class="sxs-lookup"><span data-stu-id="1675b-246">Audience size</span></span> | <span data-ttu-id="1675b-247">10,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="1675b-247">10,000 attendees</span></span> |
|<span data-ttu-id="1675b-248">活動持續時間</span><span class="sxs-lookup"><span data-stu-id="1675b-248">Duration of event</span></span> | <span data-ttu-id="1675b-249">4 小時</span><span class="sxs-lookup"><span data-stu-id="1675b-249">4 hours</span></span> |
|<span data-ttu-id="1675b-250">在 Microsoft 365 或 Office 365 組織中並行執行即時活動 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1675b-250">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="1675b-251">15</span><span class="sxs-lookup"><span data-stu-id="1675b-251">15</span></span> |

<span data-ttu-id="1675b-p111"><sup>1</sup> 您可根據自己的需求排定許多即時活動，但一次只能執行 15 個。製作人一加入即時活動，就表示該活動執行中。嘗試加入第 16 個即時活動的製作人會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="1675b-p111"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="1675b-p112">如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請移至 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。另請參閱[排程 Teams 即時活動](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。</span><span class="sxs-lookup"><span data-stu-id="1675b-p112">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1675b-257">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="1675b-257">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="1675b-258">**為了支援我們的客戶，直到 2021 年 1 月 1 日，針對 Teams、Stream 和 Yammer 中舉辦的即時活動，我們將會延長臨時的限制增加，其中包括**：</span><span class="sxs-lookup"><span data-stu-id="1675b-258">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for Live Events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
> - <span data-ttu-id="1675b-259">每個活動最多可有 20,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="1675b-259">Up to 20,000 attendees per event</span></span>
> - <span data-ttu-id="1675b-260">每個 Teams 租用戶最多可同時舉行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="1675b-260">Up to 50 simultaneous events per Teams tenant</span></span>
> - <span data-ttu-id="1675b-261">每個廣播最多 16 個小時</span><span class="sxs-lookup"><span data-stu-id="1675b-261">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="1675b-p113">此外，可透過 Microsoft 365 輔助計畫來規劃最多 10 萬位出席者參與的即時活動。小組會評估每個要求，並與您一起判斷可用的選項。[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。**2021 年 1 月 1 日之後，需要提高這些限制的客戶將需要購買 [進階通訊附加元件](teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="1675b-p113">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). **After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="1675b-266">在 Outlook 中的顯示狀態</span><span class="sxs-lookup"><span data-stu-id="1675b-266">Presence in Outlook</span></span>

<span data-ttu-id="1675b-p114">Outlook 2013 傳統型應用程式和更新版本中支援 Outlook 中的 Teams 顯示狀態。若要深入了解 Teams 中的顯示狀態，請參閱 [Teams 中的使用者顯示狀態](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="1675b-p114">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="1675b-269">儲存空間</span><span class="sxs-lookup"><span data-stu-id="1675b-269">Storage</span></span>

<span data-ttu-id="1675b-p115">Microsoft Teams 中的每個小組在 SharePoint Online 中都有一個小組網站，小組中的每個頻道在預設小組網站的文件庫中都有一個資料夾。在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="1675b-p115">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="1675b-272">每個[私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)都有自己的 SharePoint 網站 (先前稱之為 “網站集合)。</span><span class="sxs-lookup"><span data-stu-id="1675b-272">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="1675b-p116">如果您的租用戶中未啟用 SharePoint Online，Microsoft Teams 使用者就無法一律在小組中共用的檔案。私人聊天中的使用者也無法共用檔案，因為該功能需要商務用 OneDrive (其綁定至 SharePoint 授權)。</span><span class="sxs-lookup"><span data-stu-id="1675b-p116">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="1675b-p117">透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive，您將遵守所有在租用戶層級設定的合規性規則。(如需詳細資訊，請參閱 [SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="1675b-p117">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="1675b-p118">由於 Teams 是在 SharePoint Online 後端執行以進行檔案共用，因此 SharePoint 的限制會適用小組內的 [檔案] 區段。以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="1675b-p118">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="1675b-279">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-279">Feature</span></span>                 |<span data-ttu-id="1675b-280">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="1675b-280">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="1675b-281">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="1675b-281">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="1675b-282">Office 365 企業版 E1</span><span class="sxs-lookup"><span data-stu-id="1675b-282">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="1675b-283">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="1675b-283">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="1675b-284">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="1675b-284">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="1675b-285">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="1675b-285">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="1675b-286">儲存空間</span><span class="sxs-lookup"><span data-stu-id="1675b-286">Storage</span></span>                 |<span data-ttu-id="1675b-287">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-287">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="1675b-288">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-288">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="1675b-289">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-289">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="1675b-290">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-290">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="1675b-291">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-291">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="1675b-292">每個組織 1 TB </span><span class="sxs-lookup"><span data-stu-id="1675b-292">1 TB per organization</span></span>           |
|<span data-ttu-id="1675b-293">Teams 檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="1675b-293">Storage for Teams Files</span></span> |<span data-ttu-id="1675b-294">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="1675b-294">Up to 25 TB per site or group</span></span> |<span data-ttu-id="1675b-295">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="1675b-295">Up to 25 TB per site or group</span></span> |<span data-ttu-id="1675b-296">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="1675b-296">Up to 25 TB per site or group</span></span> |<span data-ttu-id="1675b-297">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="1675b-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="1675b-298">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="1675b-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="1675b-299">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="1675b-299">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="1675b-300">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="1675b-300">File upload limit  (per file)</span></span>    |<span data-ttu-id="1675b-301">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-301">2 GB</span></span>    |<span data-ttu-id="1675b-302">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-302">2 GB</span></span>    |<span data-ttu-id="1675b-303">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-303">2 GB</span></span>    |<span data-ttu-id="1675b-304">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-304">2 GB</span></span>    |<span data-ttu-id="1675b-305">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-305">2 GB</span></span>    |<span data-ttu-id="1675b-306">2 GB</span><span class="sxs-lookup"><span data-stu-id="1675b-306">2 GB</span></span>    |

<span data-ttu-id="1675b-307">頻道可由針對小組建立的 SharePoint Online 網站 (先前稱之為 "網站集合”) 內的資料夾進行備份，因此 [頻道] 內的檔案索引標籤會共用所屬小組的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="1675b-307">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="1675b-308">如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="1675b-308">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="1675b-309">課程小組</span><span class="sxs-lookup"><span data-stu-id="1675b-309">Class teams</span></span>

<span data-ttu-id="1675b-p119">Microsoft Teams 教育版提供專為獨特教育案例 (例如教室教學) 所設計的範本。如需有關小組類型 (包括課程小組) 的詳細資訊，請參閱[在 Microsoft Teams 中選擇要共同作業的小組類型](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)。</span><span class="sxs-lookup"><span data-stu-id="1675b-p119">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="1675b-312">課程小組是一個範本類型，其中包含其他應用程式，且具有的限制與小組成員數目不同。</span><span class="sxs-lookup"><span data-stu-id="1675b-312">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="1675b-313">使用課程小組需要 [Office 365 教育版授權](https://www.microsoft.com/education/products/office)。</span><span class="sxs-lookup"><span data-stu-id="1675b-313">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="1675b-314">下表列出課程小組的限制：</span><span class="sxs-lookup"><span data-stu-id="1675b-314">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="1675b-315">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-315">Feature</span></span>  |<span data-ttu-id="1675b-316">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-316">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="1675b-317">一個小組中的成員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-317">Number of members in a team</span></span>    | <span data-ttu-id="1675b-318">請參閱本文的 [Teams 和頻道](#teams-and-channels)一節</span><span class="sxs-lookup"><span data-stu-id="1675b-318">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="1675b-319">課程小組中要使用作業的成員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-319">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="1675b-320">200</span><span class="sxs-lookup"><span data-stu-id="1675b-320">200</span></span>        |
|<span data-ttu-id="1675b-321">課程小組中要使用 OneNote 課程筆記本的成員數目</span><span class="sxs-lookup"><span data-stu-id="1675b-321">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="1675b-322">200</span><span class="sxs-lookup"><span data-stu-id="1675b-322">200</span></span>         |

<span data-ttu-id="1675b-p120">課程小組可支援超過 200 個成員。不過，如果您計劃在您的小組內使用「作業」應用程式或「課程筆記本」應用程式，則您必須將成員數目保持在以上的上限之下。</span><span class="sxs-lookup"><span data-stu-id="1675b-p120">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="1675b-325">標籤</span><span class="sxs-lookup"><span data-stu-id="1675b-325">Tags</span></span>

|<span data-ttu-id="1675b-326">功能</span><span class="sxs-lookup"><span data-stu-id="1675b-326">Feature</span></span>  |<span data-ttu-id="1675b-327">最大限制</span><span class="sxs-lookup"><span data-stu-id="1675b-327">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="1675b-328">每個小組的標記數量</span><span class="sxs-lookup"><span data-stu-id="1675b-328">Number of tags per team</span></span>    | <span data-ttu-id="1675b-329">100</span><span class="sxs-lookup"><span data-stu-id="1675b-329">100</span></span>        |
|<span data-ttu-id="1675b-330">每個小組的建議預設標記數量</span><span class="sxs-lookup"><span data-stu-id="1675b-330">Number of suggested default tags per team</span></span>    | <span data-ttu-id="1675b-331">25</span><span class="sxs-lookup"><span data-stu-id="1675b-331">25</span></span>        |
|<span data-ttu-id="1675b-332">指派給標記的小組成員人數</span><span class="sxs-lookup"><span data-stu-id="1675b-332">Number of team members assign to a tag</span></span>    |<span data-ttu-id="1675b-333">100</span><span class="sxs-lookup"><span data-stu-id="1675b-333">100</span></span>         |
|<span data-ttu-id="1675b-334">指派給使用者的標記數量</span><span class="sxs-lookup"><span data-stu-id="1675b-334">Number of tags assigned to a user</span></span>    |<span data-ttu-id="1675b-335">25</span><span class="sxs-lookup"><span data-stu-id="1675b-335">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="1675b-336">連絡人</span><span class="sxs-lookup"><span data-stu-id="1675b-336">Contacts</span></span>

<span data-ttu-id="1675b-337">Teams 使用下列連絡人：</span><span class="sxs-lookup"><span data-stu-id="1675b-337">Teams uses these contacts:</span></span>

- <span data-ttu-id="1675b-338">您組織 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="1675b-338">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="1675b-339">新增至使用者 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="1675b-339">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="1675b-340">Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天] > [連絡人] 或是 [通話] > [連絡人]。</span><span class="sxs-lookup"><span data-stu-id="1675b-340">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="1675b-341">Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話] > [連絡人]。</span><span class="sxs-lookup"><span data-stu-id="1675b-341">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="1675b-342">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="1675b-342">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="1675b-343">作業系統</span><span class="sxs-lookup"><span data-stu-id="1675b-343">Operating systems</span></span>

<span data-ttu-id="1675b-344">如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="1675b-344">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
