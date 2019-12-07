---
title: 歡迎使用 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: LolaJ
description: 尋找在組織中推出 Microsoft Teams 的正確途徑。 了解 Teams 基礎結構及使用 Teams 搭配 Office 365。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef56b6e62b39d0ef0d9464c9d24b9b34d17e87cc
ms.sourcegitcommit: 2fd1fcb0e5944f36261e551df04819713d868a11
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2019
ms.locfileid: "39886190"
---
# <a name="welcome-to-microsoft-teams"></a><span data-ttu-id="0be3c-104">歡迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0be3c-104">Welcome to Microsoft Teams</span></span>
<span data-ttu-id="0be3c-105">如果您是組織中 Microsoft Teams 的系統管理員，那您便是正確的人選。</span><span class="sxs-lookup"><span data-stu-id="0be3c-105">If you're the admin for Microsoft Teams in your organization, you're in the right place.</span></span> <span data-ttu-id="0be3c-106">當您準備好開始使用 Teams 時，請從[如何推出 Teams](How-to-roll-out-teams.md) 開始。</span><span class="sxs-lookup"><span data-stu-id="0be3c-106">When you're ready to get going with Teams, start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="0be3c-107">如果您是 Teams 新手，想要深入了解，請查看我們的簡短[歡迎使用 Teams](https://www.youtube.com/embed/s3aQV3T0D6c) 影片 (55 秒)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-107">If you're new to Teams and want to learn more, check out our short [Welcome to Teams](https://www.youtube.com/embed/s3aQV3T0D6c) video (55 seconds).</span></span>

<span data-ttu-id="0be3c-108">請勿錯過我們的 Teams 系統管理員適用的「歡迎使用 Teams」影片 (剛好超過 3 分鐘)：</span><span class="sxs-lookup"><span data-stu-id="0be3c-108">Don't miss our Welcome to Teams for the Teams admin video (just over 3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE47cdp]

<span data-ttu-id="0be3c-109">如果您要尋找使用者 Teams 的說明，請按一下應用程式左側的 [說明]\*\*\*\*，或移至 [Microsoft Teams 說明中心](https://support.office.com/teams)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-109">If you're looking for end user Teams Help, click **Help** on the left side of the app, or go to the [Microsoft Teams help center](https://support.office.com/teams).</span></span> <span data-ttu-id="0be3c-110">如需訓練，請移至 [Microsoft Teams 訓練](training-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-110">For training, go to [Microsoft Teams Training](training-microsoft-teams-landing-page.md).</span></span> 

## <a name="teams-architecture"></a><span data-ttu-id="0be3c-111">Teams 架構</span><span class="sxs-lookup"><span data-stu-id="0be3c-111">Teams architecture</span></span>

<span data-ttu-id="0be3c-112">Teams 的建置基礎為 Office 365 群組、Microsoft Graph，以及與其餘 Office 365 相同的企業層級安全性、合規性和可管理性。</span><span class="sxs-lookup"><span data-stu-id="0be3c-112">Teams is built on Office 365 groups, Microsoft Graph, and the same enterprise-level security, compliance, and manageability as the rest of Office 365.</span></span> <span data-ttu-id="0be3c-113">Teams 會利用儲存在 Azure Active Directory (Azure AD) 中的身分識別。</span><span class="sxs-lookup"><span data-stu-id="0be3c-113">Teams leverages identities stored in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="0be3c-114">即使您離線或遇到時好時壞的網路狀況時，Teams 也會持續運作。</span><span class="sxs-lookup"><span data-stu-id="0be3c-114">Teams keeps working even when you're offline or experiencing spotty network conditions.</span></span>

<span data-ttu-id="0be3c-115">若要查看 Teams 在 Microsoft 365 的內容中適合的位置，請查看此架構海報：[Teams 成為 Microsoft 365 的一部分](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="0be3c-115">To see where Teams fits in the context of Microsoft 365, check out this architecture poster:  [Teams as part of Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span></span>

<span data-ttu-id="0be3c-116">當您建立團隊時，將會建立下列項目：</span><span class="sxs-lookup"><span data-stu-id="0be3c-116">When you create a team, here's what gets created:</span></span>
- <span data-ttu-id="0be3c-117">新的 [Office 365 群組](office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0be3c-117">A new [Office 365 group](office-365-groups.md)</span></span>
- <span data-ttu-id="0be3c-118">用來儲存團隊檔案的 [SharePoint Online](sharepoint-onedrive-interact.md) 網站和文件庫</span><span class="sxs-lookup"><span data-stu-id="0be3c-118">A [SharePoint Online](sharepoint-onedrive-interact.md) site and document library to store team files</span></span>
- <span data-ttu-id="0be3c-119">[Exchange Online](exchange-teams-interact.md) 共用信箱和行事曆</span><span class="sxs-lookup"><span data-stu-id="0be3c-119">An [Exchange Online](exchange-teams-interact.md) shared mailbox and calendar</span></span>
- <span data-ttu-id="0be3c-120">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="0be3c-120">A OneNote notebook</span></span>
- <span data-ttu-id="0be3c-121">綁定至其他 Office 365 應用程式，例如 Planner 和 Power BI</span><span class="sxs-lookup"><span data-stu-id="0be3c-121">Ties into other Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="0be3c-122">當您從現有的群組建立團隊，該群組的成員資格、網站、信箱和筆記本都會顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="0be3c-122">When you create a team from an existing group, that group's membership, site, mailbox, and notebook are surfaced in Teams.</span></span> <span data-ttu-id="0be3c-123">若要深入了解，請查看此海報：[適用於 IT 結構設計師的 Microsoft 365 中的群組](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="0be3c-123">To learn more, check out this poster: [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span></span>

<span data-ttu-id="0be3c-124">若要自訂及延伸 Teams，請透過[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)新增第三方應用程式。</span><span class="sxs-lookup"><span data-stu-id="0be3c-124">To customize and extend Teams, add third-party apps through [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="0be3c-125">有了 Teams，您可以將組織外部的人員[新增為團隊或頻道的來賓](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-125">With Teams, you can include people from outside your organization by [adding them as a guest](guest-access.md) to a team or channel.</span></span> <span data-ttu-id="0be3c-126">Teams 成為 Office 365 的一部分，可提供穩健的[開發平台](https://docs.microsoft.com/microsoftteams/platform)，使得您可以建置組織所需的團隊工作中樞。</span><span class="sxs-lookup"><span data-stu-id="0be3c-126">As part of Office 365, Teams offers a robust [development platform](https://docs.microsoft.com/microsoftteams/platform) so you can build the teamwork hub you need for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="0be3c-127">若要深度剖析 Teams 架構，請觀看 [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy) 上的影片。</span><span class="sxs-lookup"><span data-stu-id="0be3c-127">For a deep dive into Teams architecture, watch the videos on the [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).</span></span>


## <a name="managing-teams"></a><span data-ttu-id="0be3c-128">管理 Teams</span><span class="sxs-lookup"><span data-stu-id="0be3c-128">Managing Teams</span></span>

<span data-ttu-id="0be3c-129">身為系統管理員的您，將透過 Microsoft Teams 系統管理中心來管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="0be3c-129">As the admin, you'll manage Teams through the Microsoft Teams admin center.</span></span> <span data-ttu-id="0be3c-130">若要深入了解：</span><span class="sxs-lookup"><span data-stu-id="0be3c-130">To learn more:</span></span>
- [<span data-ttu-id="0be3c-131">使用 Teams 系統管理員角色來管理 Teams</span><span class="sxs-lookup"><span data-stu-id="0be3c-131">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="0be3c-132">在 Teams 系統管理中心管理 Teams</span><span class="sxs-lookup"><span data-stu-id="0be3c-132">Manage Teams in the Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="0be3c-133">在轉換至新 Teams 系統管理中心期間管理 Teams</span><span class="sxs-lookup"><span data-stu-id="0be3c-133">Manage Teams during the transition to the new Teams admin center</span></span>](manage-teams-in-modern-portal.md)
- [<span data-ttu-id="0be3c-134">在 Office 365 組織中管理 Teams 功能</span><span class="sxs-lookup"><span data-stu-id="0be3c-134">Manage Teams features in your Office 365 organization</span></span>](enable-features-office-365.md)

<span data-ttu-id="0be3c-135">若要掌握 Teams 和組織中所有其他 Office 365 產品和服務即將推出的內容，請務必檢查[訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)和 [Teams 藍圖](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-135">To stay on top of what’s coming for Teams and all other Office 365 products and services in your organization, be sure to check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams).</span></span> <span data-ttu-id="0be3c-136">您會收到有關新功能和更新功能、計劃的變更和問題的公告，以協助您了解並做好準備。</span><span class="sxs-lookup"><span data-stu-id="0be3c-136">You’ll get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.</span></span> 

## <a name="upgrade-from-skype-for-business-to-teams"></a><span data-ttu-id="0be3c-137">從商務用 Skype 升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="0be3c-137">Upgrade from Skype for Business to Teams</span></span>
<span data-ttu-id="0be3c-138">Teams 是 Office 365 中智慧通訊的主要用戶端，最終會取代商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="0be3c-138">Teams is the primary client for intelligent communications in Office 365, and it'll eventually replace Skype for Business Online.</span></span> <span data-ttu-id="0be3c-139">若要掌握 Teams 即將推出的新功能，請參閱 [Microsoft 365 藍圖](https://aka.ms/O365Roadmap)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-139">To stay on top of new features coming to Teams, see the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap).</span></span> <span data-ttu-id="0be3c-140">為了補足持續聊天和傳訊的功能，Teams 提供了全面性的會議和通話體驗，包括內建完全整合的語音和視訊。</span><span class="sxs-lookup"><span data-stu-id="0be3c-140">To complement persistent chat and messaging capabilities, Teams offers a comprehensive meeting and calling experience, with built in, fully integrated voice and video.</span></span> <span data-ttu-id="0be3c-141">請查看 Microsoft Teams 部落格中的 [Teams 現在是完整的會議和通話解決方案](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-141">Check out [Teams is now a complete meeting and calling solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) in the Microsoft Teams Blog.</span></span>

<span data-ttu-id="0be3c-142">如果您是執行商務用 Skype 且準備好要升級為 Teams，或是並行執行商務用 Skype 和 Teams 且準備好要完全移至 Teams，我們有工具、秘訣和指導方針可協助您順利轉換。</span><span class="sxs-lookup"><span data-stu-id="0be3c-142">If you’re running Skype for Business and are ready to upgrade to Teams, or if you’re running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful.</span></span> <span data-ttu-id="0be3c-143">若要深入了解，請參閱[升級至 Teams](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-143">To learn more, see [Upgrade to Teams](upgrade-start-here.md).</span></span>

## <a name="teamwork-and-office-365"></a><span data-ttu-id="0be3c-144">團隊工作與 Office 365</span><span class="sxs-lookup"><span data-stu-id="0be3c-144">Teamwork and Office 365</span></span>
<span data-ttu-id="0be3c-145">每個團隊都是不同的；針對共同作業，沒有一體適用的方法。</span><span class="sxs-lookup"><span data-stu-id="0be3c-145">Every team is different; there’s no one-size-fits-all approach to collaboration.</span></span> <span data-ttu-id="0be3c-146">Office 365 的設計可滿足每個團隊的獨特需求，讓人員能夠透過專門建置且整合的應用程式來進行通訊、共同作業，並實現更多功能。</span><span class="sxs-lookup"><span data-stu-id="0be3c-146">Office 365 is designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.</span></span>

<span data-ttu-id="0be3c-147">決定要使用的 Office 365 應用程式和服務時，請考慮組織的工作方式和您的組織必須擁有的交談類型。</span><span class="sxs-lookup"><span data-stu-id="0be3c-147">When deciding which Office 365 apps and services to use, think about the work your organization does and the types of conversations your teams need to have.</span></span> 

- <span data-ttu-id="0be3c-148">**Teams** 為團隊工作的中樞，它是人員 (包含組織外部) 可在其中主動交流並即時共同作業來完成工作的地方。</span><span class="sxs-lookup"><span data-stu-id="0be3c-148">**Teams**, as the hub for teamwork, is where people - including people outside your organization - can actively connect and collaborate in real time to get things done.</span></span> <span data-ttu-id="0be3c-149">在工作進行處直接交談，無論是在共同撰寫文件、開會或在其他應用程式和服務中共同作業時皆可。</span><span class="sxs-lookup"><span data-stu-id="0be3c-149">Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services.</span></span> <span data-ttu-id="0be3c-150">Teams 是進行非正式聊天、快速反覆查看專案、使用團隊檔案，以及在共用交付項目上進行共同作業之處。</span><span class="sxs-lookup"><span data-stu-id="0be3c-150">Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.</span></span> 

- <span data-ttu-id="0be3c-151">**Outlook** 可用於在熟悉的電子郵件環境中，以較正式、結構化的方式，或需要進行目標式且直接通訊時進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="0be3c-151">**Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.</span></span>

- <span data-ttu-id="0be3c-152">**SharePoint** 用於網站、入口網站、智慧型內容服務、業務程序自動化及企業搜尋。</span><span class="sxs-lookup"><span data-stu-id="0be3c-152">**SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search.</span></span> <span data-ttu-id="0be3c-153">SharePoint 會將內容保留在團隊工作的中心，讓所有類型的內容輕鬆在團隊之間共用和存取。</span><span class="sxs-lookup"><span data-stu-id="0be3c-153">SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams.</span></span> <span data-ttu-id="0be3c-154">與 Outlook、Yammer 和 Teams 的緊密整合，可在交談體驗間實現順暢的內容共同作業。</span><span class="sxs-lookup"><span data-stu-id="0be3c-154">Tight integration with Outlook, Yammer, and Teams enables seamless content collaboration across conversation experiences.</span></span>

- <span data-ttu-id="0be3c-155">**商務用 OneDrive** 用於儲存檔案，並可將檔案與使用者邀請的人員共用。</span><span class="sxs-lookup"><span data-stu-id="0be3c-155">**OneDrive for Business** for storing files and sharing them with people that a user invites.</span></span> <span data-ttu-id="0be3c-156">使用者在商務用 OneDrive 中儲存的內容是私人的 (在使用者將該內容與其他人共用為止)，使得它成為用於儲存不想共用或尚未準備共用之個人和草稿文件的最佳選項。</span><span class="sxs-lookup"><span data-stu-id="0be3c-156">Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.</span></span>

- <span data-ttu-id="0be3c-157">**Yammer** 讓組織中的人員彼此交流。</span><span class="sxs-lookup"><span data-stu-id="0be3c-157">**Yammer** to connect people across the organization.</span></span> <span data-ttu-id="0be3c-158">推動全公司的計劃、分享最佳做法，並針對共同的興趣主題或實務領域建立社群。</span><span class="sxs-lookup"><span data-stu-id="0be3c-158">Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas of practice.</span></span> <span data-ttu-id="0be3c-159">將構想群眾外包，促進與公司內部人員的開放式討論。</span><span class="sxs-lookup"><span data-stu-id="0be3c-159">Crowdsource ideas to foster open discussions with people across the company.</span></span>

- <span data-ttu-id="0be3c-160">**Office 應用程式**是人們所熟悉且經常使用的工具，包括 Word、Excel、PowerPoint 和 OneNote。</span><span class="sxs-lookup"><span data-stu-id="0be3c-160">**Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.</span></span> 

## <a name="teams-content-updates"></a><span data-ttu-id="0be3c-161">Teams 內容更新</span><span class="sxs-lookup"><span data-stu-id="0be3c-161">Teams content updates</span></span>

<span data-ttu-id="0be3c-162">請參閱[每週更新的 Teams 主題清單](teams-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-162">See a [weekly list of Teams topics that have been updated](teams-updates.md).</span></span>

## <a name="teams-known-issues"></a><span data-ttu-id="0be3c-163">Teams 的已知問題</span><span class="sxs-lookup"><span data-stu-id="0be3c-163">Teams known issues</span></span>

<span data-ttu-id="0be3c-164">請參閱 [Teams 的已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-164">See [Known issues for Teams](Known-issues.md).</span></span>

## <a name="teams-client-release-notes"></a><span data-ttu-id="0be3c-165">Teams 用戶端版本資訊</span><span class="sxs-lookup"><span data-stu-id="0be3c-165">Teams client release notes</span></span>

<span data-ttu-id="0be3c-166">請參閱 [Teams 的新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)。</span><span class="sxs-lookup"><span data-stu-id="0be3c-166">See [What's new in Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).</span></span>

