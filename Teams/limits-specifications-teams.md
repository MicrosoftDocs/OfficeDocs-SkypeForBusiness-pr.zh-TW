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
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a95606786b59718e99adedb9a33ad31c1903f75
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308196"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="f6ec9-103">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="f6ec9-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="f6ec9-104">本文說明一些套用到 Teams 的限制、規格和其他需求。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="f6ec9-105">小組和頻道</span><span class="sxs-lookup"><span data-stu-id="f6ec9-105">Teams and channels</span></span>

|<span data-ttu-id="f6ec9-106">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-106">Feature</span></span>    | <span data-ttu-id="f6ec9-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="f6ec9-108">一位使用者可以建立的小組數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-108">Number of teams a user can create</span></span> | <span data-ttu-id="f6ec9-109">受限於 250 的物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="f6ec9-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="f6ec9-110">一位使用者可以加入成為成員的團隊數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="f6ec9-111">1,000</span><span class="sxs-lookup"><span data-stu-id="f6ec9-111">1,000</span></span>|
|<span data-ttu-id="f6ec9-112">一個小組中的成員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-112">Number of members in a team</span></span> | <span data-ttu-id="f6ec9-113">10,000</span><span class="sxs-lookup"><span data-stu-id="f6ec9-113">10,000</span></span>       |
|<span data-ttu-id="f6ec9-114">每個小組擁有者人數</span><span class="sxs-lookup"><span data-stu-id="f6ec9-114">Number of owners per team</span></span> | <span data-ttu-id="f6ec9-115">100</span><span class="sxs-lookup"><span data-stu-id="f6ec9-115">100</span></span>   |
|<span data-ttu-id="f6ec9-116">一個租用戶中允許的全組織小組數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="f6ec9-117">5</span><span class="sxs-lookup"><span data-stu-id="f6ec9-117">5</span></span>     |
|<span data-ttu-id="f6ec9-118">一個[全組織小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="f6ec9-119">5,000</span><span class="sxs-lookup"><span data-stu-id="f6ec9-119">5,000</span></span>       |
|<span data-ttu-id="f6ec9-120">一位全域系統管理員可以建立的小組數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="f6ec9-121">500,000</span><span class="sxs-lookup"><span data-stu-id="f6ec9-121">500,000</span></span>   |
|<span data-ttu-id="f6ec9-122">一個 Microsoft 365 或 Office 365 組織可以擁有的小組數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="f6ec9-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="f6ec9-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="f6ec9-124">每個小組的頻道數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-124">Number of channels per team</span></span>    | <span data-ttu-id="f6ec9-125">200 (包含已刪除的頻道)&sup3;</span><span class="sxs-lookup"><span data-stu-id="f6ec9-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="f6ec9-126">每個小組的私人頻道數量</span><span class="sxs-lookup"><span data-stu-id="f6ec9-126">Number of Private channels per team</span></span>    |<span data-ttu-id="f6ec9-127">30</span><span class="sxs-lookup"><span data-stu-id="f6ec9-127">30</span></span>|
|<span data-ttu-id="f6ec9-128">私人頻道中的成員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="f6ec9-129">250</span><span class="sxs-lookup"><span data-stu-id="f6ec9-129">250</span></span>|
|<span data-ttu-id="f6ec9-130">Office 365 群組中可轉換成小組的成員數目上限</span><span class="sxs-lookup"><span data-stu-id="f6ec9-130">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="f6ec9-131">10,000</span><span class="sxs-lookup"><span data-stu-id="f6ec9-131">10,000</span></span>|
|<span data-ttu-id="f6ec9-132">頻道交談貼文大小</span><span class="sxs-lookup"><span data-stu-id="f6ec9-132">Channel conversation post size</span></span> | <span data-ttu-id="f6ec9-133">每篇貼文約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-133">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="f6ec9-134"><sup>1</sup>Azure Active Directory 中的任何目錄物件都會計入此限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-134"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="f6ec9-135">全域系統管理員不受此限制，使用[應用程式權限](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式也不受此限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-135">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="f6ec9-136"><sup>2</sup>此限制包含已封存的小組。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-136"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="f6ec9-137"><sup>3</sup>已刪除的頻道可以在 30 天內還原。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-137"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="f6ec9-138">在這 30 天內，已刪除的頻道會持續計入每個小組 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-138">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="f6ec9-139">30 天後，已刪除的頻道及其內容會永久刪除，該頻道不再計入每個小組 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-139">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="f6ec9-140"><sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-140"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="f6ec9-141">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="f6ec9-141">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="f6ec9-142">聊天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-142">Chat</span></span>

<span data-ttu-id="f6ec9-143">參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-143">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="f6ec9-144">這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-144">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="f6ec9-145">如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-145">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="f6ec9-146">例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-146">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="f6ec9-147">然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留 </span><span class="sxs-lookup"><span data-stu-id="f6ec9-147">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="f6ec9-148">(如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-148">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="f6ec9-149">Teams 的聊天是在 Microsoft Exchange 後端執行，因此 Exchange 的訊息限制會套用到 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-149">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="f6ec9-150">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-150">Feature</span></span>  | <span data-ttu-id="f6ec9-151">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-151">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f6ec9-152">一個私人聊天中的人員數目<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-152">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="f6ec9-153">250</span><span class="sxs-lookup"><span data-stu-id="f6ec9-153">250</span></span> |
|<span data-ttu-id="f6ec9-154">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="f6ec9-155">20</span><span class="sxs-lookup"><span data-stu-id="f6ec9-155">20</span></span> |
|<span data-ttu-id="f6ec9-156">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="f6ec9-157">10</span><span class="sxs-lookup"><span data-stu-id="f6ec9-157">10</span></span>     |
|<span data-ttu-id="f6ec9-158">聊天大小</span><span class="sxs-lookup"><span data-stu-id="f6ec9-158">Chat size</span></span> | <span data-ttu-id="f6ec9-159">每篇貼文約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="f6ec9-160"><sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息、輸入指示器、視訊和音訊通話、共用、讀取回條。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="f6ec9-161">當私人群組聊天包含超過 20 個成員時，也會移除 [設定傳遞選項] 按鈕 (!)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-161">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="f6ec9-162"><sup>2</sup> 如果附件數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-162"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="f6ec9-163"><sup>3</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及和回應。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-163"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="f6ec9-164">傳送電子郵件到頻道</span><span class="sxs-lookup"><span data-stu-id="f6ec9-164">Emailing a channel</span></span>

 <span data-ttu-id="f6ec9-165">如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-165">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="f6ec9-166">當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-166">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="f6ec9-167">以下是一些傳送電子郵件到頻道時適用的限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-167">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="f6ec9-168">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-168">Feature</span></span>  | <span data-ttu-id="f6ec9-169">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-169">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f6ec9-170">郵件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-170">Message size<sup>1<sup></span></span> | <span data-ttu-id="f6ec9-171">24 KB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-171">24 KB</span></span> |
|<span data-ttu-id="f6ec9-172">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-172">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="f6ec9-173">20</span><span class="sxs-lookup"><span data-stu-id="f6ec9-173">20</span></span>     |
|<span data-ttu-id="f6ec9-174">每個檔案附件的大小</span><span class="sxs-lookup"><span data-stu-id="f6ec9-174">Size of each file attachment</span></span> | <span data-ttu-id="f6ec9-175">小於 10 MB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-175">Less than 10 MB</span></span> |
|<span data-ttu-id="f6ec9-176">內嵌影像的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-176">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="f6ec9-177">50</span><span class="sxs-lookup"><span data-stu-id="f6ec9-177">50</span></span>   |

<span data-ttu-id="f6ec9-178"><sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-178"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="f6ec9-179"><sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-179"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="f6ec9-180">如需詳細資訊，請參閱 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-180">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="f6ec9-181">所有 Microsoft 365 和 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-181">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="f6ec9-182">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="f6ec9-182">Channel names</span></span>

<span data-ttu-id="f6ec9-183">頻道名稱不能包含下列字元或字詞。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-183">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="f6ec9-184">字元</span><span class="sxs-lookup"><span data-stu-id="f6ec9-184">Characters</span></span>     | <span data-ttu-id="f6ec9-185">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="f6ec9-185">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="f6ec9-186">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="f6ec9-186">&#124; ' " , .</span></span>        |
|<span data-ttu-id="f6ec9-187">這些範圍內的字元</span><span class="sxs-lookup"><span data-stu-id="f6ec9-187">Characters in these ranges</span></span>    | <span data-ttu-id="f6ec9-188">0 至 1F</span><span class="sxs-lookup"><span data-stu-id="f6ec9-188">0 to 1F</span></span><br><span data-ttu-id="f6ec9-189">80 至 9F</span><span class="sxs-lookup"><span data-stu-id="f6ec9-189">80 to 9F</span></span>        |
|<span data-ttu-id="f6ec9-190">字詞</span><span class="sxs-lookup"><span data-stu-id="f6ec9-190">Words</span></span>     | <span data-ttu-id="f6ec9-191">forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="f6ec9-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="f6ec9-192">頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-192">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="f6ec9-193">會議和通話</span><span class="sxs-lookup"><span data-stu-id="f6ec9-193">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6ec9-194">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="f6ec9-194">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="f6ec9-195">**為了支援我們的客戶，直到 2021 年 1 月 1 日，針對 Teams、Stream 和 Yammer 中舉辦的即時活動，我們將會延長臨時的限制增加，包括**：</span><span class="sxs-lookup"><span data-stu-id="f6ec9-195">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="f6ec9-196">每個活動最多可有 20,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="f6ec9-196">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="f6ec9-197">每個 Teams 租用戶最多可同時舉行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="f6ec9-197">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="f6ec9-198">每個廣播最多 16 個小時</span><span class="sxs-lookup"><span data-stu-id="f6ec9-198">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="f6ec9-199">此外，可透過 Microsoft 即時活動輔助計畫來規劃最多 100,000 位出席者參與的現場活動。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-199">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="f6ec9-200">[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-200">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="f6ec9-201">**2021 年 1 月 1 日之後，需要這些限制增加的客戶必須購買 [[進階通訊附加元件]](teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="f6ec9-201">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="f6ec9-202">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-202">Feature</span></span>     | <span data-ttu-id="f6ec9-203">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-203">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="f6ec9-204">一場會議中的人數 (可以交談和通話)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-204">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="f6ec9-205">300</span><span class="sxs-lookup"><span data-stu-id="f6ec9-205">300</span></span> |
|<span data-ttu-id="f6ec9-206">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-206">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="f6ec9-207">20</span><span class="sxs-lookup"><span data-stu-id="f6ec9-207">20</span></span> |
|<span data-ttu-id="f6ec9-208">PowerPoint 檔案大小的最大值</span><span class="sxs-lookup"><span data-stu-id="f6ec9-208">Max PowerPoint File Size</span></span> | <span data-ttu-id="f6ec9-209">2 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-209">2GB</span></span>|
|<span data-ttu-id="f6ec9-210">Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載</span><span class="sxs-lookup"><span data-stu-id="f6ec9-210">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="f6ec9-211">20 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-211">20 days</span></span> |

>[!Note]
> <span data-ttu-id="f6ec9-212">從使用 Microsoft Stream 到變更為使用[商務用 OneDrive 和 OneDrive 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-212">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="f6ec9-213">剛開始時，您可以加入這項體驗，在 11 月如果您想要繼續使用 Stream，則必須退出體驗，而在 2021 初期的某時間，我們將要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行新的會議錄製。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-213">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="f6ec9-214">會議到期</span><span class="sxs-lookup"><span data-stu-id="f6ec9-214">Meeting expiration</span></span>

|<span data-ttu-id="f6ec9-215">會議類型</span><span class="sxs-lookup"><span data-stu-id="f6ec9-215">Meeting type</span></span>  |<span data-ttu-id="f6ec9-216">會議將在這些時間後到期</span><span class="sxs-lookup"><span data-stu-id="f6ec9-216">Meeting expires after this much time</span></span>  |<span data-ttu-id="f6ec9-217">每次您開始或更新會議，到期時間會延長這麼多時間</span><span class="sxs-lookup"><span data-stu-id="f6ec9-217">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f6ec9-218">立即開會</span><span class="sxs-lookup"><span data-stu-id="f6ec9-218">Meet now</span></span>     |<span data-ttu-id="f6ec9-219">開始時間 + 8 小時</span><span class="sxs-lookup"><span data-stu-id="f6ec9-219">Start time + 8 hours</span></span>         |<span data-ttu-id="f6ec9-220">不適用</span><span class="sxs-lookup"><span data-stu-id="f6ec9-220">N/A</span></span>         |
|<span data-ttu-id="f6ec9-221">一般 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-221">Regular with no end time</span></span>     |<span data-ttu-id="f6ec9-222">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-222">Start time + 60 days</span></span>         | <span data-ttu-id="f6ec9-223">60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-223">60 days</span></span>        |
|<span data-ttu-id="f6ec9-224">一般 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-224">Regular with end time</span></span>     |<span data-ttu-id="f6ec9-225">結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-225">End time + 60 days</span></span>         |<span data-ttu-id="f6ec9-226">60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-226">60 days</span></span>         |
|<span data-ttu-id="f6ec9-227">週期性 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-227">Recurring with no end time</span></span>     |<span data-ttu-id="f6ec9-228">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-228">Start time + 60 days</span></span>         |<span data-ttu-id="f6ec9-229">60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-229">60 days</span></span>         |
|<span data-ttu-id="f6ec9-230">週期性 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-230">Recurring with end time</span></span>     |<span data-ttu-id="f6ec9-231">最後發生的結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-231">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="f6ec9-232">60 天</span><span class="sxs-lookup"><span data-stu-id="f6ec9-232">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="f6ec9-233">Microsoft Teams s會議的時間限制為 24 小時。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-233">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="f6ec9-234">Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="f6ec9-234">Teams live events</span></span>

|<span data-ttu-id="f6ec9-235">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-235">Feature</span></span>     | <span data-ttu-id="f6ec9-236">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-236">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="f6ec9-237">對象數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-237">Audience size</span></span> | <span data-ttu-id="f6ec9-238">10,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="f6ec9-238">10,000 attendees</span></span> |
|<span data-ttu-id="f6ec9-239">活動持續時間</span><span class="sxs-lookup"><span data-stu-id="f6ec9-239">Duration of event</span></span> | <span data-ttu-id="f6ec9-240">4 小時</span><span class="sxs-lookup"><span data-stu-id="f6ec9-240">4 hours</span></span> |
|<span data-ttu-id="f6ec9-241">一個 Microsoft 365 或 Office 365 組織中執行的並行即時活動 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f6ec9-241">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="f6ec9-242">15</span><span class="sxs-lookup"><span data-stu-id="f6ec9-242">15</span></span> |

<span data-ttu-id="f6ec9-243"><sup>1</sup> 您可根據自己的需求排定許多即時活動，但一次只能執行 15 個。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-243"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="f6ec9-244">製作人一加入即時活動，就表示該活動執行中。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-244">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="f6ec9-245">嘗試加入第 16 個即時活動的製作人會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-245">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="f6ec9-246">如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請參閱 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast) (英文)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-246">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6ec9-247">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="f6ec9-247">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="f6ec9-248">為了協助客戶滿足迅速變化的通訊需求，我們將針對於 Teams、Stream 和 Yammer 中進行的即時活動暫時提高預設限制，直到 2021 年 1 月 1 日止。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-248">To help customers meet rapidly changing communication needs, we will temporarily raise default limits until January 1, 2021, for live events hosted in Teams, Stream, and Yammer.</span></span>
>
> - <span data-ttu-id="f6ec9-249">出席者限制：活動最多可支援 20,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="f6ec9-249">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="f6ec9-250">同時活動：不同租用戶可以同時進行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="f6ec9-250">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="f6ec9-251">活動持續時間：每個廣播的活動長度已增加為 16 小時</span><span class="sxs-lookup"><span data-stu-id="f6ec9-251">Event duration: event length has been increased to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="f6ec9-252">此外，可透過 Microsoft 即時活動輔助計畫來規劃最多 100,000 位出席者參與的即時活動。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-252">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="f6ec9-253">[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-253">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="f6ec9-254">**2021 年 1 月 1 日之後，需要這些限制增加的客戶必須購買 [[進階通訊附加元件]](teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="f6ec9-254">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="f6ec9-255">在 Outlook 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="f6ec9-255">Presence in Outlook</span></span>

<span data-ttu-id="f6ec9-256">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-256">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="f6ec9-257">若要深入瞭解 Teams 中的目前狀態，請參閱 [Teams 中的使用者目前狀態](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-257">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="f6ec9-258">儲存空間</span><span class="sxs-lookup"><span data-stu-id="f6ec9-258">Storage</span></span>

<span data-ttu-id="f6ec9-259">Microsoft Teams 中的每個小組在 SharePoint Online 中都有一個小組網站，小組中的每個頻道在預設小組網站的文件庫中都有一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-259">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="f6ec9-260">在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-260">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f6ec9-261">每個[私人頻道](https://docs.microsoft.com/microsoftteams/private-channels) 都有自己的 SharePoint 網站集合。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-261">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="f6ec9-262">如果您未在您的租用戶中啟用 SharePoint Online，Microsoft Teams 使用者一律無法在小組中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-262">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="f6ec9-263">在私人聊天中的使用者也無法共用檔案，因為該功能需要有 OneDrive for Business (綁定至 SharePoint 授權)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-263">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="f6ec9-264">透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則 </span><span class="sxs-lookup"><span data-stu-id="f6ec9-264">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="f6ec9-265">(如需詳細資訊，請參閱 [ Sharepoint 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-265">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="f6ec9-266">由於 Teams 是在 SharePoint Online 後端執行檔案共用，因此 SharePoint 的限制會套用到小組內的 [檔案] 區段。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-266">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="f6ec9-267">以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-267">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="f6ec9-268">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-268">Feature</span></span>                 |<span data-ttu-id="f6ec9-269">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="f6ec9-269">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="f6ec9-270">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="f6ec9-270">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="f6ec9-271">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="f6ec9-271">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="f6ec9-272">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="f6ec9-272">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="f6ec9-273">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="f6ec9-273">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="f6ec9-274">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="f6ec9-274">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="f6ec9-275">儲存空間</span><span class="sxs-lookup"><span data-stu-id="f6ec9-275">Storage</span></span>                 |<span data-ttu-id="f6ec9-276">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-276">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f6ec9-277">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-277">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f6ec9-278">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-278">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="f6ec9-279">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-279">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="f6ec9-280">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-280">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f6ec9-281">每個組織 1 TB </span><span class="sxs-lookup"><span data-stu-id="f6ec9-281">1 TB per organization</span></span>           |
|<span data-ttu-id="f6ec9-282">Teams 檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="f6ec9-282">Storage for Teams Files</span></span> |<span data-ttu-id="f6ec9-283">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-283">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f6ec9-284">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-284">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f6ec9-285">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-285">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f6ec9-286">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-286">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f6ec9-287">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-287">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f6ec9-288">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-288">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="f6ec9-289">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-289">File upload limit  (per file)</span></span>    |<span data-ttu-id="f6ec9-290">100 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-290">100 GB</span></span>    |<span data-ttu-id="f6ec9-291">100 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-291">100 GB</span></span>    |<span data-ttu-id="f6ec9-292">100 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-292">100 GB</span></span>    |<span data-ttu-id="f6ec9-293">100 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-293">100 GB</span></span>    |<span data-ttu-id="f6ec9-294">100 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-294">100 GB</span></span>    |<span data-ttu-id="f6ec9-295">100 GB</span><span class="sxs-lookup"><span data-stu-id="f6ec9-295">100 GB</span></span>    |

<span data-ttu-id="f6ec9-296">頻道受資料夾所支援，而資料夾位於針對小組建立的 SharePoint Online 網站集合中，因此頻道內的檔案索引標籤會共用所屬小組的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-296">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="f6ec9-297">如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-297">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="f6ec9-298">課程小組</span><span class="sxs-lookup"><span data-stu-id="f6ec9-298">Class teams</span></span>

<span data-ttu-id="f6ec9-299">Microsoft Teams 教育版提供專為獨特教育案例 (例如教室教學) 所設計的範本。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-299">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="f6ec9-300">如需有關小組類型 (包括課程小組) 的詳細資訊，請參閱[在 Microsoft Teams 中選擇要共同作業的小組類型](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-300">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="f6ec9-301">課程小組是一個範本類型，其中包含其他應用程式，且具有的限制與小組成員數目不同。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-301">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="f6ec9-302">使用課程小組需要 [Office 365 教育版授權](https://www.microsoft.com/education/products/office)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-302">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="f6ec9-303">下表列出課程小組的限制：</span><span class="sxs-lookup"><span data-stu-id="f6ec9-303">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="f6ec9-304">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-304">Feature</span></span>  |<span data-ttu-id="f6ec9-305">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-305">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f6ec9-306">一個小組中的成員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-306">Number of members in a team</span></span>    | <span data-ttu-id="f6ec9-307">請參閱本文的 [Teams 和頻道](#teams-and-channels)一節</span><span class="sxs-lookup"><span data-stu-id="f6ec9-307">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="f6ec9-308">課程小組中要使用作業的成員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-308">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="f6ec9-309">200</span><span class="sxs-lookup"><span data-stu-id="f6ec9-309">200</span></span>        |
|<span data-ttu-id="f6ec9-310">課程小組中要使用 OneNote 課程筆記本的成員數目</span><span class="sxs-lookup"><span data-stu-id="f6ec9-310">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="f6ec9-311">200</span><span class="sxs-lookup"><span data-stu-id="f6ec9-311">200</span></span>         |

<span data-ttu-id="f6ec9-312">課程小組可支援超過 200 個成員。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-312">A class team can support more than 200 members.</span></span> <span data-ttu-id="f6ec9-313">不過，如果您計劃在您的小組內使用「作業」應用程式或「課程筆記本」應用程式，則您必須將成員數目保持在以上的上限之下。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-313">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="f6ec9-314">標記</span><span class="sxs-lookup"><span data-stu-id="f6ec9-314">Tags</span></span>

|<span data-ttu-id="f6ec9-315">功能</span><span class="sxs-lookup"><span data-stu-id="f6ec9-315">Feature</span></span>  |<span data-ttu-id="f6ec9-316">最大限制</span><span class="sxs-lookup"><span data-stu-id="f6ec9-316">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f6ec9-317">每個小組的標記數量</span><span class="sxs-lookup"><span data-stu-id="f6ec9-317">Number of tags per team</span></span>    | <span data-ttu-id="f6ec9-318">100</span><span class="sxs-lookup"><span data-stu-id="f6ec9-318">100</span></span>        |
|<span data-ttu-id="f6ec9-319">每個小組的建議預設標記數量</span><span class="sxs-lookup"><span data-stu-id="f6ec9-319">Number of suggested default tags per team</span></span>    | <span data-ttu-id="f6ec9-320">25</span><span class="sxs-lookup"><span data-stu-id="f6ec9-320">25</span></span>        |
|<span data-ttu-id="f6ec9-321">指派給標記的小組成員人數</span><span class="sxs-lookup"><span data-stu-id="f6ec9-321">Number of team members assign to a tag</span></span>    |<span data-ttu-id="f6ec9-322">100</span><span class="sxs-lookup"><span data-stu-id="f6ec9-322">100</span></span>         |
|<span data-ttu-id="f6ec9-323">指派給使用者的標記數量</span><span class="sxs-lookup"><span data-stu-id="f6ec9-323">Number of tags assigned to a user</span></span>    |<span data-ttu-id="f6ec9-324">25</span><span class="sxs-lookup"><span data-stu-id="f6ec9-324">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="f6ec9-325">連絡人</span><span class="sxs-lookup"><span data-stu-id="f6ec9-325">Contacts</span></span>

<span data-ttu-id="f6ec9-326">Teams 使用下列連絡人：</span><span class="sxs-lookup"><span data-stu-id="f6ec9-326">Teams uses these contacts:</span></span>

- <span data-ttu-id="f6ec9-327">您組織 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="f6ec9-327">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="f6ec9-328">新增至使用者 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="f6ec9-328">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="f6ec9-329">Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天]\*\*\*\* > [連絡人]\*\*\*\* 或是 [通話]\*\*\*\* > [連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-329">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="f6ec9-330">Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話]\*\*\*\* > [連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-330">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="f6ec9-331">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="f6ec9-331">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="f6ec9-332">作業系統</span><span class="sxs-lookup"><span data-stu-id="f6ec9-332">Operating systems</span></span>

<span data-ttu-id="f6ec9-333">如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ec9-333">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
