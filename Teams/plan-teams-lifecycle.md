---
title: 規劃生命週期管理
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，您將了解如何在 Teams 中規劃生命週期管理功能的實作。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6776631ec79f3f5d4f96756f1cf5ee119319171f
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428219"
---
# <a name="plan-for-lifecycle-management-in-teams"></a><span data-ttu-id="2bdae-103">Teams 中的生命週期管理方案</span><span class="sxs-lookup"><span data-stu-id="2bdae-103">Plan for lifecycle management in Teams</span></span>

<span data-ttu-id="2bdae-104">Teams 提供的豐富工具組可以在您組織中實作共同作業的生命週期管理流程。</span><span class="sxs-lookup"><span data-stu-id="2bdae-104">Teams provides a rich set of tools to implement collaboration lifecycle management processes for your organization.</span></span> <span data-ttu-id="2bdae-105">本文將指引 IT 專業人員，透過正確的問題來判斷其生命週期管理的需求，以及使用符合需求的工具。</span><span class="sxs-lookup"><span data-stu-id="2bdae-105">This article guides IT pros through the right questions to determine their requirements for lifecycle management, and the tools to use to meet them.</span></span> 

<span data-ttu-id="2bdae-106">生命週期管理的規劃至關重要，因為這表示您正在建立的方案可以更有效率地完成工作。</span><span class="sxs-lookup"><span data-stu-id="2bdae-106">Planning for lifecycle management is important, because it means you're building a plan to get your work done effectively.</span></span> <span data-ttu-id="2bdae-107">大部分的專案都包含有開始、中期和結束等階段。</span><span class="sxs-lookup"><span data-stu-id="2bdae-107">Most projects consist of a beginning, middle, and end.</span></span> <span data-ttu-id="2bdae-108">Teams 也一樣，但是因為方案的建構和使用方法五花八門，以至於不容易判斷方案目前進行到其生命週期的哪個階段。</span><span class="sxs-lookup"><span data-stu-id="2bdae-108">Teams do too, but they can be constructed and used in such a variety of ways that it's not always obvious which stage of their lifecycle they're in.</span></span> <span data-ttu-id="2bdae-109">對生命週期管理有既定方案，有助於您隨著組織方案的各個階段進程加以追蹤。</span><span class="sxs-lookup"><span data-stu-id="2bdae-109">Having a plan for lifecycle management will help you track your organization's projects as they go through these stages.</span></span>

