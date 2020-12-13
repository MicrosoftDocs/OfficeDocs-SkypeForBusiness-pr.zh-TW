---
title: 規劃內部部署使用者的雲端語音信箱服務 |PBX 商務用 Skype Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文說明實施 Microsoft Cloud 語音信箱服務的優點、規劃考慮和需求。 如需設定雲端語音信箱的詳細資訊，請參閱設定雲端語音信箱。
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662088"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="da78d-104">規劃內部部署使用者的雲端語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="da78d-104">Plan Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="da78d-105">概觀</span><span class="sxs-lookup"><span data-stu-id="da78d-105">Overview</span></span>

<span data-ttu-id="da78d-106">本文說明為您的內部部署使用者實施 Microsoft Cloud 語音信箱服務的優點、規劃考慮和需求。</span><span class="sxs-lookup"><span data-stu-id="da78d-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service for your on-premises users.</span></span> <span data-ttu-id="da78d-107">如需設定雲端語音信箱的詳細資訊，請參閱 [設定雲端語音信箱服務](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="da78d-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="da78d-108">雲端語音信箱會取代 Exchange 整合通訊 (UM) 提供語音信箱功能，以供在 Exchange Server 2019 或 Exchange Online 上擁有信箱的商務用 Skype 2019 語音使用者使用。</span><span class="sxs-lookup"><span data-stu-id="da78d-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="da78d-109">雲端語音信箱為您的內部部署和線上使用者提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="da78d-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="da78d-110">帶有增強語音功能的語音信箱應答和放入功能</span><span class="sxs-lookup"><span data-stu-id="da78d-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="da78d-111">使用商務用 Skype Online 或 Outlook 用戶端，存取使用者的 Exchange 信箱中的語音信箱</span><span class="sxs-lookup"><span data-stu-id="da78d-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span>

- <span data-ttu-id="da78d-112">使用 Microsoft 365 系統管理中心管理語音信箱選項的功能</span><span class="sxs-lookup"><span data-stu-id="da78d-112">The ability to use the Microsoft 365 admin center to manage voicemail options</span></span>

- <span data-ttu-id="da78d-113">支援內部部署或雲端的 Exchange 信箱</span><span class="sxs-lookup"><span data-stu-id="da78d-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="da78d-114">從 Exchange Online 整合通訊利用現有的使用者問候語</span><span class="sxs-lookup"><span data-stu-id="da78d-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

> [!Important]
> <span data-ttu-id="da78d-115">在2021年7月31日，使用者將無法再透過商務用 Skype Online 用戶端存取其 Exchange 信箱中的語音信箱，將會停用商務用 skype Online。</span><span class="sxs-lookup"><span data-stu-id="da78d-115">Skype for Business Online will be retired on July 31, 2021 after which users will no longer be able to access voicemail in their Exchange mailbox through the Skype for Business Online client.</span></span>

