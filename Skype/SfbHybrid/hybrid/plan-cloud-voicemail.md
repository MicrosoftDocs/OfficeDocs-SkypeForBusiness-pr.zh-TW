---
title: 針對內部部署使用者規劃雲端語音信箱服務 |PBX 商務用 Skype Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文說明實施 Microsoft 雲端語音信箱服務的優點、規劃考慮及需求。 如需設定雲端語音信箱的相關資訊, 請參閱設定雲端語音信箱。
ms.openlocfilehash: 0071154ab1b9c1211725dd9b6addc2dfd5449e15
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2019
ms.locfileid: "36185530"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="5926d-104">為內部部署使用者規劃雲端語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="5926d-104">Plan Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="5926d-105">概觀</span><span class="sxs-lookup"><span data-stu-id="5926d-105">Overview</span></span>

<span data-ttu-id="5926d-106">本文說明針對您的內部部署使用者實施 Microsoft 雲端語音信箱服務的優點、規劃考慮及需求。</span><span class="sxs-lookup"><span data-stu-id="5926d-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service for your on-premises users.</span></span> <span data-ttu-id="5926d-107">如需設定雲端語音信箱的相關資訊, 請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="5926d-108">雲端語音信箱取代 Exchange 整合訊息 (UM), 提供在 Exchange Server 2019 或 Exchange Online 上擁有信箱之商務用 Skype 2019 語音使用者的語音訊息功能。</span><span class="sxs-lookup"><span data-stu-id="5926d-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="5926d-109">雲端語音信箱可為您的內部部署和線上使用者提供下列好處:</span><span class="sxs-lookup"><span data-stu-id="5926d-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="5926d-110">使用增強的語音對話來應答及放入功能的語音信箱</span><span class="sxs-lookup"><span data-stu-id="5926d-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="5926d-111">使用商務用 Skype Online 或 Outlook 用戶端, 在使用者的 Exchange 信箱中存取語音信箱</span><span class="sxs-lookup"><span data-stu-id="5926d-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span>

- <span data-ttu-id="5926d-112">使用 Office 365 web 入口網站來管理語音信箱選項的能力</span><span class="sxs-lookup"><span data-stu-id="5926d-112">The ability to use the Office 365 web-based portal to manage voicemail options</span></span>

- <span data-ttu-id="5926d-113">在內部部署或雲端的 Exchange 信箱支援</span><span class="sxs-lookup"><span data-stu-id="5926d-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="5926d-114">從 Exchange Online 整合通訊中使用現有的使用者問候語</span><span class="sxs-lookup"><span data-stu-id="5926d-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

<span data-ttu-id="5926d-115">如需功能比較的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-115">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="5926d-116">商務用 Skype Server 2019 會繼續針對其信箱位於舊版 Exchange Server (2013、2016) 的使用者使用 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="5926d-116">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="5926d-117">瞭解將根據 Exchange Server 和商務用 Skype Server 版本使用哪些語音信箱方案, 是規劃遷移到商務用 Skype Server 2019 或 Exchange Server 2019 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="5926d-117">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="5926d-118">如需有關移植與互通性的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-118">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="5926d-119">使用雲端語音信箱, 您的管理工作會大大簡化, 因為:</span><span class="sxs-lookup"><span data-stu-id="5926d-119">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="5926d-120">您不需要設定 Exchange UM 角色。</span><span class="sxs-lookup"><span data-stu-id="5926d-120">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="5926d-121">雲端語音信箱的設定工作變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="5926d-121">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="5926d-122">語音信箱功能的更新會直接在雲端傳送, 所以您的使用者永遠能夠存取最新功能和更新, 而不依賴累計更新 (CUs)。</span><span class="sxs-lookup"><span data-stu-id="5926d-122">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="5926d-123">您在內部部署和線上 Exchange 信箱中都有相同的控制項集合。</span><span class="sxs-lookup"><span data-stu-id="5926d-123">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="5926d-124">如需這些控制項的詳細資訊, 請參閱[設定電話系統語音信箱](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="5926d-124">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).</span></span>

<span data-ttu-id="5926d-125">下圖顯示混合式部署中的雲端語音信箱:</span><span class="sxs-lookup"><span data-stu-id="5926d-125">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="5926d-127">未接聽的通話處理方式如下:</span><span class="sxs-lookup"><span data-stu-id="5926d-127">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="5926d-128">針對駐留在商務用 Skype 2019 內部部署的使用者, 未回復的通話會由內部部署商務用 Skype 伺服器傳送給線上雲端語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="5926d-128">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span>
2. <span data-ttu-id="5926d-129">此服務會處理語音信箱, 包括 [文字]。</span><span class="sxs-lookup"><span data-stu-id="5926d-129">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="5926d-130">然後, 此服務會將語音信箱存款至使用者的 Exchange 信箱中, 不論該信箱是內部部署還是在線上。</span><span class="sxs-lookup"><span data-stu-id="5926d-130">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="5926d-131">使用者可以從商務用 Skype 或 Outlook 用戶端存取其語音信箱。</span><span class="sxs-lookup"><span data-stu-id="5926d-131">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="5926d-132">需求</span><span class="sxs-lookup"><span data-stu-id="5926d-132">Requirements</span></span>

