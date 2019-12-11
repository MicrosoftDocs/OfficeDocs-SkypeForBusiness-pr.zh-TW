---
title: 使用 Advisor for Teams (預覽) 協助您推出 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: 使用 Advisor for Teams (預覽) 協助您規劃和完成您的 Microsoft Teams 部署。
ms.openlocfilehash: 63a3ae01dbe47323fd9227e65fa8c38a2d725ddf
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909469"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a><span data-ttu-id="0f324-103">使用 Advisor for Teams 協助您推出 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f324-103">Use Advisor for Teams to help you roll out Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="0f324-104">Advisor for Teams (預覽) 會引導您完成 Microsoft Teams 的推廣。</span><span class="sxs-lookup"><span data-stu-id="0f324-104">Advisor for Teams (preview) walks you through your Microsoft Teams rollout.</span></span> <span data-ttu-id="0f324-105">在您成功推出 Teams 前，Advisor for Teams 會評估您的 Office 365 租用戶環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="0f324-105">It assesses your Office 365 tenant environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span> <span data-ttu-id="0f324-106">接著，Advisor for Teams 會建立部署團隊 (在 Teams 中)，並為您要推出的每個工作負載建立頻道。部署團隊中的每項工作負載隨附有全方位的 Planner 計劃，其中包含每個工作負載的所有推出工作。</span><span class="sxs-lookup"><span data-stu-id="0f324-106">Then, Advisor for Teams creates a Deployment team (in Teams), with channels for each workload you want to roll out. Each workload in the Deployment team comes with a comprehensive Planner plan that includes all the rollout tasks for each workload.</span></span>  <span data-ttu-id="0f324-107">您可以使用此 Planner 計劃，將工作指派給每個推廣階段的負責人，包括專案經理、Teams 和 Office 365 系統管理員、支援人員，以及您的採用和使用者整備團隊。</span><span class="sxs-lookup"><span data-stu-id="0f324-107">Using this Planner plan, you'll assign tasks to the people responsible for each phase of the rollout - including the project manager, Teams and Office 365 admins, support people, and your adoption and user readiness team.</span></span> <span data-ttu-id="0f324-108">每項推廣工作都包含所有您成功完成工作所需的指引和資源。</span><span class="sxs-lookup"><span data-stu-id="0f324-108">Each rollout task contains all the guidance and resources you need to successfully complete the task.</span></span>

