---
title: 使用 Microsoft Teams 限域目錄搜尋
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 範圍目錄搜尋來提供目錄的自訂視圖。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094023"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="a232d-103">使用 Microsoft Teams 限域目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="a232d-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="a232d-104">Microsoft Teams 範圍目錄搜尋可讓組織建立虛擬邊界，控制使用者如何尋找及與組織中其他使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="a232d-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="a232d-105">Microsoft Teams 可讓組織提供目錄的自訂視圖給使用者。</span><span class="sxs-lookup"><span data-stu-id="a232d-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="a232d-106">Microsoft Teams 會 [使用資訊障礙策略](/microsoft-365/compliance/information-barriers) 來支援這些自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="a232d-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="a232d-107">一旦啟用該政策，搜尋其他使用者 (例如啟動聊天或新增成員至小組) 所返回的結果，就會根據已配置的政策進行範圍。</span><span class="sxs-lookup"><span data-stu-id="a232d-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="a232d-108">當範圍搜尋生效時，使用者將無法搜尋或探索任何團隊，但這些團隊中的現有成員可以新增使用者，如使用中的資訊障礙政策所允許。</span><span class="sxs-lookup"><span data-stu-id="a232d-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="a232d-109">在 Exchange 混合式環境中，此功能僅適用于 Exchange Online 信箱，而非內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="a232d-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="a232d-110">何時應該使用範圍目錄搜尋？</span><span class="sxs-lookup"><span data-stu-id="a232d-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="a232d-111">從範圍目錄搜尋獲益的情境與通訊錄策略案例類似。</span><span class="sxs-lookup"><span data-stu-id="a232d-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="a232d-112">例如，您可能會想要在下列情況下使用範圍目錄搜尋：</span><span class="sxs-lookup"><span data-stu-id="a232d-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="a232d-113">貴組織的租用戶中有多家公司，您想要將其分開。</span><span class="sxs-lookup"><span data-stu-id="a232d-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="a232d-114">學校需要限制教職員與學生之間的交談。</span><span class="sxs-lookup"><span data-stu-id="a232d-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="a232d-115">若要瞭解如何使用通訊錄政策，請閱讀 Exchange [Online 的資訊障礙政策](/microsoft-365/compliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="a232d-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a232d-116">通訊錄原則僅提供使用者與目錄的虛擬分隔。</span><span class="sxs-lookup"><span data-stu-id="a232d-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="a232d-117">此外，請注意，在強制執行新的或更新的通訊錄政策之前，任何已緩存的使用者資料，都會在最多 30 天內可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a232d-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="a232d-118">開啟範圍目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="a232d-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="a232d-119">使用資訊隔層策略將貴組織設定為虛擬子組。</span><span class="sxs-lookup"><span data-stu-id="a232d-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="a232d-120">詳細資訊，請參閱定義 [資訊障礙政策](/microsoft-365/compliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="a232d-120">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="a232d-121">在 Microsoft Teams 系統管理中心中，選取 **全組織設定**  >  **Teams 設定**。</span><span class="sxs-lookup"><span data-stu-id="a232d-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="a232d-122">在 **搜尋** 下，在 Teams 中使用 Exchange 通訊錄策略在 Teams 中搜尋範圍目錄 (**ABP**) ，開啟 **切換開關**。</span><span class="sxs-lookup"><span data-stu-id="a232d-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Microsoft Teams 系統管理中心的範圍目錄搜尋](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="a232d-124">此變更可能需要數小時才能複製。</span><span class="sxs-lookup"><span data-stu-id="a232d-124">This change can take a few hours to replicate.</span></span>