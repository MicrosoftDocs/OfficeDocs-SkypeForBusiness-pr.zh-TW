---
title: Microsoft Teams 的限制和規格
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 8730c1522439660652bd164d6628fdf2f78f37cb
ms.sourcegitcommit: 1c2359f10ad5f5ec10dc52508ef4774c04b631ab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44229881"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="bffce-103">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="bffce-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="bffce-104">本文說明一些套用到 Teams 的限制、規格和其他需求。</span><span class="sxs-lookup"><span data-stu-id="bffce-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="bffce-105">團隊和頻道</span><span class="sxs-lookup"><span data-stu-id="bffce-105">Teams and channels</span></span>

|<span data-ttu-id="bffce-106">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-106">Feature</span></span>    | <span data-ttu-id="bffce-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="bffce-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="bffce-108">一位使用者可以建立的團隊數目</span><span class="sxs-lookup"><span data-stu-id="bffce-108">Number of teams a user can create</span></span> | <span data-ttu-id="bffce-109">受限於 250 的物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="bffce-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="bffce-110">一位使用者可以加入成為成員的團隊數目</span><span class="sxs-lookup"><span data-stu-id="bffce-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="bffce-111">1,000</span><span class="sxs-lookup"><span data-stu-id="bffce-111">1,000</span></span>|
|<span data-ttu-id="bffce-112">一個團隊中的成員數目</span><span class="sxs-lookup"><span data-stu-id="bffce-112">Number of members in a team</span></span> | <span data-ttu-id="bffce-113">10,000</span><span class="sxs-lookup"><span data-stu-id="bffce-113">10,000</span></span>       |
|<span data-ttu-id="bffce-114">每個團隊擁有者人數</span><span class="sxs-lookup"><span data-stu-id="bffce-114">Number of owners per team</span></span> | <span data-ttu-id="bffce-115">100</span><span class="sxs-lookup"><span data-stu-id="bffce-115">100</span></span>   |
|<span data-ttu-id="bffce-116">一個租用戶中允許的全組織小組數目</span><span class="sxs-lookup"><span data-stu-id="bffce-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="bffce-117">5</span><span class="sxs-lookup"><span data-stu-id="bffce-117">5</span></span>     |
|<span data-ttu-id="bffce-118">一個[全組織小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="bffce-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="bffce-119">5,000</span><span class="sxs-lookup"><span data-stu-id="bffce-119">5,000</span></span>       |
|<span data-ttu-id="bffce-120">一位全域系統管理員可以建立的團隊數目</span><span class="sxs-lookup"><span data-stu-id="bffce-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="bffce-121">500,000</span><span class="sxs-lookup"><span data-stu-id="bffce-121">500,000</span></span>   |
|<span data-ttu-id="bffce-122">一個 Office 365 組織可以擁有的小組數目</span><span class="sxs-lookup"><span data-stu-id="bffce-122">Number of teams an Office 365 organization can have</span></span>    | <span data-ttu-id="bffce-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="bffce-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="bffce-124">每個團隊的頻道數目</span><span class="sxs-lookup"><span data-stu-id="bffce-124">Number of channels per team</span></span>    | <span data-ttu-id="bffce-125">200 (包含已刪除的頻道)&sup3;</span><span class="sxs-lookup"><span data-stu-id="bffce-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="bffce-126">每個團隊的私人頻道數量</span><span class="sxs-lookup"><span data-stu-id="bffce-126">Number of Private channels per team</span></span>    |<span data-ttu-id="bffce-127">30</span><span class="sxs-lookup"><span data-stu-id="bffce-127">30</span></span>|
|<span data-ttu-id="bffce-128">頻道交談貼文大小</span><span class="sxs-lookup"><span data-stu-id="bffce-128">Channel conversation post size</span></span> | <span data-ttu-id="bffce-129">每篇貼文約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-129">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="bffce-130">&sup1; Azure Active Directory 中的任何目錄物件都會計入此限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-130">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="bffce-131">全域系統管理員不受此限制，使用[應用程式權限](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式也不受此限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-131">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="bffce-132">&sup2; 此限制包含已封存的團隊。</span><span class="sxs-lookup"><span data-stu-id="bffce-132">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="bffce-133">&sup3; 已刪除的頻道可以在 30 天內還原。</span><span class="sxs-lookup"><span data-stu-id="bffce-133">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="bffce-134">在這 30 天內，已刪除的頻道會持續計入每個團隊 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-134">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="bffce-135">30 天後，已刪除的頻道及其內容會永久刪除，該頻道不再計入每個團隊 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-135">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="bffce-136"><sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。</span><span class="sxs-lookup"><span data-stu-id="bffce-136"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="bffce-137">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="bffce-137">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="bffce-138">聊天</span><span class="sxs-lookup"><span data-stu-id="bffce-138">Chat</span></span>

<span data-ttu-id="bffce-139">參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。</span><span class="sxs-lookup"><span data-stu-id="bffce-139">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="bffce-140">這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。</span><span class="sxs-lookup"><span data-stu-id="bffce-140">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="bffce-141">如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。</span><span class="sxs-lookup"><span data-stu-id="bffce-141">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="bffce-142">例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。</span><span class="sxs-lookup"><span data-stu-id="bffce-142">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="bffce-143">然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留 </span><span class="sxs-lookup"><span data-stu-id="bffce-143">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="bffce-144">(如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="bffce-144">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="bffce-145">Teams 的聊天是在 Microsoft Exchange 後端執行，因此 Exchange 的傳訊限制會套用到 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="bffce-145">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="bffce-146">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-146">Feature</span></span>  | <span data-ttu-id="bffce-147">最大限制</span><span class="sxs-lookup"><span data-stu-id="bffce-147">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="bffce-148">一個私人聊天中的人員數目<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-148">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="bffce-149">100</span><span class="sxs-lookup"><span data-stu-id="bffce-149">100</span></span>    |
|<span data-ttu-id="bffce-150">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="bffce-150">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="bffce-151">20</span><span class="sxs-lookup"><span data-stu-id="bffce-151">20</span></span> |
|<span data-ttu-id="bffce-152">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-152">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="bffce-153">10</span><span class="sxs-lookup"><span data-stu-id="bffce-153">10</span></span>     |
|<span data-ttu-id="bffce-154">聊天大小</span><span class="sxs-lookup"><span data-stu-id="bffce-154">Chat size</span></span> | <span data-ttu-id="bffce-155">每篇貼文約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-155">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="bffce-156"><sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息、輸入指示器、視訊和音訊通話、共用、讀取回條。</span><span class="sxs-lookup"><span data-stu-id="bffce-156"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="bffce-157"><sup>2</sup> 如果附件數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bffce-157"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="bffce-158"><sup>3</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及和回應。</span><span class="sxs-lookup"><span data-stu-id="bffce-158"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="bffce-159">傳送電子郵件到頻道</span><span class="sxs-lookup"><span data-stu-id="bffce-159">Emailing a channel</span></span>

 <span data-ttu-id="bffce-160">如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bffce-160">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="bffce-161">當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。</span><span class="sxs-lookup"><span data-stu-id="bffce-161">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="bffce-162">以下是一些傳送電子郵件到頻道時適用的限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-162">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="bffce-163">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-163">Feature</span></span>  | <span data-ttu-id="bffce-164">最大限制</span><span class="sxs-lookup"><span data-stu-id="bffce-164">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="bffce-165">郵件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="bffce-165">Message size<sup>1<sup></span></span> | <span data-ttu-id="bffce-166">24 KB</span><span class="sxs-lookup"><span data-stu-id="bffce-166">24 KB</span></span> |
|<span data-ttu-id="bffce-167">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-167">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="bffce-168">20</span><span class="sxs-lookup"><span data-stu-id="bffce-168">20</span></span>     |
|<span data-ttu-id="bffce-169">每個檔案附件的大小</span><span class="sxs-lookup"><span data-stu-id="bffce-169">Size of each file attachment</span></span> | <span data-ttu-id="bffce-170">小於 10 MB</span><span class="sxs-lookup"><span data-stu-id="bffce-170">Less than 10 MB</span></span> |
|<span data-ttu-id="bffce-171">內嵌影像的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-171">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="bffce-172">50</span><span class="sxs-lookup"><span data-stu-id="bffce-172">50</span></span>   |

<span data-ttu-id="bffce-173"><sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bffce-173"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="bffce-174"><sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bffce-174"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="bffce-175">如需詳細資訊，請參閱 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="bffce-175">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="bffce-176">所有 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。</span><span class="sxs-lookup"><span data-stu-id="bffce-176">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="bffce-177">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="bffce-177">Channel names</span></span>

<span data-ttu-id="bffce-178">頻道名稱不能包含下列字元或字詞。</span><span class="sxs-lookup"><span data-stu-id="bffce-178">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="bffce-179">字元</span><span class="sxs-lookup"><span data-stu-id="bffce-179">Characters</span></span>     | <span data-ttu-id="bffce-180">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="bffce-180">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="bffce-181">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="bffce-181">&#124; ' " ..</span></span>        |
|<span data-ttu-id="bffce-182">這些範圍內的字元</span><span class="sxs-lookup"><span data-stu-id="bffce-182">Characters in these ranges</span></span>    | <span data-ttu-id="bffce-183">0 至 1F</span><span class="sxs-lookup"><span data-stu-id="bffce-183">0 to 1F</span></span><br><span data-ttu-id="bffce-184">80 至 9F</span><span class="sxs-lookup"><span data-stu-id="bffce-184">80 to 9F</span></span>        |
|<span data-ttu-id="bffce-185">字詞</span><span class="sxs-lookup"><span data-stu-id="bffce-185">Words</span></span>     | <span data-ttu-id="bffce-186">forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="bffce-186">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="bffce-187">頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。</span><span class="sxs-lookup"><span data-stu-id="bffce-187">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="bffce-188">會議和通話</span><span class="sxs-lookup"><span data-stu-id="bffce-188">Meetings and calls</span></span>

|<span data-ttu-id="bffce-189">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-189">Feature</span></span>     | <span data-ttu-id="bffce-190">最大限制</span><span class="sxs-lookup"><span data-stu-id="bffce-190">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="bffce-191">一場會議中的人數 (可以交談和通話)</span><span class="sxs-lookup"><span data-stu-id="bffce-191">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="bffce-192">250</span><span class="sxs-lookup"><span data-stu-id="bffce-192">250</span></span>    |
|<span data-ttu-id="bffce-193">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="bffce-193">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="bffce-194">20</span><span class="sxs-lookup"><span data-stu-id="bffce-194">20</span></span> |
|<span data-ttu-id="bffce-195">PowerPoint 檔案大小的最大值</span><span class="sxs-lookup"><span data-stu-id="bffce-195">Max PowerPoint File Size</span></span> | <span data-ttu-id="bffce-196">2 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-196">2GB</span></span>|
|<span data-ttu-id="bffce-197">Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載</span><span class="sxs-lookup"><span data-stu-id="bffce-197">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="bffce-198">20 天</span><span class="sxs-lookup"><span data-stu-id="bffce-198">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="bffce-199">會議到期</span><span class="sxs-lookup"><span data-stu-id="bffce-199">Meeting expiration</span></span>

|<span data-ttu-id="bffce-200">會議類型</span><span class="sxs-lookup"><span data-stu-id="bffce-200">Meeting type</span></span>  |<span data-ttu-id="bffce-201">會議將在這些時間後到期</span><span class="sxs-lookup"><span data-stu-id="bffce-201">Meeting expires after this much time</span></span>  |<span data-ttu-id="bffce-202">每次您開始或更新會議，到期時間會延長這麼多時間</span><span class="sxs-lookup"><span data-stu-id="bffce-202">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bffce-203">立即開會</span><span class="sxs-lookup"><span data-stu-id="bffce-203">Meet now</span></span>     |<span data-ttu-id="bffce-204">開始時間 + 8 小時</span><span class="sxs-lookup"><span data-stu-id="bffce-204">Start time + 8 hours</span></span>         |<span data-ttu-id="bffce-205">不適用</span><span class="sxs-lookup"><span data-stu-id="bffce-205">N/A</span></span>         |
|<span data-ttu-id="bffce-206">一般 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="bffce-206">Regular with no end time</span></span>     |<span data-ttu-id="bffce-207">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-207">Start time + 60 days</span></span>         | <span data-ttu-id="bffce-208">60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-208">60 days</span></span>        |
|<span data-ttu-id="bffce-209">一般 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="bffce-209">Regular with end time</span></span>     |<span data-ttu-id="bffce-210">結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-210">End time + 60 days</span></span>         |<span data-ttu-id="bffce-211">60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-211">60 days</span></span>         |
|<span data-ttu-id="bffce-212">週期性 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="bffce-212">Recurring with no end time</span></span>     |<span data-ttu-id="bffce-213">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-213">Start time + 60 days</span></span>         |<span data-ttu-id="bffce-214">60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-214">60 days</span></span>         |
|<span data-ttu-id="bffce-215">週期性 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="bffce-215">Recurring with end time</span></span>     |<span data-ttu-id="bffce-216">最後發生的結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-216">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="bffce-217">60 天</span><span class="sxs-lookup"><span data-stu-id="bffce-217">60 days</span></span>         |

## <a name="teams-live-events"></a><span data-ttu-id="bffce-218">Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="bffce-218">Teams live events</span></span>

|<span data-ttu-id="bffce-219">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-219">Feature</span></span>     | <span data-ttu-id="bffce-220">最大限制</span><span class="sxs-lookup"><span data-stu-id="bffce-220">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="bffce-221">對象數目</span><span class="sxs-lookup"><span data-stu-id="bffce-221">Audience size</span></span> | <span data-ttu-id="bffce-222">10,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="bffce-222">10,000 attendees</span></span> |
|<span data-ttu-id="bffce-223">活動持續時間</span><span class="sxs-lookup"><span data-stu-id="bffce-223">Duration of event</span></span> | <span data-ttu-id="bffce-224">4 小時</span><span class="sxs-lookup"><span data-stu-id="bffce-224">4 hours</span></span> |
|<span data-ttu-id="bffce-225">一個 Office 365 組織中執行的並行即時活動 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bffce-225">Concurrent live events running in an Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="bffce-226">15</span><span class="sxs-lookup"><span data-stu-id="bffce-226">15</span></span> |

<span data-ttu-id="bffce-227"><sup>1</sup> 您可根據自己的需求排定許多即時活動，但一次只能執行 15 個。</span><span class="sxs-lookup"><span data-stu-id="bffce-227"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="bffce-228">製作人一加入即時活動，就表示該活動執行中。</span><span class="sxs-lookup"><span data-stu-id="bffce-228">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="bffce-229">嘗試加入第 16 個即時活動的製作人會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="bffce-229">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="bffce-230">如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請參閱 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast) (英文)。</span><span class="sxs-lookup"><span data-stu-id="bffce-230">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bffce-231">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="bffce-231">**Microsoft 365 live event limit increases**</span></span>
> 
> <span data-ttu-id="bffce-232">為了協助客戶滿足迅速變化的通訊需求，Microsoft 365 即時活動將針對於 Teams 中進行的即時活動暫時提高預設限制，直到 2020 年 7 月 1 日止。</span><span class="sxs-lookup"><span data-stu-id="bffce-232">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until July 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="bffce-233">以下限制將於 2020 年 4 月底推出：</span><span class="sxs-lookup"><span data-stu-id="bffce-233">The following increases are being rolled out in late April 2020:</span></span>
> - <span data-ttu-id="bffce-234">出席者限制：活動最多可支援 20,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="bffce-234">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="bffce-235">同時活動：不同租用戶可以同時進行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="bffce-235">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="bffce-236">活動持續時間：每個廣播的活動長度已增加為 16 小時</span><span class="sxs-lookup"><span data-stu-id="bffce-236">Event duration: event length has been increased to 16 hours per broadcast</span></span>



## <a name="presence-in-outlook"></a><span data-ttu-id="bffce-237">在 Outlook 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="bffce-237">Presence in Outlook</span></span>

<span data-ttu-id="bffce-238">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="bffce-238">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="bffce-239">若要深入瞭解 Teams 中的目前狀態，請參閱 [Teams 中的使用者目前狀態](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="bffce-239">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="bffce-240">儲存空間</span><span class="sxs-lookup"><span data-stu-id="bffce-240">Storage</span></span>

<span data-ttu-id="bffce-241">Microsoft Teams 中的每個團隊在 SharePoint Online 中都有一個團隊網站，團隊中的每個頻道在預設團隊網站的文件庫中都有一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="bffce-241">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="bffce-242">在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="bffce-242">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="bffce-243">如果您未在您的租用戶中啟用 SharePoint Online，Microsoft Teams 使用者一律無法在團隊中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="bffce-243">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="bffce-244">在私人聊天中的使用者也無法共用檔案，因為該功能需要有 OneDrive for Business (綁定至 SharePoint 授權)。</span><span class="sxs-lookup"><span data-stu-id="bffce-244">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="bffce-245">透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則 </span><span class="sxs-lookup"><span data-stu-id="bffce-245">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="bffce-246">(如需詳細資訊，請參閱 [ Sharepoint 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="bffce-246">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="bffce-247">由於 Teams 是在 SharePoint Online 後端執行檔案共用，因此 SharePoint 的限制會套用到團隊內的 [檔案] 區段。</span><span class="sxs-lookup"><span data-stu-id="bffce-247">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="bffce-248">以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-248">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="bffce-249">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-249">Feature</span></span>                 |<span data-ttu-id="bffce-250">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="bffce-250">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="bffce-251">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="bffce-251">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="bffce-252">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="bffce-252">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="bffce-253">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="bffce-253">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="bffce-254">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="bffce-254">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="bffce-255">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="bffce-255">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="bffce-256">儲存空間</span><span class="sxs-lookup"><span data-stu-id="bffce-256">Storage</span></span>                 |<span data-ttu-id="bffce-257">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-257">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="bffce-258">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-258">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="bffce-259">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-259">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="bffce-260">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-260">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="bffce-261">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-261">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="bffce-262">每個組織 1 TB </span><span class="sxs-lookup"><span data-stu-id="bffce-262">1 TB per organization</span></span>           |
|<span data-ttu-id="bffce-263">Teams 檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="bffce-263">Storage for Teams Files</span></span> |<span data-ttu-id="bffce-264">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="bffce-264">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bffce-265">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="bffce-265">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bffce-266">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="bffce-266">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bffce-267">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="bffce-267">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bffce-268">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="bffce-268">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bffce-269">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="bffce-269">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="bffce-270">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="bffce-270">File upload limit  (per file)</span></span>    |<span data-ttu-id="bffce-271">15 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-271">15 GB</span></span>    |<span data-ttu-id="bffce-272">15 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-272">15 GB</span></span>    |<span data-ttu-id="bffce-273">15 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-273">15 GB</span></span>    |<span data-ttu-id="bffce-274">15 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-274">15 GB</span></span>    |<span data-ttu-id="bffce-275">15 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-275">15 GB</span></span>    |<span data-ttu-id="bffce-276">15 GB</span><span class="sxs-lookup"><span data-stu-id="bffce-276">15 GB</span></span>    |

<span data-ttu-id="bffce-277">頻道受資料夾所支援，而資料夾位於針對團隊建立的 SharePoint Online 網站集合中，因此頻道內的檔案索引標籤會共用所屬團隊的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="bffce-277">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="bffce-278">如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="bffce-278">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="bffce-279">標記</span><span class="sxs-lookup"><span data-stu-id="bffce-279">Tags</span></span>

|<span data-ttu-id="bffce-280">功能</span><span class="sxs-lookup"><span data-stu-id="bffce-280">Feature</span></span>  |<span data-ttu-id="bffce-281">最大限制</span><span class="sxs-lookup"><span data-stu-id="bffce-281">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="bffce-282">每個小組的標記數量</span><span class="sxs-lookup"><span data-stu-id="bffce-282">Number of tags per team</span></span>    | <span data-ttu-id="bffce-283">100</span><span class="sxs-lookup"><span data-stu-id="bffce-283">100</span></span>        |
|<span data-ttu-id="bffce-284">每個小組的建議預設標記數量</span><span class="sxs-lookup"><span data-stu-id="bffce-284">Number of suggested default tags per team</span></span>    | <span data-ttu-id="bffce-285">25</span><span class="sxs-lookup"><span data-stu-id="bffce-285">25</span></span>        |
|<span data-ttu-id="bffce-286">指派給標記的小組成員人數</span><span class="sxs-lookup"><span data-stu-id="bffce-286">Number of team members assign to a tag</span></span>    |<span data-ttu-id="bffce-287">100</span><span class="sxs-lookup"><span data-stu-id="bffce-287">100</span></span>         |
|<span data-ttu-id="bffce-288">指派給使用者的標記數量</span><span class="sxs-lookup"><span data-stu-id="bffce-288">Number of tags assigned to a user</span></span>    |<span data-ttu-id="bffce-289">25</span><span class="sxs-lookup"><span data-stu-id="bffce-289">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="bffce-290">連絡人</span><span class="sxs-lookup"><span data-stu-id="bffce-290">Contacts</span></span>

<span data-ttu-id="bffce-291">Teams 使用下列連絡人：</span><span class="sxs-lookup"><span data-stu-id="bffce-291">Teams uses these contacts:</span></span>

- <span data-ttu-id="bffce-292">您組織 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="bffce-292">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="bffce-293">新增至使用者 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="bffce-293">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="bffce-294">Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天]\*\*\*\* > [連絡人]\*\*\*\* 或是 [通話]\*\*\*\* > [連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bffce-294">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="bffce-295">Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話]\*\*\*\* > [連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bffce-295">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="bffce-296">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="bffce-296">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="bffce-297">作業系統</span><span class="sxs-lookup"><span data-stu-id="bffce-297">Operating systems</span></span>

<span data-ttu-id="bffce-298">如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="bffce-298">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