<span data-ttu-id="da78d-116">如需有關功能比較的詳細資訊，請參閱 [Plan For 商務用 Skype server 和 Exchange Server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="da78d-116">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="da78d-117">商務用 Skype Server 2019 繼續針對信箱在舊版 Exchange Server 上的使用者使用 Exchange UM (2013，2016) 。</span><span class="sxs-lookup"><span data-stu-id="da78d-117">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="da78d-118">瞭解將根據 Exchange Server 和商務用 Skype Server 版本使用哪些語音信箱解決方案，是規劃將遷移至商務用 Skype Server 2019 或 Exchange Server 2019 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="da78d-118">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="da78d-119">如需有關遷移和互通性的詳細資訊，請參閱 [Plan For 商務用 Skype server 和 Exchange Server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="da78d-119">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="da78d-120">透過雲端語音信箱，您的系統管理工作會極大地簡化，原因如下：</span><span class="sxs-lookup"><span data-stu-id="da78d-120">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="da78d-121">不需要設定 Exchange UM 角色。</span><span class="sxs-lookup"><span data-stu-id="da78d-121">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="da78d-122">雲端語音信箱的設定工作變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="da78d-122">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="da78d-123">語音信箱功能的更新是直接在雲端中傳遞，所以您的使用者永遠可以存取最新的功能和更新，但不依賴累計更新 (Cu) 。</span><span class="sxs-lookup"><span data-stu-id="da78d-123">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="da78d-124">您可以在內部部署和線上 Exchange 信箱中使用相同的控制項集合。</span><span class="sxs-lookup"><span data-stu-id="da78d-124">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="da78d-125">如需這些控制項的詳細資訊，請參閱 [Set Up Phone 系統語音信箱](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。</span><span class="sxs-lookup"><span data-stu-id="da78d-125">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).</span></span>

<span data-ttu-id="da78d-126">下圖顯示混合式部署中的雲端語音信箱：</span><span class="sxs-lookup"><span data-stu-id="da78d-126">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="da78d-128">未回復的呼叫的處理方式如下：</span><span class="sxs-lookup"><span data-stu-id="da78d-128">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="da78d-129">若為位於內部部署商務用 Skype 2019 的使用者，則內部部署商務用 Skype Server 會將未應答的呼叫傳送至線上雲端語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="da78d-129">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span>
2. <span data-ttu-id="da78d-130">此服務會處理語音信箱，包括語音語音。</span><span class="sxs-lookup"><span data-stu-id="da78d-130">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="da78d-131">然後，此服務會將語音信箱存款至使用者的 Exchange 信箱中，不論該信箱是內部部署或線上。</span><span class="sxs-lookup"><span data-stu-id="da78d-131">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="da78d-132">使用者可以從商務用 Skype 或 Outlook 用戶端存取其語音信箱。</span><span class="sxs-lookup"><span data-stu-id="da78d-132">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="da78d-133">需求</span><span class="sxs-lookup"><span data-stu-id="da78d-133">Requirements</span></span>

<span data-ttu-id="da78d-134">下列需求假設您已在支援的拓撲中部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="da78d-134">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="da78d-135">您的需求取決於您的案例：</span><span class="sxs-lookup"><span data-stu-id="da78d-135">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="da78d-136">如果您已經在使用 Exchange UM 線上，且升級至商務用 Skype 2019，您將需要修改主控的語音信箱原則，並確認您的主機服務提供者設定正確。</span><span class="sxs-lookup"><span data-stu-id="da78d-136">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="da78d-137">如需詳細資訊，請參閱 [Configure Cloud 語音信箱服務](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="da78d-137">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="da78d-138">如果您在內部部署上使用 Exchange UM，或是使用 Exchange UM online 和內部部署混合使用使用者，您就需要修改所裝載的語音信箱原則及主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="da78d-138">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="da78d-139">如需詳細資訊，請參閱 [Configure Cloud 語音信箱服務](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="da78d-139">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="da78d-140">若要取得雲端語音信箱的新設定，請遵循 [設定雲端語音信箱服務](configure-cloud-voicemail.md)中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="da78d-140">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="da78d-141">除了上述需求之外，還必須設定下列需求，才能連線至 Microsoft 雲端語音信箱服務：</span><span class="sxs-lookup"><span data-stu-id="da78d-141">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="da78d-142">混合連接。</span><span class="sxs-lookup"><span data-stu-id="da78d-142">Hybrid connectivity.</span></span> <span data-ttu-id="da78d-143">如果您已部署商務用 Skype Server，而且想要為您的內部部署使用者啟用雲端語音信箱，您必須確定您的內部部署與線上環境之間已設定混合式連線能力。</span><span class="sxs-lookup"><span data-stu-id="da78d-143">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="da78d-144">這有時稱為分割網域設定。</span><span class="sxs-lookup"><span data-stu-id="da78d-144">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="da78d-145">如需詳細資訊，請參閱 [規劃商務用 Skype server 與 Microsoft 365 或 office 365 之間的混合](plan-hybrid-connectivity.md) 式連線，以及 [設定商務用 Skype server 與 office 365 的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="da78d-145">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="da78d-146">內部部署使用者必須在商務用 Skype Server 中啟用 Enterprise Voice 和主控語音信箱。</span><span class="sxs-lookup"><span data-stu-id="da78d-146">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="da78d-147">必須設定外部 Exchange Web 服務 (EWS) URL 和自動探索，否則將會限制某些雲端語音信箱功能。</span><span class="sxs-lookup"><span data-stu-id="da78d-147">An External Exchange Web Services (EWS) URL and Autodiscover must be set up or some Cloud Voicemail features will be limited.</span></span>

- <span data-ttu-id="da78d-148">如果您有內部部署 Exchange 伺服器，請使用 [設定 Exchange Server 信箱使用者的雲端語音信箱](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)中的步驟，來設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="da78d-148">If you have an on-premises Exchange server, set up Cloud Voicemail using the steps in [Set up Cloud Voicemail for Exchange Server Mailbox Users](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).</span></span>

## <a name="migration-and-interoperability"></a><span data-ttu-id="da78d-149">遷移和互通性</span><span class="sxs-lookup"><span data-stu-id="da78d-149">Migration and interoperability</span></span>

<span data-ttu-id="da78d-150">如果您計畫要部署商務用 Skype Server 2019 和/或 Exchange Server 2019，您必須仔細規劃遷移，以確保持續的語音訊息服務。</span><span class="sxs-lookup"><span data-stu-id="da78d-150">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="da78d-151">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="da78d-151">Keep the following in mind:</span></span>

- <span data-ttu-id="da78d-152">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="da78d-152">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="da78d-153">商務用 Skype Server 2019 不再與 Exchange Online UM 整合</span><span class="sxs-lookup"><span data-stu-id="da78d-153">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="da78d-154">下表列出雲端語音信箱的版本互通性和支援的拓撲，這會比較使用者可能所在的商務用 Skype Server 版本，其可提供其 Exchange 信箱的可能版本。</span><span class="sxs-lookup"><span data-stu-id="da78d-154">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table, which compares the Skype for Business Server versions the user might be homed on with the possible version providing their Exchange Mailbox.</span></span> <span data-ttu-id="da78d-155">如果您想要使用商務用 Skype 2019 與 Exchange Online 或 Exchange Server 2019，您必須使用雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="da78d-155">You need to use Cloud Voicemail if you want to use Skype for Business 2019 with Exchange Online or Exchange Server 2019.</span></span>

| | <span data-ttu-id="da78d-156">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="da78d-156">Exchange Server 2013</span></span> | <span data-ttu-id="da78d-157">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="da78d-157">Exchange Server 2016</span></span> | <span data-ttu-id="da78d-158">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="da78d-158">Exchange Server 2019</span></span> | <span data-ttu-id="da78d-159">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="da78d-159">Exchange Online</span></span>   |
|:---    |:--- |:--- |:--- |:---  |
| <span data-ttu-id="da78d-160">商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="da78d-160">Skype for Business Server 2019</span></span> | <span data-ttu-id="da78d-161">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="da78d-161">Exchange Server UM</span></span> | <span data-ttu-id="da78d-162">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="da78d-162">Exchange Server UM</span></span> | <span data-ttu-id="da78d-163">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="da78d-163">Cloud Voicemail</span></span> | <span data-ttu-id="da78d-164">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="da78d-164">Cloud Voicemail</span></span> |
| <span data-ttu-id="da78d-165">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="da78d-165">Skype for Business Server 2015</span></span> | <span data-ttu-id="da78d-166">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="da78d-166">Exchange Server UM</span></span> | <span data-ttu-id="da78d-167">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="da78d-167">Exchange Server UM</span></span> | <span data-ttu-id="da78d-168">不支援</span><span class="sxs-lookup"><span data-stu-id="da78d-168">Not supported</span></span> | <span data-ttu-id="da78d-169">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="da78d-169">Cloud Voicemail</span></span> |
| <span data-ttu-id="da78d-170">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da78d-170">Lync Server 2013</span></span> <br>  | <span data-ttu-id="da78d-171">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="da78d-171">Exchange Server UM</span></span> | <span data-ttu-id="da78d-172">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="da78d-172">Exchange Server UM</span></span> | <span data-ttu-id="da78d-173">不支援</span><span class="sxs-lookup"><span data-stu-id="da78d-173">Not Supported</span></span> | <span data-ttu-id="da78d-174">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="da78d-174">Cloud Voicemail</span></span> |

<span data-ttu-id="da78d-175">Microsoft 建議下列遷移路徑：</span><span class="sxs-lookup"><span data-stu-id="da78d-175">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="da78d-176">如果您要升級至商務用 Skype Server 2019，您可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果您使用 Exchange Server 2019，則必須升級至雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="da78d-176">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>
- <span data-ttu-id="da78d-177">如果您要升級至 Exchange Server 2019，而您使用舊版的 Exchange Server UM 來進行商務用 Skype Server 語音訊息，Microsoft 建議您在信箱升級之前，先升級至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="da78d-177">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="da78d-178">否則，語音訊息功能將會遺失。</span><span class="sxs-lookup"><span data-stu-id="da78d-178">Otherwise, voice messaging capabilities will be lost.</span></span>
- <span data-ttu-id="da78d-179">如果您要升級至商務用 Skype Server 2019，並已針對含 Exchange Online UM 的語音信箱設定商務用 Skype Server 2015，使用者的語音信箱將會在其帳戶移至商務用 Skype Server 2019 時，自動從 Exchange Online UM 遷移至雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="da78d-179">If you are upgrading to Skype for Business Server 2019, and have Skype for Business Server 2015 configured for voicemail with Exchange Online UM, users' voicemail will automatically migrate from Exchange Online UM to Cloud Voicemail when their account is moved to Skype for Business Server 2019.</span></span> 

<span data-ttu-id="da78d-180">如需規劃遷移的詳細資訊，請參閱 [規劃商務用 Skype Server 和 Exchange Server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="da78d-180">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
