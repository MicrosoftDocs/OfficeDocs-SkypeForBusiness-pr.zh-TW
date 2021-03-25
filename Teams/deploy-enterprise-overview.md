---
title: Microsoft Teams 企業部署概觀
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 瞭解如何部署 Microsoft Teams 的企業功能。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd3e60fafecd3cf025187935a9dc28b492c39d1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121411"
---
# <a name="teams-enterprise-deployment-overview"></a><span data-ttu-id="da533-103">Teams 企業部署概觀</span><span class="sxs-lookup"><span data-stu-id="da533-103">Teams enterprise deployment overview</span></span>

<span data-ttu-id="da533-104">如果您是中型或大型企業，您需要思考如何向使用者推出服務、如何部署 Microsoft Teams 用戶端給使用者、您的網路設計對即時通訊品質的影響效果等等。</span><span class="sxs-lookup"><span data-stu-id="da533-104">If you're a medium or large business, you need to think about how you're going to roll out the service to your users, how you're going to deploy the Microsoft Teams client to them, how your network design could impact the quality of real-time communication, and so on.</span></span> <span data-ttu-id="da533-105">請查看下列各章節的文章指標，協助您在組織中規劃 Teams。</span><span class="sxs-lookup"><span data-stu-id="da533-105">Check out the following sections for pointers to articles that'll help you plan for Teams in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="da533-106">如果您尚未這麼做，我們強烈建議您可以從試驗點開始進行您的 Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="da533-106">If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot.</span></span> <span data-ttu-id="da533-107">試驗將可使您和一些早期採用者在您進行規劃和最終推出之前熟悉 Teams 及其功能。若需更多資訊說明如何開始試驗，請查閱 [開始使用 Microsoft Teams](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="da533-107">A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).</span></span>

