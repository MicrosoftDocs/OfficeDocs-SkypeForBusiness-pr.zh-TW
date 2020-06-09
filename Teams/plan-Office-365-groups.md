---
title: 在建立團隊時規劃 Microsoft 365 群組
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解小組中的 Microsoft 365 群組規劃，包括群組 & 小組交談之間的差異，以及團隊如何尊重群組命名原則。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 3c428966f07fc82d37520025ea3526c067003373
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637832"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="c55a0-103">在 Microsoft 團隊中建立小組時規劃 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c55a0-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="c55a0-104">在考慮使用 Microsoft 365 群組或建立小組時，請考慮該小組將用於哪些人員、誰應該擁有存取權，以及小組預期會達到哪些結果。</span><span class="sxs-lookup"><span data-stu-id="c55a0-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="c55a0-105">特別注意的是，您所建立的頻道數量可能會因為內容散佈太窄（超過太多頻道）而逐漸溢出。</span><span class="sxs-lookup"><span data-stu-id="c55a0-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="c55a0-106">有兩種情況可在規劃 Microsoft 365 群組，以及其對（或由） Microsoft 團隊的影響等方面，進行一些討論：</span><span class="sxs-lookup"><span data-stu-id="c55a0-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="c55a0-107">首先，因為客戶可以在群組中擁有現有投資，所以我們目前支援不超過5000成員的公用和私人群組。</span><span class="sxs-lookup"><span data-stu-id="c55a0-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="c55a0-108">如先前所述，您想要使用團隊用戶端（而不是 Office 365 管理員網頁主控台），管理人員至團隊的成員資格。</span><span class="sxs-lookup"><span data-stu-id="c55a0-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Office 365 admin web console.</span></span> <span data-ttu-id="c55a0-109">在此案例中，如果使用者是用來在 Microsoft 365 群組中進行執行緒交談，則值得注意的是，群組交談實質上是電子郵件，而不是團隊頻道中的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="c55a0-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="c55a0-110">在小組中教育您的人員，並建議他們採用更具彈性的聊天訊息格式，而不是使用 Outlook 或 OWA 以電子郵件傳送群組。</span><span class="sxs-lookup"><span data-stu-id="c55a0-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="c55a0-111">其次，對於沒有在 Office 365 中定義之現有群組的客戶，您可以使用 Microsoft 365 系統管理中心、團隊網頁或桌面用戶端來建立它們。</span><span class="sxs-lookup"><span data-stu-id="c55a0-111">Second, for customers who don't have existing Groups defined in Office 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="c55a0-112">如先前所述，您可以使用團隊用戶端管理所有未來的成員資格至 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="c55a0-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="c55a0-113">因為成員資格成為小組，所以也定義了 Microsoft 365 群組的成員資格，所以您應該為人員準備此變更。</span><span class="sxs-lookup"><span data-stu-id="c55a0-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="c55a0-114">小組尊重 Microsoft 365 群組命名原則（在私人預覽中）</span><span class="sxs-lookup"><span data-stu-id="c55a0-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="c55a0-115">當使用者建立或編輯團隊名稱時，系統會在團隊中套用任何由您的系統管理員設定的 Microsoft 365 群組命名原則。</span><span class="sxs-lookup"><span data-stu-id="c55a0-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="c55a0-116">這包括強制性首碼或尾碼之類的內容，以及不含禁止的字。</span><span class="sxs-lookup"><span data-stu-id="c55a0-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="c55a0-117">這項功能是私人預覽，這表示如果您不是此預覽的一部分，小組還不會遵守此 Microsoft 365 群組命名原則。</span><span class="sxs-lookup"><span data-stu-id="c55a0-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="c55a0-118">若要深入瞭解，請參閱[小組中的 Microsoft 365 群組命名原則](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="c55a0-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="c55a0-119">下列文章是尋找 Microsoft 365 群組的準備就緒與採納內容的好地方：</span><span class="sxs-lookup"><span data-stu-id="c55a0-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="c55a0-120">在 Outlook 中取得群組的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="c55a0-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="c55a0-121">使用 Microsoft 365 系統管理中心新增或移除 Microsoft 365 群組中的成員</span><span class="sxs-lookup"><span data-stu-id="c55a0-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="c55a0-122">還原已刪除的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c55a0-122">Restore a deleted Microsoft 365 group</span></span>](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)