> [!Tip]
> <span data-ttu-id="2bdae-110">請觀賞下列一段影片以深入了解 Microsoft Teams 中的生命週期：[Microsoft Teams 中的控管、管理和生命週期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="2bdae-110">Watch the following session to learn about more about lifecycle in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>


## <a name="lifecycle-concepts"></a><span data-ttu-id="2bdae-111">生命週期的概念</span><span class="sxs-lookup"><span data-stu-id="2bdae-111">Lifecycle concepts</span></span>

<span data-ttu-id="2bdae-112">下列概念和定義全都會影響您對生命週期管理所做的決定。</span><span class="sxs-lookup"><span data-stu-id="2bdae-112">The following concepts and definitions all affect the decisions you make for lifecycle management.</span></span>

<span data-ttu-id="2bdae-113">**團隊**</span><span class="sxs-lookup"><span data-stu-id="2bdae-113">**Teams**</span></span>

<span data-ttu-id="2bdae-114">_團隊_ 是促進共同作業的人員、內容和工具的集合。</span><span class="sxs-lookup"><span data-stu-id="2bdae-114">A _team_ is a collection of people, content, and tools that facilitate collaboration.</span></span> <span data-ttu-id="2bdae-115">團隊會定義其成員，以及會套用到這些成員的權限和原則。</span><span class="sxs-lookup"><span data-stu-id="2bdae-115">A team defines who its members are, and the permissions and policies that apply to those members.</span></span> <span data-ttu-id="2bdae-116">Teams 的建置基礎為 Microsoft 365 群組，因此 Microsoft 365 群組成員資格的變更會同步處理至該小組。</span><span class="sxs-lookup"><span data-stu-id="2bdae-116">Teams are built on Microsoft 365 Groups, and changes to Microsoft 365 group membership sync to the team.</span></span> <span data-ttu-id="2bdae-117">就像其他 Microsoft 365 群組一樣，小組會在 Microsoft 365 或 Office 365 中自動佈建 Exchange 信箱、SharePoint 網站、OneNote 筆記本和其他資產。</span><span class="sxs-lookup"><span data-stu-id="2bdae-117">Like other Microsoft 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2bdae-118">[深入了解 Microsoft 365 群組](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-118">[Learn more about Microsoft 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<span data-ttu-id="2bdae-119">**頻道**</span><span class="sxs-lookup"><span data-stu-id="2bdae-119">**Channels**</span></span>

<span data-ttu-id="2bdae-120">頻道是團隊實際完成工作的共同作業空間。</span><span class="sxs-lookup"><span data-stu-id="2bdae-120">Channels are the collaboration spaces within a team where the actual work is done.</span></span> <span data-ttu-id="2bdae-121">每個頻道代表整個團隊中不同的主題或工作流程。</span><span class="sxs-lookup"><span data-stu-id="2bdae-121">Each channel represents a different topic or workstream within the overall team.</span></span> <span data-ttu-id="2bdae-122">針對每個頻道，系統會自動在 SharePoint 網站上建立一個資料夾，儲存該頻道共用的所有檔案，讓使用者能夠輕鬆尋找及處理他們所關注的文件。</span><span class="sxs-lookup"><span data-stu-id="2bdae-122">For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about.</span></span> <span data-ttu-id="2bdae-123">您也可以使用與特定工作流程相關的應用程式來擴充頻道，例如，您可以將 Power BI 儀表板新增至頻道，追蹤專案某一層面的成功。</span><span class="sxs-lookup"><span data-stu-id="2bdae-123">Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.</span></span>

<span data-ttu-id="2bdae-124">**團隊存取類型**</span><span class="sxs-lookup"><span data-stu-id="2bdae-124">**Team access types**</span></span>

<span data-ttu-id="2bdae-125">這些設定決定誰可以加入團隊：</span><span class="sxs-lookup"><span data-stu-id="2bdae-125">These determine who can join the team:</span></span>

-   <span data-ttu-id="2bdae-126">_私人_ 團隊限團隊擁有者核准的團隊成員。</span><span class="sxs-lookup"><span data-stu-id="2bdae-126">_Private_ teams are restricted to team members approved by the team owner(s).</span></span> <span data-ttu-id="2bdae-127">這是大型組織中專案團隊和虛擬團隊的標準設定。</span><span class="sxs-lookup"><span data-stu-id="2bdae-127">This is a typical setting for project teams and virtual teams in a large organization.</span></span>
-   <span data-ttu-id="2bdae-128">_公開_ 團隊對組織中的任何人開放，任何人都能直接加入。</span><span class="sxs-lookup"><span data-stu-id="2bdae-128">_Public_ teams are open for anyone in the organization to join directly.</span></span> <span data-ttu-id="2bdae-129">這項設定對於在不同專案中工作的不同部門人員、針對一般興趣的主題進行共同作業時非常有用。</span><span class="sxs-lookup"><span data-stu-id="2bdae-129">This is useful for collaboration on topics of general interest to people in different departments working on different projects.</span></span> <span data-ttu-id="2bdae-130">這是非常適合小型組織的預設設定。</span><span class="sxs-lookup"><span data-stu-id="2bdae-130">This is a good default setting for smaller organizations.</span></span>

<span data-ttu-id="2bdae-131">**團隊使用者類型和系統管理員角色**</span><span class="sxs-lookup"><span data-stu-id="2bdae-131">**Team user types and admin roles**</span></span> 

<span data-ttu-id="2bdae-132">團隊使用者類型決定團隊成員擁有的控制權：</span><span class="sxs-lookup"><span data-stu-id="2bdae-132">Team user types determine how much control a team member has:</span></span>

-   <span data-ttu-id="2bdae-133">*團隊建立者* 擁有可以在目錄中建立群組或團隊的權限。</span><span class="sxs-lookup"><span data-stu-id="2bdae-133">*Team creator* has permissions to create a group or team in the directory.</span></span> <span data-ttu-id="2bdae-134">系統管理員可以將此使用者類型限制為系統管理員或使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="2bdae-134">The admin can constrain this user type to a subset of admins or users.</span></span> <span data-ttu-id="2bdae-135">如需詳細資訊，請參閱[管理能建立 Microsoft 365 群組的使用者](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-135">For more information, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span> <span data-ttu-id="2bdae-136">小組建立者會自動成為小組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="2bdae-136">Team creators automatically become an owner of the team.</span></span>
-   <span data-ttu-id="2bdae-137">*團隊擁有者* 管理團隊的成員資格和設定。</span><span class="sxs-lookup"><span data-stu-id="2bdae-137">*Team owner* manages membership and settings for the team.</span></span> <span data-ttu-id="2bdae-138">每個團隊最多可以有 100 位團隊擁有者。</span><span class="sxs-lookup"><span data-stu-id="2bdae-138">There can be as many as 100 team owners per team.</span></span>
-   <span data-ttu-id="2bdae-139">*團隊成員* 是參與團隊的組織成員。</span><span class="sxs-lookup"><span data-stu-id="2bdae-139">*Team member* is a member of your organization who participates in a team.</span></span>
-   <span data-ttu-id="2bdae-140">*來賓* 是組織外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="2bdae-140">*Guest* is a user who's external to your organization.</span></span> <span data-ttu-id="2bdae-141">如果您的組織已啟用[來賓存取](guest-access.md)，則擁有電子郵件地址的任何人都可以受邀成為來賓。</span><span class="sxs-lookup"><span data-stu-id="2bdae-141">Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).</span></span>

> [!Note]
> <span data-ttu-id="2bdae-142">若要深入了解團隊擁有者和團隊成員的能力，請參閱[在 Microsoft Teams 中指派角色和權限](assign-roles-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-142">You can learn more about team owner and team member capabilities in the article [Assign role and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>

<span data-ttu-id="2bdae-143">Teams 系統管理員角色決定每個系統管理員角色持有者所擁有的能力。</span><span class="sxs-lookup"><span data-stu-id="2bdae-143">Teams admin roles determine what capabilities each admin role holder has.</span></span> <span data-ttu-id="2bdae-144">下表將說明這些角色。</span><span class="sxs-lookup"><span data-stu-id="2bdae-144">These are described in the following table.</span></span>

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%"><span data-ttu-id="2bdae-145">角色&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="2bdae-145">Role&nbsp;&nbsp;</span></span></th>
    <th width="25%"><span data-ttu-id="2bdae-146">說明</span><span class="sxs-lookup"><span data-stu-id="2bdae-146">Description</span></span></th>
    <th width="60%"><span data-ttu-id="2bdae-147">可以使用標註的工具執行下列工作</span><span class="sxs-lookup"><span data-stu-id="2bdae-147">Can do the following tasks, using tools as noted</span></span></th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><span data-ttu-id="2bdae-148">Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2bdae-148">Teams Administrator</span></span></td>
    <td valign="top"><span data-ttu-id="2bdae-149">管理 Teams 服務，建立和管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="2bdae-149">Manage the Teams service, and create and manage Microsoft 365 Groups</span></span></td>
    <td valign="top"><span data-ttu-id="2bdae-150">管理會議，包括會議原則、組態和會議橋接器<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-150">Manage meetings, including meeting policies, configurations, and conference bridges<sup>1</sup></span></span><br><br><span data-ttu-id="2bdae-151">管理語音，包括通話原則、電話號碼的庫存和指派、通話佇列以及自動語音應答<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-151">Manage voice, including calling policies, phone number inventory and assignment, call queues, and auto attendants<sup>1</sup></span></span><br><br><span data-ttu-id="2bdae-152">管理訊息，包括訊息原則<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-152">Manage messaging, including messaging policies<sup>1</sup></span></span><br><br><span data-ttu-id="2bdae-153">管理所有的全組織設定，包括同盟、Teams 升級和 Teams 用戶端設定<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-153">Manage all org-wide settings, including federation, Teams upgrade, and Teams client settings<sup>1</sup></span></span><br><br><span data-ttu-id="2bdae-154">管理組織中的團隊及其相關設定，包括成員資格<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-154">Manage the teams in the organization and their associated settings, including membership<sup>2</sup></span></span><br><br><span data-ttu-id="2bdae-155">透過使用進階的疑難排解工具組<sup>3</sup>，檢視使用者設定檔頁面，並針對使用者通話品質問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="2bdae-155">View the user profile page and troubleshoot user call quality problems by using advanced troubleshooting toolset<sup>3</sup></span></span></td>
</tr>
<tr>
<td valign="top" colspan="2"><span data-ttu-id="2bdae-156">Teams 通訊系統管理員</span><span class="sxs-lookup"><span data-stu-id="2bdae-156">Teams Communications Administrator</span></span></td>
<td valign="top"><span data-ttu-id="2bdae-157">管理 Microsoft Teams 服務內的通話和會議功能</span><span class="sxs-lookup"><span data-stu-id="2bdae-157">Manage calling and meetings features within the Microsoft Teams service</span></span></td>
<td valign="top"><span data-ttu-id="2bdae-158">管理會議，包括會議原則、組態和會議橋接器<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-158">Manage meetings, including meeting policies, configurations, and conference bridges<sup>1</sup></span></span><br><br><span data-ttu-id="2bdae-159">管理語音，包括通話原則、電話號碼的庫存和指派、通話佇列以及自動語音應答<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-159">Manage voice, including calling policies, phone number inventory and assignment, call queues, and auto attendants<sup>1</sup></span></span><br><br><span data-ttu-id="2bdae-160">透過使用進階的疑難排解工具組<sup>1</sup>，檢視使用者設定檔頁面，並針對使用者通話品質問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="2bdae-160">View user profile page and troubleshoot user call quality problems using advanced troubleshooting toolset<sup>1</sup></span></span></td>
</tr>
<tr>
<td valign="top" colspan="2"><span data-ttu-id="2bdae-161">Teams 通訊專家</span><span class="sxs-lookup"><span data-stu-id="2bdae-161">Teams Communications Specialist</span></span></td>
<td valign="top"><span data-ttu-id="2bdae-162">使用基本工具在 Teams 內針對通訊問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="2bdae-162">Troubleshoot communications issues within Teams by using basic tools</span></span></td>
<td valign="top"><span data-ttu-id="2bdae-163">存取使用者設定檔頁面，以便在通話分析中針對通話進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="2bdae-163">Access to the user profile page for troubleshooting calls in Call Analytics.</span></span> <span data-ttu-id="2bdae-164">針對搜尋所得的特定使用者，僅能檢視使用者資訊。<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-164">Can only view user information for the specific user being searched for.<sup>3</sup></span></span></td>
</tr>
<tr>
<td valign="top" colspan="2"><span data-ttu-id="2bdae-165">Teams 通訊支援工程師</span><span class="sxs-lookup"><span data-stu-id="2bdae-165">Teams Communications Support Engineer</span></span></td>
<td valign="top"><span data-ttu-id="2bdae-166">使用進階工具針對 Teams 內的通訊問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="2bdae-166">Troubleshoot communications issues within Teams by using advanced tools</span></span></td>
<td valign="top"><span data-ttu-id="2bdae-167">存取使用者設定檔頁面，以便在通話分析中針對通話進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="2bdae-167">Access to the user profile page for troubleshooting calls in Call Analytics.</span></span> <span data-ttu-id="2bdae-168">可以檢視完整的通話記錄資訊。<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-168">Can view the full call record information.<sup>3</sup></span></span></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><span data-ttu-id="2bdae-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-169"><sup>1</sup></span></span></td><td colspan="3"><span data-ttu-id="2bdae-170"><a href="/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell - 商務用 Skype 模組</a>或 <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 系統管理中心</a></span><span class="sxs-lookup"><span data-stu-id="2bdae-170"><a href="/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell—Skype for Business module</a> or <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams admin center</a></span></span></td></tr>
<tr><td align="right"><span data-ttu-id="2bdae-171"><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-171"><sup>2</sup></span></span></td><td colspan="3"><span data-ttu-id="2bdae-172"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell - Microsoft Teams 模組</a>或 <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 系統管理中心</a></span><span class="sxs-lookup"><span data-stu-id="2bdae-172"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell—Microsoft Teams module</a> or <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams admin center</a></span></span></td></tr>
<tr><td align="right"><span data-ttu-id="2bdae-173"><sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2bdae-173"><sup>3</sup></span></span></td><td colspan="3"><span data-ttu-id="2bdae-174">僅 <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 系統管理中心</a></span><span class="sxs-lookup"><span data-stu-id="2bdae-174"><a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams admin center</a> only</span></span></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a><span data-ttu-id="2bdae-175">開始使用前必須做出的 IT 決策</span><span class="sxs-lookup"><span data-stu-id="2bdae-175">IT decisions to make before getting started</span></span>

<span data-ttu-id="2bdae-176">在向組織推出 Teams 前，請先實作組織已決定為必要的任何控管原則。</span><span class="sxs-lookup"><span data-stu-id="2bdae-176">Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires.</span></span> <span data-ttu-id="2bdae-177">這些原則包括如命名慣例、到期原則、保留原則等項目。</span><span class="sxs-lookup"><span data-stu-id="2bdae-177">These can include items like naming conventions, expiration policies, retention policies, and more.</span></span> <span data-ttu-id="2bdae-178">一般來說，在組織內擴大部署之前實作這些需求會較為容易。</span><span class="sxs-lookup"><span data-stu-id="2bdae-178">Generally speaking, it's much easier to implement these requirements prior to scaling your deployment across your organization.</span></span>

<span data-ttu-id="2bdae-179">如需詳細資訊，請參閱 [Teams 中的控管方案](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-179">For more information, see [Plan for governance in Teams](plan-teams-governance.md).</span></span>

## <a name="teams-lifecycle-stages"></a><span data-ttu-id="2bdae-180">Teams 生命週期階段</span><span class="sxs-lookup"><span data-stu-id="2bdae-180">Teams lifecycle stages</span></span>

<span data-ttu-id="2bdae-p114">一般來說，團隊的目的與專案一致或與完成目標有關。即使團隊是根據共同的興趣而形成，團隊的成員資格可能會隨著時間而有所變更，討論內容顯得陳舊過時，只是在不同的團隊中以稍微不同的方式再次呈現。</span><span class="sxs-lookup"><span data-stu-id="2bdae-p114">Generally speaking, a team has a purpose that's aligned with a project or accomplishing a goal. Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.</span></span>

<span data-ttu-id="2bdae-183">每個團隊都有開始，就是團隊建立和頻道設定的時候；中期時，團隊會被使用且共同作業會發生以符合工作流程的節奏；接著 (有時) 是結束，團隊會完成其目的並到達使用期限的終點。</span><span class="sxs-lookup"><span data-stu-id="2bdae-183">Each team has a beginning, when the team is created and the channels are set up; a middle, when the team is used and collaboration occurs to match the rhythm of the workflow; and—sometimes—an end, when the team has completed its purpose and reached the end of its useful life.</span></span> 

<span data-ttu-id="2bdae-184">如需詳細資訊，請參閱[在 Microsoft Teams 系統管理中心管理團隊](manage-teams-in-modern-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-184">For more information, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="stage-1-beginning"></a><span data-ttu-id="2bdae-185">階段 1：開始</span><span class="sxs-lookup"><span data-stu-id="2bdae-185">Stage 1: Beginning</span></span>

#### <a name="create-the-team"></a><span data-ttu-id="2bdae-186">建立團隊</span><span class="sxs-lookup"><span data-stu-id="2bdae-186">Create the team</span></span>

<span data-ttu-id="2bdae-187">第一個步驟是定義團隊的目標 (範圍可從商務流程到組織結構再到專案，或者只是建立開放、未結構化的共同作業中心)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-187">The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub).</span></span> <span data-ttu-id="2bdae-188">定義團隊的目標與找出正確的人員有密不可分的關係。</span><span class="sxs-lookup"><span data-stu-id="2bdae-188">Defining the team goal goes hand in hand with identifying the right people.</span></span> <span data-ttu-id="2bdae-189">在可行的情況下，透過以廣泛成員資格為目標來促進開放式共同作業不失為一個好方法。</span><span class="sxs-lookup"><span data-stu-id="2bdae-189">As far as practicable, it's a good idea to foster open collaboration by aiming for broad membership.</span></span> 

<span data-ttu-id="2bdae-190">團隊擁有者可以邀請團隊成員、設定團隊圖片和說明，以及設定個別成員的權限。</span><span class="sxs-lookup"><span data-stu-id="2bdae-190">Team owners invite team members, set the team picture and description, and can set permissions for individual members.</span></span> 

> [!Tip]
>  <span data-ttu-id="2bdae-191">為顧及缺席或重新指派的情形，最佳做法是找出至少兩位團隊擁有者。</span><span class="sxs-lookup"><span data-stu-id="2bdae-191">It's optimal to identify at least two team owners, to account for absence or reassignment.</span></span>

#### <a name="team-origins"></a><span data-ttu-id="2bdae-192">團隊來源</span><span class="sxs-lookup"><span data-stu-id="2bdae-192">Team origins</span></span>

<span data-ttu-id="2bdae-193">團隊來源可以有各種不同的方法，包括：</span><span class="sxs-lookup"><span data-stu-id="2bdae-193">Teams can originate from a variety of methods, including:</span></span>

-   <span data-ttu-id="2bdae-p116">從頭開始建立團隊。使用個人的電子郵件別名或使用者名稱新增成員，或是展開通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="2bdae-p116">Create the team from scratch. Add members by using individual email aliases or usernames, or expand a distribution list.</span></span>
-   <span data-ttu-id="2bdae-p117">從現有團隊建立團隊，然後使用該團隊的頻道設定和任何應用程式設定做為範本。您也可以選擇性地使用該團隊的成員資格清單。</span><span class="sxs-lookup"><span data-stu-id="2bdae-p117">Create the team from an existing team, and use its channel configuration and any app configuration as a template. You can optionally also use its membership list.</span></span>
-   <span data-ttu-id="2bdae-198">將團隊新增至現有的 Microsoft 365 群組，這樣也可讓團隊存取信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="2bdae-198">Add a team to an existing Microsoft 365 group, which also gives the team access to its mailbox and SharePoint site.</span></span>
-   <span data-ttu-id="2bdae-p118">使用 Microsoft Graph Teams API 或 PowerShell Cmdlet 建立團隊。API 可以根據全域通訊錄的屬性 (例如地區或部門) 或商務流程 (例如客戶參與或教室名冊)，透過程式設計的方式建立團隊。</span><span class="sxs-lookup"><span data-stu-id="2bdae-p118">Use the Microsoft Graph Teams APIs or PowerShell cmdlets to create teams. The APIs can programmatically create teams based on Global Address Book attributes (such as region or department) or business processes (client engagements or classroom rosters, for example).</span></span>

<span data-ttu-id="2bdae-201">請利用下列連結取得更多有關組織團隊的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="2bdae-201">Use these links to get more information about organizing your teams:</span></span>

-   [<span data-ttu-id="2bdae-202">在 Teams 中組織團隊的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2bdae-202">Best practices for organizing teams in Teams</span></span>](best-practices-organizing.md)
-   [<span data-ttu-id="2bdae-203">部署交談、團隊、頻道和應用程式</span><span class="sxs-lookup"><span data-stu-id="2bdae-203">Deploy chat, teams, channels, & apps</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [<span data-ttu-id="2bdae-204">部署會議和研討會</span><span class="sxs-lookup"><span data-stu-id="2bdae-204">Deploy meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
-   [<span data-ttu-id="2bdae-205">部署雲端語音</span><span class="sxs-lookup"><span data-stu-id="2bdae-205">Deploy cloud voice</span></span>](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2bdae-207">決策點</span><span class="sxs-lookup"><span data-stu-id="2bdae-207">Decision points</span></span>|<ul><li><span data-ttu-id="2bdae-208">團隊的目的為何？</span><span class="sxs-lookup"><span data-stu-id="2bdae-208">What's the purpose of the team?</span></span></li><li><span data-ttu-id="2bdae-209">哪些人屬於團隊？</span><span class="sxs-lookup"><span data-stu-id="2bdae-209">Who belongs on the team?</span></span></li><li><span data-ttu-id="2bdae-210">小組是私人還是公開的？</span><span class="sxs-lookup"><span data-stu-id="2bdae-210">Will the team be private or public?</span></span></li><li><span data-ttu-id="2bdae-211">新成員可以自行加入，還是須由小組擁有者將其加入？</span><span class="sxs-lookup"><span data-stu-id="2bdae-211">Can new members add themselves or do team owners add them?</span></span></li><li><span data-ttu-id="2bdae-212">哪些人擁有可以建立頻道或新增索引標籤、Bot 和連接器的權限？</span><span class="sxs-lookup"><span data-stu-id="2bdae-212">Who will have permissions to create channels or add tabs, bots, and connectors?</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2bdae-214">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bdae-214">Next steps</span></span>|<ul><li><span data-ttu-id="2bdae-215">建立團隊。</span><span class="sxs-lookup"><span data-stu-id="2bdae-215">Create the team.</span></span></li><li><span data-ttu-id="2bdae-216">規劃頻道。</span><span class="sxs-lookup"><span data-stu-id="2bdae-216">Plan for channels.</span></span></li></ul>|


#### <a name="set-up-channels"></a><span data-ttu-id="2bdae-217">設定頻道</span><span class="sxs-lookup"><span data-stu-id="2bdae-217">Set up channels</span></span>

<span data-ttu-id="2bdae-218">任何擁有適當權限的團隊擁有者或成員都能在團隊中建立頻道。</span><span class="sxs-lookup"><span data-stu-id="2bdae-218">Any team owner or member with appropriate permissions can create channels in a team.</span></span> <span data-ttu-id="2bdae-219">請務必將每個頻道的目標納入考量，您的選項包括有與專案相關的共同作業、主題的討論或共同興趣的領域等。</span><span class="sxs-lookup"><span data-stu-id="2bdae-219">It's important to consider the goal of each channel—options include collaboration around projects, discussions of topics, or areas of common interest.</span></span> <span data-ttu-id="2bdae-220">依預設，每個團隊都包含有 [一般] 頻道；大部分團隊的需求不只這一個，因此成員會建立額外的頻道。</span><span class="sxs-lookup"><span data-stu-id="2bdae-220">By default, every team includes a General channel; most teams need more than this, and members will create additional channels.</span></span> <span data-ttu-id="2bdae-221">頻道組很可能會隨著新主題或專案的提出而蓬勃發展，討論的成長比成員剛加入頻道時更為快速。</span><span class="sxs-lookup"><span data-stu-id="2bdae-221">It's likely that the set of channels will grow organically as new topics or projects arise, and discussions might outgrow the channel they began in.</span></span>

<span data-ttu-id="2bdae-222">為引起興趣，頻道擁有者可以張貼歡迎訊息，將相關文件上傳至 [檔案] 索引標籤，或是在頻道中新增索引標籤或連接器。</span><span class="sxs-lookup"><span data-stu-id="2bdae-222">To spark interest, the channel owner can post a welcome message, upload relevant documents to the **Files** tab, or add tabs or connectors to the channel.</span></span> <span data-ttu-id="2bdae-223">擁有者也可以設定頻道的描述，可以將重要頻道「自動加入我的最愛」，使這些頻道能夠依預設對所有團隊成員列出。</span><span class="sxs-lookup"><span data-stu-id="2bdae-223">The owner also sets the channel description, and can "auto-favorite" important channels so they're listed by default for all team members.</span></span>

<span data-ttu-id="2bdae-224">建立頻道名稱之前請三思，因爲在小組中重新命名頻道並不會重新命名 SharePoint 文件庫中對應的資料夾，這可能會造成終端使用者混淆。</span><span class="sxs-lookup"><span data-stu-id="2bdae-224">Consider channel names before creating them as renaming a channel in the team will not rename the corresponding folder in the SharePoint document library which can lead to end-user confusion.</span></span> 

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2bdae-226">決策點</span><span class="sxs-lookup"><span data-stu-id="2bdae-226">Decision points</span></span>|<ul><li><span data-ttu-id="2bdae-227">團隊中會新增哪些初始頻道？</span><span class="sxs-lookup"><span data-stu-id="2bdae-227">What initial channels will be added to the team?</span></span></li><li><span data-ttu-id="2bdae-228">如果有的話，系統可以針對新增新頻道提供哪些指引？</span><span class="sxs-lookup"><span data-stu-id="2bdae-228">What guidance, if any, will be provided for adding new channels?</span></span> <span data-ttu-id="2bdae-229">(這些頻道的設定依據是專案、主題或是...？)</span><span class="sxs-lookup"><span data-stu-id="2bdae-229">(Will they be set up by project, by topic, or ...?)</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2bdae-231">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bdae-231">Next steps</span></span>|<ul><li><span data-ttu-id="2bdae-232">建立初始頻道。</span><span class="sxs-lookup"><span data-stu-id="2bdae-232">Create initial channels.</span></span></li><li><span data-ttu-id="2bdae-233">張貼歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="2bdae-233">Post a welcome message.</span></span></li><li><span data-ttu-id="2bdae-234">開始共同作業。</span><span class="sxs-lookup"><span data-stu-id="2bdae-234">Start collaborating.</span></span></li></ul>|

### <a name="stage-2-middle"></a><span data-ttu-id="2bdae-235">階段 2：中期</span><span class="sxs-lookup"><span data-stu-id="2bdae-235">Stage 2: Middle</span></span>

<span data-ttu-id="2bdae-236">隨著團隊合作的開始，團隊的成員資格可能會隨著頻道階層開始演進。</span><span class="sxs-lookup"><span data-stu-id="2bdae-236">As the teamwork begins, the team membership probably begins to evolve, along with the channel hierarchy.</span></span> <span data-ttu-id="2bdae-237">除非團隊需要進行嚴格的控制和鎖定，否則鼓勵深入探索不失為一個好主意，即使探索沒有結果。</span><span class="sxs-lookup"><span data-stu-id="2bdae-237">Unless the team needs to be strictly controlled and locked down, it's a good idea to encourage exploration even if it leads to dead ends.</span></span> <span data-ttu-id="2bdae-238">隨著使用者逐漸熟悉，他們可以試驗使用 \@團隊提及、將頻道標示為我的最愛，以及使用 [一般] 頻道來熟悉張貼功能。</span><span class="sxs-lookup"><span data-stu-id="2bdae-238">As users get more comfortable, they can experiment with \@team mentions, marking channels as favorite, and using the General channel to get comfortable with posting.</span></span> <span data-ttu-id="2bdae-239">每個團隊都是獨一無二的；讓使用情況指引設計的演進。</span><span class="sxs-lookup"><span data-stu-id="2bdae-239">Each team is different; let usage guide the evolution of the design.</span></span> <span data-ttu-id="2bdae-240">透過團隊報告功能監視團隊的使用情況和健康情況。</span><span class="sxs-lookup"><span data-stu-id="2bdae-240">Monitor the usage and health of the team via Teams reporting capabilities.</span></span>

<span data-ttu-id="2bdae-241">信賴、包容和共同作業的精神會蓬勃發展，因為關鍵的群組溝通可以在 Teams 中起始並延續下去。</span><span class="sxs-lookup"><span data-stu-id="2bdae-241">Trust, tolerance, and a spirit of collaboration grow organically as key group communications are initiated and sustained in Teams.</span></span> <span data-ttu-id="2bdae-242">比起一對一交談，團隊成員更加看重群組交談的實用性。</span><span class="sxs-lookup"><span data-stu-id="2bdae-242">Team members see the usefulness of group conversations over one-on-one chats.</span></span> <span data-ttu-id="2bdae-243">個別團隊傾向借助有趣的功能 (如 Giphys 和貼紙) 開發出自己的風格。</span><span class="sxs-lookup"><span data-stu-id="2bdae-243">Individual teams tend to develop their own personality, aided by fun features like Giphys and stickers.</span></span> <span data-ttu-id="2bdae-244">同時，有一點很重要，就是任何時候都不鼓勵惡意或無禮的行為。</span><span class="sxs-lookup"><span data-stu-id="2bdae-244">At the same time, it's important that rogue or rude behavior be discouraged any time it occurs.</span></span>

<span data-ttu-id="2bdae-p124">由於團隊並非一成不變，因此偶爾需要檢查和照料。以下是一些最佳做法：</span><span class="sxs-lookup"><span data-stu-id="2bdae-p124">Because teams are living organisms, they occasionally need to be checked on and cared for. These are some best practices:</span></span>

- <span data-ttu-id="2bdae-247">如果使用率開始往下掉，利用風雲人物維持使用率，同時間可以探索和傳播有創意的新行為。</span><span class="sxs-lookup"><span data-stu-id="2bdae-247">Use champions to sustain usage if it starts to drop, and also to discover and propagate creative new behaviors.</span></span> 
- <span data-ttu-id="2bdae-248">謹慎地管理來賓，確保來賓的存取權在業務需求結束時終止。</span><span class="sxs-lookup"><span data-stu-id="2bdae-248">Manage guests judiciously, making sure their access ends when the business need ends.</span></span>
- <span data-ttu-id="2bdae-249">鼓勵成員將交談討論串與主旨列搭配使用，以改善瀏覽頻道時的可見度和關注度。</span><span class="sxs-lookup"><span data-stu-id="2bdae-249">Encourage members to use threaded conversations with subject lines to improve visibility and attention with scrolling through a channel.</span></span>
- <span data-ttu-id="2bdae-250">讓頻道隨著業務需求而演進，必要時新增新頻道並讓舊頻道逐漸退場 (或者，如果頻道包含敏感性或暫時性資料，您可以根據保留需求，考慮封存或刪除頻道)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-250">Let channels evolve with business needs, adding new ones as necessary and allowing old ones to fade (or consider archiving or deleting them if they contain sensitive or ephemeral data, based on your retention requirements).</span></span>
- <span data-ttu-id="2bdae-251">隨著大型群組或興趣型領域的出現，打造全新的團隊。</span><span class="sxs-lookup"><span data-stu-id="2bdae-251">Carve out new teams as larger groups or interest-based areas emerge.</span></span>
- <span data-ttu-id="2bdae-252">嘗試不同頻道的共同作業，例如與文件相關的頻道會議或索引標籤交談。</span><span class="sxs-lookup"><span data-stu-id="2bdae-252">Try different channel collaborations, such as channel meetings or tab conversations around documents.</span></span>
- <span data-ttu-id="2bdae-253">使用 Microsoft Teams 行動裝置應用程式來提高參與。</span><span class="sxs-lookup"><span data-stu-id="2bdae-253">Use the Microsoft Teams mobile app to increase engagement.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2bdae-255">決策點</span><span class="sxs-lookup"><span data-stu-id="2bdae-255">Decision points</span></span>|<ul><li><span data-ttu-id="2bdae-256">誰負責監視使用情況以找出問題？</span><span class="sxs-lookup"><span data-stu-id="2bdae-256">Who will monitor usage to identify problems?</span></span></li><li><span data-ttu-id="2bdae-257">將使用哪些指標來判斷團隊的健康情況？</span><span class="sxs-lookup"><span data-stu-id="2bdae-257">What metrics will be used to determine whether a team is healthy?</span></span></li><li><span data-ttu-id="2bdae-258">找出任何已到達使用期限的團隊。</span><span class="sxs-lookup"><span data-stu-id="2bdae-258">Identify any teams that have reached the end of their useful life.</span></span></li><li><span data-ttu-id="2bdae-259">找出狀況不良但仍在使用、而需要重整的團隊。</span><span class="sxs-lookup"><span data-stu-id="2bdae-259">Identify unhealthy teams that still serve a purpose but need revitalizing.</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2bdae-261">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bdae-261">Next step</span></span>|<ul><li><span data-ttu-id="2bdae-262">實作一個流程來監視個別團隊的健康情況。</span><span class="sxs-lookup"><span data-stu-id="2bdae-262">Implement a process to monitor individual team health.</span></span></li></ul>|

### <a name="stage-3-end"></a><span data-ttu-id="2bdae-263">階段 3：結束</span><span class="sxs-lookup"><span data-stu-id="2bdae-263">Stage 3: End</span></span>

<span data-ttu-id="2bdae-264">當團隊的工作持續到自然結束，正式告知團隊已結束非常重要。</span><span class="sxs-lookup"><span data-stu-id="2bdae-264">When the work of a team has run its course, it's important to formally acknowledge that it's over.</span></span> <span data-ttu-id="2bdae-265">這樣可以讓團隊成員感覺到團隊已關閉，也可以避免任何人存取過期過時的資訊。</span><span class="sxs-lookup"><span data-stu-id="2bdae-265">This gives team members a sense of closure and also prevents anyone from accessing outdated, stale information.</span></span> <span data-ttu-id="2bdae-266">您可以利用團隊本身來舉辦如事後剖析和執行摘要等的關閉儀式。</span><span class="sxs-lookup"><span data-stu-id="2bdae-266">You can use the team itself to conduct closure rituals like postmortems and executive summaries.</span></span>

<span data-ttu-id="2bdae-267">您可以刪除您知道已不再需要的團隊 (例如專為測試而建立的團隊，或是含有敏感性資料的團隊)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-267">You can delete teams that you know you don't need (for example, a team created purely for testing or a team that contains sensitive data).</span></span> <span data-ttu-id="2bdae-268">實際上，團隊會以「虛刪除」的方式刪除，而 IT 人員最多可以在 30 天內復原。</span><span class="sxs-lookup"><span data-stu-id="2bdae-268">Teams are actually deleted with a "soft delete" that IT can reverse for up to 30 days.</span></span> <span data-ttu-id="2bdae-269">刪除團隊不會影響依照合規性原則而保留的任何交談或內容。</span><span class="sxs-lookup"><span data-stu-id="2bdae-269">Deleting teams doesn't affect any chats or content that were retained in accordance with compliance policies.</span></span> <span data-ttu-id="2bdae-270">頻道也有「虛刪除」，而且可以在刪除後最多 21 天內回復。</span><span class="sxs-lookup"><span data-stu-id="2bdae-270">Channels also have a "soft delete" and can be reversed for up to 21 days after deletion.</span></span> <span data-ttu-id="2bdae-271">刪除頻道並不會刪除 SharePoint 文件庫中的資料夾或內容。</span><span class="sxs-lookup"><span data-stu-id="2bdae-271">Deleting a channel will not delete the folder or its contents from the SharePoint document library.</span></span>

<span data-ttu-id="2bdae-272">除了封存功能之外，您也可以使用到期和保留原則，針對不再使用的團隊或是擁有者已離開組織的團隊，減少這些團隊的曝光率。</span><span class="sxs-lookup"><span data-stu-id="2bdae-272">You can also use expiration and retention policies in addition to archiving capabilities to reduce exposure from teams that aren't active any longer or whose owners have left the organization.</span></span>

<span data-ttu-id="2bdae-273">套用到 Teams 或相關服務（例如 SharePoint）的保留原則，可能會禁止刪除小組。</span><span class="sxs-lookup"><span data-stu-id="2bdae-273">Retention policies applied to Teams or associated services such as SharePoint may prohibit the deletion of teams.</span></span> <span data-ttu-id="2bdae-274">此外，請考慮小組中的內容通常不只是 SharePoint 文件庫中的檔案；其中有交談、Planner 看板、wiki、表單結果、記錄的會議、OneNote 筆記本，以及其他各種內容。</span><span class="sxs-lookup"><span data-stu-id="2bdae-274">Additionally, consider that content in a team is often more than just files in the SharePoint document library; it is conversations, Planner boards, wikis, Forms results, recorded meetings, OneNote notebooks, and various others.</span></span>

<span data-ttu-id="2bdae-275">如需設定到期和保留原則的相關資訊，請參閱 [Microsoft Teams 安全性與合規性概述](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-275">For information about setting up expiration and retention policies, see [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2bdae-277">決策點</span><span class="sxs-lookup"><span data-stu-id="2bdae-277">Decision points</span></span>|<ul><li><span data-ttu-id="2bdae-278">定義團隊生命週期結束的形式。</span><span class="sxs-lookup"><span data-stu-id="2bdae-278">Define what the end of a team's life looks like.</span></span></li><li><span data-ttu-id="2bdae-279">決定是否要保留團隊的內容，以及要保留多久。</span><span class="sxs-lookup"><span data-stu-id="2bdae-279">Decide whether to keep the content of a team available, and for how long.</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2bdae-281">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bdae-281">Next steps</span></span>|<ul><li><span data-ttu-id="2bdae-282">記錄最佳做法和經驗傳承。</span><span class="sxs-lookup"><span data-stu-id="2bdae-282">Document best practices and lessons learned.</span></span></li><li><span data-ttu-id="2bdae-283">封存資料 (如有需要)。</span><span class="sxs-lookup"><span data-stu-id="2bdae-283">Archive data, if necessary.</span></span></li></ul>|

## <a name="related-topics"></a><span data-ttu-id="2bdae-284">相關主題</span><span class="sxs-lookup"><span data-stu-id="2bdae-284">Related topics</span></span>

[<span data-ttu-id="2bdae-285">Teams 的控管快速入門</span><span class="sxs-lookup"><span data-stu-id="2bdae-285">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)
