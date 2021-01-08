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
description: 瞭解如何使用 Microsoft 團隊範圍的目錄搜尋來提供目錄的自訂視圖。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779927"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="fc16c-103">使用 Microsoft Teams 限域目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="fc16c-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="fc16c-104">Microsoft 團隊範圍的目錄搜尋可讓組織建立虛擬邊界，以控制使用者如何在組織中找到其他使用者並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="fc16c-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="fc16c-105">Microsoft 團隊可讓組織為使用者提供目錄的自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="fc16c-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="fc16c-106">Microsoft 團隊使用 [資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 來支援這些自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="fc16c-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="fc16c-107">啟用原則後，搜尋由其他使用者所傳回的結果 (例如，啟動聊天或將成員新增至團隊) 將根據設定的原則進行範圍。</span><span class="sxs-lookup"><span data-stu-id="fc16c-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="fc16c-108">當作用中的搜尋生效時，使用者將無法搜尋或探索團隊。</span><span class="sxs-lookup"><span data-stu-id="fc16c-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="fc16c-109">在 Exchange 混合式環境中，這項功能僅適用于 Exchange Online 信箱，不適用於內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="fc16c-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="fc16c-110">您何時應該使用範圍的目錄搜尋？</span><span class="sxs-lookup"><span data-stu-id="fc16c-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="fc16c-111">從範圍目錄搜尋獲益的案例，與通訊錄原則案例類似。</span><span class="sxs-lookup"><span data-stu-id="fc16c-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="fc16c-112">例如，您可能會想在下列情況下使用範圍內的目錄搜尋：</span><span class="sxs-lookup"><span data-stu-id="fc16c-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="fc16c-113">貴組織的租用戶中有多家公司，您想要將其分開。</span><span class="sxs-lookup"><span data-stu-id="fc16c-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="fc16c-114">學校需要限制教職員與學生之間的交談。</span><span class="sxs-lookup"><span data-stu-id="fc16c-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="fc16c-115">若要瞭解如何使用通訊錄原則，請參閱 [Exchange Online 中的資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="fc16c-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc16c-116">通訊錄原則只提供從目錄角度來看使用者的虛擬隔離。</span><span class="sxs-lookup"><span data-stu-id="fc16c-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="fc16c-117">另外，請務必注意，在強制執行新的或更新的通訊錄原則之前，已進行過快取的任何使用者資料，都會持續提供給最多30天的使用者。</span><span class="sxs-lookup"><span data-stu-id="fc16c-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="fc16c-118">開啟作用中的目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="fc16c-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="fc16c-119">使用資訊屏障原則將您的組織設定為虛擬子群組。</span><span class="sxs-lookup"><span data-stu-id="fc16c-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="fc16c-120">如需詳細資訊，請參閱 [定義資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="fc16c-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="fc16c-121">在 Microsoft [團隊管理中心] 中，選取 [全 **組織性設定**  >  **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="fc16c-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="fc16c-122">在 [**搜尋**] 底下，在 **使用 Exchange 通訊錄原則的小組中，[範圍目錄搜尋] 旁 (ABP)**，請開啟 **[開啟]。**</span><span class="sxs-lookup"><span data-stu-id="fc16c-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Microsoft 團隊系統管理中心的作用中目錄搜尋範圍](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="fc16c-124">這項變更可能需要幾個小時才能進行複製。</span><span class="sxs-lookup"><span data-stu-id="fc16c-124">This change can take a few hours to replicate.</span></span>
