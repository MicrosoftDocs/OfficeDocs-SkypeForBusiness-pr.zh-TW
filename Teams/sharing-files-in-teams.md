---
title: 在 Microsoft Teams 中共用檔案和資料夾
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
description: 瞭解 Microsoft Teams 中的檔案和資料夾共用體驗。
ms.openlocfilehash: 53997f4493a0217e980427ab0d1f85d64095b9c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117021"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="a950f-103">在 Microsoft Teams 中共用檔案</span><span class="sxs-lookup"><span data-stu-id="a950f-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="a950f-104">在 Microsoft Teams 中，使用者可以與組織內外的其他 Teams 使用者共用內容。</span><span class="sxs-lookup"><span data-stu-id="a950f-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="a950f-105">在 Teams 中共用檔案和資料夾是以 SharePoint 和 OneDrive 中設定設定為基礎，因此您為 SharePoint 和 OneDrive 所設定的任何專案也會影響 Teams 中的共用。</span><span class="sxs-lookup"><span data-stu-id="a950f-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="a950f-106">概觀</span><span class="sxs-lookup"><span data-stu-id="a950f-106">Overview</span></span>

<span data-ttu-id="a950f-107">使用者可以從 OneDrive、他們存取的團隊和網站，以及從電腦共用檔案。</span><span class="sxs-lookup"><span data-stu-id="a950f-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="a950f-108">若要共用檔案，使用者可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a950f-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="a950f-109">在頻道中，按一下 [附加 (形針圖示) ，選取 [最近使用、流覽Teams 和頻道 **、OneDrive** 或從電腦上傳，然後選擇他們想要共用檔案。 </span><span class="sxs-lookup"><span data-stu-id="a950f-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="a950f-110">![顯示從頻道共用檔案的螢幕擷取畫面](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="a950f-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="a950f-111">在聊天中，按一下[附加 (剪貼圖示) 、選取或 **選取 [OneDrive** 或從我的電腦上傳」，然後選擇他們想要共用檔案。</span><span class="sxs-lookup"><span data-stu-id="a950f-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="a950f-112">![顯示從聊天共用檔案的螢幕擷取畫面](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="a950f-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="a950f-113">複製並貼上撰寫方塊中的共用連結。</span><span class="sxs-lookup"><span data-stu-id="a950f-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="a950f-114">![在撰寫方塊中顯示檔案預覽的螢幕擷取畫面](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="a950f-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="a950f-115">共用檔案和共用連結的許可權</span><span class="sxs-lookup"><span data-stu-id="a950f-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="a950f-116">當使用者從 Teams 中共用檔案時，他們可以設定誰可以存取檔案，就像他們跨 Microsoft 365 一樣。</span><span class="sxs-lookup"><span data-stu-id="a950f-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="a950f-117">他們可以提供任何人、貴組織人員、現有存取權人員或特定人員 (其中可包含 1：1 聊天、群組聊天或頻道) 。</span><span class="sxs-lookup"><span data-stu-id="a950f-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="a950f-118">共用檔案時，郵件中會提供檔案預覽，以及所有檔案動作 ，例如開啟 **線上**、下載及 **複製連結**。 </span><span class="sxs-lookup"><span data-stu-id="a950f-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="a950f-119">根據預設，檔案會在 Teams 中開啟。</span><span class="sxs-lookup"><span data-stu-id="a950f-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="a950f-120">當使用者在聊天或頻道中共用檔案時，系統將會通知他們是否有部分或所有收件者沒有許可權來查看檔案。</span><span class="sxs-lookup"><span data-stu-id="a950f-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="a950f-121">他們可以在共用檔案之前先變更檔案的許可權，方法是按一下現在出現在郵件中的檔案預覽旁的箭箭。</span><span class="sxs-lookup"><span data-stu-id="a950f-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![如果收件者沒有許可權，通知的螢幕擷取畫面](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="a950f-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="a950f-123">Related topics</span></span>

[<span data-ttu-id="a950f-124">SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動</span><span class="sxs-lookup"><span data-stu-id="a950f-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="a950f-125">變更網站的預設連結類型</span><span class="sxs-lookup"><span data-stu-id="a950f-125">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

[<span data-ttu-id="a950f-126">在團隊中與來賓共同合作</span><span class="sxs-lookup"><span data-stu-id="a950f-126">Collaborate with guests in a team</span></span>](/microsoft-365/solutions/collaborate-as-team)