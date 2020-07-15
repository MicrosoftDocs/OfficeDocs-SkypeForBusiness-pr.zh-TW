---
title: 在 Microsoft 團隊中共用檔案
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: 瞭解 Microsoft 團隊中的檔案共用體驗。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138332"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="cfffe-103">在 Microsoft 團隊中共用檔案</span><span class="sxs-lookup"><span data-stu-id="cfffe-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="cfffe-104">在 Microsoft 團隊中，使用者可以與組織內部和外部的其他團隊使用者共用內容。</span><span class="sxs-lookup"><span data-stu-id="cfffe-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="cfffe-105">[在小組中共用] 是以 SharePoint 和 OneDrive 中所設定的設定為基礎，因此您針對 SharePoint 和 OneDrive 設定的任何內容，都會同時控制小組中的共用功能。</span><span class="sxs-lookup"><span data-stu-id="cfffe-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="cfffe-106">概觀</span><span class="sxs-lookup"><span data-stu-id="cfffe-106">Overview</span></span>

<span data-ttu-id="cfffe-107">使用者可以從 OneDrive、他們有權存取的小組和網站，以及從他們的電腦上共用檔案。</span><span class="sxs-lookup"><span data-stu-id="cfffe-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="cfffe-108">若要共用檔案，使用者可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cfffe-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="cfffe-109">在頻道中，按一下 [**附加**] （曲別針圖示）、選取 [**最近** **]、[流覽團隊和頻道]、[** **OneDrive**] 或 [**從我的電腦上傳**]，然後選擇他們要共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="cfffe-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="cfffe-110">![螢幕擷取畫面顯示如何從頻道共用檔案](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="cfffe-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="cfffe-111">在聊天中，按一下 [**附加**] （曲別針圖示），選取或 [ **OneDrive** ] 或 [**從我的電腦上傳**]，然後選擇他們要共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="cfffe-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="cfffe-112">![螢幕擷取畫面顯示如何從聊天共用檔案](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="cfffe-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="cfffe-113">在撰寫方塊中複製並貼上共用連結。</span><span class="sxs-lookup"><span data-stu-id="cfffe-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="cfffe-114">![螢幕擷取畫面顯示撰寫方塊中的檔案預覽](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="cfffe-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="cfffe-115">檔案共用體驗所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="cfffe-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="cfffe-116">共用檔案和共用連結的許可權</span><span class="sxs-lookup"><span data-stu-id="cfffe-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="cfffe-117">當使用者透過在 OneDrive 或團隊和頻道中流覽來共用檔案時，系統會向所有收件者授與[組織層級所設定的預設許可權](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。</span><span class="sxs-lookup"><span data-stu-id="cfffe-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="cfffe-118">當使用者複製並貼上共用連結時，該共用連結上所設定的許可權即會生效，SharePoint URL 會縮短為檔案名。</span><span class="sxs-lookup"><span data-stu-id="cfffe-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="cfffe-119">換句話說，小組只會使用檔案名來連結至檔案。</span><span class="sxs-lookup"><span data-stu-id="cfffe-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="cfffe-120">當使用者在團隊中共用檔案時，他們可以設定誰可以存取該檔案，就像在 Microsoft 365 中一樣。</span><span class="sxs-lookup"><span data-stu-id="cfffe-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="cfffe-121">他們可以為您組織中的人員、擁有現有存取權的人員或特定人員（可在1:1 聊天、群組聊天或頻道中加入人員）提供存取權。</span><span class="sxs-lookup"><span data-stu-id="cfffe-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="cfffe-122">共用檔案時，會在郵件中提供檔案預覽，以及**開啟 [線上**]、[**下載**] 和 [**複製連結**] 等所有檔案動作。</span><span class="sxs-lookup"><span data-stu-id="cfffe-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="cfffe-123">根據預設，檔案會在 [團隊] 中開啟。</span><span class="sxs-lookup"><span data-stu-id="cfffe-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="cfffe-124">有時候，共用連結可能不會在使用者傳送郵件時轉換成檔案預覽。</span><span class="sxs-lookup"><span data-stu-id="cfffe-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="cfffe-125">系統會產生檔案預覽，但在這種情況下，不會將共用連結截短至唯一的檔案名。</span><span class="sxs-lookup"><span data-stu-id="cfffe-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="cfffe-126">當使用者在聊天或頻道中共用檔案時，系統會通知您是否有部分或所有收件者沒有許可權來查看檔案。</span><span class="sxs-lookup"><span data-stu-id="cfffe-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="cfffe-127">他們可以在共用檔案前，按一下現在出現在郵件中的檔案預覽旁邊的箭號，即可變更該檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="cfffe-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![如果收件者沒有許可權，螢幕擷取畫面顯示通知](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="cfffe-129">複製小組中的共用連結</span><span class="sxs-lookup"><span data-stu-id="cfffe-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="cfffe-130">使用者可以複製 SharePoint 共用連結，並變更共用許可權，就像在 Microsoft 365 中一樣。</span><span class="sxs-lookup"><span data-stu-id="cfffe-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="cfffe-131">他們可以授與您組織中的人員、擁有現有存取權的人員，或特定人員的存取權。</span><span class="sxs-lookup"><span data-stu-id="cfffe-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="cfffe-132">連結的預設許可權會與組織階層的預設許可權集相同，除非 SharePoint 網站層級許可權覆蓋它。</span><span class="sxs-lookup"><span data-stu-id="cfffe-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="cfffe-133">在 OneDrive 和 SharePoint 中設定共用</span><span class="sxs-lookup"><span data-stu-id="cfffe-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="cfffe-134">如需在 OneDrive 和 SharePoint 中共用檔案的詳細資訊，包括如何設定共用，以及如何開啟和關閉共用，請參閱：</span><span class="sxs-lookup"><span data-stu-id="cfffe-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="cfffe-135">[[外部共用] 概覽](https://docs.microsoft.com/sharepoint/external-sharing-overview)-說明使用者共用時所發生的情況，視其共用和人員的情況而定。</span><span class="sxs-lookup"><span data-stu-id="cfffe-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="cfffe-136">[管理共用設定](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)-說明全域和 SharePoint 系統管理員可以如何變更其組織層級的 SharePoint 和 OneDrive 共用設定。</span><span class="sxs-lookup"><span data-stu-id="cfffe-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="cfffe-137">[開啟或關閉網站的外部共用](https://docs.microsoft.com/sharepoint/change-external-sharing-site)–說明全域和 SharePoint 系統管理員可以如何開啟或關閉網站的外部共用。</span><span class="sxs-lookup"><span data-stu-id="cfffe-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="cfffe-138">[變更網站的預設連結類型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)-說明如何設定預設連結類型，讓它更具限制性。</span><span class="sxs-lookup"><span data-stu-id="cfffe-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="cfffe-139">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="cfffe-139">More information</span></span>

- [<span data-ttu-id="cfffe-140">SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式</span><span class="sxs-lookup"><span data-stu-id="cfffe-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="cfffe-141">SharePoint 與團隊：更緊密地合作</span><span class="sxs-lookup"><span data-stu-id="cfffe-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="cfffe-142">共用 OneDrive 檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="cfffe-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="cfffe-143">共用 SharePoint 檔案或資料夾</span><span class="sxs-lookup"><span data-stu-id="cfffe-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
