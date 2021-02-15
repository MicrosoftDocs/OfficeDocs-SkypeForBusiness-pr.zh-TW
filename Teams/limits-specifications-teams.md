---
title: Microsoft Teams 的限制和規格
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
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
ms.openlocfilehash: daba993118348bbd4de2b1677e6a75cbce7c0ae9
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196787"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="ca896-103">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="ca896-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="ca896-104">本文說明一些套用到 Teams 的限制、規格和其他需求。</span><span class="sxs-lookup"><span data-stu-id="ca896-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="ca896-105">小組和頻道</span><span class="sxs-lookup"><span data-stu-id="ca896-105">Teams and channels</span></span>

|<span data-ttu-id="ca896-106">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-106">Feature</span></span>    | <span data-ttu-id="ca896-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="ca896-108">一位使用者可以建立的小組數目</span><span class="sxs-lookup"><span data-stu-id="ca896-108">Number of teams a user can create</span></span> | <span data-ttu-id="ca896-109">受限於 250 的物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="ca896-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="ca896-110">一位使用者可以加入成為成員的團隊數目</span><span class="sxs-lookup"><span data-stu-id="ca896-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="ca896-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="ca896-111">1,000&sup2;</span></span>|
|<span data-ttu-id="ca896-112">一個小組中的成員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-112">Number of members in a team</span></span> | <span data-ttu-id="ca896-113">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-113">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="ca896-114">每個小組擁有者人數</span><span class="sxs-lookup"><span data-stu-id="ca896-114">Number of owners per team</span></span> | <span data-ttu-id="ca896-115">100</span><span class="sxs-lookup"><span data-stu-id="ca896-115">100</span></span>   |
|<span data-ttu-id="ca896-116">一個租用戶中允許的全組織小組數目</span><span class="sxs-lookup"><span data-stu-id="ca896-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="ca896-117">5</span><span class="sxs-lookup"><span data-stu-id="ca896-117">5</span></span>     |
|<span data-ttu-id="ca896-118">一個[全組織小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="ca896-119">10,000</span><span class="sxs-lookup"><span data-stu-id="ca896-119">10,000</span></span>       |
|<span data-ttu-id="ca896-120">一位全域系統管理員可以建立的小組數目</span><span class="sxs-lookup"><span data-stu-id="ca896-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="ca896-121">500,000</span><span class="sxs-lookup"><span data-stu-id="ca896-121">500,000</span></span>   |
|<span data-ttu-id="ca896-122">一個 Microsoft 365 或 Office 365 組織可以擁有的小組數目</span><span class="sxs-lookup"><span data-stu-id="ca896-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="ca896-123">500,000&sup3;</span><span class="sxs-lookup"><span data-stu-id="ca896-123">500,000&sup3;</span></span>     |
|<span data-ttu-id="ca896-124">每個小組的頻道數目</span><span class="sxs-lookup"><span data-stu-id="ca896-124">Number of channels per team</span></span>    | <span data-ttu-id="ca896-125">200 (包含已刪除的頻道)&sup4;</span><span class="sxs-lookup"><span data-stu-id="ca896-125">200 (includes deleted channels)&sup4;</span></span>         |
|<span data-ttu-id="ca896-126">每個小組的私人頻道數量</span><span class="sxs-lookup"><span data-stu-id="ca896-126">Number of Private channels per team</span></span>    |<span data-ttu-id="ca896-127">30</span><span class="sxs-lookup"><span data-stu-id="ca896-127">30</span></span>| <span data-ttu-id="ca896-128">(包含已刪除的頻道)&sup4;</span><span class="sxs-lookup"><span data-stu-id="ca896-128">(includes deleted channels)&sup4;</span></span>
|<span data-ttu-id="ca896-129">私人頻道中的成員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="ca896-130">250</span><span class="sxs-lookup"><span data-stu-id="ca896-130">250</span></span>|
|<span data-ttu-id="ca896-131">可匯入小組中的通訊群組清單、安全性群組或 Office 365 群組的大小上限</span><span class="sxs-lookup"><span data-stu-id="ca896-131">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="ca896-132">3,500</span><span class="sxs-lookup"><span data-stu-id="ca896-132">3,500</span></span>|
|<span data-ttu-id="ca896-133">Office 365 群組中可轉換成小組的成員數目上限</span><span class="sxs-lookup"><span data-stu-id="ca896-133">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="ca896-134">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-134">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="ca896-135">頻道交談貼文大小</span><span class="sxs-lookup"><span data-stu-id="ca896-135">Channel conversation post size</span></span> | <span data-ttu-id="ca896-136">每篇貼文約 28 KB<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-136">Approximately 28 KB per post<sup>5</sup></span></span> |

<span data-ttu-id="ca896-p101"><sup>1</sup> Azure Active Directory 中的任何目錄物件都會計入此限制。全域系統管理員會從此限制豁免，使用[應用程式權限](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式亦然。</span><span class="sxs-lookup"><span data-stu-id="ca896-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="ca896-139"><sup>2</sup> 此限制包含已封存的小組。</span><span class="sxs-lookup"><span data-stu-id="ca896-139"><sup>2</sup> This limit includes archived teams.</span></span> 

<span data-ttu-id="ca896-140"><sup>3</sup> 若要進一步增加小組數目，您必須與 Microsoft 支援服務連絡，並要求進一步增加您的租用戶中 Azure Active Directory 物件的數量。</span><span class="sxs-lookup"><span data-stu-id="ca896-140"><sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant.</span></span> <span data-ttu-id="ca896-141">只有實際生產案例才會增加。</span><span class="sxs-lookup"><span data-stu-id="ca896-141">Increase is only made for real-life production scenarios.</span></span>

<span data-ttu-id="ca896-142"><sup>4</sup> 已刪除的頻道可以在 30 天內還原。</span><span class="sxs-lookup"><span data-stu-id="ca896-142"><sup>4</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="ca896-143">在這 30 天內，已刪除的頻道會持續計入每個小組 200 個頻道或 30 個私人頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="ca896-143">During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit.</span></span> <span data-ttu-id="ca896-144">30 天後，已刪除的頻道及其內容會永久刪除，且該頻道不再會計入每個小組頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="ca896-144">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="ca896-145"><sup>5</sup> 28 KB 是大約限制，因為其包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。</span><span class="sxs-lookup"><span data-stu-id="ca896-145"><sup>5</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="ca896-146"><sup>6</sup> GCC 中的 Teams 只能容納 5,000 個成員，而 GCCH/DoD 中只能容納 2,500 個成員。</span><span class="sxs-lookup"><span data-stu-id="ca896-146"><sup>6</sup> Teams in GCC can only accommodate 5,000 members and teams in GCCH/DoD can only accommodate 2,500 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="ca896-147">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="ca896-147">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="ca896-148">聊天</span><span class="sxs-lookup"><span data-stu-id="ca896-148">Chat</span></span>

<span data-ttu-id="ca896-p104">參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留。(如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="ca896-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="ca896-155">Teams 的聊天是在 Microsoft Exchange 後端執行，因此 Exchange 的訊息限制會套用到 Teams 內的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="ca896-155">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="ca896-156">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-156">Feature</span></span>  | <span data-ttu-id="ca896-157">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-157">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ca896-158">一個私人聊天中的人員數目<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-158">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="ca896-159">250<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-159">250<sup>2</sup></span></span> |
|<span data-ttu-id="ca896-160">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-160">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="ca896-161">20</span><span class="sxs-lookup"><span data-stu-id="ca896-161">20</span></span> |
|<span data-ttu-id="ca896-162">檔案附件的數目<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-162">Number of file attachments<sup>3</sup></span></span>  |<span data-ttu-id="ca896-163">10</span><span class="sxs-lookup"><span data-stu-id="ca896-163">10</span></span>     |
|<span data-ttu-id="ca896-164">聊天大小</span><span class="sxs-lookup"><span data-stu-id="ca896-164">Chat size</span></span> | <span data-ttu-id="ca896-165">每篇貼文約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-165">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="ca896-p105"><sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息；輸入指示器；視訊和音訊通話；共用；讀取回條。當私人群組聊天包含超過 20 個成員時，也會移除 [設定傳遞選項] 按鈕 (!)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="ca896-168"><sup>2</sup> 每次只能將 200 名成員新增至群組聊天。</span><span class="sxs-lookup"><span data-stu-id="ca896-168"><sup>2</sup> Only 200 members at a time can be added to a group chat.</span></span> <span data-ttu-id="ca896-169">[如需詳細資訊，請參閱這篇文章](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)。</span><span class="sxs-lookup"><span data-stu-id="ca896-169">[See this article for more information](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span></span>

<span data-ttu-id="ca896-170"><sup>3</sup> 如果附件數量超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="ca896-170"><sup>3</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="ca896-171"><sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@-提及和回應。</span><span class="sxs-lookup"><span data-stu-id="ca896-171"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="ca896-172">傳送電子郵件到頻道</span><span class="sxs-lookup"><span data-stu-id="ca896-172">Emailing a channel</span></span>

 <span data-ttu-id="ca896-p107">如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。以下是一些傳送電子郵件到頻道時適用的限制。</span><span class="sxs-lookup"><span data-stu-id="ca896-p107">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="ca896-176">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-176">Feature</span></span>  | <span data-ttu-id="ca896-177">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-177">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ca896-178">郵件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="ca896-178">Message size<sup>1<sup></span></span> | <span data-ttu-id="ca896-179">24 KB</span><span class="sxs-lookup"><span data-stu-id="ca896-179">24 KB</span></span> |
|<span data-ttu-id="ca896-180">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-180">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="ca896-181">20</span><span class="sxs-lookup"><span data-stu-id="ca896-181">20</span></span>     |
|<span data-ttu-id="ca896-182">每個檔案附件的大小</span><span class="sxs-lookup"><span data-stu-id="ca896-182">Size of each file attachment</span></span> | <span data-ttu-id="ca896-183">小於 10 MB</span><span class="sxs-lookup"><span data-stu-id="ca896-183">Less than 10 MB</span></span> |
|<span data-ttu-id="ca896-184">內嵌影像的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-184">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="ca896-185">50</span><span class="sxs-lookup"><span data-stu-id="ca896-185">50</span></span>   |

<span data-ttu-id="ca896-186"><sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ca896-186"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="ca896-187"><sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="ca896-187"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="ca896-188">如需詳細資訊，請參閱 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="ca896-188">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="ca896-p108">所有 Microsoft 365 和 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。在 Teams 中寄送電子郵件給頻道的功能不適用 Office GCC/GCCH/DOD 組織。</span><span class="sxs-lookup"><span data-stu-id="ca896-p108">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="ca896-191">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="ca896-191">Channel names</span></span>

<span data-ttu-id="ca896-192">頻道名稱不能包含下列字元或字詞：</span><span class="sxs-lookup"><span data-stu-id="ca896-192">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="ca896-193">類型</span><span class="sxs-lookup"><span data-stu-id="ca896-193">Type</span></span>|<span data-ttu-id="ca896-194">範例</span><span class="sxs-lookup"><span data-stu-id="ca896-194">Example</span></span>|
|---------|---------|
|<span data-ttu-id="ca896-195">字元</span><span class="sxs-lookup"><span data-stu-id="ca896-195">Characters</span></span>     | <span data-ttu-id="ca896-p109">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span><span class="sxs-lookup"><span data-stu-id="ca896-p109">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span></span>        |
|<span data-ttu-id="ca896-198">這些範圍內的字元</span><span class="sxs-lookup"><span data-stu-id="ca896-198">Characters in these ranges</span></span>    | <span data-ttu-id="ca896-199">0 至 1F</span><span class="sxs-lookup"><span data-stu-id="ca896-199">0 to 1F</span></span><br><span data-ttu-id="ca896-200">80 至 9F</span><span class="sxs-lookup"><span data-stu-id="ca896-200">80 to 9F</span></span>        |
|<span data-ttu-id="ca896-201">字詞</span><span class="sxs-lookup"><span data-stu-id="ca896-201">Words</span></span>     | <span data-ttu-id="ca896-202">forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="ca896-202">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="ca896-203">頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。</span><span class="sxs-lookup"><span data-stu-id="ca896-203">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="ca896-204">會議和通話</span><span class="sxs-lookup"><span data-stu-id="ca896-204">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca896-205">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="ca896-205">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="ca896-206">**為能持續支援我們客戶的需求，直到 2021 年 6 月 30 日，我們將延長即時活動的暫時性限制增加**：</span><span class="sxs-lookup"><span data-stu-id="ca896-206">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="ca896-207">活動支援最多達 20000 個出席者</span><span class="sxs-lookup"><span data-stu-id="ca896-207">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="ca896-208">不同租用戶可以同時進行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="ca896-208">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="ca896-209">每個廣播的活動持續時間 (16 小時)</span><span class="sxs-lookup"><span data-stu-id="ca896-209">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="ca896-p110">此外，可透過 Microsoft 365 輔助計畫來規劃最多 100,000 位出席者參與的即時活動。小組會評估每個要求，並與您一起判斷可用的選項。[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p110">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span>

|<span data-ttu-id="ca896-213">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-213">Feature</span></span>     | <span data-ttu-id="ca896-214">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-214">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="ca896-215">一場會議中的人數 (可以交談和通話)</span><span class="sxs-lookup"><span data-stu-id="ca896-215">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="ca896-216">300。**僅檢視** 會允許高達 10,000 名僅限聆聽參與者加入會議，其中的召集人擁有 E3/E5/A3/A5 SKU 的授權。</span><span class="sxs-lookup"><span data-stu-id="ca896-216">300. **View-only** allows for up to 10,000 listen-only participants to join a meeting in which the organizer has a license for E3/E5/A3/A5 SKU.</span></span><br><span data-ttu-id="ca896-217">**附註：** 針對政府用 Teams (GCC、GCC、DoD)，其限制仍為 250。</span><span class="sxs-lookup"><span data-stu-id="ca896-217">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 250.</span></span> <span data-ttu-id="ca896-218">當政府用雲端限制從 250 增加至 300 並支援會議溢出時，我們就會更新本文章。</span><span class="sxs-lookup"><span data-stu-id="ca896-218">We'll update this article when the government cloud limit increases from 250 to 300 and supports meeting overflow.</span></span> <span data-ttu-id="ca896-219">深入了解[僅檢視體驗](view-only-meeting-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="ca896-219">Learn more about the [View-only experience](view-only-meeting-experience.md).</span></span>|
|<span data-ttu-id="ca896-220">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-220">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="ca896-221">20</span><span class="sxs-lookup"><span data-stu-id="ca896-221">20</span></span> |
|<span data-ttu-id="ca896-222">PowerPoint 檔案大小的最大值</span><span class="sxs-lookup"><span data-stu-id="ca896-222">Max PowerPoint File Size</span></span> | <span data-ttu-id="ca896-223">2 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-223">2GB</span></span>|
|<span data-ttu-id="ca896-224">Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載</span><span class="sxs-lookup"><span data-stu-id="ca896-224">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="ca896-225">20 天</span><span class="sxs-lookup"><span data-stu-id="ca896-225">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="ca896-226">會議到期</span><span class="sxs-lookup"><span data-stu-id="ca896-226">Meeting expiration</span></span>

|<span data-ttu-id="ca896-227">會議類型</span><span class="sxs-lookup"><span data-stu-id="ca896-227">Meeting type</span></span>  |<span data-ttu-id="ca896-228">會議將在這些時間後到期</span><span class="sxs-lookup"><span data-stu-id="ca896-228">Meeting expires after this much time</span></span>  |<span data-ttu-id="ca896-229">每次您開始或更新會議，到期時間會延長這麼多時間</span><span class="sxs-lookup"><span data-stu-id="ca896-229">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ca896-230">立即開會</span><span class="sxs-lookup"><span data-stu-id="ca896-230">Meet now</span></span>     |<span data-ttu-id="ca896-231">開始時間 + 8 小時</span><span class="sxs-lookup"><span data-stu-id="ca896-231">Start time + 8 hours</span></span>         |<span data-ttu-id="ca896-232">不適用</span><span class="sxs-lookup"><span data-stu-id="ca896-232">N/A</span></span>         |
|<span data-ttu-id="ca896-233">一般 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="ca896-233">Regular with no end time</span></span>     |<span data-ttu-id="ca896-234">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-234">Start time + 60 days</span></span>         | <span data-ttu-id="ca896-235">60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-235">60 days</span></span>        |
|<span data-ttu-id="ca896-236">一般 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="ca896-236">Regular with end time</span></span>     |<span data-ttu-id="ca896-237">結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-237">End time + 60 days</span></span>         |<span data-ttu-id="ca896-238">60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-238">60 days</span></span>         |
|<span data-ttu-id="ca896-239">週期性 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="ca896-239">Recurring with no end time</span></span>     |<span data-ttu-id="ca896-240">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-240">Start time + 60 days</span></span>         |<span data-ttu-id="ca896-241">60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-241">60 days</span></span>         |
|<span data-ttu-id="ca896-242">週期性 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="ca896-242">Recurring with end time</span></span>     |<span data-ttu-id="ca896-243">最後發生的結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-243">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="ca896-244">60 天</span><span class="sxs-lookup"><span data-stu-id="ca896-244">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="ca896-245">Microsoft Teams s會議的時間限制為 24 小時。</span><span class="sxs-lookup"><span data-stu-id="ca896-245">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="ca896-246">Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="ca896-246">Teams Live Events</span></span>

|<span data-ttu-id="ca896-247">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-247">Feature</span></span>     | <span data-ttu-id="ca896-248">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-248">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="ca896-249">對象數目</span><span class="sxs-lookup"><span data-stu-id="ca896-249">Audience size</span></span> | <span data-ttu-id="ca896-250">10,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="ca896-250">10,000 attendees</span></span> |
|<span data-ttu-id="ca896-251">活動持續時間</span><span class="sxs-lookup"><span data-stu-id="ca896-251">Duration of event</span></span> | <span data-ttu-id="ca896-252">4 小時</span><span class="sxs-lookup"><span data-stu-id="ca896-252">4 hours</span></span> |
|<span data-ttu-id="ca896-253">在 Microsoft 365 或 Office 365 組織中並行執行即時活動 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca896-253">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="ca896-254">15</span><span class="sxs-lookup"><span data-stu-id="ca896-254">15</span></span> |

<span data-ttu-id="ca896-p112"><sup>1</sup> 您可根據自己的需求排定許多即時活動，但一次只能執行 15 個。製作人一加入即時活動，就表示該活動執行中。嘗試加入第 16 個即時活動的製作人會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="ca896-p112"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="ca896-p113">如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請移至 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。另請參閱[排程 Teams 即時活動](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p113">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca896-260">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="ca896-260">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="ca896-261">**為能持續支援我們客戶的需求，直到 2021 年 6 月 30 日，我們將延長即時活動的暫時性限制增加**：</span><span class="sxs-lookup"><span data-stu-id="ca896-261">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="ca896-262">活動支援最多達 20000 個出席者</span><span class="sxs-lookup"><span data-stu-id="ca896-262">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="ca896-263">不同租用戶可以同時進行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="ca896-263">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="ca896-264">每個廣播的活動持續時間 (16 小時)</span><span class="sxs-lookup"><span data-stu-id="ca896-264">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="ca896-p114">此外，可透過 Microsoft 365 輔助計畫來規劃最多 100,000 位出席者參與的即時活動。小組會評估每個要求，並與您一起判斷可用的選項。[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p114">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

## <a name="presence-in-outlook"></a><span data-ttu-id="ca896-268">在 Outlook 中的顯示狀態</span><span class="sxs-lookup"><span data-stu-id="ca896-268">Presence in Outlook</span></span>

<span data-ttu-id="ca896-p115">Outlook 2013 傳統型應用程式和更新版本中支援 Outlook 中的 Teams 顯示狀態。若要深入了解 Teams 中的顯示狀態，請參閱 [Teams 中的使用者顯示狀態](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p115">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="ca896-271">儲存空間</span><span class="sxs-lookup"><span data-stu-id="ca896-271">Storage</span></span>

<span data-ttu-id="ca896-p116">Microsoft Teams 中的每個小組在 SharePoint Online 中都有一個小組網站，小組中的每個頻道在預設小組網站的文件庫中都有一個資料夾。在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="ca896-p116">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="ca896-274">每個[私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)都有自己的 SharePoint 網站 (先前稱之為 “網站集合)。</span><span class="sxs-lookup"><span data-stu-id="ca896-274">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="ca896-p117">如果您的租用戶中未啟用 SharePoint Online，Microsoft Teams 使用者就無法一律在小組中共用的檔案。私人聊天中的使用者也無法共用檔案，因為該功能需要商務用 OneDrive (其綁定至 SharePoint 授權)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p117">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="ca896-p118">透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive，您將遵守所有在租用戶層級設定的合規性規則。(如需詳細資訊，請參閱 [SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="ca896-p118">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="ca896-p119">由於 Teams 是在 SharePoint Online 後端執行以進行檔案共用，因此 SharePoint 的限制會適用小組內的 [檔案] 區段。以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="ca896-p119">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="ca896-281">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-281">Feature</span></span>                 |<span data-ttu-id="ca896-282">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="ca896-282">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="ca896-283">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="ca896-283">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="ca896-284">Office 365 企業版 E1</span><span class="sxs-lookup"><span data-stu-id="ca896-284">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="ca896-285">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="ca896-285">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="ca896-286">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="ca896-286">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="ca896-287">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="ca896-287">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="ca896-288">儲存空間</span><span class="sxs-lookup"><span data-stu-id="ca896-288">Storage</span></span>                 |<span data-ttu-id="ca896-289">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-289">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="ca896-290">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-290">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="ca896-291">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-291">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="ca896-292">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-292">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="ca896-293">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-293">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="ca896-294">每個組織 1 TB </span><span class="sxs-lookup"><span data-stu-id="ca896-294">1 TB per organization</span></span>           |
|<span data-ttu-id="ca896-295">Teams 檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="ca896-295">Storage for Teams Files</span></span> |<span data-ttu-id="ca896-296">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ca896-296">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ca896-297">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ca896-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ca896-298">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ca896-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ca896-299">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ca896-299">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ca896-300">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ca896-300">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ca896-301">每個網站或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ca896-301">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="ca896-302">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="ca896-302">File upload limit  (per file)</span></span>    |<span data-ttu-id="ca896-303">100 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-303">100 GB</span></span>    |<span data-ttu-id="ca896-304">100 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-304">100 GB</span></span>    |<span data-ttu-id="ca896-305">100 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-305">100 GB</span></span>    |<span data-ttu-id="ca896-306">100 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-306">100 GB</span></span>    |<span data-ttu-id="ca896-307">100 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-307">100 GB</span></span>    |<span data-ttu-id="ca896-308">100 GB</span><span class="sxs-lookup"><span data-stu-id="ca896-308">100 GB</span></span>    |

<span data-ttu-id="ca896-309">頻道可由針對小組建立的 SharePoint Online 網站 (先前稱之為 "網站集合”) 內的資料夾進行備份，因此 [頻道] 內的檔案索引標籤會共用所屬小組的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="ca896-309">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="ca896-310">如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="ca896-310">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="ca896-311">課程小組</span><span class="sxs-lookup"><span data-stu-id="ca896-311">Class teams</span></span>

<span data-ttu-id="ca896-p120">Microsoft Teams 教育版提供專為獨特教育案例 (例如教室教學) 所設計的範本。如需有關小組類型 (包括課程小組) 的詳細資訊，請參閱[在 Microsoft Teams 中選擇要共同作業的小組類型](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)。</span><span class="sxs-lookup"><span data-stu-id="ca896-p120">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="ca896-314">課程小組是一個範本類型，其中包含其他應用程式，且具有的限制與小組成員數目不同。</span><span class="sxs-lookup"><span data-stu-id="ca896-314">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="ca896-315">使用課程小組需要 [Office 365 教育版授權](https://www.microsoft.com/education/products/office)。</span><span class="sxs-lookup"><span data-stu-id="ca896-315">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="ca896-316">下表列出課程小組的限制：</span><span class="sxs-lookup"><span data-stu-id="ca896-316">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="ca896-317">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-317">Feature</span></span>  |<span data-ttu-id="ca896-318">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-318">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ca896-319">一個小組中的成員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-319">Number of members in a team</span></span>    | <span data-ttu-id="ca896-320">請參閱本文的 [Teams 和頻道](#teams-and-channels)一節</span><span class="sxs-lookup"><span data-stu-id="ca896-320">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="ca896-321">課程小組中要使用作業的成員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-321">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="ca896-322">200</span><span class="sxs-lookup"><span data-stu-id="ca896-322">200</span></span>        |
|<span data-ttu-id="ca896-323">課程小組中要使用 OneNote 課程筆記本的成員數目</span><span class="sxs-lookup"><span data-stu-id="ca896-323">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="ca896-324">200</span><span class="sxs-lookup"><span data-stu-id="ca896-324">200</span></span>         |

<span data-ttu-id="ca896-p121">課程小組可支援超過 200 個成員。不過，如果您計劃在您的小組內使用「作業」應用程式或「課程筆記本」應用程式，則您必須將成員數目保持在以上的上限之下。</span><span class="sxs-lookup"><span data-stu-id="ca896-p121">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="ca896-327">標籤</span><span class="sxs-lookup"><span data-stu-id="ca896-327">Tags</span></span>

|<span data-ttu-id="ca896-328">功能</span><span class="sxs-lookup"><span data-stu-id="ca896-328">Feature</span></span>  |<span data-ttu-id="ca896-329">最大限制</span><span class="sxs-lookup"><span data-stu-id="ca896-329">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ca896-330">每個小組的標記數量</span><span class="sxs-lookup"><span data-stu-id="ca896-330">Number of tags per team</span></span>    | <span data-ttu-id="ca896-331">100</span><span class="sxs-lookup"><span data-stu-id="ca896-331">100</span></span>        |
|<span data-ttu-id="ca896-332">每個小組的建議預設標記數量</span><span class="sxs-lookup"><span data-stu-id="ca896-332">Number of suggested default tags per team</span></span>    | <span data-ttu-id="ca896-333">25</span><span class="sxs-lookup"><span data-stu-id="ca896-333">25</span></span>        |
|<span data-ttu-id="ca896-334">指派給標記的小組成員人數</span><span class="sxs-lookup"><span data-stu-id="ca896-334">Number of team members assign to a tag</span></span>    |<span data-ttu-id="ca896-335">100</span><span class="sxs-lookup"><span data-stu-id="ca896-335">100</span></span>         |
|<span data-ttu-id="ca896-336">指派給使用者的標記數量</span><span class="sxs-lookup"><span data-stu-id="ca896-336">Number of tags assigned to a user</span></span>    |<span data-ttu-id="ca896-337">25</span><span class="sxs-lookup"><span data-stu-id="ca896-337">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="ca896-338">連絡人</span><span class="sxs-lookup"><span data-stu-id="ca896-338">Contacts</span></span>

<span data-ttu-id="ca896-339">Teams 使用下列連絡人：</span><span class="sxs-lookup"><span data-stu-id="ca896-339">Teams uses these contacts:</span></span>

- <span data-ttu-id="ca896-340">您組織 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="ca896-340">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="ca896-341">新增至使用者 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="ca896-341">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="ca896-342">Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天] > [連絡人] 或是 [通話] > [連絡人]。</span><span class="sxs-lookup"><span data-stu-id="ca896-342">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="ca896-343">Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話] > [連絡人]。</span><span class="sxs-lookup"><span data-stu-id="ca896-343">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="ca896-344">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="ca896-344">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="ca896-345">作業系統</span><span class="sxs-lookup"><span data-stu-id="ca896-345">Operating systems</span></span>

<span data-ttu-id="ca896-346">如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="ca896-346">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
