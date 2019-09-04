---
title: Microsoft 團隊的限制與規格
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: 瞭解適用于 Microsoft 團隊的限制、規格及其他需求。
localization_priority: Priority
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82fbaa955c080446619558a7a90410200f4be604
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715899"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="a7ab2-103">Microsoft 團隊的限制與規格</span><span class="sxs-lookup"><span data-stu-id="a7ab2-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="a7ab2-104">本文將說明適用于團隊的一些限制、規格及其他需求。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="a7ab2-105">團隊和頻道</span><span class="sxs-lookup"><span data-stu-id="a7ab2-105">Teams and channels</span></span>

|<span data-ttu-id="a7ab2-106">功能</span><span class="sxs-lookup"><span data-stu-id="a7ab2-106">Feature</span></span>    | <span data-ttu-id="a7ab2-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="a7ab2-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="a7ab2-108">使用者可以建立的團隊人數</span><span class="sxs-lookup"><span data-stu-id="a7ab2-108">Number of teams a user can create</span></span> | <span data-ttu-id="a7ab2-109">受限於250物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="a7ab2-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="a7ab2-110">團隊中的成員數目</span><span class="sxs-lookup"><span data-stu-id="a7ab2-110">Number of members in a team</span></span> | <span data-ttu-id="a7ab2-111">5000</span><span class="sxs-lookup"><span data-stu-id="a7ab2-111">5,000</span></span>       |
|<span data-ttu-id="a7ab2-112">租使用者允許的組織內團隊人數</span><span class="sxs-lookup"><span data-stu-id="a7ab2-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="a7ab2-113">500</span><span class="sxs-lookup"><span data-stu-id="a7ab2-113">5</span></span>     |
|<span data-ttu-id="a7ab2-114">[組織內小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="a7ab2-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="a7ab2-115">5000</span><span class="sxs-lookup"><span data-stu-id="a7ab2-115">5,000</span></span>       |
|<span data-ttu-id="a7ab2-116">全域管理員可建立的團隊人數</span><span class="sxs-lookup"><span data-stu-id="a7ab2-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="a7ab2-117">500000</span><span class="sxs-lookup"><span data-stu-id="a7ab2-117">500,000</span></span>   |
|<span data-ttu-id="a7ab2-118">Office 365 租使用者可擁有的團隊人數</span><span class="sxs-lookup"><span data-stu-id="a7ab2-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="a7ab2-119">500000&sup2;</span><span class="sxs-lookup"><span data-stu-id="a7ab2-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="a7ab2-120">每個團隊的頻道數目</span><span class="sxs-lookup"><span data-stu-id="a7ab2-120">Number of channels per team</span></span>    | <span data-ttu-id="a7ab2-121">200 (包括刪除的通道) &sup3;</span><span class="sxs-lookup"><span data-stu-id="a7ab2-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="a7ab2-122">&sup1;Azure Active Directory 中的任何目錄物件都會計入此限制。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="a7ab2-123">全域管理員會免除這個限制, 就像是使用[應用程式許可權](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的 app 一樣。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="a7ab2-124">&sup2;此限制包括已歸檔的團隊。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="a7ab2-125">&sup3; 刪除的頻道可以在30天內還原。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="a7ab2-126">在30天內, 已刪除的頻道會繼續依每個團隊的200頻道數量計算。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="a7ab2-127">在30天之後, 已刪除的頻道及其內容會永久刪除, 且頻道不會在每個團隊的200頻道限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="a7ab2-128">傳送</span><span class="sxs-lookup"><span data-stu-id="a7ab2-128">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="a7ab2-129">交流</span><span class="sxs-lookup"><span data-stu-id="a7ab2-129">Chat</span></span>

<span data-ttu-id="a7ab2-130">參與小組中聊天清單之交談的使用者必須有 Exchange Online (雲端) 信箱供系統管理員搜尋聊天交談。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-130">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="a7ab2-131">這是因為聊天清單中的交談是儲存在聊天參與者的雲端型信箱中。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-131">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="a7ab2-132">如果聊天參與者沒有 Exchange Online 信箱, 系統管理員將無法在聊天交談中搜尋或進行封存。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-132">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="a7ab2-133">例如, 在 Exchange 混合式部署中, 擁有內部部署信箱的使用者可以參與在小組中的聊天清單中的交談。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-133">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="a7ab2-134">不過, 在這種情況下, 來自這些交談的內容無法進行搜尋, 而且無法保留, 因為使用者沒有雲端信箱。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-134">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="a7ab2-135">(如需詳細資訊, 請參閱[Exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-135">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="a7ab2-136">團隊聊天是在 Microsoft Exchange 後端使用, 因此 Exchange 訊息限制適用于團隊中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-136">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="a7ab2-137">功能</span><span class="sxs-lookup"><span data-stu-id="a7ab2-137">Feature</span></span>  | <span data-ttu-id="a7ab2-138">最大限制</span><span class="sxs-lookup"><span data-stu-id="a7ab2-138">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="a7ab2-139">私人聊天<sup>1</sup>中的人員人數</span><span class="sxs-lookup"><span data-stu-id="a7ab2-139">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="a7ab2-140">100</span><span class="sxs-lookup"><span data-stu-id="a7ab2-140">100</span></span>    |
|<span data-ttu-id="a7ab2-141">檔附件數<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7ab2-141">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="a7ab2-142">第</span><span class="sxs-lookup"><span data-stu-id="a7ab2-142">10</span></span>     |

<span data-ttu-id="a7ab2-143"><sup>1</sup>如果您在聊天中有超過20名人員, 則會關閉下列聊天功能: Outlook 自動回復和小組狀態訊息;輸入指標;影片和音訊通話;正在讀信回條。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-143"><sup>1</sup>If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="a7ab2-144"><sup>2</sup>如果附件數超過此限制, 您會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-144"><sup>2</sup>If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="a7ab2-145">以電子郵件傳送頻道</span><span class="sxs-lookup"><span data-stu-id="a7ab2-145">Emailing a channel</span></span>

 <span data-ttu-id="a7ab2-146">如果使用者想要傳送電子郵件至小組中的頻道, 他們會使用頻道電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-146">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="a7ab2-147">當電子郵件是頻道的一部分時, 任何人都可以回復以開始交談。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-147">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="a7ab2-148">以下是一些適用于傳送電子郵件到頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-148">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="a7ab2-149">功能</span><span class="sxs-lookup"><span data-stu-id="a7ab2-149">Feature</span></span>  | <span data-ttu-id="a7ab2-150">最大限制</span><span class="sxs-lookup"><span data-stu-id="a7ab2-150">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="a7ab2-151">郵件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="a7ab2-151">Message size<sup>1<sup></span></span> | <span data-ttu-id="a7ab2-152">24 KB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-152">24 KB</span></span> |
|<span data-ttu-id="a7ab2-153">檔附件數<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7ab2-153">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="a7ab2-154">20</span><span class="sxs-lookup"><span data-stu-id="a7ab2-154">20</span></span>     |
|<span data-ttu-id="a7ab2-155">每個檔案附件的大小</span><span class="sxs-lookup"><span data-stu-id="a7ab2-155">Size of each file attachment</span></span> | <span data-ttu-id="a7ab2-156">小於 10 MB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-156">Less than 10 MB</span></span> |
|<span data-ttu-id="a7ab2-157">內嵌圖像<sup>2</sup>的數目</span><span class="sxs-lookup"><span data-stu-id="a7ab2-157">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="a7ab2-158">50</span><span class="sxs-lookup"><span data-stu-id="a7ab2-158">50</span></span>   |

<span data-ttu-id="a7ab2-159"><sup>1</sup>如果郵件超過這個限制, 就會產生預覽訊息, 並要求使用者從提供的連結下載並查看原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-159"><sup>1</sup>If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="a7ab2-160"><sup>2</sup>如果附件數或影像超過此限制, 您會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-160"><sup>2</sup>If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="a7ab2-161">如需詳細資訊, 請參閱[Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-161">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="a7ab2-162">在所有 Office 365 授權中, 郵件大小、檔案附件及內嵌圖像限制都是相同的。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-162">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="a7ab2-163">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="a7ab2-163">Channel names</span></span>

<span data-ttu-id="a7ab2-164">頻道名稱不能包含下列字元或單字。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-164">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="a7ab2-165">標點符號</span><span class="sxs-lookup"><span data-stu-id="a7ab2-165">Characters</span></span>     | <span data-ttu-id="a7ab2-166">~ #% & \* {} +/\:  < > ？</span><span class="sxs-lookup"><span data-stu-id="a7ab2-166">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="a7ab2-167">&#124; "" .。。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-167">&#124; ' " ..</span></span>        |
|<span data-ttu-id="a7ab2-168">這些範圍中的字元</span><span class="sxs-lookup"><span data-stu-id="a7ab2-168">Characters in these ranges</span></span>    | <span data-ttu-id="a7ab2-169">0到1F</span><span class="sxs-lookup"><span data-stu-id="a7ab2-169">0 to 1F</span></span><br><span data-ttu-id="a7ab2-170">80到9F</span><span class="sxs-lookup"><span data-stu-id="a7ab2-170">80 to 9F</span></span>        |
|<span data-ttu-id="a7ab2-171">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a7ab2-171">Words</span></span>     | <span data-ttu-id="a7ab2-172">forms、CON、CONIN $、CONOUT $、PRN、AUX、NUL、COM1 至 COM9、LPT1 到 LPT9、desktop &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="a7ab2-172">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="a7ab2-173">頻道名稱也無法以底線 (_) 或句號 (.) 開頭, 或以句點 (.) 結尾。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-173">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="a7ab2-174">會議和通話</span><span class="sxs-lookup"><span data-stu-id="a7ab2-174">Meetings and calls</span></span>

|<span data-ttu-id="a7ab2-175">功能</span><span class="sxs-lookup"><span data-stu-id="a7ab2-175">Feature</span></span>     | <span data-ttu-id="a7ab2-176">最大限制</span><span class="sxs-lookup"><span data-stu-id="a7ab2-176">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="a7ab2-177">會議中的人員人數</span><span class="sxs-lookup"><span data-stu-id="a7ab2-177">Number of people in a meeting</span></span>  | <span data-ttu-id="a7ab2-178">250</span><span class="sxs-lookup"><span data-stu-id="a7ab2-178">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="a7ab2-179">團隊即時事件</span><span class="sxs-lookup"><span data-stu-id="a7ab2-179">Teams live events</span></span>

|<span data-ttu-id="a7ab2-180">功能</span><span class="sxs-lookup"><span data-stu-id="a7ab2-180">Feature</span></span>     | <span data-ttu-id="a7ab2-181">最大限制</span><span class="sxs-lookup"><span data-stu-id="a7ab2-181">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="a7ab2-182">物件大小</span><span class="sxs-lookup"><span data-stu-id="a7ab2-182">Audience size</span></span> | <span data-ttu-id="a7ab2-183">10000出席者</span><span class="sxs-lookup"><span data-stu-id="a7ab2-183">10,000 attendees</span></span> |
|<span data-ttu-id="a7ab2-184">事件的持續時間</span><span class="sxs-lookup"><span data-stu-id="a7ab2-184">Duration of event</span></span> | <span data-ttu-id="a7ab2-185">4小時</span><span class="sxs-lookup"><span data-stu-id="a7ab2-185">4 hours</span></span> |
|<span data-ttu-id="a7ab2-186">Office 365 租使用者中的併發即時事件</span><span class="sxs-lookup"><span data-stu-id="a7ab2-186">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="a7ab2-187">工資</span><span class="sxs-lookup"><span data-stu-id="a7ab2-187">15</span></span> |

<span data-ttu-id="a7ab2-188">如需即時事件的詳細資訊, 以及團隊即時事件與 Skype 會議廣播的比較, 請移至 [[小組即時事件] 和 [Skype 會議](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)廣播]。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-188">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="a7ab2-189">容量</span><span class="sxs-lookup"><span data-stu-id="a7ab2-189">Storage</span></span>

<span data-ttu-id="a7ab2-190">Microsoft 團隊中的每個小組在 SharePoint Online 中都有小組網站, 小組中的每個頻道都在預設的小組網站文件庫中取得一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-190">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="a7ab2-191">在交談中共用的檔案會自動新增至文件庫, SharePoint 中設定的許可權和檔案安全性選項會自動反映在小組中。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-191">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="a7ab2-192">如果您未在租使用者中啟用 SharePoint Online, Microsoft 團隊使用者就無法在小組中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-192">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="a7ab2-193">私人聊天中的使用者也無法共用檔案, 因為該功能需要商務用 OneDrive (與 SharePoint 授權相關聯)。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-193">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="a7ab2-194">透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive 中, 就會遵循在租使用者層級設定的所有合規性規則。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-194">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="a7ab2-195">(如需詳細資訊, 請參閱[SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="a7ab2-195">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="a7ab2-196">由於團隊是在 SharePoint Online 後端執行檔案共用, 因此 SharePoint 限制適用于小組中的 [檔案] 區段。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-196">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="a7ab2-197">以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-197">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="a7ab2-198">功能</span><span class="sxs-lookup"><span data-stu-id="a7ab2-198">Feature</span></span>                 |<span data-ttu-id="a7ab2-199">Office 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="a7ab2-199">Office 365 Business Essentials</span></span>  |<span data-ttu-id="a7ab2-200">Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="a7ab2-200">Office 365 Business Premium</span></span>   |<span data-ttu-id="a7ab2-201">Office 365 企業版 E1</span><span class="sxs-lookup"><span data-stu-id="a7ab2-201">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="a7ab2-202">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="a7ab2-202">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="a7ab2-203">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="a7ab2-203">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="a7ab2-204">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="a7ab2-204">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="a7ab2-205">容量</span><span class="sxs-lookup"><span data-stu-id="a7ab2-205">Storage</span></span>                 |<span data-ttu-id="a7ab2-206">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-206">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="a7ab2-207">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-207">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="a7ab2-208">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-208">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="a7ab2-209">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-209">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="a7ab2-210">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-210">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="a7ab2-211">每個組織 1 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-211">1 TB per organization</span></span>           |
|<span data-ttu-id="a7ab2-212">小組檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="a7ab2-212">Storage for Teams Files</span></span> |<span data-ttu-id="a7ab2-213">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-213">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a7ab2-214">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-214">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a7ab2-215">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-215">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a7ab2-216">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-216">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a7ab2-217">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-217">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a7ab2-218">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-218">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="a7ab2-219">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="a7ab2-219">File upload limit  (per file)</span></span>    |<span data-ttu-id="a7ab2-220">15 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-220">15 GB</span></span>    |<span data-ttu-id="a7ab2-221">15 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-221">15 GB</span></span>    |<span data-ttu-id="a7ab2-222">15 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-222">15 GB</span></span>    |<span data-ttu-id="a7ab2-223">15 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-223">15 GB</span></span>    |<span data-ttu-id="a7ab2-224">15 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-224">15 GB</span></span>    |<span data-ttu-id="a7ab2-225">15 GB</span><span class="sxs-lookup"><span data-stu-id="a7ab2-225">15 GB</span></span>    |

<span data-ttu-id="a7ab2-226">頻道是由針對小組建立的 SharePoint Online 網站集合中的資料夾所支援, 因此頻道內的檔案索引標籤會共用其所屬團隊的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-226">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="a7ab2-227">如需詳細資訊, 請參閱[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-227">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="a7ab2-228">聯絡</span><span class="sxs-lookup"><span data-stu-id="a7ab2-228">Contacts</span></span>

<span data-ttu-id="a7ab2-229">小組使用下列連絡人:</span><span class="sxs-lookup"><span data-stu-id="a7ab2-229">Teams uses these contacts:</span></span>

- <span data-ttu-id="a7ab2-230">貴組織的 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="a7ab2-230">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="a7ab2-231">新增至使用者的 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="a7ab2-231">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="a7ab2-232">團隊使用者可以與貴組織的 active directory 中的任何人通訊, 也可以移至**聊天** > **連絡人**或**通話** >  , 將您組織的 active directory 中的任何人新增為連絡人, 並加入其連絡人清單。**連絡人**。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-232">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="a7ab2-233">團隊使用者也可以移至 [**呼叫** > **連絡人**], 將您組織的 Active Directory 以外的人員新增為連絡人。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-233">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="a7ab2-234">流覽</span><span class="sxs-lookup"><span data-stu-id="a7ab2-234">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="a7ab2-235">作業系統</span><span class="sxs-lookup"><span data-stu-id="a7ab2-235">Operating systems</span></span>

<span data-ttu-id="a7ab2-236">如需作業系統需求的相關資訊, 請參閱[取得 Microsoft 團隊的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ab2-236">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