<span data-ttu-id="5926d-133">下列需求假設您已在支援的拓撲中部署商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5926d-133">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="5926d-134">您的需求取決於您的案例:</span><span class="sxs-lookup"><span data-stu-id="5926d-134">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="5926d-135">如果您已在線上使用 Exchange UM, 且您升級至商務用 Skype 2019, 您將需要修改託管的語音信箱原則, 並確認您的主機服務提供者已正確設定。</span><span class="sxs-lookup"><span data-stu-id="5926d-135">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="5926d-136">如需詳細資訊, 請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-136">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="5926d-137">如果您是在內部部署使用 Exchange UM, 或是使用 Exchange UM online 和內部部署的使用者混合, 您將需要修改您的託管語音信箱原則和主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="5926d-137">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="5926d-138">如需詳細資訊, 請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-138">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="5926d-139">針對雲端語音信箱的新設定, 請依照[設定雲端語音信箱服務](configure-cloud-voicemail.md)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="5926d-139">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="5926d-140">除了上述需求之外, 下列需求必須設定為連線至 Microsoft 雲端語音信箱服務:</span><span class="sxs-lookup"><span data-stu-id="5926d-140">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="5926d-141">混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="5926d-141">Hybrid connectivity.</span></span> <span data-ttu-id="5926d-142">如果您已部署商務用 Skype Server, 且想要為您的內部部署使用者啟用雲端語音信箱, 您必須確保您在內部部署與線上環境之間已設定混合式連接。</span><span class="sxs-lookup"><span data-stu-id="5926d-142">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="5926d-143">這有時稱為分割網域配置。</span><span class="sxs-lookup"><span data-stu-id="5926d-143">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="5926d-144">如需詳細資訊, 請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md), 以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="5926d-144">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="5926d-145">在商務用 Skype Server 中, 您必須在企業語音及託管語音信箱中啟用內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="5926d-145">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="5926d-146">必須設定外部 Exchange Web 服務 (EWS) URL 和自動探索, 或一些雲端語音信箱功能將會受到限制。</span><span class="sxs-lookup"><span data-stu-id="5926d-146">An External Exchange Web Services (EWS) URL and Autodiscover must be set up or some Cloud Voicemail features will be limited.</span></span>

- <span data-ttu-id="5926d-147">如果您僅限內部部署&#x2014;也就是, 只有 Exchange 和商務用 Skype 內部部署伺服器&#x2014;, 但是您想要利用雲端語音信箱, 就不需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="5926d-147">If you have an on-premises only deployment&#x2014;that is, only Exchange and Skype for Business on-premises servers&#x2014;but you want to take advantage of Cloud Voicemail, you will not need additional licenses.</span></span>

## <a name="migration-and-interoperability"></a><span data-ttu-id="5926d-148">遷移和互通性</span><span class="sxs-lookup"><span data-stu-id="5926d-148">Migration and interoperability</span></span>

<span data-ttu-id="5926d-149">如果您打算部署商務用 Skype Server 2019 和/或 Exchange Server 2019, 您必須仔細規劃遷移, 以確保繼續提供語音訊息服務。</span><span class="sxs-lookup"><span data-stu-id="5926d-149">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="5926d-150">請記住下列事項:</span><span class="sxs-lookup"><span data-stu-id="5926d-150">Keep the following in mind:</span></span>

- <span data-ttu-id="5926d-151">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="5926d-151">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="5926d-152">商務用 Skype Server 2019 不再與 Exchange Online UM 整合</span><span class="sxs-lookup"><span data-stu-id="5926d-152">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="5926d-153">[雲端語音信箱] 的版本互通性和支援的拓撲會列在下表中, 此表格會比較使用者可能駐留的商務用 Skype 伺服器版本, 以及提供 Exchange 信箱的可能版本。</span><span class="sxs-lookup"><span data-stu-id="5926d-153">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table, which compares the Skype for Business Server versions the user might be homed on with the possible version providing their Exchange Mailbox.</span></span> <span data-ttu-id="5926d-154">雲端語音信箱只適用于商務用 Skype Server 和 Exchange Server 2019 或 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5926d-154">Cloud Voicemail only works with Skype for Business Server and Exchange Server 2019 or Exchange Online.</span></span>

