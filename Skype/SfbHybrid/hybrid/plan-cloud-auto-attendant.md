---
title: 規劃雲端自動語音應答
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動助手的概覽
ms.openlocfilehash: 1a5f1aad4cd983f1f3839f47c54404d168ecf7f0
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "36185536"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="3b7e9-103">規劃雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="3b7e9-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="3b7e9-104">Exchange Server 2019 或 exchange Online 中已不再提供與 Exchange 整合通訊 (Exchange Server 2013 或 Exchange Server 2016) 搭配使用的自動回應。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="3b7e9-105">如果您的商務用 Skype Server 2019 實現與其中一個 Exchange 版本整合, 您將需要使用與電話系統相關聯的線上雲端語音功能。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="3b7e9-106">請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)的相關資訊, 瞭解如何將 exchange UM 服務託管于 exchange Server 2013 和2016移至雲端。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="3b7e9-107">這本身就代表, 如果您想要使用 [自動語音傳送] 等統一訊息功能, 就會有混合式的商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="3b7e9-108">如需詳細資訊, 請參閱[設定商務用 Skype Server 與 Office 365 之間的混合式連接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-108">See [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="3b7e9-109">自動語音應答是一種雲端服務, 可接受客戶呼叫及播放問候語、透過功能表選項提供, 以及使用語音或撥號鍵台與來電者進行互動, 以將來電路由到正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-109">An Auto attendant is a cloud service that accept customer calls and play greetings, provide them with menu options, and interact with callers using speech or the dialpad to route their calls to the right destination.</span></span> <span data-ttu-id="3b7e9-110">每個自動語音應答都會獲指派**資源帳戶**(請參閱[設定](configure-onprem-ra.md)您的商務用 Skype Server 2019 系統), 該系統會直接連結到 Microsoft 團隊系統管理中心的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-110">Each auto attendant is assigned a **resource account** (see[Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3b7e9-111">請參閱[什麼是雲端自動](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)語音應答？如需自動語音應答的詳細資訊, 以及自動語音應答的選項和功能。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="3b7e9-112">您可以將多個 Microsoft 服務號碼或混合式編號指派給自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-112">You can assign multiple Microsoft service numbers or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="3b7e9-113">對雲端自動語音應答的撥入呼叫可以採用數種路徑, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![自動語音應答的圖表](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="3b7e9-115">透過商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="3b7e9-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="3b7e9-116">透過[會話邊界控制器](/MicrosoftTeams/direct-routing-border-controllers.md)和[直接路由](/MicrosoftTeams/direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="3b7e9-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="3b7e9-117">透過 Office 365 中的數位線上進行。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-117">Via a number homed online in Office 365.</span></span>

<span data-ttu-id="3b7e9-118">另請參閱:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-118">Also see:</span></span>

- [<span data-ttu-id="3b7e9-119">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="3b7e9-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="3b7e9-120">自動接聽來電並傳送來電</span><span class="sxs-lookup"><span data-stu-id="3b7e9-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="3b7e9-121">需求</span><span class="sxs-lookup"><span data-stu-id="3b7e9-121">Requirements</span></span>

<span data-ttu-id="3b7e9-122">下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="3b7e9-123">您的需求取決於您的案例:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="3b7e9-124">如果您已經在使用 Exchange UM 線上或內部部署, 且您升級至商務用 Skype 2019, 您將需要使用雲端自動語音應答來捕獲自動語音應答的結構, 並在雲端重新建立。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-124">If you are already using Exchange UM online or on premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="3b7e9-125">如需詳細資訊, 請參閱[將 EXCHANGE UM 自動語音應答或呼叫佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="3b7e9-126">如需雲端自動語音應答的新設定, 請依照[設定資源帳戶](configure-onprem-ra.md)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="3b7e9-127">除了上述需求之外, 必須將以下需求設定為連線至 Microsoft 雲端自動語音應答服務:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="3b7e9-128">混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-128">Hybrid connectivity.</span></span> <span data-ttu-id="3b7e9-129">如果您已部署商務用 Skype Server, 且想要為您的內部部署使用者啟用雲端自動回應, 您必須確保您在內部部署與線上環境之間已設定混合式連接。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="3b7e9-130">這有時稱為分割網域配置。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="3b7e9-131">如需詳細資訊, 請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md), 以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="3b7e9-132">如果您要將電話號碼指派給自動語音應答, 您必須具備[Office 365 企業版 E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)授權。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="3b7e9-133">針對每個自動語音應答建立內部部署[資源帳戶](/MicrosoftTeams/manage-resource-accounts.md), 並指派電話號碼和授權。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-133">Create an on-premises [resource account](/MicrosoftTeams/manage-resource-accounts.md) for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="3b7e9-134">遷移和互通性</span><span class="sxs-lookup"><span data-stu-id="3b7e9-134">Migration and interoperability</span></span>

<span data-ttu-id="3b7e9-135">如果您打算部署商務用 Skype Server 2019 和/或 Exchange Server 2019, 您必須小心地規劃您的遷移, 以確保自動語音應答的支援。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="3b7e9-136">請記住下列事項:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-136">Keep the following in mind:</span></span>

- <span data-ttu-id="3b7e9-137">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="3b7e9-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="3b7e9-138">Exchange 整合訊息線上處於停用模式</span><span class="sxs-lookup"><span data-stu-id="3b7e9-138">Exchange Unified Messaging Online is in retirement mode</span></span>
- <span data-ttu-id="3b7e9-139">商務用 Skype Server 2019 不再與 Exchange Online UM 整合</span><span class="sxs-lookup"><span data-stu-id="3b7e9-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="3b7e9-140">雲端自動語音應答可以使用商務用 Skype Server 2019、2015和2013進行設定。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="3b7e9-141">Microsoft 建議下列遷移路徑:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="3b7e9-142">如果您要升級到商務用 Skype Server 2019, 您可以在 Exchange Server 2013 或2016中使用 Exchange UM, 但如果您使用的是 Exchange Server 2019, 則必須升級至雲端自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="3b7e9-143">如果您要升級到 Exchange Server 2019, 且您使用舊版 Exchange Server UM 進行商務用 Skype Server 語音訊息, Microsoft 建議您先升級到商務用 Skype Server 2019, 然後再升級信箱。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="3b7e9-144">否則, 語音訊息功能將會遺失。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="3b7e9-145">如需規劃遷移的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="3b7e9-146">遷移先前實施的 Exchange UM 自動語音應答系統</span><span class="sxs-lookup"><span data-stu-id="3b7e9-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="3b7e9-147">我們目前不支援自動遷移至在 Exchange 2013 或2016中建立的 UM 自動語音應答系統雲端。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="3b7e9-148">若要手動重新建立自動語音應答系統, 您必須:</span><span class="sxs-lookup"><span data-stu-id="3b7e9-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="3b7e9-149">使用 Exchange admin powershell 命令來查看舊自動語音應答系統的結構, 包括任何嵌套的自動語音應答及呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-149">Use Exchange admin powershell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="3b7e9-150">建立與每個 UM 自動語音應答節點相關聯的文字轉換語音腳本或錄製郵件的複本。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="3b7e9-151">針對每個自動語音應答節點建立內部部署端點, 包括將測試電話號碼和授權指派給物件。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="3b7e9-152">請注意, 您現在可以指派線上服務 (例如電話系統) 所使用的內部部署電話號碼授權。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="3b7e9-153">使用商務用 Skype Online 和電話系統來執行新的雲端自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-153">Implement a new Cloud auto attendant service with Skype for Business Online and Phone System.</span></span> <span data-ttu-id="3b7e9-154">請參閱[設定資源帳戶](configure-onprem-ra.md)以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="3b7e9-155">如此一來, 請上傳與每個 UM 自動語音應答節點相關聯的文字轉換語音腳本或錄製的訊息。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="3b7e9-156">測試雲端自動語音應答的功能。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="3b7e9-157">將指派給舊版 Exchange UM 自動語音應答的電話號碼重新指派給新建立的主雲端自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="3b7e9-158">如需這些步驟的詳細資訊, 請參閱[將 EXCHANGE UM 自動語音應答或呼叫佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

## <a name="additional-planning-resources"></a><span data-ttu-id="3b7e9-159">其他規劃資源</span><span class="sxs-lookup"><span data-stu-id="3b7e9-159">Additional planning resources</span></span>

<span data-ttu-id="3b7e9-160">標題為「小型企業」的教學課程[範例-設定自動](/microsoftteams/tutorial-org-aa)語音應答: 完成收集使用者需求之資訊的程式、規劃自動語音應答及使用者的結構 (以及可能通話佇列)、撰寫功能表提示, 以及在線上系統管理中心實施方案。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-160">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="3b7e9-161">查看教學課程, 並使用這裡的練習來建立您的方案。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-161">review the tutorial and use the exercises there to create your plan.</span></span>

<span data-ttu-id="3b7e9-162">當您有符合您需求的實體結構, 以及能有效引導客戶的腳本時, 請繼續[設定資源帳戶](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-162">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="3b7e9-163">如[KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)所述, 不鼓勵將在伺服器2015中建立的 Exchange UM 自動語音應答移至執行伺服器2019的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-163">As mentioned in [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="3b7e9-164">針對時間, 您必須將它們放在在 coexistance 模式下執行的商務用 Skype Server 2015 池。</span><span class="sxs-lookup"><span data-stu-id="3b7e9-164">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b7e9-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="3b7e9-165">See Also</span></span>

[<span data-ttu-id="3b7e9-166">規劃商務用 Skype Server 與 Exchange Server 遷移</span><span class="sxs-lookup"><span data-stu-id="3b7e9-166">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="3b7e9-167">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="3b7e9-167">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="3b7e9-168">使用電話使用者介面啟用自訂提示錄製</span><span class="sxs-lookup"><span data-stu-id="3b7e9-168">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="3b7e9-169">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="3b7e9-169">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="3b7e9-170">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="3b7e9-170">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="3b7e9-171">Exchange UM:[自動接聽並傳送來電](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="3b7e9-171">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="3b7e9-172">規劃商務用 Skype Server 與 Office 365 之間的混合式連接</span><span class="sxs-lookup"><span data-stu-id="3b7e9-172">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="3b7e9-173">在商務用 Skype Server 和 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="3b7e9-173">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="3b7e9-174">KB4480742: 將連絡人物件移至商務用 Skype Server 2019 後, 無法呼叫訂閱者存取或自動語音應答失敗並出現「500伺服器內部」錯誤</span><span class="sxs-lookup"><span data-stu-id="3b7e9-174">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
