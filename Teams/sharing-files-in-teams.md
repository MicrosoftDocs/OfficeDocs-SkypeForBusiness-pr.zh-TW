---
title: 在 Microsoft 團隊中共用檔案和資料夾
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: 瞭解 Microsoft 團隊中的檔案和資料夾共用體驗。
ms.openlocfilehash: 5b6847c42f13701e289b2efaad4a5489351f339b
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795771"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="220e1-103">在 Microsoft 團隊中共用檔案</span><span class="sxs-lookup"><span data-stu-id="220e1-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="220e1-104">在 Microsoft 團隊中，使用者可以與組織內部和外部的其他團隊使用者共用內容。</span><span class="sxs-lookup"><span data-stu-id="220e1-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="220e1-105">[在團隊中共用檔案和資料夾] 是以 SharePoint 和 OneDrive 中設定的設定為基礎，因此您針對 SharePoint 和 OneDrive 所做的任何設定，都會影響團隊中的共用功能。</span><span class="sxs-lookup"><span data-stu-id="220e1-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="220e1-106">概觀</span><span class="sxs-lookup"><span data-stu-id="220e1-106">Overview</span></span>

<span data-ttu-id="220e1-107">使用者可以從 OneDrive、他們有權存取的小組和網站，以及從他們的電腦上共用檔案。</span><span class="sxs-lookup"><span data-stu-id="220e1-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="220e1-108">若要共用檔案，使用者可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="220e1-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="220e1-109">在頻道中，按一下 [ **附加** ] (曲別針圖示) ，選取 [ **最近** **]、[流覽團隊和頻道]、[** **OneDrive**] 或 [ **從我的電腦上傳**]，然後選擇他們要共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="220e1-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="220e1-110">![螢幕擷取畫面顯示如何從頻道共用檔案](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="220e1-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="220e1-111">在聊天中，按一下 [ **附加** ] (曲別針圖示) ，選取或 [ **OneDrive** ] 或 [ **從我的電腦上傳**]，然後選擇他們要共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="220e1-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="220e1-112">![螢幕擷取畫面顯示如何從聊天共用檔案](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="220e1-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="220e1-113">在撰寫方塊中複製並貼上共用連結。</span><span class="sxs-lookup"><span data-stu-id="220e1-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="220e1-114">![螢幕擷取畫面顯示撰寫方塊中的檔案預覽](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="220e1-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="220e1-115">共用檔案和共用連結的許可權</span><span class="sxs-lookup"><span data-stu-id="220e1-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="220e1-116">當使用者在團隊中共用檔案時，他們可以設定誰可以存取該檔案，就像在 Microsoft 365 中一樣。</span><span class="sxs-lookup"><span data-stu-id="220e1-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="220e1-117">他們可以將存取權授與您組織中的人員、擁有現有存取權的人員，或特定人員 (，這些人員可以在1:1 聊天、群組聊天或頻道) 中加入人員。</span><span class="sxs-lookup"><span data-stu-id="220e1-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="220e1-118">共用檔案時，會在郵件中提供檔案預覽，以及 **開啟 [線上**]、[ **下載**] 和 [ **複製連結**] 等所有檔案動作。</span><span class="sxs-lookup"><span data-stu-id="220e1-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="220e1-119">根據預設，檔案會在 [團隊] 中開啟。</span><span class="sxs-lookup"><span data-stu-id="220e1-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="220e1-120">當使用者在聊天或頻道中共用檔案時，系統會通知您是否有部分或所有收件者沒有許可權來查看檔案。</span><span class="sxs-lookup"><span data-stu-id="220e1-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="220e1-121">他們可以在共用檔案前，按一下現在出現在郵件中的檔案預覽旁邊的箭號，即可變更該檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="220e1-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![如果收件者沒有許可權，螢幕擷取畫面顯示通知](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="220e1-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="220e1-123">Related topics</span></span>

[<span data-ttu-id="220e1-124">SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式</span><span class="sxs-lookup"><span data-stu-id="220e1-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="220e1-125">變更網站的預設連結類型</span><span class="sxs-lookup"><span data-stu-id="220e1-125">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

[<span data-ttu-id="220e1-126">與團隊中的來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="220e1-126">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)