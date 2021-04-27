---
title: 在建立團隊時規劃 Microsoft 365 群組
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解在 Teams 中規劃 Microsoft 365 群組，包括群組與 Teams 交談&之間的差異，以及 Teams 如何尊重群組命名政策。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 7e93b66f9a7a0abc4dfc2e3484818da28a65f36a
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030043"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="650bd-103">在 Microsoft Teams 中建立團隊時，規劃 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="650bd-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="650bd-104">考慮使用 Microsoft 365 群組或建立團隊時，請考慮團隊會用於哪些用途、誰應擁有存取權限，以及團隊預期會取得什麼成果。</span><span class="sxs-lookup"><span data-stu-id="650bd-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="650bd-105">請特別注意您建立頻道的數量，因為人員可能會因為內容散佈過細而 (過多頻道) 。</span><span class="sxs-lookup"><span data-stu-id="650bd-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="650bd-106">有兩種案例需要討論 Microsoft 365 群組的規劃，以及這些群組對 Microsoft Teams (或) 的影響：</span><span class="sxs-lookup"><span data-stu-id="650bd-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="650bd-107">首先，由於客戶可以在 Groups 中擁有現有的投資，我們目前同時支援公用和私人群組，針對目前支援的成員數目，請參閱 [Microsoft Teams](./limits-specifications-teams.md)的限制和規格。</span><span class="sxs-lookup"><span data-stu-id="650bd-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="650bd-108">如先前所述，您想要使用 Teams 用戶端而非 Microsoft 365 系統管理中心來管理團隊中的人員成員資格。</span><span class="sxs-lookup"><span data-stu-id="650bd-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="650bd-109">根據此案例，如果人員習慣在 Microsoft 365 群組中討論討論，則值得注意的是，群組交談基本上是電子郵件，與 Teams 頻道中的聊天訊息不同。</span><span class="sxs-lookup"><span data-stu-id="650bd-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="650bd-110">教育您的人員瞭解這一差異，並建議他們採用 Teams 中更靈活的聊天訊息格式，而不是使用 Outlook 或 OWA 以電子郵件方式將群組使用電子郵件。</span><span class="sxs-lookup"><span data-stu-id="650bd-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="650bd-111">第二，針對在 Microsoft 365 中尚未定義現有群組的客戶，您可以使用 Microsoft 365 系統管理中心、Teams Web 或桌面用戶端建立群組。</span><span class="sxs-lookup"><span data-stu-id="650bd-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="650bd-112">如先前所述，使用 Teams 用戶端管理 Microsoft 365 群組的所有未來成員資格。</span><span class="sxs-lookup"><span data-stu-id="650bd-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="650bd-113">由於團隊成員資格也會定義 Microsoft 365 群組的成員資格，因此您應該為人員進行這項變更做好準備。</span><span class="sxs-lookup"><span data-stu-id="650bd-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy"></a><span data-ttu-id="650bd-114">Teams 尊重 Microsoft 365 群組命名政策</span><span class="sxs-lookup"><span data-stu-id="650bd-114">Teams respects Microsoft 365 Groups naming policy</span></span>

<span data-ttu-id="650bd-115">當使用者建立或編輯團隊名稱時，系統將會套用系統管理員所設定的任何 Microsoft 365 群組命名原則。</span><span class="sxs-lookup"><span data-stu-id="650bd-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="650bd-116">這包括強制首碼或尾碼，以及排除禁止的字詞等專案。</span><span class="sxs-lookup"><span data-stu-id="650bd-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

<span data-ttu-id="650bd-117">若要深入瞭解，請參閱 [Teams 中的 Microsoft 365 群組命名政策](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="650bd-117">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="650bd-118">下列文章是尋找 Microsoft 365 群組的就緒狀態和採用內容的地方：</span><span class="sxs-lookup"><span data-stu-id="650bd-118">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="650bd-119">在 Outlook 中取得群組的更多功能</span><span class="sxs-lookup"><span data-stu-id="650bd-119">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="650bd-120">使用 Microsoft 365 系統管理中心從 Microsoft 365 群組新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="650bd-120">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="650bd-121">還原已刪除的群組</span><span class="sxs-lookup"><span data-stu-id="650bd-121">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)
