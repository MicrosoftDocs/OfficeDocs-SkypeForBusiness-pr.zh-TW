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
description: 瞭解如何使用Microsoft Teams目錄搜尋來提供目錄的自訂視圖。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717794"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="af72b-103">使用 Microsoft Teams 限域目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="af72b-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="af72b-104">Microsoft Teams目錄搜尋功能可讓組織建立虛擬邊界，控制使用者如何尋找及與組織中其他使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="af72b-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="af72b-105">Microsoft Teams可讓組織提供目錄的自訂視圖給使用者。</span><span class="sxs-lookup"><span data-stu-id="af72b-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="af72b-106">Microsoft Teams資訊[障礙策略來](/microsoft-365/compliance/information-barriers)支援這些自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="af72b-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="af72b-107">啟用該政策後，搜尋其他使用者 (例如啟動聊天或新增成員至小組) 所返回的結果，將會根據已配置的政策進行範圍。</span><span class="sxs-lookup"><span data-stu-id="af72b-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="af72b-108">當範圍搜尋生效時，使用者將無法搜尋或探索任何團隊，但這些團隊中的現有成員可以新增使用者，如使用中的資訊障礙政策所允許。</span><span class="sxs-lookup"><span data-stu-id="af72b-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="af72b-109">在Exchange環境中，此功能僅適用于Exchange Online信箱，而非內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="af72b-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

<span data-ttu-id="af72b-110">另請參閱在 Exchange Online[中的通訊錄Exchange Online。](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)</span><span class="sxs-lookup"><span data-stu-id="af72b-110">See also [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="af72b-111">何時應該使用範圍目錄搜尋？</span><span class="sxs-lookup"><span data-stu-id="af72b-111">When should you use scoped directory searches?</span></span>

<span data-ttu-id="af72b-112">從範圍目錄搜尋獲益的情境與通訊錄策略案例類似。</span><span class="sxs-lookup"><span data-stu-id="af72b-112">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="af72b-113">例如，您可能會想要在下列情況下使用範圍目錄搜尋：</span><span class="sxs-lookup"><span data-stu-id="af72b-113">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="af72b-114">貴組織的租用戶中有多家公司，您想要將其分開。</span><span class="sxs-lookup"><span data-stu-id="af72b-114">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="af72b-115">學校需要限制教職員與學生之間的交談。</span><span class="sxs-lookup"><span data-stu-id="af72b-115">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="af72b-116">若要瞭解如何使用通訊錄政策，請參閱在 Exchange Online 中[的資訊Exchange Online。](/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="af72b-116">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af72b-117">通訊錄原則僅提供使用者與目錄的虛擬分隔。</span><span class="sxs-lookup"><span data-stu-id="af72b-117">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="af72b-118">此外，請注意，在強制執行新的或更新的通訊錄政策之前，任何已緩存的使用者資料，都會在最多 30 天內可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="af72b-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="af72b-119">開啟範圍目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="af72b-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="af72b-120">使用資訊隔層策略將貴組織設定為虛擬子組。</span><span class="sxs-lookup"><span data-stu-id="af72b-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="af72b-121">詳細資訊，請參閱定義 [資訊障礙政策](/microsoft-365/compliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="af72b-121">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="af72b-122">在 Microsoft Teams系統管理中心中，選取整個 **組織** 範圍的設定  >  **Teams設定**。</span><span class="sxs-lookup"><span data-stu-id="af72b-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="af72b-123">在 **搜尋** 下，在 Teams 中使用 Exchange 通訊錄 **(搜尋** 範圍目錄) ，開啟 **切換開關**。</span><span class="sxs-lookup"><span data-stu-id="af72b-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![系統管理中心中的Microsoft Teams目錄搜尋](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="af72b-125">此變更可能需要數小時才能複製。</span><span class="sxs-lookup"><span data-stu-id="af72b-125">This change can take a few hours to replicate.</span></span>
