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
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54c71dfb692dc5981699babdfdb708c404eb6231
ms.sourcegitcommit: fd5d48b36d70e3f42e029572fe003ee397db090d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2019
ms.locfileid: "36473368"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="80c06-103">Microsoft 團隊的限制與規格</span><span class="sxs-lookup"><span data-stu-id="80c06-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="80c06-104">本文將說明適用于團隊的一些限制、規格及其他需求。</span><span class="sxs-lookup"><span data-stu-id="80c06-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="80c06-105">團隊和頻道</span><span class="sxs-lookup"><span data-stu-id="80c06-105">Teams and channels</span></span>

|<span data-ttu-id="80c06-106">功能</span><span class="sxs-lookup"><span data-stu-id="80c06-106">Feature</span></span>    | <span data-ttu-id="80c06-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="80c06-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="80c06-108">使用者可以建立的團隊人數</span><span class="sxs-lookup"><span data-stu-id="80c06-108">Number of teams a user can create</span></span> | <span data-ttu-id="80c06-109">受限於250物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="80c06-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="80c06-110">團隊中的成員數目</span><span class="sxs-lookup"><span data-stu-id="80c06-110">Number of members in a team</span></span> | <span data-ttu-id="80c06-111">5000</span><span class="sxs-lookup"><span data-stu-id="80c06-111">5,000</span></span>       |
|<span data-ttu-id="80c06-112">租使用者允許的組織內團隊人數</span><span class="sxs-lookup"><span data-stu-id="80c06-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="80c06-113">500</span><span class="sxs-lookup"><span data-stu-id="80c06-113">5</span></span>     |
|<span data-ttu-id="80c06-114">[組織內小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="80c06-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="80c06-115">5000</span><span class="sxs-lookup"><span data-stu-id="80c06-115">5,000</span></span>       |
|<span data-ttu-id="80c06-116">全域管理員可建立的團隊人數</span><span class="sxs-lookup"><span data-stu-id="80c06-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="80c06-117">500000</span><span class="sxs-lookup"><span data-stu-id="80c06-117">500,000</span></span>   |
|<span data-ttu-id="80c06-118">Office 365 租使用者可擁有的團隊人數</span><span class="sxs-lookup"><span data-stu-id="80c06-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="80c06-119">500000&sup2;</span><span class="sxs-lookup"><span data-stu-id="80c06-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="80c06-120">每個團隊的頻道數目</span><span class="sxs-lookup"><span data-stu-id="80c06-120">Number of channels per team</span></span>    | <span data-ttu-id="80c06-121">200 (包括刪除的通道) &sup3;</span><span class="sxs-lookup"><span data-stu-id="80c06-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="80c06-122">&sup1;Azure Active Directory 中的任何目錄物件都會計入此限制。</span><span class="sxs-lookup"><span data-stu-id="80c06-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="80c06-123">全域管理員會免除這個限制, 就像是使用[應用程式許可權](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的 app 一樣。</span><span class="sxs-lookup"><span data-stu-id="80c06-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="80c06-124">&sup2;此限制包括已歸檔的團隊。</span><span class="sxs-lookup"><span data-stu-id="80c06-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="80c06-125">&sup3; 刪除的頻道可以在30天內還原。</span><span class="sxs-lookup"><span data-stu-id="80c06-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="80c06-126">在30天內, 已刪除的頻道會繼續依每個團隊的200頻道數量計算。</span><span class="sxs-lookup"><span data-stu-id="80c06-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="80c06-127">在30天之後, 已刪除的頻道及其內容會永久刪除, 且頻道不會在每個團隊的200頻道限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="80c06-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="channel-names"></a><span data-ttu-id="80c06-128">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="80c06-128">Channel names</span></span>

<span data-ttu-id="80c06-129">頻道名稱不能包含下列字元或單字。</span><span class="sxs-lookup"><span data-stu-id="80c06-129">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="80c06-130">標點符號</span><span class="sxs-lookup"><span data-stu-id="80c06-130">Characters</span></span>     | <span data-ttu-id="80c06-131">~ #% & \* {} +/\:  < > ？</span><span class="sxs-lookup"><span data-stu-id="80c06-131">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="80c06-132">&#124; "" .。。</span><span class="sxs-lookup"><span data-stu-id="80c06-132">&#124; ' " ..</span></span>        |
|<span data-ttu-id="80c06-133">這些範圍中的字元</span><span class="sxs-lookup"><span data-stu-id="80c06-133">Characters in these ranges</span></span>    | <span data-ttu-id="80c06-134">0到1F</span><span class="sxs-lookup"><span data-stu-id="80c06-134">0 to 1F</span></span><br><span data-ttu-id="80c06-135">80到9F</span><span class="sxs-lookup"><span data-stu-id="80c06-135">80 to 9F</span></span>        |
|<span data-ttu-id="80c06-136">關鍵字</span><span class="sxs-lookup"><span data-stu-id="80c06-136">Words</span></span>     | <span data-ttu-id="80c06-137">forms、CON、CONIN $、CONOUT $、PRN、AUX、NUL、COM1 至 COM9、LPT1 到 LPT9、desktop &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="80c06-137">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="80c06-138">頻道名稱也無法以底線 (_) 或句號 (.) 開頭, 或以句點 (.) 結尾。</span><span class="sxs-lookup"><span data-stu-id="80c06-138">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="80c06-139">會議和通話</span><span class="sxs-lookup"><span data-stu-id="80c06-139">Meetings and calls</span></span>

|<span data-ttu-id="80c06-140">功能</span><span class="sxs-lookup"><span data-stu-id="80c06-140">Feature</span></span>     | <span data-ttu-id="80c06-141">最大限制</span><span class="sxs-lookup"><span data-stu-id="80c06-141">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="80c06-142">會議中的人員人數</span><span class="sxs-lookup"><span data-stu-id="80c06-142">Number of people in a meeting</span></span>  | <span data-ttu-id="80c06-143">250</span><span class="sxs-lookup"><span data-stu-id="80c06-143">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="80c06-144">團隊即時事件</span><span class="sxs-lookup"><span data-stu-id="80c06-144">Teams live events</span></span>

|<span data-ttu-id="80c06-145">功能</span><span class="sxs-lookup"><span data-stu-id="80c06-145">Feature</span></span>     | <span data-ttu-id="80c06-146">最大限制</span><span class="sxs-lookup"><span data-stu-id="80c06-146">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="80c06-147">物件大小</span><span class="sxs-lookup"><span data-stu-id="80c06-147">Audience size</span></span> | <span data-ttu-id="80c06-148">10000出席者</span><span class="sxs-lookup"><span data-stu-id="80c06-148">10,000 attendees</span></span> |
|<span data-ttu-id="80c06-149">事件的持續時間</span><span class="sxs-lookup"><span data-stu-id="80c06-149">Duration of event</span></span> | <span data-ttu-id="80c06-150">4小時</span><span class="sxs-lookup"><span data-stu-id="80c06-150">4 hours</span></span> |
|<span data-ttu-id="80c06-151">Office 365 租使用者中的併發即時事件</span><span class="sxs-lookup"><span data-stu-id="80c06-151">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="80c06-152">工資</span><span class="sxs-lookup"><span data-stu-id="80c06-152">15</span></span> |

<span data-ttu-id="80c06-153">如需即時事件的詳細資訊, 以及團隊即時事件與 Skype 會議廣播的比較, 請移至 [[小組即時事件] 和 [Skype 會議](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)廣播]。</span><span class="sxs-lookup"><span data-stu-id="80c06-153">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="80c06-154">容量</span><span class="sxs-lookup"><span data-stu-id="80c06-154">Storage</span></span>

<span data-ttu-id="80c06-155">Microsoft 團隊中的每個小組在 SharePoint Online 中都有小組網站, 小組中的每個頻道都在預設的小組網站文件庫中取得一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="80c06-155">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="80c06-156">在交談中共用的檔案會自動新增至文件庫, SharePoint 中設定的許可權和檔案安全性選項會自動反映在小組中。</span><span class="sxs-lookup"><span data-stu-id="80c06-156">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="80c06-157">如果您未在租使用者中啟用 SharePoint Online, Microsoft 團隊使用者就無法在小組中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="80c06-157">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="80c06-158">私人聊天中的使用者也無法共用檔案, 因為該功能需要商務用 OneDrive (與 SharePoint 授權相關聯)。</span><span class="sxs-lookup"><span data-stu-id="80c06-158">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="80c06-159">透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive 中, 就會遵循在租使用者層級設定的所有合規性規則。</span><span class="sxs-lookup"><span data-stu-id="80c06-159">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="80c06-160">(如需詳細資訊, 請參閱[SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="80c06-160">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="80c06-161">由於團隊是在 SharePoint Online 後端執行檔案共用, 因此 SharePoint 限制適用于小組中的 [檔案] 區段。</span><span class="sxs-lookup"><span data-stu-id="80c06-161">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="80c06-162">以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="80c06-162">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="80c06-163">功能</span><span class="sxs-lookup"><span data-stu-id="80c06-163">Feature</span></span>                 |<span data-ttu-id="80c06-164">Office 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="80c06-164">Office 365 Business Essentials</span></span>  |<span data-ttu-id="80c06-165">Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="80c06-165">Office 365 Business Premium</span></span>   |<span data-ttu-id="80c06-166">Office 365 企業版 E1</span><span class="sxs-lookup"><span data-stu-id="80c06-166">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="80c06-167">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="80c06-167">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="80c06-168">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="80c06-168">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="80c06-169">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="80c06-169">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="80c06-170">容量</span><span class="sxs-lookup"><span data-stu-id="80c06-170">Storage</span></span>                 |<span data-ttu-id="80c06-171">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-171">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="80c06-172">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-172">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="80c06-173">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-173">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="80c06-174">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-174">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="80c06-175">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-175">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="80c06-176">每個組織 1 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-176">1 TB per organization</span></span>           |
|<span data-ttu-id="80c06-177">小組檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="80c06-177">Storage for Teams Files</span></span> |<span data-ttu-id="80c06-178">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-178">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="80c06-179">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-179">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="80c06-180">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-180">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="80c06-181">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-181">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="80c06-182">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-182">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="80c06-183">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="80c06-183">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="80c06-184">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="80c06-184">File upload limit  (per file)</span></span>    |<span data-ttu-id="80c06-185">15 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-185">15 GB</span></span>    |<span data-ttu-id="80c06-186">15 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-186">15 GB</span></span>    |<span data-ttu-id="80c06-187">15 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-187">15 GB</span></span>    |<span data-ttu-id="80c06-188">15 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-188">15 GB</span></span>    |<span data-ttu-id="80c06-189">15 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-189">15 GB</span></span>    |<span data-ttu-id="80c06-190">15 GB</span><span class="sxs-lookup"><span data-stu-id="80c06-190">15 GB</span></span>    |

<span data-ttu-id="80c06-191">頻道是由針對小組建立的 SharePoint Online 網站集合中的資料夾所支援, 因此頻道內的檔案索引標籤會共用其所屬團隊的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="80c06-191">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="80c06-192">如需詳細資訊, 請參閱[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="80c06-192">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="messaging"></a><span data-ttu-id="80c06-193">傳送</span><span class="sxs-lookup"><span data-stu-id="80c06-193">Messaging</span></span>

<span data-ttu-id="80c06-194">參與 Microsoft 團隊中聊天清單一部分交談的使用者, 必須擁有 Exchange Online (雲端) 信箱, 以供系統管理員搜尋交談交談。</span><span class="sxs-lookup"><span data-stu-id="80c06-194">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="80c06-195">這是因為聊天清單中的交談是儲存在聊天參與者的雲端型信箱中。</span><span class="sxs-lookup"><span data-stu-id="80c06-195">That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="80c06-196">如果聊天參與者沒有 Exchange Online 信箱, 系統管理員將無法在聊天交談中搜尋或進行封存。</span><span class="sxs-lookup"><span data-stu-id="80c06-196">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="80c06-197">例如, 在 Exchange 混合式部署中, 擁有內部部署信箱的使用者可能可以參與 Microsoft 團隊中的聊天清單中的交談。</span><span class="sxs-lookup"><span data-stu-id="80c06-197">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="80c06-198">不過, 在這種情況下, 來自這些交談的內容無法進行搜尋, 而且無法保留, 因為使用者沒有雲端信箱。</span><span class="sxs-lookup"><span data-stu-id="80c06-198">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="80c06-199">(如需詳細資訊, 請參閱[Exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="80c06-199">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="80c06-200">Microsoft 團隊聊天功能可在 Microsoft Exchange 後端使用, 因此您可以將 Exchange 郵件限制套用至 Microsoft 團隊中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="80c06-200">Microsoft Teams chat function works on a Microsoft Exchange backend, so you can apply the Exchange messaging limits to the chat function within Microsoft Teams.</span></span> <span data-ttu-id="80c06-201">如果使用者想要傳送電子郵件至小組中的頻道, 他們會使用頻道電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="80c06-201">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="80c06-202">一旦電子郵件是頻道的一部分, 任何人都可以回復以開始交談。</span><span class="sxs-lookup"><span data-stu-id="80c06-202">Once an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="80c06-203">以下是一些適用于傳送電子郵件到頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="80c06-203">Here are some of the applicable limits for sending email to a channel.</span></span> 

|<span data-ttu-id="80c06-204">功能</span><span class="sxs-lookup"><span data-stu-id="80c06-204">Feature</span></span>  | <span data-ttu-id="80c06-205">最大限制</span><span class="sxs-lookup"><span data-stu-id="80c06-205">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="80c06-206">私人聊天中的人員人數</span><span class="sxs-lookup"><span data-stu-id="80c06-206">Number of people in a private chat</span></span>  | <span data-ttu-id="80c06-207">100</span><span class="sxs-lookup"><span data-stu-id="80c06-207">100</span></span>    |
|<span data-ttu-id="80c06-208">郵件大小&dagger;</span><span class="sxs-lookup"><span data-stu-id="80c06-208">Message size &dagger;</span></span>  |<span data-ttu-id="80c06-209">25 KB</span><span class="sxs-lookup"><span data-stu-id="80c06-209">25 KB</span></span>   |
|<span data-ttu-id="80c06-210">檔附件的數目&Dagger;</span><span class="sxs-lookup"><span data-stu-id="80c06-210">Number of file attachments &Dagger;</span></span>  |<span data-ttu-id="80c06-211">第</span><span class="sxs-lookup"><span data-stu-id="80c06-211">10</span></span>     |
|<span data-ttu-id="80c06-212">內嵌圖像的數目&Dagger;</span><span class="sxs-lookup"><span data-stu-id="80c06-212">Number of inline images &Dagger;</span></span> |<span data-ttu-id="80c06-213">50</span><span class="sxs-lookup"><span data-stu-id="80c06-213">50</span></span>   |

<span data-ttu-id="80c06-214">&dagger;如果郵件超過這個限制, 就會產生預覽訊息, 並要求使用者從提供的連結中查看或下載原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="80c06-214">&dagger; If the message exceeds this limit, a preview message is generated and the user is asked to view/download the original email from the link provided.</span></span>

<span data-ttu-id="80c06-215">&Dagger;如果附件或影像數量超過這個限制, 就不會處理郵件, 而且 NDR 電子郵件會傳回給寄件者, 通知他們發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="80c06-215">&Dagger; If the number of attachments or images exceeds this limit, the message will not be processed and an NDR email will be sent back to the sender notifying them of the error.</span></span>

> [!NOTE]
> <span data-ttu-id="80c06-216">在所有 Office 365 授權中, 郵件大小、檔案附件及內嵌圖像限制都是相同的。</span><span class="sxs-lookup"><span data-stu-id="80c06-216">The message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

<span data-ttu-id="80c06-217">如需詳細資訊, 請參閱[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="80c06-217">For more information, see [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>

## <a name="contacts"></a><span data-ttu-id="80c06-218">聯絡</span><span class="sxs-lookup"><span data-stu-id="80c06-218">Contacts</span></span>

<span data-ttu-id="80c06-219">小組使用下列連絡人:</span><span class="sxs-lookup"><span data-stu-id="80c06-219">Teams uses these contacts:</span></span>

- <span data-ttu-id="80c06-220">貴組織的 Active Directory 中的連絡人</span><span class="sxs-lookup"><span data-stu-id="80c06-220">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="80c06-221">新增至使用者的 Outlook 預設資料夾的連絡人</span><span class="sxs-lookup"><span data-stu-id="80c06-221">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="80c06-222">團隊使用者可以與貴組織的 active directory 中的任何人通訊, 也可以移至**聊天** > **連絡人**或**通話** >  , 將您組織的 active directory 中的任何人新增為連絡人, 並加入其連絡人清單。**連絡人**。</span><span class="sxs-lookup"><span data-stu-id="80c06-222">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="80c06-223">團隊使用者也可以移至 [**呼叫** > **連絡人**], 將您組織的 Active Directory 以外的人員新增為連絡人。</span><span class="sxs-lookup"><span data-stu-id="80c06-223">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="80c06-224">流覽</span><span class="sxs-lookup"><span data-stu-id="80c06-224">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="80c06-225">作業系統</span><span class="sxs-lookup"><span data-stu-id="80c06-225">Operating systems</span></span>

<span data-ttu-id="80c06-226">如需作業系統需求的相關資訊, 請參閱[取得 Microsoft 團隊的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="80c06-226">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
