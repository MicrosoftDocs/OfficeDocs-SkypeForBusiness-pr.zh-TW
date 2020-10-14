---
title: Microsoft 365 群組和 Microsoft 團隊
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 瞭解 Microsoft 365 群組與群組成員資格如何與 Microsoft 團隊搭配使用。
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456077"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="fbbb0-103">Microsoft 365 群組和 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="fbbb0-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="fbbb0-104">Microsoft 365 群組是 Microsoft 365 中的跨應用程式成員資格服務。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="fbbb0-105">在基本層面上，Microsoft 365 群組是 Azure Active Directory 中的一個物件，其中包含一份成員清單，以及與相關工作負載耦合，包括 SharePoint 小組網站、共用 Exchange 信箱、Planner 及 Power BI 工作區。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="fbbb0-106">您可以將人員新增或移除至群組，就像在 Active Directory 中的任何其他群組安全物件一樣。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![顯示 Microsoft 365 群組和相關服務的圖表](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="fbbb0-108">根據預設，Microsoft 365 中的使用者可以建立及管理群組。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="fbbb0-109">如需有關 Microsoft 365 群組的詳細資訊，請參閱 [瞭解 microsoft 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) ，以及 [適用于 IT 架構師海報的 microsoft 365 中的群組](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="fbbb0-110">Microsoft 365 群組如何與團隊搭配運作</span><span class="sxs-lookup"><span data-stu-id="fbbb0-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="fbbb0-111">建立小組時，會建立 Microsoft 365 群組以管理團隊成員資格。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="fbbb0-112">群組的相關服務（例如 SharePoint 網站、Power BI 工作區等）是同時建立的。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="fbbb0-113">如果使用者是群組的擁有者，則建立小組的人員可以選擇使用現有的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="fbbb0-114">小組中的每個頻道在文件庫中都有一個獨立的資料夾。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="fbbb0-115">直接在文件庫中建立資料夾，不會在團隊中建立頻道。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="fbbb0-116">在 Outlook 或 SharePoint 中建立 Microsoft 365 群組時，會在 Outlook 中看到群組信箱。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="fbbb0-117">在小組中建立小組時，預設會隱藏群組信箱。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="fbbb0-118">您可以將 [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 與 **HiddenFromExchangeClientsEnabled** 參數搭配使用，以顯示信箱。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-118">You can use the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="fbbb0-119">群組成員資格</span><span class="sxs-lookup"><span data-stu-id="fbbb0-119">Group membership</span></span>

<span data-ttu-id="fbbb0-120">如果您移除團隊的成員，也會從 Microsoft 365 群組中移除。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="fbbb0-121">從群組中移除會立即從團隊用戶端移除團隊和頻道。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="fbbb0-122">如果您使用 Microsoft 365 系統管理中心從群組中移除人員，他們將無法存取其他共同作業的內容，例如 SharePoint Online 文件庫、Yammer 群組或共用的 OneNote。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="fbbb0-123">不過，他們仍可存取團隊的聊天功能大約兩小時的時間。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="fbbb0-124">作為管理團隊成員的最佳做法，您可以在團隊用戶端新增及移除這些成員，以確保其他群組連線工作負載的許可權更新很快就會發生。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="fbbb0-125">如果您是使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell) 在團隊用戶端 (新增或移除團隊成員，可能需要長達24小時才能反映在團隊中的變更。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="fbbb0-126">刪除群組和小組</span><span class="sxs-lookup"><span data-stu-id="fbbb0-126">Deleting groups and teams</span></span>

<span data-ttu-id="fbbb0-127">刪除 Microsoft 365 群組會移除持續性 Outlook/OWA 交談和團隊會議邀請的信箱別名，並標示要刪除的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="fbbb0-128">在 Outlook 中移除團隊和其效果之間大約需要20分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="fbbb0-129">從小組用戶端刪除小組後，就會立即將其從 [查看] 移至團隊成員的所有人。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="fbbb0-130">如果您移除已在其上啟用團隊功能的 Microsoft 365 群組成員，則在團隊用戶端中針對已移除的人員在團隊用戶端中移除該小組前，可能會有大約兩小時的延遲。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="fbbb0-131">如需群組和小組的相關詳細資料，請參閱  [群組、團隊和 Yammer 的週期選項結束](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) ，以及 [在 Microsoft 團隊中封存或刪除小組](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)。</span><span class="sxs-lookup"><span data-stu-id="fbbb0-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fbbb0-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="fbbb0-132">Related topics</span></span>

[<span data-ttu-id="fbbb0-133">Microsoft 團隊 (影片的基礎) </span><span class="sxs-lookup"><span data-stu-id="fbbb0-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="fbbb0-134">還原已刪除的群組</span><span class="sxs-lookup"><span data-stu-id="fbbb0-134">Restore a deleted Group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)