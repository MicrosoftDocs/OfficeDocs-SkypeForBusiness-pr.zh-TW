---
title: SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & 與團隊進行商務用 OneDrive 互動私人聊天檔案儲存 & 在團隊、標準通道、& 文件庫之間互動。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f4f536c6395e17e58f255ac3b88ccca0a092815c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778559"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="e55b6-103">SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式</span><span class="sxs-lookup"><span data-stu-id="e55b6-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="e55b6-104">請觀看下列會話，瞭解團隊與 Azure Active Directory （AAD）、Microsoft 365 群組、Exchange、SharePoint 和商務用 OneDrive 的互動方式： [Microsoft 團隊的基礎](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="e55b6-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="e55b6-105">Microsoft 團隊中的每個團隊在 SharePoint Online 中都有小組網站，小組中的每個標準頻道都會在預設的小組網站文件庫中取得一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="e55b6-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="e55b6-106">在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="e55b6-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="e55b6-107">若要查看在 SharePoint 中變更網站位址的影響，請參閱[變更網站位址](https://docs.microsoft.com/sharepoint/change-site-address)。</span><span class="sxs-lookup"><span data-stu-id="e55b6-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="e55b6-108">本文只適用于標準頻道。</span><span class="sxs-lookup"><span data-stu-id="e55b6-108">This article applies only to standard channels.</span></span> <span data-ttu-id="e55b6-109">專用通道的架構與標準通道不同。</span><span class="sxs-lookup"><span data-stu-id="e55b6-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="e55b6-110">每個私人頻道都有自己的 SharePoint 網站集合，與父小組網站不同。</span><span class="sxs-lookup"><span data-stu-id="e55b6-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="e55b6-111">若要深入瞭解，請參閱[Microsoft 團隊中的私人頻道](private-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="e55b6-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="e55b6-112">私人聊天檔案會儲存在寄件者的商務用 OneDrive 資料夾中，而許可權會自動授與所有參與者，做為檔案共用程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="e55b6-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="e55b6-113">如果使用者未使用 SharePoint Online 授權指派及啟用，他們在 Office 365 中就沒有商務用 OneDrive 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e55b6-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="e55b6-114">檔案共用功能會在標準頻道中繼續運作，但是使用者無法在 Office 365 中的商務用 OneDrive 儲存空間中共用檔案。</span><span class="sxs-lookup"><span data-stu-id="e55b6-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="e55b6-115">透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則 </span><span class="sxs-lookup"><span data-stu-id="e55b6-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="e55b6-116">目前 Microsoft 團隊不支援與 SharePoint 內部部署的整合。</span><span class="sxs-lookup"><span data-stu-id="e55b6-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="e55b6-117">下列是團隊、標準頻道與文件庫之間的關聯性範例。</span><span class="sxs-lookup"><span data-stu-id="e55b6-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="e55b6-118">針對每個小組，都會建立一個 SharePoint 網站，而 [**共用文件**] 資料夾則是為該小組建立的預設資料夾。</span><span class="sxs-lookup"><span data-stu-id="e55b6-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="e55b6-119">每個標準通道，包括**一般**通道（每個團隊的預設通道）在 [**共用檔**] 中都有一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="e55b6-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online 中的 [共用文件] 資料夾圖表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="e55b6-121">目前無法將預設的 SharePoint 網站與文件庫取代為其他人。</span><span class="sxs-lookup"><span data-stu-id="e55b6-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="e55b6-122">我們已聽取您想要的內容，我們正在考慮。</span><span class="sxs-lookup"><span data-stu-id="e55b6-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="e55b6-123">檢查 [[團隊藍圖](https://aka.ms/teamsroadmap)] 或 [[團隊 UserVoice](https://aka.ms/TeamsUserVoice) ]，掌握即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="e55b6-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="e55b6-124">若要將索引標籤新增至您的小組，以連結至現有的 SharePoint 網站頁面或現有的 SharePoint 文件庫：</span><span class="sxs-lookup"><span data-stu-id="e55b6-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="e55b6-125">選取索引標籤旁的加號。</span><span class="sxs-lookup"><span data-stu-id="e55b6-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="e55b6-126">針對現有的文件庫，選取任一**sharepoint**的現有 sharepoint 網站頁面或**文件庫**。</span><span class="sxs-lookup"><span data-stu-id="e55b6-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="e55b6-127">選取適當的頁面或文件庫。</span><span class="sxs-lookup"><span data-stu-id="e55b6-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="e55b6-128">針對每位使用者， **Microsoft 團隊聊天**檔案是用來儲存在私人聊天中與其他使用者共用的所有檔案（1:1 或1：許多），並自動設定許可權，以限制只有預定使用者才能存取。</span><span class="sxs-lookup"><span data-stu-id="e55b6-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![名為 Microsoft 團隊聊天檔案的 OneDrive 資料夾圖表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="e55b6-130">[頻道檔案] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="e55b6-130">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="e55b6-131">團隊中的 [檔案] 索引標籤會與 [SharePoint**檔**] 視圖密切類似。</span><span class="sxs-lookup"><span data-stu-id="e55b6-131">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="e55b6-132">**在 [檔案**] 索引標籤上，使用者可以：</span><span class="sxs-lookup"><span data-stu-id="e55b6-132">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="e55b6-133">請參閱 [**新增**檔案] 功能表中的其他選項。</span><span class="sxs-lookup"><span data-stu-id="e55b6-133">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="e55b6-134">將檔案同步處理到其本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="e55b6-134">Sync files to their local drive.</span></span>
- <span data-ttu-id="e55b6-135">在 [**所有檔**] 功能表上，從 [**清單**] 視圖切換至 [將**清單壓縮**至 [**磚**] 視圖。</span><span class="sxs-lookup"><span data-stu-id="e55b6-135">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="e55b6-136">找出需要注意或有惡意程式碼的檔案。</span><span class="sxs-lookup"><span data-stu-id="e55b6-136">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="e55b6-137">立即查看檔案是唯讀或取出。</span><span class="sxs-lookup"><span data-stu-id="e55b6-137">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="e55b6-138">取出和存回檔案。</span><span class="sxs-lookup"><span data-stu-id="e55b6-138">Check out and check in files.</span></span>
- <span data-ttu-id="e55b6-139">釘選、解除固定及變更檔的排序次序。</span><span class="sxs-lookup"><span data-stu-id="e55b6-139">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="e55b6-140">找出需要中繼資料的檔案</span><span class="sxs-lookup"><span data-stu-id="e55b6-140">Identify which files need metadata</span></span>
- <span data-ttu-id="e55b6-141">從許多其他篩選選項中進行選擇。</span><span class="sxs-lookup"><span data-stu-id="e55b6-141">Choose from many more filter options.</span></span>
- <span data-ttu-id="e55b6-142">根據欄標題來分組檔案。</span><span class="sxs-lookup"><span data-stu-id="e55b6-142">Group files based on column headings.</span></span>
- <span data-ttu-id="e55b6-143">修改欄設定（向左或向右移動、隱藏）和欄寬。</span><span class="sxs-lookup"><span data-stu-id="e55b6-143">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="e55b6-144">預設連結類型設定</span><span class="sxs-lookup"><span data-stu-id="e55b6-144">Default link type setting</span></span>

<span data-ttu-id="e55b6-145">SharePoint 和 OneDrive 擁有管理員設定，可指定為檔案建立之連結的預設連結類型。</span><span class="sxs-lookup"><span data-stu-id="e55b6-145">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="e55b6-146">團隊會重複使用系統管理員針對 SharePoint 和 OneDrive 設定的設定，採用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="e55b6-146">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="e55b6-147">如需有關此方法的詳細資訊，[請參閱變更使用者取得共用連結時的預設連結類型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。</span><span class="sxs-lookup"><span data-stu-id="e55b6-147">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="e55b6-148">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e55b6-148">More information</span></span>

<span data-ttu-id="e55b6-149">如需 SharePoint 與團隊搭配運作方式的詳細資訊，請參閱[sharepoint 與團隊：更好搭配](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)使用。</span><span class="sxs-lookup"><span data-stu-id="e55b6-149">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="e55b6-150">若要深入瞭解團隊中的來賓體驗，請閱讀[來賓體驗](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="e55b6-150">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

