---
title: Microsoft 365群組和Microsoft Teams
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
description: 瞭解如何使用Microsoft 365群組和群組成員資格Microsoft Teams。
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105239"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="25c9d-103">Microsoft 365群組和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25c9d-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="25c9d-104">Microsoft 365群組是應用程式中的跨應用程式成員資格Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="25c9d-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="25c9d-105">在基本層級，Microsoft 365群組是 Azure Active Directory 中的物件，包含成員清單，並聯結到相關的工作負載，包括 SharePoint 小組網站、共用 Exchange 信箱、Planner 和 Power BI 工作區。</span><span class="sxs-lookup"><span data-stu-id="25c9d-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="25c9d-106">您可以新增或移除人員至群組，就像在 Active Directory 中任何其他群組式安全性物件一樣。</span><span class="sxs-lookup"><span data-stu-id="25c9d-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![顯示群組Microsoft 365相關服務的圖表](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="25c9d-108">根據預設，Microsoft 365使用者可以建立及管理群組。</span><span class="sxs-lookup"><span data-stu-id="25c9d-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="25c9d-109">如需有關群組Microsoft 365，請參閱瞭解 Microsoft 365[群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)和 IT 架構Microsoft 365[中的](teams-architecture-solutions-posters.md#groups-in-microsoft-365)群組。</span><span class="sxs-lookup"><span data-stu-id="25c9d-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="25c9d-110">群組Microsoft 365群組如何使用Teams</span><span class="sxs-lookup"><span data-stu-id="25c9d-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="25c9d-111">當您建立團隊時，會Microsoft 365群組來管理團隊成員資格。</span><span class="sxs-lookup"><span data-stu-id="25c9d-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="25c9d-112">群組的相關服務 ，例如SharePoint網站、Power BI工作區等，會同時建立。</span><span class="sxs-lookup"><span data-stu-id="25c9d-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="25c9d-113">建立團隊的人可以選擇使用現有的Microsoft 365群組，如果他們是該群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="25c9d-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="25c9d-114">團隊中的每個頻道在文件庫中都有個別的資料夾。</span><span class="sxs-lookup"><span data-stu-id="25c9d-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="25c9d-115">直接在文件庫中建立資料夾不會在團隊中建立頻道。</span><span class="sxs-lookup"><span data-stu-id="25c9d-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="25c9d-116">在 Microsoft 365 或 Outlook 中SharePoint群組群組時，群組信箱會顯示在 Outlook。</span><span class="sxs-lookup"><span data-stu-id="25c9d-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="25c9d-117">在 Teams中建立團隊時，群組信箱預設會隱藏。</span><span class="sxs-lookup"><span data-stu-id="25c9d-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="25c9d-118">您可以使用 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 與 **HiddenFromExchangeClientsEnabled** 參數，讓信箱可見。</span><span class="sxs-lookup"><span data-stu-id="25c9d-118">You can use the [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="25c9d-119">群組成員資格</span><span class="sxs-lookup"><span data-stu-id="25c9d-119">Group membership</span></span>

<span data-ttu-id="25c9d-120">如果您移除團隊的成員，他們Microsoft 365群組中移除。</span><span class="sxs-lookup"><span data-stu-id="25c9d-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="25c9d-121">從群組移除會立即從用戶端移除團隊Teams頻道。</span><span class="sxs-lookup"><span data-stu-id="25c9d-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="25c9d-122">如果您使用 Microsoft 365 系統管理中心將人員從群組移除，他們將不再能夠存取其他共同合作層面，例如 SharePoint Online 文件庫、Yammer群組或共用OneNote。</span><span class="sxs-lookup"><span data-stu-id="25c9d-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="25c9d-123">不過，他們仍然可以存取團隊的聊天功能大約兩小時。</span><span class="sxs-lookup"><span data-stu-id="25c9d-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="25c9d-124">作為管理小組成員的最佳作法，請從 Teams 用戶端新增和移除成員，以確保其他群組連接工作負載的許可權更新快速發生。</span><span class="sxs-lookup"><span data-stu-id="25c9d-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="25c9d-125">如果您使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell) ，在 Teams 用戶端 (之外新增或移除小組成員，最多可能需要 24 小時才能在 Teams 中反映變更。</span><span class="sxs-lookup"><span data-stu-id="25c9d-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="25c9d-126">刪除群組和團隊</span><span class="sxs-lookup"><span data-stu-id="25c9d-126">Deleting groups and teams</span></span>

<span data-ttu-id="25c9d-127">刪除Microsoft 365群組會移除永久 Outlook/OWA 交談和 Teams 會議邀請的信箱別名，並SharePoint網站進行刪除。</span><span class="sxs-lookup"><span data-stu-id="25c9d-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="25c9d-128">移除團隊及其對團隊的影響之間大約需要 20 分鐘Outlook。</span><span class="sxs-lookup"><span data-stu-id="25c9d-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="25c9d-129">從用戶端刪除Teams將團隊從所有小組成員的視野中立即移除。</span><span class="sxs-lookup"><span data-stu-id="25c9d-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="25c9d-130">如果您移除已啟用 Teams 功能的 Microsoft 365 群組成員，則團隊在 Teams 用戶端中移除受影響的人員之前，可能會延遲約兩小時。</span><span class="sxs-lookup"><span data-stu-id="25c9d-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="25c9d-131">有關群組和團隊生命週期結束選項的詳細資訊，請參閱群組、[](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)團隊和團隊的生命週期結束選項Yammer及在 Microsoft Teams 中存檔[或刪除Microsoft Teams。](./archive-or-delete-a-team.md)</span><span class="sxs-lookup"><span data-stu-id="25c9d-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](./archive-or-delete-a-team.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="25c9d-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="25c9d-132">Related topics</span></span>

[<span data-ttu-id="25c9d-133">影片Microsoft Teams (基礎) </span><span class="sxs-lookup"><span data-stu-id="25c9d-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="25c9d-134">還原已刪除的群組</span><span class="sxs-lookup"><span data-stu-id="25c9d-134">Restore a deleted Group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)