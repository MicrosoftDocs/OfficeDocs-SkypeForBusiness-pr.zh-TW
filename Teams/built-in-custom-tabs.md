---
title: 使用內建和自訂的Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
f1.keywords:
- NOCSH
search.appverid: MET150
description: 瞭解如何使用內建和自訂的定位停駐點來包含交談、檔案、地圖等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f98024b10cf6fc191e9225a447903ff6dc25d6ff
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203716"
---
<a name="use-built-in-and-custom-tabs-in-microsoft-teams"></a><span data-ttu-id="09556-103">使用內建和自訂的Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09556-103">Use built-in and custom tabs in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="09556-104">使用定位停駐點，小組成員可以存取頻道或聊天中專用空間中的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="09556-104">Tabs allow team members to access services and content in a dedicated space within a channel or in a chat.</span></span> <span data-ttu-id="09556-105">這可讓小組直接使用工具和資料，並且與工具和資料進行交談，而所有內容都位於頻道或聊天中。</span><span class="sxs-lookup"><span data-stu-id="09556-105">This lets the team work directly with tools and data, and have conversations about the tools and data, all within the context of the channel or chat.</span></span>

<span data-ttu-id="09556-106">擁有者與團隊成員可以在頻道、私人聊天和群組聊天中新增索引標籤，協助整合其雲端服務。</span><span class="sxs-lookup"><span data-stu-id="09556-106">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="09556-107">您可以新增定位停駐點，協助使用者輕鬆存取及管理所需的資料，或與大部分使用者互動。</span><span class="sxs-lookup"><span data-stu-id="09556-107">Tabs can be added to help users easily access and manage the data they need or interact with the most.</span></span> <span data-ttu-id="09556-108">這可以是一個Power BI、儀表板，甚至是[您發佈](https://go.microsoft.com/fwlink/?linkid=855785)訓練影片的 Microsoft Stream 影片頻道。</span><span class="sxs-lookup"><span data-stu-id="09556-108">This can be a Power BI report, a dashboard, or even a [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) video channel where you publish training videos.</span></span>

![三個選項卡中各種內容的螢幕擷取畫面。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image4.png)

>[!Note]
> <span data-ttu-id="09556-p103">從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="09556-p103">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="work-with-tabs"></a><span data-ttu-id="09556-112">使用定位字元</span><span class="sxs-lookup"><span data-stu-id="09556-112">Work with tabs</span></span>

- <span data-ttu-id="09556-113">根據預設，每一個新頻道都會提供兩個選項卡：交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="09556-113">With every new channel, two tabs are provisioned by default: Conversations and Files.</span></span>

    ![行銷小組的交談區段螢幕擷取畫面。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image1.png)
- <span data-ttu-id="09556-115">根據預設，每一個私人聊天都會提供四個選項卡：交談、檔案、組織和活動。</span><span class="sxs-lookup"><span data-stu-id="09556-115">With every private chat, four tabs are provisioned by default: Conversations, Files, Organization, and Activity.</span></span>

    ![聊天中選項卡的螢幕擷取畫面。](media/Use_built-in_and_custom_tabs_add_tabs_to_a_chat.png)

- <span data-ttu-id="09556-117">擁有者和小組成員可以按一下新增 Tab 按鈕的 Tab 螢幕快照，顯示 +符號，以在頻道或聊天中新增 ![ 更多定位停駐點。](media/Use_built-in_and_custom_tabs_add_a_tab_button.png)</span><span class="sxs-lookup"><span data-stu-id="09556-117">Owners and team members can add more tabs to a channel or chat by clicking **Add a tab** ![Screenshot of the Add a tab button, showing a + sign.](media/Use_built-in_and_custom_tabs_add_a_tab_button.png)</span></span> <span data-ttu-id="09556-118">位於頻道或聊天頂端。</span><span class="sxs-lookup"><span data-stu-id="09556-118">at the top of the channel or chat.</span></span>

- <span data-ttu-id="09556-119">Excel、PowerPoint、Word 和 PDF 檔案必須上傳到檔案標籤，才能轉換成定位字元。</span><span class="sxs-lookup"><span data-stu-id="09556-119">Excel, PowerPoint, Word, and PDF files must be uploaded to the **Files** tab before they can be converted to tabs.</span></span> <span data-ttu-id="09556-120">只要按一下即可將任何現有的上傳檔案轉換成定位停駐點，如下所示。</span><span class="sxs-lookup"><span data-stu-id="09556-120">Any existing uploaded file can be converted to a tab with a single click, as shown below.</span></span>

    ![已選取檔案的檔案PowerPoint螢幕擷取畫面。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image2.png)

- <span data-ttu-id="09556-122">若要新增網站，URL 必須以 **HTTPs** 首碼開頭，以便交換的資訊保持安全。</span><span class="sxs-lookup"><span data-stu-id="09556-122">To add a website, the URL must start with an **https** prefix so information that's exchanged remains secure.</span></span>

- <span data-ttu-id="09556-123">當團隊成員嘗試在頻道或聊天中新增自訂定位停駐點時，會提供詳細指示。</span><span class="sxs-lookup"><span data-stu-id="09556-123">Detailed instructions are provided when a team member tries to add a custom tab to their channel or chat.</span></span> <span data-ttu-id="09556-124">將自訂的定位停駐點新加到頻道時，會建立 **Tab** 交談，讓小組成員對內容進行焦點討論。</span><span class="sxs-lookup"><span data-stu-id="09556-124">When a custom tab is added to a channel, a **Tab conversation** is created that allows team members to have focused discussions about the content.</span></span>

    ![右側有定位停駐點交談的自訂定位停駐點螢幕擷取畫面](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image3.png)

## <a name="develop-custom-tabs"></a><span data-ttu-id="09556-126">開發自訂的定位停駐點</span><span class="sxs-lookup"><span data-stu-id="09556-126">Develop custom tabs</span></span>

<span data-ttu-id="09556-127">除了內建的定位停駐點之外，您還可以設計及開發自己的定位停駐點，Teams與社群其他人共用。</span><span class="sxs-lookup"><span data-stu-id="09556-127">In addition to the built-in tabs, you can design and develop your own tabs to integrate to Teams or share with the rest of the community.</span></span> <span data-ttu-id="09556-128">如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/tabs/what-are-tabs)。</span><span class="sxs-lookup"><span data-stu-id="09556-128">See our [developer documentation](/microsoftteams/platform/tabs/what-are-tabs) for more information.</span></span>

![螢幕擷取畫面顯示範例自訂Microsoft Teams。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image5.png)

---