<span data-ttu-id="da533-108">在您完成閱讀下列章節並準備開始在組織中部署 Teams 之後，請參閱 [在企業中設定 Microsoft Teams](deploy-enterprise-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="da533-108">After you've read the sections below and are ready to start deploying Teams in your organization, see [Set up Microsoft Teams in your enterprise](deploy-enterprise-setup.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="da533-109">架構</span><span class="sxs-lookup"><span data-stu-id="da533-109">Architecture</span></span>

<span data-ttu-id="da533-110">Teams 與 Microsoft 365 緊密整合，並且使用許多功能以開啟聊天、檔案共用、會議、電話語音、影片串流等其他功能。</span><span class="sxs-lookup"><span data-stu-id="da533-110">Teams is tightly integrated into Microsoft 365 and uses many features to power chat, file sharing, meetings, telephony, video streaming, and more.</span></span> <span data-ttu-id="da533-111">推出 Teams 之前，請查看 [Microsoft Teams IT 架構設計人員與電話語音解決方案海報](teams-architecture-solutions-posters.md) 以熟悉 Teams 與其他 Microsoft 365 一起運作的方式，並為使用者建立完整的共同作業體驗。</span><span class="sxs-lookup"><span data-stu-id="da533-111">Before you roll out Teams, check out [Microsoft Teams IT architecture and telephony solutions posters](teams-architecture-solutions-posters.md) to get familiar with how Teams works with the rest of Microsoft 365 to create a complete collaboration experience for your users.</span></span>

## <a name="workloads"></a><span data-ttu-id="da533-112">工作負載</span><span class="sxs-lookup"><span data-stu-id="da533-112">Workloads</span></span>

<span data-ttu-id="da533-113">Teams 有三種工作負載可以彼此獨立部署：**聊天、Teams 和頻道**；**會議和研討會**；和 **電話系統和 PSTN (公用交換電話網路) 連線**。</span><span class="sxs-lookup"><span data-stu-id="da533-113">Teams has three workloads that can be deployed independently of each other: **chat, teams, and channels**; **meetings and conferencing**; and **Phone System and PSTN (public switched telephone network) connectivity**.</span></span> <span data-ttu-id="da533-114">在我們的文件中每個工作負載都有各自的章節，可更容易找到該工作負載的資訊。</span><span class="sxs-lookup"><span data-stu-id="da533-114">Each workload has its own section in our documentation to make it easier to find information about that workload.</span></span> <span data-ttu-id="da533-115">這包括部署規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="da533-115">This includes deployment planning information.</span></span>

<span data-ttu-id="da533-116">若要查看您想要部署之工作負載的部署規劃資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="da533-116">To see deployment planning information for the workload you want to deploy, see the following articles:</span></span>

- [<span data-ttu-id="da533-117">聊天、Teams 和頻道</span><span class="sxs-lookup"><span data-stu-id="da533-117">Chat, teams, and channels</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [<span data-ttu-id="da533-118">會議和研討會</span><span class="sxs-lookup"><span data-stu-id="da533-118">Meetings and conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="da533-119">電話系統與 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="da533-119">Phone System and PSTN connectivity</span></span>](cloud-voice-landing-page.md)

## <a name="network-planner"></a><span data-ttu-id="da533-120">網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="da533-120">Network planner</span></span>

<span data-ttu-id="da533-121">當您擁有大量使用者、或複雜網路或兩者皆具備時，Teams 的網路規劃即非常重要。</span><span class="sxs-lookup"><span data-stu-id="da533-121">Network planning for Teams is extremely important when you have large numbers of users, complex networks, or both.</span></span> <span data-ttu-id="da533-122">Teams 支援語音通話和視訊會議，兩者都仰賴即時通訊，以盡可能為使用者提供最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="da533-122">Teams supports voice calling and video conferencing, both of which rely on real-time communications to provide the best experience possible for users.</span></span> <span data-ttu-id="da533-123">網路必須具備：</span><span class="sxs-lookup"><span data-stu-id="da533-123">Networks must:</span></span>

- <span data-ttu-id="da533-124">充足的頻寬容量，以容納並行的語音通話、視訊會議、會議、螢幕畫面分享等等。</span><span class="sxs-lookup"><span data-stu-id="da533-124">Have sufficient bandwidth capacity to accommodate the number of concurrent voice calls, video conferences, meetings, screen sharing, and so on.</span></span>
- <span data-ttu-id="da533-125">具有支援即時通訊協定的網路硬體。</span><span class="sxs-lookup"><span data-stu-id="da533-125">Have network hardware that supports real-time communication protocols.</span></span>
- <span data-ttu-id="da533-126">允許在您網路上的裝置、Microsoft 365 服務與外部使用者之間的必要網路埠。</span><span class="sxs-lookup"><span data-stu-id="da533-126">Allow the required network ports between devices on your networks, Microsoft 365 services, and external users.</span></span>

<span data-ttu-id="da533-127">請參閱下列文章，以協助您瞭解 Microsoft Teams 的網路需求：</span><span class="sxs-lookup"><span data-stu-id="da533-127">See the following articles to help you understand Teams network requirements:</span></span>

- [<span data-ttu-id="da533-128">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="da533-128">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)
- [<span data-ttu-id="da533-129">適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="da533-129">Proxy servers for Teams or Skype for Business Online</span></span>](proxy-servers-for-skype-for-business-online.md)

<span data-ttu-id="da533-130">為協助您進行規劃，Teams 包含網路規劃工具。</span><span class="sxs-lookup"><span data-stu-id="da533-130">To help you with your planning, Teams includes the Network planner.</span></span> <span data-ttu-id="da533-131">網路規劃中心會詢問有關您擁有的使用者數量和類型、貴組織擁有的網站數量、您的網路連結頻寬容量等問題。</span><span class="sxs-lookup"><span data-stu-id="da533-131">The Network planner asks you questions about the number and types of users you have, how many sites your organization has, the bandwidth capacity of your network links, and more.</span></span> <span data-ttu-id="da533-132">透過使用這項資訊，網路規劃中心會建立一份報告，其中會顯示每個活動的頻寬需求及建議。</span><span class="sxs-lookup"><span data-stu-id="da533-132">Using this information, the Network planner creates a report that shows the bandwidth requirements for each activity, along with the recommendations.</span></span>

 > [!div class="nextstepaction"]
> [<span data-ttu-id="da533-133">前往網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="da533-133">Go to Network planner</span></span>](https://admin.teams.microsoft.com/networkplanner/organization)

<span data-ttu-id="da533-134">(您必須是 [Microsoft 365 全域系統管理員](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) 才能開啟網路規劃中心。)</span><span class="sxs-lookup"><span data-stu-id="da533-134">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Network planner.)</span></span>

<span data-ttu-id="da533-135">有關網路規劃中心運作方式的詳細資訊，請參閱 [使用 Microsoft Teams 的網路規劃中心](network-planner.md)。</span><span class="sxs-lookup"><span data-stu-id="da533-135">For details about how the Network planner works, see [Use the Network planner for Microsoft Teams](network-planner.md).</span></span>

<span data-ttu-id="da533-136">若要瞭解網路規劃中心如何規劃您的網路範例，請參閱 [使用網路規劃中心 - 範例案例](tutorial-network-planner-example.yml)。</span><span class="sxs-lookup"><span data-stu-id="da533-136">To see an example of how Network planner can plan your network, see [Using Network Planner - example scenario](tutorial-network-planner-example.yml).</span></span>

## <a name="teams-advisor"></a><span data-ttu-id="da533-137">Teams 顧問</span><span class="sxs-lookup"><span data-stu-id="da533-137">Teams advisor</span></span>

<span data-ttu-id="da533-138">Teams 顧問是 Teams 內的解決方案，將 Teams、頻道、檔案共用和 Microsoft Planner 彙集在一起，以為您的組織建立部署專案。</span><span class="sxs-lookup"><span data-stu-id="da533-138">The Teams advisor is a solution within Teams that brings together teams, channels, file sharing, and Planner, to create a deployment project for your organization.</span></span> <span data-ttu-id="da533-139">Teams 顧問會針對您選取的工作負載 (例如聊天、團隊和頻道) 建立專案計劃，其中包含在部署期間您應執行的建議工作。</span><span class="sxs-lookup"><span data-stu-id="da533-139">Teams advisor creates project plan, specific to the workload you select (such as chat, teams, and channels), that includes the recommended tasks you should perform during your deployment.</span></span> <span data-ttu-id="da533-140">每項工作都包含相關文章的指示、建議和連結，以引導您完成此程序。</span><span class="sxs-lookup"><span data-stu-id="da533-140">Each task contains instructions, suggestions, and links to relevant articles, to guide you through the process.</span></span> <span data-ttu-id="da533-141">您可以輕鬆地將工作指派給一或多個人員，並為每個工作指定開始日期和結束日期。</span><span class="sxs-lookup"><span data-stu-id="da533-141">You can easily assign tasks to one or more individuals, and specify start and end dates for each task.</span></span>

> [!TIP]
> <span data-ttu-id="da533-142">完成 Microsoft Learn 上的 [使用 Teams 顧問執行](/learn/modules/m365-teams-rollout-using-advisor/) 模組，以瞭解如何使用 Teams 顧問協助您規劃 Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="da533-142">See how you can use Teams advisor to help you plan your Teams deployment by completing the [Roll out using the Teams advisor](/learn/modules/m365-teams-rollout-using-advisor/) module on Microsoft Learn.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="da533-143">前往 Teams 顧問</span><span class="sxs-lookup"><span data-stu-id="da533-143">Go to Teams advisor</span></span>](https://admin.teams.microsoft.com/teams-deployment)

<span data-ttu-id="da533-144">(您必須是 [Microsoft 365 全域系統管理員](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) 才能開啟 Teams 顧問。)</span><span class="sxs-lookup"><span data-stu-id="da533-144">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Teams advisor.)</span></span>

<span data-ttu-id="da533-145">如需 Teams 顧問運作方式的詳細資訊，請參閱 [使用適用於 Teams 的建議程式以協助您執行 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="da533-145">For details about how the Teams advisor works, see [Use Advisor for Teams to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>

## <a name="lifecycle-and-governance-planning"></a><span data-ttu-id="da533-146">生命週期與控管規劃</span><span class="sxs-lookup"><span data-stu-id="da533-146">Lifecycle and governance planning</span></span>

<span data-ttu-id="da533-147">當您在規劃 Teams 部署時，您必須考慮在貴組織中的 Teams、頻道、檔案等的生命週期。</span><span class="sxs-lookup"><span data-stu-id="da533-147">As you plan your Teams deployment, you need to consider the lifecycle of teams, channels, files, and so on, in your organization.</span></span> <span data-ttu-id="da533-148">您也應該考慮要將哪些類型的資訊儲存其中。</span><span class="sxs-lookup"><span data-stu-id="da533-148">You should also think about what types of information will be stored in them.</span></span> <span data-ttu-id="da533-149">Teams 可能為特定專案、部門而建立，或作為整個組織的中央資源。</span><span class="sxs-lookup"><span data-stu-id="da533-149">Teams may be created for a specific project, for a department, or they might be used as a central resource for the entire organization.</span></span> <span data-ttu-id="da533-150">每個用途都有不同的需求，也就推動了下列問題：</span><span class="sxs-lookup"><span data-stu-id="da533-150">Each of these uses have different requirements, which drive questions like the following:</span></span>

- <span data-ttu-id="da533-151">Teams 維持使用中的狀態可達多長時間？</span><span class="sxs-lookup"><span data-stu-id="da533-151">How long will the teams remain active?</span></span>
- <span data-ttu-id="da533-152">誰應該擁有及管理 Teams 及其頻道？</span><span class="sxs-lookup"><span data-stu-id="da533-152">Who should own and manage the teams and their channels?</span></span>
- <span data-ttu-id="da533-153">某些合規性需求是否應該只套用到某些 Teams，但不能套用至其他？</span><span class="sxs-lookup"><span data-stu-id="da533-153">Should certain compliance requirements apply to some teams, but not others?</span></span>
- <span data-ttu-id="da533-154">是否應該有命名原則以協助使用者識別正確的 Teams？</span><span class="sxs-lookup"><span data-stu-id="da533-154">Should there be a naming policy to help users identify the right team?</span></span>

<span data-ttu-id="da533-155">建立原則與指導方針並做為初始部署的一部分，將可協助確保您的使用者可以找到所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="da533-155">Creating policies and guidelines as part of your initial deployment will help ensure that your users can find the information they need.</span></span> <span data-ttu-id="da533-156">同樣重要的是，適當的原則將可協助保護貴組織避免資訊外泄、協助您符合法規需求，並協助您針對保存目的保留需要的資訊。</span><span class="sxs-lookup"><span data-stu-id="da533-156">Just as importantly, however, appropriate policies will help protect your organization from information leakage, help you conform to regulatory requirements, and help you retain information as needed for archival purposes.</span></span>

<span data-ttu-id="da533-157">若要深入瞭解 Teams 中的生命週期管理和控管，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="da533-157">To learn more about lifecycle management and governance in Teams, see the following:</span></span>

- [<span data-ttu-id="da533-158">Teams 中的生命週期管理方案</span><span class="sxs-lookup"><span data-stu-id="da533-158">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
- [<span data-ttu-id="da533-159">Teams 中的控管方案</span><span class="sxs-lookup"><span data-stu-id="da533-159">Plan for governance in Teams</span></span>](plan-teams-governance.md)

## <a name="adoption"></a><span data-ttu-id="da533-160">採用</span><span class="sxs-lookup"><span data-stu-id="da533-160">Adoption</span></span>

<span data-ttu-id="da533-161">若要確保貴組織和使用者能從 Teams 獲得最大收益，您需要一份採用計畫。</span><span class="sxs-lookup"><span data-stu-id="da533-161">To ensure that your organization and your users get the most out of Teams, you need an adoption program.</span></span> <span data-ttu-id="da533-162">一份有效的採用計畫可以動員早期採用者，這些採用者可以：</span><span class="sxs-lookup"><span data-stu-id="da533-162">An effective adoption program can mobilize early adopters who can:</span></span>

- <span data-ttu-id="da533-163">向同事以及企業或群組領導者說明 Teams 的好處。</span><span class="sxs-lookup"><span data-stu-id="da533-163">Articulate the benefits of Teams to their colleagues and to business or group leaders.</span></span>
- <span data-ttu-id="da533-164">在看到 Teams 如何改善共同作業的其他人中，激發他們的熱情並使他們更輕鬆地彼此聯繫。</span><span class="sxs-lookup"><span data-stu-id="da533-164">Spark excitement in others who see how Teams improves collaboration and makes it easier to connect with each other.</span></span>
- <span data-ttu-id="da533-165">協助評估現有的商務程序，並針對 Teams 如何整合到其中的方式提出建議。</span><span class="sxs-lookup"><span data-stu-id="da533-165">Help evaluate existing business processes and make recommendations for how Teams can be integrated into them.</span></span>
- <span data-ttu-id="da533-166">向部署小組回報成功之處和困難之處，以協助改善採用程序。</span><span class="sxs-lookup"><span data-stu-id="da533-166">Report back to the deployment team both successes and difficulties to help improve the adoption process.</span></span>

<span data-ttu-id="da533-167">有關設定採用計畫的詳細資訊，請參閱 [採用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="da533-167">For details about setting up an adoption program, see [Adopt Microsoft Teams](adopt-microsoft-teams-landing-page.md).</span></span>