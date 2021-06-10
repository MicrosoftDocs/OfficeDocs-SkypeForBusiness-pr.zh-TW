---
title: SharePoint與OneDrive互動Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive與Teams;私人聊天檔案儲存&小組、標準頻道、&文件庫之間的互動。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855952"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="810ff-103">SharePoint與OneDrive互動Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="810ff-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="810ff-104">觀看下列會話，瞭解如何Teams AAD Azure Active Directory (、) 、Microsoft 365 群組、Exchange、SharePoint和 OneDrive互動：Microsoft Teams [](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="810ff-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="810ff-105">每個團隊Microsoft Teams小組網站SharePoint，團隊中的每個標準頻道會獲得預設小組網站文件庫中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="810ff-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="810ff-106">每個[私人頻道](private-channels.md)都有各自獨立的SharePoint網站。</span><span class="sxs-lookup"><span data-stu-id="810ff-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="810ff-107">在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。</span><span class="sxs-lookup"><span data-stu-id="810ff-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="810ff-108">若要查看變更網站位址在 SharePoint 的影響，請參閱[變更網站位址](/sharepoint/change-site-address)。</span><span class="sxs-lookup"><span data-stu-id="810ff-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="810ff-109">私人聊天檔案會儲存在寄件者的 OneDrive 資料夾中，並會在檔案共用過程中自動授予所有參與者許可權。</span><span class="sxs-lookup"><span data-stu-id="810ff-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="810ff-110">如果使用者未SharePoint授權，他們OneDrive儲存Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="810ff-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="810ff-111">檔案共用可以在標準頻道中運作，但使用者無法共用聊天中的檔案，OneDrive儲存Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="810ff-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="810ff-112">將檔案儲存于文件庫SharePoint文件庫中OneDrive，所有在組織層級所配置的合規性規則都會遵循。</span><span class="sxs-lookup"><span data-stu-id="810ff-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="810ff-113">系統不支援SharePoint伺服器Teams。</span><span class="sxs-lookup"><span data-stu-id="810ff-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="810ff-114">以下是小組、標準頻道和文件庫之間關係範例。</span><span class="sxs-lookup"><span data-stu-id="810ff-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="810ff-115">針對每個小組，SharePoint網站，**而共用檔** 資料夾是團隊建立的預設資料夾。</span><span class="sxs-lookup"><span data-stu-id="810ff-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="810ff-116">每個標準頻道 ，包括一般 (每個團隊的預設頻道) 共用 **檔中的資料夾**。</span><span class="sxs-lookup"><span data-stu-id="810ff-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![共用文件資料夾圖表在 SharePoint。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="810ff-118">無法SharePoint網站和文件庫的預設文件庫。</span><span class="sxs-lookup"><span data-stu-id="810ff-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="810ff-119">針對每個使用者，OneDrive 資料夾 **Microsoft Teams** 聊天檔案會用來儲存與其他使用者 (1：1 或 1：多) 私人聊天中共用的所有檔案，並自動將許可權配置為僅限制預定使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="810ff-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![名為 OneDrive 聊天檔案Microsoft Teams資料夾圖表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="810ff-121">請注意，對於公用小組，SharePoint網站會布布「外部使用者以外的所有人」存取權。</span><span class="sxs-lookup"><span data-stu-id="810ff-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="810ff-122">公用團隊不會顯示在 Teams中，適用于不是該團隊成員的人。</span><span class="sxs-lookup"><span data-stu-id="810ff-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="810ff-123">不過，他們可以使用小組SharePoint網站的 URL 存取SharePoint內容。</span><span class="sxs-lookup"><span data-stu-id="810ff-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="810ff-124">頻道檔案選項卡</span><span class="sxs-lookup"><span data-stu-id="810ff-124">Channel Files tab</span></span>

<span data-ttu-id="810ff-125">檔案 **中的** 檔案Teams與檔SharePoint類似。</span><span class="sxs-lookup"><span data-stu-id="810ff-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="810ff-126">在檔案 **選項卡** 上，使用者可以：</span><span class="sxs-lookup"><span data-stu-id="810ff-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="810ff-127">請參閱新增檔案功能表中 **的其他** 選項。</span><span class="sxs-lookup"><span data-stu-id="810ff-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="810ff-128">將檔案同步處理至其本地磁碟機。</span><span class="sxs-lookup"><span data-stu-id="810ff-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="810ff-129">在所有 **檔功能表** 上，從清單視圖切換到 **壓縮清單** 至 **磚** 視圖。</span><span class="sxs-lookup"><span data-stu-id="810ff-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="810ff-130">識別需要注意或具有惡意攻擊的檔案。</span><span class="sxs-lookup"><span data-stu-id="810ff-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="810ff-131">立即查看檔案是唯讀還是已簽出。</span><span class="sxs-lookup"><span data-stu-id="810ff-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="810ff-132">簽出並簽入檔案。</span><span class="sxs-lookup"><span data-stu-id="810ff-132">Check out and check in files.</span></span>
- <span data-ttu-id="810ff-133">釘選、取消釘選及變更檔案的排序次序。</span><span class="sxs-lookup"><span data-stu-id="810ff-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="810ff-134">識別哪些檔案需要中繼資料</span><span class="sxs-lookup"><span data-stu-id="810ff-134">Identify which files need metadata</span></span>
- <span data-ttu-id="810ff-135">選擇更多篩選選項。</span><span class="sxs-lookup"><span data-stu-id="810ff-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="810ff-136">根據欄標題將檔案分組。</span><span class="sxs-lookup"><span data-stu-id="810ff-136">Group files based on column headings.</span></span>
- <span data-ttu-id="810ff-137">修改欄設定 (左右移動、隱藏) 欄寬。</span><span class="sxs-lookup"><span data-stu-id="810ff-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="810ff-138">預設連結類型設定</span><span class="sxs-lookup"><span data-stu-id="810ff-138">Default link type setting</span></span>

<span data-ttu-id="810ff-139">系統管理中心已設定使用者共用檔案時預設顯示的共用SharePoint類型。</span><span class="sxs-lookup"><span data-stu-id="810ff-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="810ff-140">當使用者 [取得共用資訊的連結時，](/sharepoint/change-default-sharing-link) 請參閱變更預設連結類型。</span><span class="sxs-lookup"><span data-stu-id="810ff-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="810ff-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="810ff-141">Related topics</span></span>

<span data-ttu-id="810ff-142">[SharePoint和Teams：一起變得更好](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="810ff-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="810ff-143">來賓體驗像什麼</span><span class="sxs-lookup"><span data-stu-id="810ff-143">What the guest experience is like</span></span>](guest-experience.md)