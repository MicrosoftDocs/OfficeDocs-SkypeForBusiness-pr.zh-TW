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
ms.openlocfilehash: 28a77271c66dc473dfb774db2c02ca80bc842587
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2020
ms.locfileid: "43950968"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="9c83e-103">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="9c83e-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="9c83e-104">本文說明一些套用到 Teams 的限制、規格和其他需求。</span><span class="sxs-lookup"><span data-stu-id="9c83e-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="9c83e-105">團隊和頻道</span><span class="sxs-lookup"><span data-stu-id="9c83e-105">Teams and channels</span></span>

|<span data-ttu-id="9c83e-106">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-106">Feature</span></span>    | <span data-ttu-id="9c83e-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="9c83e-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="9c83e-108">一位使用者可以建立的團隊數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-108">Number of teams a user can create</span></span> | <span data-ttu-id="9c83e-109">受限於 250 的物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="9c83e-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="9c83e-110">一位使用者可以加入成為成員的團隊數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="9c83e-111">1,000</span><span class="sxs-lookup"><span data-stu-id="9c83e-111">1,000</span></span>|
|<span data-ttu-id="9c83e-112">一個團隊中的成員數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-112">Number of members in a team</span></span> | <span data-ttu-id="9c83e-113">5,000</span><span class="sxs-lookup"><span data-stu-id="9c83e-113">5,000</span></span>       |
|<span data-ttu-id="9c83e-114">每個團隊擁有者人數</span><span class="sxs-lookup"><span data-stu-id="9c83e-114">Number of owners per team</span></span> | <span data-ttu-id="9c83e-115">100</span><span class="sxs-lookup"><span data-stu-id="9c83e-115">100</span></span>   |
|<span data-ttu-id="9c83e-116">一個租用戶中允許的全組織小組數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="9c83e-117">5</span><span class="sxs-lookup"><span data-stu-id="9c83e-117">5</span></span>     |
|<span data-ttu-id="9c83e-118">一個[全組織小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="9c83e-119">5,000</span><span class="sxs-lookup"><span data-stu-id="9c83e-119">5,000</span></span>       |
|<span data-ttu-id="9c83e-120">一位全域系統管理員可以建立的團隊數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="9c83e-121">500,000</span><span class="sxs-lookup"><span data-stu-id="9c83e-121">500,000</span></span>   |
|<span data-ttu-id="9c83e-122">一個 Office 365 組織可以擁有的小組數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-122">Number of teams an Office 365 organization can have</span></span>    | <span data-ttu-id="9c83e-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="9c83e-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="9c83e-124">每個團隊的頻道數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-124">Number of channels per team</span></span>    | <span data-ttu-id="9c83e-125">200 (包含已刪除的頻道)&sup3;</span><span class="sxs-lookup"><span data-stu-id="9c83e-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="9c83e-126">每個團隊的私人頻道數量</span><span class="sxs-lookup"><span data-stu-id="9c83e-126">Number of Private channels per team</span></span>    |<span data-ttu-id="9c83e-127">30</span><span class="sxs-lookup"><span data-stu-id="9c83e-127">30</span></span>|
|<span data-ttu-id="9c83e-128">頻道交談貼文大小</span><span class="sxs-lookup"><span data-stu-id="9c83e-128">Channel conversation post size</span></span> | <span data-ttu-id="9c83e-129">每篇貼文約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-129">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="9c83e-130">&sup1; Azure Active Directory 中的任何目錄物件都會計入此限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-130">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="9c83e-131">全域系統管理員不受此限制，使用[應用程式權限](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式也不受此限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-131">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="9c83e-132">&sup2; 此限制包含已封存的團隊。</span><span class="sxs-lookup"><span data-stu-id="9c83e-132">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="9c83e-133">&sup3; 已刪除的頻道可以在 30 天內還原。</span><span class="sxs-lookup"><span data-stu-id="9c83e-133">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="9c83e-134">在這 30 天內，已刪除的頻道會持續計入每個團隊 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-134">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="9c83e-135">30 天後，已刪除的頻道及其內容會永久刪除，該頻道不再計入每個團隊 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-135">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="9c83e-136"><sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。</span><span class="sxs-lookup"><span data-stu-id="9c83e-136"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="9c83e-137">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="9c83e-137">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="9c83e-138">聊天</span><span class="sxs-lookup"><span data-stu-id="9c83e-138">Chat</span></span>

<span data-ttu-id="9c83e-139">參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。</span><span class="sxs-lookup"><span data-stu-id="9c83e-139">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="9c83e-140">這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。</span><span class="sxs-lookup"><span data-stu-id="9c83e-140">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="9c83e-141">如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。</span><span class="sxs-lookup"><span data-stu-id="9c83e-141">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="9c83e-142">例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。</span><span class="sxs-lookup"><span data-stu-id="9c83e-142">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="9c83e-143">然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留 </span><span class="sxs-lookup"><span data-stu-id="9c83e-143">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="9c83e-144">(如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="9c83e-144">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="9c83e-145">Teams 的聊天是在 Microsoft Exchange 後端執行，因此 Exchange 的傳訊限制會套用到 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="9c83e-145">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="9c83e-146">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-146">Feature</span></span>  | <span data-ttu-id="9c83e-147">最大限制</span><span class="sxs-lookup"><span data-stu-id="9c83e-147">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="9c83e-148">一個私人聊天中的人員數目<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-148">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="9c83e-149">100</span><span class="sxs-lookup"><span data-stu-id="9c83e-149">100</span></span>    |
|<span data-ttu-id="9c83e-150">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-150">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="9c83e-151">20</span><span class="sxs-lookup"><span data-stu-id="9c83e-151">20</span></span> |
|<span data-ttu-id="9c83e-152">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-152">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="9c83e-153">10</span><span class="sxs-lookup"><span data-stu-id="9c83e-153">10</span></span>     |
|<span data-ttu-id="9c83e-154">聊天大小</span><span class="sxs-lookup"><span data-stu-id="9c83e-154">Chat size</span></span> | <span data-ttu-id="9c83e-155">每篇貼文約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-155">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="9c83e-156"><sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息、輸入指示器、視訊和音訊通話、共用、讀取回條。</span><span class="sxs-lookup"><span data-stu-id="9c83e-156"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="9c83e-157"><sup>2</sup> 如果附件數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="9c83e-157"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="9c83e-158"><sup>3</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及和回應。</span><span class="sxs-lookup"><span data-stu-id="9c83e-158"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="9c83e-159">傳送電子郵件到頻道</span><span class="sxs-lookup"><span data-stu-id="9c83e-159">Emailing a channel</span></span>

 <span data-ttu-id="9c83e-160">如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="9c83e-160">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="9c83e-161">當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。</span><span class="sxs-lookup"><span data-stu-id="9c83e-161">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="9c83e-162">以下是一些傳送電子郵件到頻道時適用的限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-162">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="9c83e-163">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-163">Feature</span></span>  | <span data-ttu-id="9c83e-164">最大限制</span><span class="sxs-lookup"><span data-stu-id="9c83e-164">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="9c83e-165">郵件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-165">Message size<sup>1<sup></span></span> | <span data-ttu-id="9c83e-166">24 KB</span><span class="sxs-lookup"><span data-stu-id="9c83e-166">24 KB</span></span> |
|<span data-ttu-id="9c83e-167">檔案附件的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-167">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="9c83e-168">20</span><span class="sxs-lookup"><span data-stu-id="9c83e-168">20</span></span>     |
|<span data-ttu-id="9c83e-169">每個檔案附件的大小</span><span class="sxs-lookup"><span data-stu-id="9c83e-169">Size of each file attachment</span></span> | <span data-ttu-id="9c83e-170">小於 10 MB</span><span class="sxs-lookup"><span data-stu-id="9c83e-170">Less than 10 MB</span></span> |
|<span data-ttu-id="9c83e-171">內嵌影像的數目<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9c83e-171">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="9c83e-172">50</span><span class="sxs-lookup"><span data-stu-id="9c83e-172">50</span></span>   |

<span data-ttu-id="9c83e-173"><sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9c83e-173"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="9c83e-174"><sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="9c83e-174"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="9c83e-175">如需詳細資訊，請參閱 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="9c83e-175">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="9c83e-176">所有 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。</span><span class="sxs-lookup"><span data-stu-id="9c83e-176">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="9c83e-177">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="9c83e-177">Channel names</span></span>

<span data-ttu-id="9c83e-178">頻道名稱不能包含下列字元或字詞。</span><span class="sxs-lookup"><span data-stu-id="9c83e-178">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="9c83e-179">字元</span><span class="sxs-lookup"><span data-stu-id="9c83e-179">Characters</span></span>     | <span data-ttu-id="9c83e-180">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="9c83e-180">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="9c83e-181">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="9c83e-181">&#124; ' " ..</span></span>        |
|<span data-ttu-id="9c83e-182">這些範圍內的字元</span><span class="sxs-lookup"><span data-stu-id="9c83e-182">Characters in these ranges</span></span>    | <span data-ttu-id="9c83e-183">0 至 1F</span><span class="sxs-lookup"><span data-stu-id="9c83e-183">0 to 1F</span></span><br><span data-ttu-id="9c83e-184">80 至 9F</span><span class="sxs-lookup"><span data-stu-id="9c83e-184">80 to 9F</span></span>        |
|<span data-ttu-id="9c83e-185">字詞</span><span class="sxs-lookup"><span data-stu-id="9c83e-185">Words</span></span>     | <span data-ttu-id="9c83e-186">forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="9c83e-186">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="9c83e-187">頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。</span><span class="sxs-lookup"><span data-stu-id="9c83e-187">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="9c83e-188">會議和通話</span><span class="sxs-lookup"><span data-stu-id="9c83e-188">Meetings and calls</span></span>

|<span data-ttu-id="9c83e-189">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-189">Feature</span></span>     | <span data-ttu-id="9c83e-190">最大限制</span><span class="sxs-lookup"><span data-stu-id="9c83e-190">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="9c83e-191">一個會議中的人員數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-191">Number of people in a meeting</span></span>  | <span data-ttu-id="9c83e-192">250</span><span class="sxs-lookup"><span data-stu-id="9c83e-192">250</span></span>    |
|<span data-ttu-id="9c83e-193">交談視訊或音訊通話中的人員數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-193">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="9c83e-194">20</span><span class="sxs-lookup"><span data-stu-id="9c83e-194">20</span></span> |
|<span data-ttu-id="9c83e-195">PowerPoint 檔案大小的最大值</span><span class="sxs-lookup"><span data-stu-id="9c83e-195">Max PowerPoint File Size</span></span> | <span data-ttu-id="9c83e-196">2 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-196">2GB</span></span>|
|<span data-ttu-id="9c83e-197">Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載</span><span class="sxs-lookup"><span data-stu-id="9c83e-197">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="9c83e-198">20 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-198">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="9c83e-199">會議到期</span><span class="sxs-lookup"><span data-stu-id="9c83e-199">Meeting expiration</span></span>

|<span data-ttu-id="9c83e-200">會議類型</span><span class="sxs-lookup"><span data-stu-id="9c83e-200">Meeting type</span></span>  |<span data-ttu-id="9c83e-201">會議將在這些時間後到期</span><span class="sxs-lookup"><span data-stu-id="9c83e-201">Meeting expires after this much time</span></span>  |<span data-ttu-id="9c83e-202">每次您開始或更新會議，到期時間會延長這麼多時間</span><span class="sxs-lookup"><span data-stu-id="9c83e-202">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9c83e-203">立即開會</span><span class="sxs-lookup"><span data-stu-id="9c83e-203">Meet now</span></span>     |<span data-ttu-id="9c83e-204">開始時間 + 8 小時</span><span class="sxs-lookup"><span data-stu-id="9c83e-204">Start time + 8 hours</span></span>         |<span data-ttu-id="9c83e-205">不適用</span><span class="sxs-lookup"><span data-stu-id="9c83e-205">N/A</span></span>         |
|<span data-ttu-id="9c83e-206">一般 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="9c83e-206">Regular with no end time</span></span>     |<span data-ttu-id="9c83e-207">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-207">Start time + 60 days</span></span>         | <span data-ttu-id="9c83e-208">60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-208">60 days</span></span>        |
|<span data-ttu-id="9c83e-209">一般 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="9c83e-209">Regular with end time</span></span>     |<span data-ttu-id="9c83e-210">結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-210">End time + 60 days</span></span>         |<span data-ttu-id="9c83e-211">60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-211">60 days</span></span>         |
|<span data-ttu-id="9c83e-212">週期性 (沒有結束時間)</span><span class="sxs-lookup"><span data-stu-id="9c83e-212">Recurring with no end time</span></span>     |<span data-ttu-id="9c83e-213">開始時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-213">Start time + 60 days</span></span>         |<span data-ttu-id="9c83e-214">60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-214">60 days</span></span>         |
|<span data-ttu-id="9c83e-215">週期性 (有結束時間)</span><span class="sxs-lookup"><span data-stu-id="9c83e-215">Recurring with end time</span></span>     |<span data-ttu-id="9c83e-216">最後發生的結束時間 + 60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-216">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="9c83e-217">60 天</span><span class="sxs-lookup"><span data-stu-id="9c83e-217">60 days</span></span>         |

## <a name="teams-live-events"></a><span data-ttu-id="9c83e-218">Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="9c83e-218">Teams live events</span></span>

|<span data-ttu-id="9c83e-219">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-219">Feature</span></span>     | <span data-ttu-id="9c83e-220">最大限制</span><span class="sxs-lookup"><span data-stu-id="9c83e-220">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="9c83e-221">對象數目</span><span class="sxs-lookup"><span data-stu-id="9c83e-221">Audience size</span></span> | <span data-ttu-id="9c83e-222">10,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="9c83e-222">10,000 attendees</span></span> |
|<span data-ttu-id="9c83e-223">活動持續時間</span><span class="sxs-lookup"><span data-stu-id="9c83e-223">Duration of event</span></span> | <span data-ttu-id="9c83e-224">4 小時</span><span class="sxs-lookup"><span data-stu-id="9c83e-224">4 hours</span></span> |
|<span data-ttu-id="9c83e-225">一個 Office 365 組織的並行即時活動</span><span class="sxs-lookup"><span data-stu-id="9c83e-225">Concurrent live events in an Office 365 organization</span></span> | <span data-ttu-id="9c83e-226">15</span><span class="sxs-lookup"><span data-stu-id="9c83e-226">15</span></span> |

<span data-ttu-id="9c83e-227">如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請參閱 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9c83e-227">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c83e-228">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="9c83e-228">**Microsoft 365 live event limit increases**</span></span>
> 
> <span data-ttu-id="9c83e-229">為了協助客戶滿足迅速變化的通訊需求，Microsoft 365 即時活動將針對於 Teams 中進行的即時活動暫時提高預設限制，直到 2020 年 7 月 1 日止。</span><span class="sxs-lookup"><span data-stu-id="9c83e-229">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until July 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="9c83e-230">以下限制將於 2020 年 4 月底推出：</span><span class="sxs-lookup"><span data-stu-id="9c83e-230">The following increases are being rolled out in late April 2020:</span></span>
> - <span data-ttu-id="9c83e-231">出席者限制：活動最多可支援 20,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="9c83e-231">Attendee limit: events can suport up to 20,000 attendees</span></span>
> - <span data-ttu-id="9c83e-232">同時活動：不同租用戶可以同時進行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="9c83e-232">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="9c83e-233">活動持續時間：每個廣播的活動長度已增加為 16 小時</span><span class="sxs-lookup"><span data-stu-id="9c83e-233">Event duration: event length has been increased to 16 hours per broadcast</span></span>



## <a name="presence-in-outlook"></a><span data-ttu-id="9c83e-234">在 Outlook 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="9c83e-234">Presence in Outlook</span></span>

<span data-ttu-id="9c83e-235">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="9c83e-235">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="9c83e-236">若要深入瞭解 Teams 中的目前狀態，請參閱 [Teams 中的使用者目前狀態](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="9c83e-236">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="9c83e-237">儲存空間</span><span class="sxs-lookup"><span data-stu-id="9c83e-237">Storage</span></span>

<span data-ttu-id="9c83e-238">Microsoft Teams 中的每個團隊在 SharePoint Online 中都有一個團隊網站，團隊中的每個頻道在預設團隊網站的文件庫中都有一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="9c83e-238">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="9c83e-239">在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="9c83e-239">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="9c83e-240">如果您未在您的租用戶中啟用 SharePoint Online，Microsoft Teams 使用者一律無法在團隊中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="9c83e-240">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="9c83e-241">在私人聊天中的使用者也無法共用檔案，因為該功能需要有 OneDrive for Business (綁定至 SharePoint 授權)。</span><span class="sxs-lookup"><span data-stu-id="9c83e-241">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="9c83e-242">透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則 </span><span class="sxs-lookup"><span data-stu-id="9c83e-242">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="9c83e-243">(如需詳細資訊，請參閱 [ Sharepoint 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="9c83e-243">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="9c83e-244">由於 Teams 是在 SharePoint Online 後端執行檔案共用，因此 SharePoint 的限制會套用到團隊內的 [檔案] 區段。</span><span class="sxs-lookup"><span data-stu-id="9c83e-244">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="9c83e-245">以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-245">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="9c83e-246">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-246">Feature</span></span>                 |<span data-ttu-id="9c83e-247">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="9c83e-247">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="9c83e-248">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="9c83e-248">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="9c83e-249">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9c83e-249">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="9c83e-250">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="9c83e-250">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="9c83e-251">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="9c83e-251">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="9c83e-252">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="9c83e-252">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="9c83e-253">儲存空間</span><span class="sxs-lookup"><span data-stu-id="9c83e-253">Storage</span></span>                 |<span data-ttu-id="9c83e-254">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-254">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="9c83e-255">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-255">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="9c83e-256">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-256">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="9c83e-257">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-257">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="9c83e-258">每個組織 1 TB，加上每個購買授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-258">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="9c83e-259">每個組織 1 TB </span><span class="sxs-lookup"><span data-stu-id="9c83e-259">1 TB per organization</span></span>           |
|<span data-ttu-id="9c83e-260">Teams 檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="9c83e-260">Storage for Teams Files</span></span> |<span data-ttu-id="9c83e-261">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="9c83e-261">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="9c83e-262">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="9c83e-262">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="9c83e-263">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="9c83e-263">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="9c83e-264">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="9c83e-264">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="9c83e-265">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="9c83e-265">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="9c83e-266">每個網站集合或群組最多 25 TB。</span><span class="sxs-lookup"><span data-stu-id="9c83e-266">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="9c83e-267">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="9c83e-267">File upload limit  (per file)</span></span>    |<span data-ttu-id="9c83e-268">15 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-268">15 GB</span></span>    |<span data-ttu-id="9c83e-269">15 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-269">15 GB</span></span>    |<span data-ttu-id="9c83e-270">15 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-270">15 GB</span></span>    |<span data-ttu-id="9c83e-271">15 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-271">15 GB</span></span>    |<span data-ttu-id="9c83e-272">15 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-272">15 GB</span></span>    |<span data-ttu-id="9c83e-273">15 GB</span><span class="sxs-lookup"><span data-stu-id="9c83e-273">15 GB</span></span>    |

<span data-ttu-id="9c83e-274">頻道受資料夾所支援，而資料夾位於針對團隊建立的 SharePoint Online 網站集合中，因此頻道內的檔案索引標籤會共用所屬團隊的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="9c83e-274">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="9c83e-275">如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="9c83e-275">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="9c83e-276">標記</span><span class="sxs-lookup"><span data-stu-id="9c83e-276">Tags</span></span>

|<span data-ttu-id="9c83e-277">功能</span><span class="sxs-lookup"><span data-stu-id="9c83e-277">Feature</span></span>  |<span data-ttu-id="9c83e-278">最大限制</span><span class="sxs-lookup"><span data-stu-id="9c83e-278">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="9c83e-279">每個小組的標記數量</span><span class="sxs-lookup"><span data-stu-id="9c83e-279">Number of tags per team</span></span>    | <span data-ttu-id="9c83e-280">100</span><span class="sxs-lookup"><span data-stu-id="9c83e-280">100</span></span>        |
|<span data-ttu-id="9c83e-281">每個小組的建議預設標記數量</span><span class="sxs-lookup"><span data-stu-id="9c83e-281">Number of suggested default tags per team</span></span>    | <span data-ttu-id="9c83e-282">25</span><span class="sxs-lookup"><span data-stu-id="9c83e-282">25</span></span>        |
|<span data-ttu-id="9c83e-283">指派給標記的小組成員人數</span><span class="sxs-lookup"><span data-stu-id="9c83e-283">Number of team members assign to a tag</span></span>    |<span data-ttu-id="9c83e-284">100</span><span class="sxs-lookup"><span data-stu-id="9c83e-284">100</span></span>         |
|<span data-ttu-id="9c83e-285">指派給使用者的標記數量</span><span class="sxs-lookup"><span data-stu-id="9c83e-285">Number of tags assigned to a user</span></span>    |<span data-ttu-id="9c83e-286">25</span><span class="sxs-lookup"><span data-stu-id="9c83e-286">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="9c83e-287">連絡人</span><span class="sxs-lookup"><span data-stu-id="9c83e-287">Contacts</span></span>

<span data-ttu-id="9c83e-288">Teams 使用下列連絡人：</span><span class="sxs-lookup"><span data-stu-id="9c83e-288">Teams uses these contacts:</span></span>

- <span data-ttu-id="9c83e-289">您組織 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="9c83e-289">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="9c83e-290">新增至使用者 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="9c83e-290">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="9c83e-291">Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天]\*\*\*\* > [連絡人]\*\*\*\* 或是 [通話]\*\*\*\* > [連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c83e-291">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="9c83e-292">Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話]\*\*\*\* > [連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c83e-292">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="9c83e-293">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="9c83e-293">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="9c83e-294">作業系統</span><span class="sxs-lookup"><span data-stu-id="9c83e-294">Operating systems</span></span>

<span data-ttu-id="9c83e-295">如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="9c83e-295">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
