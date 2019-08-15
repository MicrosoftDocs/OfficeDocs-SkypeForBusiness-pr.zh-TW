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
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407993"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="b15a7-103">Microsoft 團隊的限制與規格</span><span class="sxs-lookup"><span data-stu-id="b15a7-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="b15a7-104">本文將說明適用于團隊的一些限制、規格及其他需求。</span><span class="sxs-lookup"><span data-stu-id="b15a7-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="b15a7-105">團隊和頻道</span><span class="sxs-lookup"><span data-stu-id="b15a7-105">Teams and channels</span></span> 

|<span data-ttu-id="b15a7-106">功能</span><span class="sxs-lookup"><span data-stu-id="b15a7-106">Feature</span></span>    | <span data-ttu-id="b15a7-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="b15a7-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="b15a7-108">使用者可以建立的團隊人數</span><span class="sxs-lookup"><span data-stu-id="b15a7-108">Number of teams a user can create</span></span> | <span data-ttu-id="b15a7-109">受限於250物件限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="b15a7-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="b15a7-110">團隊中的成員數目</span><span class="sxs-lookup"><span data-stu-id="b15a7-110">Number of members in a team</span></span> | <span data-ttu-id="b15a7-111">5000</span><span class="sxs-lookup"><span data-stu-id="b15a7-111">5,000</span></span>       |
|<span data-ttu-id="b15a7-112">租使用者允許的組織內團隊人數</span><span class="sxs-lookup"><span data-stu-id="b15a7-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="b15a7-113">500</span><span class="sxs-lookup"><span data-stu-id="b15a7-113">5</span></span>     |
|<span data-ttu-id="b15a7-114">[組織內小組](create-an-org-wide-team.md)中的成員數目</span><span class="sxs-lookup"><span data-stu-id="b15a7-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="b15a7-115">5000</span><span class="sxs-lookup"><span data-stu-id="b15a7-115">5,000</span></span>       |
|<span data-ttu-id="b15a7-116">全域管理員可建立的團隊人數</span><span class="sxs-lookup"><span data-stu-id="b15a7-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="b15a7-117">500000</span><span class="sxs-lookup"><span data-stu-id="b15a7-117">500,000</span></span>   |
|<span data-ttu-id="b15a7-118">Office 365 租使用者可擁有的團隊人數</span><span class="sxs-lookup"><span data-stu-id="b15a7-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="b15a7-119">500000&sup2;</span><span class="sxs-lookup"><span data-stu-id="b15a7-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="b15a7-120">每個團隊的頻道數目</span><span class="sxs-lookup"><span data-stu-id="b15a7-120">Number of channels per team</span></span>    | <span data-ttu-id="b15a7-121">200 (包括刪除的通道) &sup3;</span><span class="sxs-lookup"><span data-stu-id="b15a7-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="b15a7-122">&sup1;Azure Active Directory 中的任何目錄物件都會計入此限制。</span><span class="sxs-lookup"><span data-stu-id="b15a7-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="b15a7-123">全域管理員會免除這個限制, 就像是使用[應用程式許可權](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的 app 一樣。</span><span class="sxs-lookup"><span data-stu-id="b15a7-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="b15a7-124">&sup2;此限制包括已歸檔的團隊。</span><span class="sxs-lookup"><span data-stu-id="b15a7-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="b15a7-125">&sup3; 刪除的頻道可以在30天內還原。</span><span class="sxs-lookup"><span data-stu-id="b15a7-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="b15a7-126">在30天內, 已刪除的頻道會繼續依每個團隊的200頻道數量計算。</span><span class="sxs-lookup"><span data-stu-id="b15a7-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="b15a7-127">在30天之後, 已刪除的頻道及其內容會永久刪除, 且頻道不會在每個團隊的200頻道限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="b15a7-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="channel-names"></a><span data-ttu-id="b15a7-128">頻道名稱</span><span class="sxs-lookup"><span data-stu-id="b15a7-128">Channel names</span></span>

<span data-ttu-id="b15a7-129">頻道名稱不能包含下列字元或單字。</span><span class="sxs-lookup"><span data-stu-id="b15a7-129">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="b15a7-130">標點符號</span><span class="sxs-lookup"><span data-stu-id="b15a7-130">Characters</span></span>     | <span data-ttu-id="b15a7-131">~ #% & \* {} +/\:  < > ？</span><span class="sxs-lookup"><span data-stu-id="b15a7-131">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="b15a7-132">&#124; "" .。。</span><span class="sxs-lookup"><span data-stu-id="b15a7-132">&#124; ' " ..</span></span>        |
|<span data-ttu-id="b15a7-133">這些範圍中的字元</span><span class="sxs-lookup"><span data-stu-id="b15a7-133">Characters in these ranges</span></span>    | <span data-ttu-id="b15a7-134">0到1F</span><span class="sxs-lookup"><span data-stu-id="b15a7-134">0 to 1F</span></span><br><span data-ttu-id="b15a7-135">80到9F</span><span class="sxs-lookup"><span data-stu-id="b15a7-135">80 to 9F</span></span>        |
|<span data-ttu-id="b15a7-136">關鍵字</span><span class="sxs-lookup"><span data-stu-id="b15a7-136">Words</span></span>     | <span data-ttu-id="b15a7-137">forms、CON、CONIN $、CONOUT $、PRN、AUX、NUL、COM1 至 COM9、LPT1 到 LPT9、desktop &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="b15a7-137">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="b15a7-138">頻道名稱也無法以底線 (_) 或句號 (.) 開頭, 或以句點 (.) 結尾。</span><span class="sxs-lookup"><span data-stu-id="b15a7-138">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="b15a7-139">會議和通話</span><span class="sxs-lookup"><span data-stu-id="b15a7-139">Meetings and calls</span></span>

|<span data-ttu-id="b15a7-140">功能</span><span class="sxs-lookup"><span data-stu-id="b15a7-140">Feature</span></span>     | <span data-ttu-id="b15a7-141">最大限制</span><span class="sxs-lookup"><span data-stu-id="b15a7-141">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="b15a7-142">會議中的人員人數</span><span class="sxs-lookup"><span data-stu-id="b15a7-142">Number of people in a meeting</span></span>  | <span data-ttu-id="b15a7-143">250</span><span class="sxs-lookup"><span data-stu-id="b15a7-143">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="b15a7-144">團隊即時事件</span><span class="sxs-lookup"><span data-stu-id="b15a7-144">Teams live events</span></span>

|<span data-ttu-id="b15a7-145">功能</span><span class="sxs-lookup"><span data-stu-id="b15a7-145">Feature</span></span>     | <span data-ttu-id="b15a7-146">最大限制</span><span class="sxs-lookup"><span data-stu-id="b15a7-146">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="b15a7-147">物件大小</span><span class="sxs-lookup"><span data-stu-id="b15a7-147">Audience size</span></span> | <span data-ttu-id="b15a7-148">10000出席者</span><span class="sxs-lookup"><span data-stu-id="b15a7-148">10,000 attendees</span></span> |
|<span data-ttu-id="b15a7-149">事件的持續時間</span><span class="sxs-lookup"><span data-stu-id="b15a7-149">Duration of event</span></span> | <span data-ttu-id="b15a7-150">4小時</span><span class="sxs-lookup"><span data-stu-id="b15a7-150">4 hours</span></span> |
|<span data-ttu-id="b15a7-151">欄1</span><span class="sxs-lookup"><span data-stu-id="b15a7-151">Column1</span></span>  |<span data-ttu-id="b15a7-152">欄2等</span><span class="sxs-lookup"><span data-stu-id="b15a7-152">Column2</span></span>  |
|---------|---------|
|<span data-ttu-id="b15a7-153">Row1</span><span class="sxs-lookup"><span data-stu-id="b15a7-153">Row1</span></span>     |         |
|<span data-ttu-id="b15a7-154">Row2</span><span class="sxs-lookup"><span data-stu-id="b15a7-154">Row2</span></span>     |         |

<span data-ttu-id="b15a7-155">|Office 365 租使用者 | 中的併發即時事件 |15 |</span><span class="sxs-lookup"><span data-stu-id="b15a7-155">|Concurrent live events in an Office 365 tenant | 15 |</span></span>

<span data-ttu-id="b15a7-156">如需即時事件的詳細資訊, 以及團隊即時事件與 Skype 會議廣播的比較, 請移至 [[小組即時事件] 和 [Skype 會議](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)廣播]。</span><span class="sxs-lookup"><span data-stu-id="b15a7-156">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="b15a7-157">容量</span><span class="sxs-lookup"><span data-stu-id="b15a7-157">Storage</span></span>

<span data-ttu-id="b15a7-158">Microsoft 團隊中的每個小組在 SharePoint Online 中都有小組網站, 小組中的每個頻道都在預設的小組網站文件庫中取得一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="b15a7-158">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="b15a7-159">在交談中共用的檔案會自動新增至文件庫, SharePoint 中設定的許可權和檔案安全性選項會自動反映在小組中。</span><span class="sxs-lookup"><span data-stu-id="b15a7-159">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="b15a7-160">如果您未在租使用者中啟用 SharePoint Online, Microsoft 團隊使用者就無法在小組中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="b15a7-160">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="b15a7-161">私人聊天中的使用者也無法共用檔案, 因為該功能需要商務用 OneDrive (與 SharePoint 授權相關聯)。</span><span class="sxs-lookup"><span data-stu-id="b15a7-161">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="b15a7-162">透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive 中, 就會遵循在租使用者層級設定的所有合規性規則。</span><span class="sxs-lookup"><span data-stu-id="b15a7-162">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="b15a7-163">(如需詳細資訊, 請參閱[SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="b15a7-163">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="b15a7-164">由於團隊是在 SharePoint Online 後端執行檔案共用, 因此 SharePoint 限制適用于小組中的 [檔案] 區段。</span><span class="sxs-lookup"><span data-stu-id="b15a7-164">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="b15a7-165">以下是 SharePoint Online 適用的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="b15a7-165">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="b15a7-166">功能</span><span class="sxs-lookup"><span data-stu-id="b15a7-166">Feature</span></span>                 |<span data-ttu-id="b15a7-167">Office 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="b15a7-167">Office 365 Business Essentials</span></span>  |<span data-ttu-id="b15a7-168">Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="b15a7-168">Office 365 Business Premium</span></span>   |<span data-ttu-id="b15a7-169">Office 365 企業版 E1</span><span class="sxs-lookup"><span data-stu-id="b15a7-169">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="b15a7-170">Office 365 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="b15a7-170">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="b15a7-171">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="b15a7-171">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="b15a7-172">Office 365 企業版 F1</span><span class="sxs-lookup"><span data-stu-id="b15a7-172">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="b15a7-173">容量</span><span class="sxs-lookup"><span data-stu-id="b15a7-173">Storage</span></span>                 |<span data-ttu-id="b15a7-174">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-174">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="b15a7-175">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-175">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="b15a7-176">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-176">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="b15a7-177">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-177">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="b15a7-178">每個組織 1 TB 加上購買的每個授權 10 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-178">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="b15a7-179">每個組織 1 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-179">1 TB per organization</span></span>           |
|<span data-ttu-id="b15a7-180">小組檔案的儲存空間</span><span class="sxs-lookup"><span data-stu-id="b15a7-180">Storage for Teams Files</span></span> |<span data-ttu-id="b15a7-181">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-181">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b15a7-182">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-182">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b15a7-183">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-183">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b15a7-184">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-184">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b15a7-185">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-185">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b15a7-186">每個網站集合或群組最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="b15a7-186">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="b15a7-187">檔案上傳限制 (每個檔案)</span><span class="sxs-lookup"><span data-stu-id="b15a7-187">File upload limit  (per file)</span></span>    |<span data-ttu-id="b15a7-188">15 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-188">15 GB</span></span>    |<span data-ttu-id="b15a7-189">15 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-189">15 GB</span></span>    |<span data-ttu-id="b15a7-190">15 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-190">15 GB</span></span>    |<span data-ttu-id="b15a7-191">15 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-191">15 GB</span></span>    |<span data-ttu-id="b15a7-192">15 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-192">15 GB</span></span>    |<span data-ttu-id="b15a7-193">15 GB</span><span class="sxs-lookup"><span data-stu-id="b15a7-193">15 GB</span></span>    |

<span data-ttu-id="b15a7-194">頻道是由針對小組建立的 SharePoint Online 網站集合中的資料夾所支援, 因此頻道內的檔案索引標籤會共用其所屬團隊的儲存空間限制。</span><span class="sxs-lookup"><span data-stu-id="b15a7-194">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="b15a7-195">如需詳細資訊, 請參閱[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="b15a7-195">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="messaging"></a><span data-ttu-id="b15a7-196">傳送</span><span class="sxs-lookup"><span data-stu-id="b15a7-196">Messaging</span></span>

<span data-ttu-id="b15a7-197">參與 Microsoft 團隊中聊天清單一部分交談的使用者, 必須擁有 Exchange Online (雲端) 信箱, 以供系統管理員搜尋交談交談。</span><span class="sxs-lookup"><span data-stu-id="b15a7-197">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="b15a7-198">這是因為聊天清單中的交談是儲存在聊天參與者的雲端型信箱中。</span><span class="sxs-lookup"><span data-stu-id="b15a7-198">That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="b15a7-199">如果聊天參與者沒有 Exchange Online 信箱, 系統管理員將無法在聊天交談中搜尋或進行封存。</span><span class="sxs-lookup"><span data-stu-id="b15a7-199">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="b15a7-200">例如, 在 Exchange 混合式部署中, 擁有內部部署信箱的使用者可能可以參與 Microsoft 團隊中的聊天清單中的交談。</span><span class="sxs-lookup"><span data-stu-id="b15a7-200">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="b15a7-201">不過, 在這種情況下, 來自這些交談的內容無法進行搜尋, 而且無法保留, 因為使用者沒有雲端信箱。</span><span class="sxs-lookup"><span data-stu-id="b15a7-201">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="b15a7-202">(如需詳細資訊, 請參閱[Exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md))。</span><span class="sxs-lookup"><span data-stu-id="b15a7-202">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="b15a7-203">Microsoft 團隊聊天功能可在 Microsoft Exchange 後端使用, 因此您可以將 Exchange 郵件限制套用至 Microsoft 團隊中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="b15a7-203">Microsoft Teams chat function works on a Microsoft Exchange backend, so you can apply the Exchange messaging limits to the chat function within Microsoft Teams.</span></span> <span data-ttu-id="b15a7-204">如果使用者想要傳送電子郵件至小組中的頻道, 他們會使用頻道電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b15a7-204">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="b15a7-205">一旦電子郵件是頻道的一部分, 任何人都可以回復以開始交談。</span><span class="sxs-lookup"><span data-stu-id="b15a7-205">Once an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="b15a7-206">以下是一些適用于傳送電子郵件到頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="b15a7-206">Here are some of the applicable limits for sending email to a channel.</span></span> 

|<span data-ttu-id="b15a7-207">功能</span><span class="sxs-lookup"><span data-stu-id="b15a7-207">Feature</span></span>  | <span data-ttu-id="b15a7-208">最大限制</span><span class="sxs-lookup"><span data-stu-id="b15a7-208">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="b15a7-209">私人聊天中的人員人數</span><span class="sxs-lookup"><span data-stu-id="b15a7-209">Number of people in a private chat</span></span>  | <span data-ttu-id="b15a7-210">100</span><span class="sxs-lookup"><span data-stu-id="b15a7-210">100</span></span>    |
|<span data-ttu-id="b15a7-211">郵件大小&dagger;</span><span class="sxs-lookup"><span data-stu-id="b15a7-211">Message size &dagger;</span></span>  |<span data-ttu-id="b15a7-212">25 KB</span><span class="sxs-lookup"><span data-stu-id="b15a7-212">25 KB</span></span>   |
|<span data-ttu-id="b15a7-213">檔附件的數目&Dagger;</span><span class="sxs-lookup"><span data-stu-id="b15a7-213">Number of file attachments &Dagger;</span></span>  |<span data-ttu-id="b15a7-214">第</span><span class="sxs-lookup"><span data-stu-id="b15a7-214">10</span></span>     |
|<span data-ttu-id="b15a7-215">內嵌圖像的數目&Dagger;</span><span class="sxs-lookup"><span data-stu-id="b15a7-215">Number of inline images &Dagger;</span></span> |<span data-ttu-id="b15a7-216">50</span><span class="sxs-lookup"><span data-stu-id="b15a7-216">50</span></span>   |

<span data-ttu-id="b15a7-217">&dagger;如果郵件超過這個限制, 就會產生預覽訊息, 並要求使用者從提供的連結中查看或下載原始電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b15a7-217">&dagger; If the message exceeds this limit, a preview message is generated and the user is asked to view/download the original email from the link provided.</span></span>

<span data-ttu-id="b15a7-218">&Dagger;如果附件或影像數量超過這個限制, 就不會處理郵件, 而且 NDR 電子郵件會傳回給寄件者, 通知他們發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="b15a7-218">&Dagger; If the number of attachments or images exceeds this limit, the message will not be processed and an NDR email will be sent back to the sender notifying them of the error.</span></span>

> [!NOTE]
> <span data-ttu-id="b15a7-219">在所有 Office 365 授權中, 郵件大小、檔案附件及內嵌圖像限制都是相同的。</span><span class="sxs-lookup"><span data-stu-id="b15a7-219">The message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

<span data-ttu-id="b15a7-220">如需詳細資訊, 請參閱[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b15a7-220">For more information, see [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>

## <a name="browsers"></a><span data-ttu-id="b15a7-221">流覽</span><span class="sxs-lookup"><span data-stu-id="b15a7-221">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="b15a7-222">作業系統</span><span class="sxs-lookup"><span data-stu-id="b15a7-222">Operating systems</span></span>

<span data-ttu-id="b15a7-223">如需作業系統需求的相關資訊, 請參閱[取得 Microsoft 團隊的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="b15a7-223">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
