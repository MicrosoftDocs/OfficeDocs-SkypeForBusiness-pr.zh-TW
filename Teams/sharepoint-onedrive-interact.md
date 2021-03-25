---
title: SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online &商務用 OneDrive 與 Teams 互動;私人聊天檔案儲存&小組、標準頻道、&文件庫之間的互動。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b69b156e5cea0ff63925e91f5e3c077c794b3425
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117031"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="09745-103">SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動</span><span class="sxs-lookup"><span data-stu-id="09745-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="09745-104">觀看以下工作階段以了解 Teams 如何與 Azure Active Directory (AAD)、Microsoft 365 群組、Exchange、SharePoint 和商務用 OneDrive 進行互動：[Microsoft Teams 的基礎](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="09745-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="09745-105">Microsoft Teams 中的每個團隊在 SharePoint Online 中都有一個小組網站，而團隊中的每個標準頻道會獲得預設小組網站文件庫中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="09745-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="09745-106">在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="09745-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="09745-107">若要在 SharePoint 中查看變更網站位址的影響，請閱讀 [變更網站位址](/sharepoint/change-site-address)。</span><span class="sxs-lookup"><span data-stu-id="09745-107">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="09745-108">本文僅適用于標準頻道。</span><span class="sxs-lookup"><span data-stu-id="09745-108">This article applies only to standard channels.</span></span> <span data-ttu-id="09745-109">私人頻道的架構與標準通道不同。</span><span class="sxs-lookup"><span data-stu-id="09745-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="09745-110">每個私人頻道都有自己的 SharePoint 網站集合，與父小組網站分開。</span><span class="sxs-lookup"><span data-stu-id="09745-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="09745-111">若要深入瞭解，請參閱 [Microsoft Teams 中的私人頻道](private-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="09745-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="09745-112">私人聊天檔案會儲存在寄件者的商務用 OneDrive 資料夾中，並會在檔案共用過程中自動授予所有參與者許可權。</span><span class="sxs-lookup"><span data-stu-id="09745-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="09745-113">若使用者並非以 SharePoint Online 進行指派及授權，他們將無法使用 Microsoft 365 或 Office 365 中的 [商務用 OneDrive] 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="09745-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="09745-114">檔案共用會繼續在標準頻道中使用，但若沒有 Microsoft 365 或 Office 365 中的商務用 OneDrive 儲存空間，使用者將無法在聊天中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="09745-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="09745-115">透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則 </span><span class="sxs-lookup"><span data-stu-id="09745-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="09745-116">Microsoft Teams 目前不支援與 SharePoint 內部部署整合。</span><span class="sxs-lookup"><span data-stu-id="09745-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="09745-117">以下是小組、標準頻道和文件庫之間關係範例。</span><span class="sxs-lookup"><span data-stu-id="09745-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="09745-118">針對每個小組，會建立 SharePoint 網站，而 **共用檔** 資料夾是團隊建立的預設資料夾。</span><span class="sxs-lookup"><span data-stu-id="09745-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="09745-119">每個標準頻道 ，包括一般 (每個團隊的預設頻道) 共用 **檔中的資料夾**。</span><span class="sxs-lookup"><span data-stu-id="09745-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online 中共用文件資料夾的圖表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="09745-121">目前無法將預設的 SharePoint 網站和文件庫取代為另一個網站和文件庫。</span><span class="sxs-lookup"><span data-stu-id="09745-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="09745-122">我們聽到您要求，我們正在考慮。</span><span class="sxs-lookup"><span data-stu-id="09745-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="09745-123">查看 [Teams 藍圖](https://aka.ms/teamsroadmap) 或 [Teams UserVoice，](https://aka.ms/TeamsUserVoice) 以隨時瞭解即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="09745-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="09745-124">若要新增連結至現有 SharePoint 網站頁面或現有 SharePoint 文件庫的小組的 Tab：</span><span class="sxs-lookup"><span data-stu-id="09745-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="09745-125">選取定位停駐點旁的加號。</span><span class="sxs-lookup"><span data-stu-id="09745-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="09745-126">選取 **現有 SharePoint** 網站頁面的 SharePoint或現有文件庫的文件庫。</span><span class="sxs-lookup"><span data-stu-id="09745-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="09745-127">選取適當的頁面或文件庫。</span><span class="sxs-lookup"><span data-stu-id="09745-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="09745-128">針對每個使用者，Microsoft **Teams** 聊天檔案的 OneDrive 資料夾會用來儲存在私人聊天中與其他使用者共用的所有檔案 (1：1 或 1：) ，並自動將許可權配置為僅限制預定使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="09745-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![名為 Microsoft Teams 聊天檔案的 OneDrive 資料夾圖表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="09745-130">請注意，對於公用團隊，SharePoint 小組網站會布備「外部使用者以外的所有人」存取權。</span><span class="sxs-lookup"><span data-stu-id="09745-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="09745-131">對於不是該團隊成員的人，公用團隊不會顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="09745-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="09745-132">不過，他們可以使用 SharePoint 小組網站的 URL 存取 SharePoint 小組網站上的內容。</span><span class="sxs-lookup"><span data-stu-id="09745-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="09745-133">頻道檔案選項卡</span><span class="sxs-lookup"><span data-stu-id="09745-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="09745-134">Teams **中的** 檔案選項卡與 SharePoint 檔視圖非常類似。</span><span class="sxs-lookup"><span data-stu-id="09745-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="09745-135">在檔案 **選項卡** 上，使用者可以：</span><span class="sxs-lookup"><span data-stu-id="09745-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="09745-136">在新增檔案功能表中查看 **其他** 選項。</span><span class="sxs-lookup"><span data-stu-id="09745-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="09745-137">將檔案同步處理至其本地磁碟機。</span><span class="sxs-lookup"><span data-stu-id="09745-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="09745-138">在所有 **檔功能表** 上，從清單視圖切換到 **壓縮清單** 至 **磚** 視圖。</span><span class="sxs-lookup"><span data-stu-id="09745-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="09745-139">識別需要注意或具有惡意攻擊的檔案。</span><span class="sxs-lookup"><span data-stu-id="09745-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="09745-140">立即查看檔案是唯讀還是已簽出。</span><span class="sxs-lookup"><span data-stu-id="09745-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="09745-141">簽出並簽入檔案。</span><span class="sxs-lookup"><span data-stu-id="09745-141">Check out and check in files.</span></span>
- <span data-ttu-id="09745-142">釘選、取消釘選及變更檔案的排序次序。</span><span class="sxs-lookup"><span data-stu-id="09745-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="09745-143">識別哪些檔案需要中繼資料</span><span class="sxs-lookup"><span data-stu-id="09745-143">Identify which files need metadata</span></span>
- <span data-ttu-id="09745-144">選擇更多篩選選項。</span><span class="sxs-lookup"><span data-stu-id="09745-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="09745-145">根據欄標題將檔案分組。</span><span class="sxs-lookup"><span data-stu-id="09745-145">Group files based on column headings.</span></span>
- <span data-ttu-id="09745-146">修改欄設定 (向左或向右移動、隱藏) 欄寬。</span><span class="sxs-lookup"><span data-stu-id="09745-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="09745-147">預設連結類型設定</span><span class="sxs-lookup"><span data-stu-id="09745-147">Default link type setting</span></span>

<span data-ttu-id="09745-148">SharePoint 和 OneDrive 具有系統管理員設定，可指定為檔案建立的連結的預設連結類型。</span><span class="sxs-lookup"><span data-stu-id="09745-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="09745-149">Teams 會採用相同的方法，方法是重新使用系統管理員為 SharePoint 和 OneDrive 所設定。</span><span class="sxs-lookup"><span data-stu-id="09745-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="09745-150">有關此方法的詳細資訊，請參閱當使用者取得共用連結時變更[預設連結類型。](/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="09745-150">More details about this approach are described in [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="09745-151">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="09745-151">More information</span></span>

<span data-ttu-id="09745-152">有關 SharePoint 如何與 Teams 合作之詳細資訊，請參閱 [SharePoint 和 Teams：更好在一起](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="09745-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="09745-153">若要深入瞭解 Teams 中的來賓體驗，請閱讀來賓 [體驗是什麼](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="09745-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>