| | <span data-ttu-id="5926d-155">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="5926d-155">Exchange Server 2013</span></span> | <span data-ttu-id="5926d-156">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="5926d-156">Exchange Server 2016</span></span> | <span data-ttu-id="5926d-157">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="5926d-157">Exchange Server 2019</span></span> | <span data-ttu-id="5926d-158">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5926d-158">Exchange Online</span></span>   |
|:---    |:--- |:--- |:--- |:---  |
| <span data-ttu-id="5926d-159">商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="5926d-159">Skype for Business Server 2019</span></span> | <span data-ttu-id="5926d-160">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="5926d-160">Exchange Server UM</span></span> | <span data-ttu-id="5926d-161">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="5926d-161">Exchange Server UM</span></span> | <span data-ttu-id="5926d-162">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="5926d-162">Cloud Voicemail</span></span> | <span data-ttu-id="5926d-163">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="5926d-163">Cloud Voicemail</span></span> |
| <span data-ttu-id="5926d-164">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="5926d-164">Skype for Business Server 2015</span></span> | <span data-ttu-id="5926d-165">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="5926d-165">Exchange Server UM</span></span> | <span data-ttu-id="5926d-166">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="5926d-166">Exchange Server UM</span></span> | <span data-ttu-id="5926d-167">雲端語音信箱<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5926d-167">Cloud Voicemail<sup>1</sup></span></span> | <span data-ttu-id="5926d-168">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="5926d-168">Cloud Voicemail</span></span> <br> <span data-ttu-id="5926d-169">Exchange Online UM<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5926d-169">Exchange Online UM<sup>2</sup></span></span> |
| <span data-ttu-id="5926d-170">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5926d-170">Lync Server 2013</span></span> <br>  | <span data-ttu-id="5926d-171">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="5926d-171">Exchange Server UM</span></span> | <span data-ttu-id="5926d-172">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="5926d-172">Exchange Server UM</span></span> | <span data-ttu-id="5926d-173">不支援</span><span class="sxs-lookup"><span data-stu-id="5926d-173">Not Supported</span></span> | <span data-ttu-id="5926d-174">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="5926d-174">Cloud Voicemail</span></span> <br> <span data-ttu-id="5926d-175">Exchange Online UM<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5926d-175">Exchange Online UM<sup>2</sup></span></span> |

<span data-ttu-id="5926d-176"><sup>1</sup>還沒有看到這個選項嗎？</span><span class="sxs-lookup"><span data-stu-id="5926d-176"><sup>1</sup> Don't see this option yet?</span></span> <span data-ttu-id="5926d-177">目前正在推出, 您的組織可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="5926d-177">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="5926d-178">請參閱步驟 6, 考慮選擇 [ [Exchange 整合訊息] 線上遷移支援](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support
), 以加入與雲端語音信箱的計畫內連接。</span><span class="sxs-lookup"><span data-stu-id="5926d-178">See Step 6, Consider opting in, in [Exchange Unified Messaging Online migration support](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support
) to opt-in for planned connectivity to Cloud Voicemail.</span></span>

<span data-ttu-id="5926d-179"><sup>2</sup> , 直到棄用為止。</span><span class="sxs-lookup"><span data-stu-id="5926d-179"><sup>2</sup> Until deprecated.</span></span> <span data-ttu-id="5926d-180">如需詳細資訊, 請參閱[Exchange 整合訊息線上遷移支援](../../sfbserver2019/plan/exchange-unified-messaging-online-migration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-180">See [Exchange Unified Messaging Online migration support](../../sfbserver2019/plan/exchange-unified-messaging-online-migration-support.md) for more information.</span></span> 

<span data-ttu-id="5926d-181">Microsoft 建議下列遷移路徑:</span><span class="sxs-lookup"><span data-stu-id="5926d-181">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="5926d-182">如果您要升級到商務用 Skype Server 2019, 您可以在 Exchange Server 2013 或2016中使用 Exchange UM, 但如果您使用的是 Exchange Server 2019, 則必須升級至雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="5926d-182">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>
- <span data-ttu-id="5926d-183">如果您要升級到 Exchange Server 2019, 且您使用舊版 Exchange Server UM 進行商務用 Skype Server 語音訊息, Microsoft 建議您先升級到商務用 Skype Server 2019, 然後再升級信箱。</span><span class="sxs-lookup"><span data-stu-id="5926d-183">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="5926d-184">否則, 語音訊息功能將會遺失。</span><span class="sxs-lookup"><span data-stu-id="5926d-184">Otherwise, voice messaging capabilities will be lost.</span></span>
- <span data-ttu-id="5926d-185">如果您要升級到商務用 Skype Server 2019, 且已針對含 Exchange Online UM 的語音信箱設定商務用 Skype Server 2015, 則使用者的語音信箱會自動從 Exchange Online UM 遷移到雲端語音信箱 (當他們的帳戶移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="5926d-185">If you are upgrading to Skype for Business Server 2019, and have Skype for Business Server 2015 configured for voicemail with Exchange Online UM, users' voicemail will automatically migrate from Exchange Online UM to Cloud Voicemail when their account is moved to Skype for Business Server 2019.</span></span> 

<span data-ttu-id="5926d-186">如需規劃遷移的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="5926d-186">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