<span data-ttu-id="0f324-109">Advisor for Teams 是 [Teams 系統管理中心](https://admin.teams.microsoft.com)的功能之一。</span><span class="sxs-lookup"><span data-stu-id="0f324-109">Advisor for Teams is part of the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="0f324-110">首次若要使用 Advisor for Teams，在儀表板上，按一下 **[部署 Teams 工作負載]** 小工具中的 **[啟動]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0f324-110">To use Advisor for Teams the first time, click the **Start** button in the **Deploying Teams workload** widget on the Dashboard.</span></span> <span data-ttu-id="0f324-111">或移至 **[Planning]** > **[Advisor]**。</span><span class="sxs-lookup"><span data-stu-id="0f324-111">Or go to **Planning** > **Advisor**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f324-112">Advisor for Teams 不適用於 Microsoft 365 政府版 - GCC High 或 DoD 部署。</span><span class="sxs-lookup"><span data-stu-id="0f324-112">Advisor for Teams isn't available for Microsoft 365 Government - GCC High or DoD deployments.</span></span>

<span data-ttu-id="0f324-113">在此 [部署和設定 Teams 的簡介](https://youtu.be/o2mlsUubIO4?t=44)影片中了解 Advisor for Teams (Advisor for Teams 在 0:50-3:15 分處)。</span><span class="sxs-lookup"><span data-stu-id="0f324-113">Check out Advisor for Teams in this [Deploy & Configure Teams Intro](https://youtu.be/o2mlsUubIO4?t=44) video (Advisor for Teams is at 0:50-3:15 minutes).</span></span>

## <a name="using-advisor-for-teams-preview"></a><span data-ttu-id="0f324-114">使用 Advisor for Teams (預覽)</span><span class="sxs-lookup"><span data-stu-id="0f324-114">Using Advisor for Teams (preview)</span></span>

<span data-ttu-id="0f324-115">若要使用 Advisor for Teams，您不必成為 Teams 系統管理員，組織中的任何人都能使用。</span><span class="sxs-lookup"><span data-stu-id="0f324-115">You don't have to be a Teams admin to use Advisor for Teams - anybody in your organization can use it.</span></span> <span data-ttu-id="0f324-116">我們已設定特殊權限，讓非系統管理員的使用者可以使用 Advisor for Teams，即使 Advisor for Teams 位於 Teams 系統管理中心亦可。</span><span class="sxs-lookup"><span data-stu-id="0f324-116">We've set up special permissions so non-admin users can get to Advisor for Teams, even though it's in the Teams admin center.</span></span> <span data-ttu-id="0f324-117">您「必須」是 Teams 系統管理員、Teams 服務系統管理員或全域系統管理員，才能開啟租用戶整備評估。</span><span class="sxs-lookup"><span data-stu-id="0f324-117">You DO have to be a Teams admin, Teams Service Administrator, or Global Administrator to open the tenant readiness assessments.</span></span>

<span data-ttu-id="0f324-118">第一次使用 Advisor for Teams 時，Advisor for Teams 會在 Teams 中為您建立部署團隊。</span><span class="sxs-lookup"><span data-stu-id="0f324-118">The first time you use Advisor for Teams, it'll create a Deployment team for you in Teams.</span></span> <span data-ttu-id="0f324-119">針對您要推出的每個工作負載新增頻道。</span><span class="sxs-lookup"><span data-stu-id="0f324-119">It adds channels for each workload you want to roll out.</span></span> 


## <a name="available-advisor-for-teams-plans"></a><span data-ttu-id="0f324-120">可使用的 Advisor for Teams 方案</span><span class="sxs-lookup"><span data-stu-id="0f324-120">Available Advisor for Teams plans</span></span>

<span data-ttu-id="0f324-121">由於 Advisor for Teams 目前為預覽，我們提供以下兩個方案：</span><span class="sxs-lookup"><span data-stu-id="0f324-121">While Advisor for Teams is in preview, we're providing these two plans:</span></span>

1. <span data-ttu-id="0f324-122">交談、團隊、頻道和應用程式</span><span class="sxs-lookup"><span data-stu-id="0f324-122">Chat, teams, channels, and apps</span></span>
    - <span data-ttu-id="0f324-123">租用戶評估</span><span class="sxs-lookup"><span data-stu-id="0f324-123">Tenant assessment</span></span>
    - <span data-ttu-id="0f324-124">Planner 計劃，包括採用工作</span><span class="sxs-lookup"><span data-stu-id="0f324-124">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="0f324-125">Forms 使用者問卷</span><span class="sxs-lookup"><span data-stu-id="0f324-125">Forms user survey</span></span>
1. <span data-ttu-id="0f324-126">會議和研討會</span><span class="sxs-lookup"><span data-stu-id="0f324-126">Meetings and conferencing</span></span>
    - <span data-ttu-id="0f324-127">租用戶評估</span><span class="sxs-lookup"><span data-stu-id="0f324-127">Tenant assessment</span></span>
    - <span data-ttu-id="0f324-128">Planner 計劃，包括採用工作</span><span class="sxs-lookup"><span data-stu-id="0f324-128">Planner plan, including adoption tasks</span></span>
    - <span data-ttu-id="0f324-129">Forms 使用者問卷</span><span class="sxs-lookup"><span data-stu-id="0f324-129">Forms user survey</span></span>

<span data-ttu-id="0f324-130">我們建議您從交談、團隊、頻道和應用程式的方案開始。</span><span class="sxs-lookup"><span data-stu-id="0f324-130">We recommend that you start with the Chat, teams, channels, and apps plan.</span></span> <span data-ttu-id="0f324-131">您完成該工作負載的部署後，請返回 [Advisor]，按一下 **[新增頻道]** 以開始下一項工作負載。</span><span class="sxs-lookup"><span data-stu-id="0f324-131">When you're done deploying that workload, go back to Advisor and click **Add channel** to start the next workload.</span></span> 

## <a name="tenant-assessment"></a><span data-ttu-id="0f324-132">租用戶評估</span><span class="sxs-lookup"><span data-stu-id="0f324-132">Tenant assessment</span></span>
<span data-ttu-id="0f324-133">每個方案都包含租用戶整備評估，可讓您在推出 Teams 前，用來找出並修復環境中任何不足之處。</span><span class="sxs-lookup"><span data-stu-id="0f324-133">Each plan includes a tenant readiness assessment that you can use to identify and remediate any deficiencies in your environment before you roll out Teams.</span></span> <span data-ttu-id="0f324-134">以下是每項評估的檢查項目：</span><span class="sxs-lookup"><span data-stu-id="0f324-134">Here's what each assessment checks:</span></span>

### <a name="chat-teams-channels-and-apps"></a><span data-ttu-id="0f324-135">交談、團隊、頻道和應用程式</span><span class="sxs-lookup"><span data-stu-id="0f324-135">Chat, teams, channels, and apps</span></span>


|<span data-ttu-id="0f324-136">評估</span><span class="sxs-lookup"><span data-stu-id="0f324-136">Assessment</span></span>  |<span data-ttu-id="0f324-137">代表意義</span><span class="sxs-lookup"><span data-stu-id="0f324-137">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="0f324-138">Teams 授權</span><span class="sxs-lookup"><span data-stu-id="0f324-138">Teams licenses</span></span>     |<span data-ttu-id="0f324-139">您的可用 Teams 授權是否為有效訂閱</span><span class="sxs-lookup"><span data-stu-id="0f324-139">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="0f324-140">Exchange 授權</span><span class="sxs-lookup"><span data-stu-id="0f324-140">Exchange licenses</span></span>     |<span data-ttu-id="0f324-141">您的可用 Exchange Online 授權是否為有效訂閱。</span><span class="sxs-lookup"><span data-stu-id="0f324-141">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="0f324-142">雖然 Exchange 並非 Teams 基本功能的必要項目，但是與 Exchange 整合可以提供最佳的 Teams 體驗。</span><span class="sxs-lookup"><span data-stu-id="0f324-142">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span>         |
|<span data-ttu-id="0f324-143">SharePoint Online 授權</span><span class="sxs-lookup"><span data-stu-id="0f324-143">SharePoint Online licenses</span></span>     | <span data-ttu-id="0f324-144">您的可用 SharePoint Online 授權是否為有效訂閱。</span><span class="sxs-lookup"><span data-stu-id="0f324-144">Whether you have an active subscription with available SharePoint Online licenses.</span></span> <span data-ttu-id="0f324-145">每位使用者都需要一個 SharePoint Online 授權才能使用檔案儲存空間、頻道共同作業及交談。</span><span class="sxs-lookup"><span data-stu-id="0f324-145">You need one SharePoint Online license per user for file storage, channel collaboration, and chat.</span></span> 
|<span data-ttu-id="0f324-146">已啟用來賓存取</span><span class="sxs-lookup"><span data-stu-id="0f324-146">Guest access enabled</span></span>     |<span data-ttu-id="0f324-147">Teams 中的來賓存取是否已開啟。</span><span class="sxs-lookup"><span data-stu-id="0f324-147">If guest access is turned on in Teams.</span></span> <span data-ttu-id="0f324-148">來賓存取的 Azure Active Directory 設定未檢閱。</span><span class="sxs-lookup"><span data-stu-id="0f324-148">Azure Active Directory settings for guest access are not reviewed.</span></span>   |
|<span data-ttu-id="0f324-149">已設定虛名網域</span><span class="sxs-lookup"><span data-stu-id="0f324-149">Vanity domain configured</span></span>     |<span data-ttu-id="0f324-150">您的租用戶是否有設定非 @onmicrosoft.com 的網域</span><span class="sxs-lookup"><span data-stu-id="0f324-150">Whether there's a non-@onmicrosoft.com domain configured for your tenant</span></span>  |
|<span data-ttu-id="0f324-151">已設定 Office 365 群組命名標準</span><span class="sxs-lookup"><span data-stu-id="0f324-151">Office 365 Group naming standard configured</span></span>     | <span data-ttu-id="0f324-152">是否已針對 Office 365 群組設定命名標準</span><span class="sxs-lookup"><span data-stu-id="0f324-152">Whether naming standards have been configured for Office 365 Groups</span></span>        |
|<span data-ttu-id="0f324-153">已設定 Office 365 群組到期原則</span><span class="sxs-lookup"><span data-stu-id="0f324-153">Office 365 Group expiration configured</span></span>     |  <span data-ttu-id="0f324-154">是否已為 Office 365 群組定義群組過期原則。</span><span class="sxs-lookup"><span data-stu-id="0f324-154">Whether a Group expiration policy has been defined for Office 365 Groups.</span></span> <span data-ttu-id="0f324-155">如果未設定，該值會設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="0f324-155">If not, the value is set to never.</span></span>        |
|<span data-ttu-id="0f324-156">已設定外部存取</span><span class="sxs-lookup"><span data-stu-id="0f324-156">External access configured</span></span>     |<span data-ttu-id="0f324-157">如果已開啟外部存取，則您可以在 Teams 中與外部組織進行溝通。</span><span class="sxs-lookup"><span data-stu-id="0f324-157">If external access is turned on so you can communicate with external organizations in Teams.</span></span>          |

### <a name="meetings-and-conferencing"></a><span data-ttu-id="0f324-158">會議和研討會</span><span class="sxs-lookup"><span data-stu-id="0f324-158">Meetings and conferencing</span></span>


|<span data-ttu-id="0f324-159">評估</span><span class="sxs-lookup"><span data-stu-id="0f324-159">Assessment</span></span>  |<span data-ttu-id="0f324-160">代表意義</span><span class="sxs-lookup"><span data-stu-id="0f324-160">What it tells you</span></span>  |
|---------|---------|
|<span data-ttu-id="0f324-161">Teams 授權</span><span class="sxs-lookup"><span data-stu-id="0f324-161">Teams licenses</span></span>     |<span data-ttu-id="0f324-162">您的可用 Teams 授權是否為有效訂閱</span><span class="sxs-lookup"><span data-stu-id="0f324-162">Whether you have an active subscription with available Teams licenses</span></span> |
|<span data-ttu-id="0f324-163">Exchange 授權</span><span class="sxs-lookup"><span data-stu-id="0f324-163">Exchange licenses</span></span>     |<span data-ttu-id="0f324-164">您的可用 Exchange Online 授權是否為有效訂閱。</span><span class="sxs-lookup"><span data-stu-id="0f324-164">Whether you have an active subscription with available Exchange Online licenses.</span></span> <span data-ttu-id="0f324-165">雖然 Exchange 並非 Teams 基本功能的必要項目，但是與 Exchange 整合可以提供最佳的 Teams 體驗。</span><span class="sxs-lookup"><span data-stu-id="0f324-165">While Exchange isn't required for basic Teams functionality, integration with Exchange provides an optimal Teams experience.</span></span> |
|<span data-ttu-id="0f324-166">音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="0f324-166">Audio conferencing licenses</span></span>    |<span data-ttu-id="0f324-167">您的音訊會議授權是否為有效訂閱</span><span class="sxs-lookup"><span data-stu-id="0f324-167">Whether you have an active subscription with Audio conferencing licenses</span></span> |
|<span data-ttu-id="0f324-168">Stream 授權</span><span class="sxs-lookup"><span data-stu-id="0f324-168">Stream licenses</span></span>     |<span data-ttu-id="0f324-169">您的 Stream 授權是否為有效訂閱，該授權可以在需要會議錄製時使用。</span><span class="sxs-lookup"><span data-stu-id="0f324-169">Whether you have an active subscription with Stream licenses, which can used should Meeting Recording be desired.</span></span> |
|<span data-ttu-id="0f324-170">來賓存取</span><span class="sxs-lookup"><span data-stu-id="0f324-170">Guest access</span></span>     |<span data-ttu-id="0f324-171">Teams 中的來賓存取是否已開啟。</span><span class="sxs-lookup"><span data-stu-id="0f324-171">If guest access is turned on in Teams.</span></span> <span data-ttu-id="0f324-172">來賓存取的 Azure Active Directory 設定未檢閱。</span><span class="sxs-lookup"><span data-stu-id="0f324-172">Azure Active Directory settings for guest access are not reviewed.</span></span>|
|<span data-ttu-id="0f324-173">虛名網域</span><span class="sxs-lookup"><span data-stu-id="0f324-173">Vanity domain</span></span>     |<span data-ttu-id="0f324-174">您的租用戶是否有設定非 @onmicrosoft.com 的網域。</span><span class="sxs-lookup"><span data-stu-id="0f324-174">Whether there's a non-@onmicrosoft.com domain configured for your tenant.</span></span>  |
|<span data-ttu-id="0f324-175">外部存取</span><span class="sxs-lookup"><span data-stu-id="0f324-175">External access</span></span>     |<span data-ttu-id="0f324-176">如果已開啟外部存取，則您可以在 Teams 中與外部組織進行溝通。</span><span class="sxs-lookup"><span data-stu-id="0f324-176">If external access is turned on so you can communicate with external organizations in Teams.</span></span> |


### <a name="advisor-bot"></a><span data-ttu-id="0f324-177">Advisor Bot</span><span class="sxs-lookup"><span data-stu-id="0f324-177">Advisor bot</span></span>
<span data-ttu-id="0f324-178">Advisor 建立部署團隊後，Advisor Bot 會傳遞下列訊息。</span><span class="sxs-lookup"><span data-stu-id="0f324-178">Once Advisor creates your Deployment team, the Advisor bot delivers the following message.</span></span>

><span data-ttu-id="0f324-179">**歡迎使用 Microsoft Teams 的部署團隊！**</span><span class="sxs-lookup"><span data-stu-id="0f324-179">**Welcome to your Deployment team for Microsoft Teams!**</span></span>
>  
><span data-ttu-id="0f324-180">此團隊的目的是引導您完成您組織的 Teams 推廣，給予您所有需要的資源並提供共同作業空間給專案團隊使用。</span><span class="sxs-lookup"><span data-stu-id="0f324-180">The purpose of this team is to walk you through your organization's Teams rollout by giving you all the resources you need and providing a collaboration space for the project team.</span></span> <span data-ttu-id="0f324-181">使用 Advisor for Teams 建立的每個頻道都包含有逐步的 Planner 規劃和其他資源，例如可在推廣期間使用的 Forms 使用者問卷。</span><span class="sxs-lookup"><span data-stu-id="0f324-181">Each channel created using Advisor for Teams includes a step-by-step Planner plan and other resources such as a Forms users survey that can be used throughout your rollout.</span></span> <span data-ttu-id="0f324-182">您可以隨時返回並檢閱租用戶整備評估，或是使用 Teams 系統管理中心新增額外的工作負載計劃。</span><span class="sxs-lookup"><span data-stu-id="0f324-182">At any point, you can you go back and review the tenant readiness assessment or add additional workload plans using the Teams admin center.</span></span> 
> 
><span data-ttu-id="0f324-183">**行動信號**</span><span class="sxs-lookup"><span data-stu-id="0f324-183">**Call to action**</span></span> 
>- <span data-ttu-id="0f324-184">如果您剛開始使用 Teams 或 Planner，請參閱我們的 [Teams 逐步解說](https://teamsdemo.office.com/) 並觀賞 [Planner 快速入門影片](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。</span><span class="sxs-lookup"><span data-stu-id="0f324-184">If you're new to Teams or Planner, check out our [Teams walkthrough](https://teamsdemo.office.com/) and watch the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 
>- <span data-ttu-id="0f324-185">前往 Teams 中的部署團隊。</span><span class="sxs-lookup"><span data-stu-id="0f324-185">Head over to your Deployment team in Teams.</span></span> <span data-ttu-id="0f324-186">選取您的工作負載頻道 (例如交談、團隊、頻道和應用程式)，然後選取 **[Planner]** 索引標籤以開始使用。</span><span class="sxs-lookup"><span data-stu-id="0f324-186">Select your workload channel (for example, Chat, teams, channels, and apps), and select the **Planner** tab to get started.</span></span>
> 
><span data-ttu-id="0f324-187">若要深入了解 Advisor for Teams，請閱讀 [使用 Advisor for Teams 推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="0f324-187">To learn more about Advisor for Teams, read [Use Advisor for Teams to roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="0f324-188">Advisor for Teams Bot 只能用來傳遞歡迎訊息給部署團隊。</span><span class="sxs-lookup"><span data-stu-id="0f324-188">The Advisor for Teams Bot is only used to send a welcome message to your Deployment team.</span></span> <span data-ttu-id="0f324-189">不會收集額外的資料。</span><span class="sxs-lookup"><span data-stu-id="0f324-189">No additional data is collected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f324-190">Advisor for Teams Bot 依預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="0f324-190">The Advisor for Teams bot is enabled by default.</span></span> <span data-ttu-id="0f324-191">如果您使用或規劃要使用 Advisor for Teams，則請勿停用此功能。</span><span class="sxs-lookup"><span data-stu-id="0f324-191">Do not disable it if you use or plan on using Advisor for Teams.</span></span>


## <a name="frequently-asked-questions"></a><span data-ttu-id="0f324-192">常見問題集</span><span class="sxs-lookup"><span data-stu-id="0f324-192">Frequently asked questions</span></span>
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a><span data-ttu-id="0f324-193">Advisor for Teams 的授權需求為何？</span><span class="sxs-lookup"><span data-stu-id="0f324-193">What are the licensing requirements for Advisor for Teams?</span></span>
<span data-ttu-id="0f324-194">除了 Teams 的授權之外，沒有其他額外的授權需求。</span><span class="sxs-lookup"><span data-stu-id="0f324-194">There are no additional licensing requirements other than being licensed for Teams.</span></span>

### <a name="can-i-delete-the-deployment-team"></a><span data-ttu-id="0f324-195">我可以刪除部署團隊嗎？</span><span class="sxs-lookup"><span data-stu-id="0f324-195">Can I delete the Deployment team?</span></span>
<span data-ttu-id="0f324-196">在 Advisor for Teams 建立您的部署團隊後，請像管理其他團隊一樣管理該團隊，包括刪除團隊。</span><span class="sxs-lookup"><span data-stu-id="0f324-196">After Advisor for Teams has created your Deployment team, manage the team like any other team - including the ability to delete it.</span></span> <span data-ttu-id="0f324-197">請注意，如果您不是使用 Teams 系統管理中心刪除團隊，系統會報告該團隊依然存在。</span><span class="sxs-lookup"><span data-stu-id="0f324-197">Be aware that, if you don't delete the team by using the Teams admin center, it will be reported that the team exists.</span></span>

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a><span data-ttu-id="0f324-198">我是否可以在部署團隊中新增或移除頻道？</span><span class="sxs-lookup"><span data-stu-id="0f324-198">Can I add or remove channels in the Deployment team?</span></span>
<span data-ttu-id="0f324-199">可以，部署團隊建立後，您就能使用與其他任何團隊相同的方式管理頻道。</span><span class="sxs-lookup"><span data-stu-id="0f324-199">Yes, once the Deployment team has been created, you'll manage the channels the same way as any other team.</span></span>

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a><span data-ttu-id="0f324-200">我是否可以在部署團隊中新增或移除專案團隊成員？</span><span class="sxs-lookup"><span data-stu-id="0f324-200">Can I add or remove project team members in the Deployment team?</span></span>
<span data-ttu-id="0f324-201">可以，部署團隊建立後，您就能使用與其他任何團隊相同的方式管理該團隊。</span><span class="sxs-lookup"><span data-stu-id="0f324-201">Yes, once the Deployment team has been created, you'll manage it the same way as any other team.</span></span>

### <a name="can-i-modify-the-planner-plans"></a><span data-ttu-id="0f324-202">我可以修改 Planner 計劃嗎？</span><span class="sxs-lookup"><span data-stu-id="0f324-202">Can I modify the Planner plans?</span></span>
<span data-ttu-id="0f324-203">是的，Advisor for Teams 建立部署團隊後，您應該更新 Planner 計劃，使這項計劃能夠完全支援 Teams 的推出。</span><span class="sxs-lookup"><span data-stu-id="0f324-203">Yes, after Advisor for Teams has created your Deployment team, you should update the Planner plan so it best supports your Teams rollout.</span></span> <span data-ttu-id="0f324-204">您可以修改任何項目，如目標區、工作、工作詳細資訊，就像其他任何 Planner 計劃一樣。</span><span class="sxs-lookup"><span data-stu-id="0f324-204">You can modify anything - buckets, tasks, task details - just like any other Planner plan.</span></span>


### <a name="can-i-modify-the-forms-survey"></a><span data-ttu-id="0f324-205">我可以修改 Forms 問卷嗎？</span><span class="sxs-lookup"><span data-stu-id="0f324-205">Can I modify the Forms survey?</span></span>
<span data-ttu-id="0f324-206">可以，Advisor for Teams 建立部署團隊後，您可以視需要修改 Forms 問卷。</span><span class="sxs-lookup"><span data-stu-id="0f324-206">Yes, after Advisor for Teams has created your Deployment team, you can modify the Forms survey as needed.</span></span>

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a><span data-ttu-id="0f324-207">Advisor for Teams 會收集有關我組織的哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="0f324-207">What information is Advisor for Teams collecting about my organization?</span></span>
<span data-ttu-id="0f324-208">Advisor for Teams 會尋求您的同意才收集非 EUII (使用者識別資訊)。</span><span class="sxs-lookup"><span data-stu-id="0f324-208">Advisor for Teams requests your agreement to collecting non-EUII (end user identifying information).</span></span> <span data-ttu-id="0f324-209">這些資訊以遙測形式進行收集，將有關 Advisor for Teams 成功導入後的成果以及需要改善之處的回饋意見提供給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0f324-209">The information that is collected is in the form of telemetry that provides feedback to Microsoft on how well Advisor for Teams is driving successful outcomes and where it may need to be improved.</span></span> <span data-ttu-id="0f324-210">相同的資料也會用來找出 Microsoft 可以主動與您組織合作的機會，協助您進行部署。</span><span class="sxs-lookup"><span data-stu-id="0f324-210">This same data is used to identify opportunities for Microsoft to proactively engage with your organization in an effort to assist with your deployment.</span></span>

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a><span data-ttu-id="0f324-211">我可以使用 Advisor for Teams 搭配 FastTrack 嗎？</span><span class="sxs-lookup"><span data-stu-id="0f324-211">Can I use Advisor for Teams with FastTrack?</span></span>
<span data-ttu-id="0f324-212">可以，FastTrack 會針對所有希望部署 Teams 的客戶運用 Advisor for Teams。</span><span class="sxs-lookup"><span data-stu-id="0f324-212">Yes, FastTrack leverages Advisor for Teams for all customers looking to deploy Teams.</span></span> <span data-ttu-id="0f324-213">他們可以使用 Advisor for Teams 協助您部署團隊的初始設定 (如有需要)，也可以在 Teams 推出期間針對特定主題提供所需的支援。</span><span class="sxs-lookup"><span data-stu-id="0f324-213">They can assist with the initial setup of your Deployment team using Advisor for Teams (if required) and also provide as-needed support on specific topics during your Teams rollout.</span></span>

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a><span data-ttu-id="0f324-214">我可以與合作夥伴一起使用 Advisor for Teams 嗎？</span><span class="sxs-lookup"><span data-stu-id="0f324-214">Can I use Advisor for Teams with a partner?</span></span>
<span data-ttu-id="0f324-215">可以，您使用 Advisor for Teams 的同時，也可以利用部署合作夥伴進行 Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="0f324-215">Yes, you can use Advisor for Teams while also using a deployment partner for your Teams deployment.</span></span> <span data-ttu-id="0f324-216">如果您的合作夥伴是 CSP 並代替您管理租用戶，則您的合作夥伴可以使用 Advisor for Teams 建立部署團隊並協助您執行整個專案。</span><span class="sxs-lookup"><span data-stu-id="0f324-216">If your partner is a CSP and manages your tenant on your behalf, they can use Advisor for Teams to create your Deployment team and assist you with executing the overall project.</span></span> <span data-ttu-id="0f324-217">此外，您可以與任何合作夥伴合作，方法是將這些個人新增為部署團隊中的來賓，讓他們參與成為整個專案團隊的成員。</span><span class="sxs-lookup"><span data-stu-id="0f324-217">Additionally, you can work with any partner by adding those individuals as guests in your Deployment team, to allow them to participate as a member of the overall project team.</span></span>

### <a name="how-do-i-use-planner"></a><span data-ttu-id="0f324-218">如何使用 Planner？</span><span class="sxs-lookup"><span data-stu-id="0f324-218">How do I use Planner?</span></span>
<span data-ttu-id="0f324-219">請參閱 [Microsoft Planner 說明](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) 和 [Planner 快速入門影片](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。</span><span class="sxs-lookup"><span data-stu-id="0f324-219">Check out [Microsoft Planner help](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) and the [Planner quick-start videos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).</span></span> 

### <a name="how-do-i-use-forms"></a><span data-ttu-id="0f324-220">如何使用 Forms？</span><span class="sxs-lookup"><span data-stu-id="0f324-220">How do I use Forms?</span></span>
<span data-ttu-id="0f324-221">請前往 [Forms 說明中心](https://support.office.com/forms)。</span><span class="sxs-lookup"><span data-stu-id="0f324-221">Go to the [Forms help center](https://support.office.com/forms).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0f324-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="0f324-222">Related topics</span></span>

[<span data-ttu-id="0f324-223">如何推出 Teams</span><span class="sxs-lookup"><span data-stu-id="0f324-223">How to roll out Teams</span></span>](How-to-roll-out-teams.md)
