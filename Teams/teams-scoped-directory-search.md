---
title: 使用 Microsoft 團隊範圍的目錄搜尋
author: LolaJacobsen
ms.author: lolaj
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
- Teams_ITAdmin_Help
description: 瞭解如何使用 Microsoft 團隊範圍的目錄搜尋來提供目錄的自訂視圖。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 068a37af62ea31c53caed8c9dc22feec6fd60ec6
ms.sourcegitcommit: bd9b29cdaa183b1f5cc2d643a5a2d231a56a2c3f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2019
ms.locfileid: "36184797"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="0018c-103">使用 Microsoft 團隊範圍的目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="0018c-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="0018c-104">Microsoft 團隊範圍的目錄搜尋可讓組織建立虛擬邊界, 以控制使用者如何在組織中找到其他使用者並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="0018c-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="0018c-105">Microsoft 團隊可讓組織為使用者提供目錄的自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="0018c-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="0018c-106">Microsoft 團隊使用[Exchange 通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)來支援這些自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="0018c-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="0018c-107">啟用原則後, 搜尋由其他使用者所傳回的結果 (例如, 啟動聊天或將成員新增至團隊) 將會根據設定的原則來設定範圍。</span><span class="sxs-lookup"><span data-stu-id="0018c-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="0018c-108">當作用中的搜尋生效時, 使用者將無法搜尋或探索團隊。</span><span class="sxs-lookup"><span data-stu-id="0018c-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="0018c-109">您何時應該使用範圍的目錄搜尋？</span><span class="sxs-lookup"><span data-stu-id="0018c-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="0018c-110">從範圍目錄搜尋獲益的案例, 與通訊錄原則案例類似。</span><span class="sxs-lookup"><span data-stu-id="0018c-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="0018c-111">例如, 您可能會想在下列情況下使用範圍內的目錄搜尋:</span><span class="sxs-lookup"><span data-stu-id="0018c-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="0018c-112">貴組織在其租使用者中有多個公司, 您想要彼此分隔。</span><span class="sxs-lookup"><span data-stu-id="0018c-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="0018c-113">您的學校想要限制教職員和學生之間的聊天。</span><span class="sxs-lookup"><span data-stu-id="0018c-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="0018c-114">若要瞭解如何使用通訊錄原則, 請參閱[Exchange Online 中的通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="0018c-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0018c-115">通訊錄原則只提供從目錄角度來看使用者的虛擬隔離。</span><span class="sxs-lookup"><span data-stu-id="0018c-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="0018c-116">使用者仍可提供完整的電子郵件地址, 以與其他人發起通訊。</span><span class="sxs-lookup"><span data-stu-id="0018c-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="0018c-117">另外, 請務必注意, 在強制執行新的或更新的通訊錄原則之前, 已進行過快取的任何使用者資料, 都會持續提供給最多30天的使用者。</span><span class="sxs-lookup"><span data-stu-id="0018c-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="0018c-118">開啟作用中的目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="0018c-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="0018c-119">使用通訊錄原則將您的組織設定為虛擬子群組。</span><span class="sxs-lookup"><span data-stu-id="0018c-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="0018c-120">如需詳細資訊, 請參閱[通訊錄原則的程式](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="0018c-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="0018c-121">在 Microsoft [團隊管理中心] 中, 選取 [全**組織性設定** > **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="0018c-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="0018c-122">在 [**搜尋**] 底下, 在**使用 Exchange 通訊錄原則 (APB)** 的 [小組] 中的 [範圍\*\*\*\* 目錄搜尋] 旁, 開啟 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="0018c-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Microsoft 團隊系統管理中心的作用中目錄搜尋範圍](media/teams-scoped-directory-search-image1.png)



