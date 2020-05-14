---
title: 規劃雲端自動語音應答
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動語音應答的概覽
ms.openlocfilehash: d85c846a05448d8b1021bb5c1cac62c80ee1bf22
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221293"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="ac821-103">規劃雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="ac821-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="ac821-104">Exchange Server 2019 或 Exchange Online 中已不再提供與 Exchange 整合通訊（Exchange Server 2013 或 Exchange Server 2016）搭配使用的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ac821-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="ac821-105">如果您對商務用 Skype Server 2019 的實施與上述任一 Exchange 版本整合，您必須使用與電話系統相關聯的線上雲端語音功能。</span><span class="sxs-lookup"><span data-stu-id="ac821-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="ac821-106">如需將 exchange Server 2013 和2016上的 Exchange UM 服務移至雲端的詳細資訊，請參閱[Plan For 商務用 Skype server 和 Exchange Server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="ac821-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="ac821-107">如果您想要使用「整合通訊」功能（如自動語音應答），則這本身就表示您將具備商務用 Skype Server 2019 的混合式實現。</span><span class="sxs-lookup"><span data-stu-id="ac821-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="ac821-108">如需詳細資訊，請參閱[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="ac821-108">See [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="ac821-109">自動語音應答是一項雲端服務，可接受客戶來電和播放問候語、提供功能表選項，並與使用語音或撥號盤的來電者互動，以將來電路由傳送至正確目的地。</span><span class="sxs-lookup"><span data-stu-id="ac821-109">An auto attendant is a cloud service that accepts customer calls and plays greetings, provides them with menu options, and interacts with callers using speech or the dial pad to route their calls to the right destination.</span></span> <span data-ttu-id="ac821-110">每個自動語音應答都會被指派一個*資源帳戶*（請參閱[設定資源帳戶](configure-onprem-ra.md)）的商務用 Skype Server 2019 系統，該系統將直接連結到 Microsoft 小組系統管理中心中的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ac821-110">Each auto attendant is assigned a *resource account* (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ac821-111">請參閱[什麼是雲端自動](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)語音應答？如需有關自動語音應答的詳細資訊，以及自動語音應答的選項及功能有哪些。</span><span class="sxs-lookup"><span data-stu-id="ac821-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="ac821-112">您可以將多個 Microsoft 服務號碼、直接路由編號或混合號碼指派給自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ac821-112">You can assign multiple Microsoft service numbers, Direct Routing numbers, or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="ac821-113">對雲端自動語音應答的來電可以採用下列其中一種路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ac821-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![自動語音應答的圖表](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="ac821-115">透過商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="ac821-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="ac821-116">透過[會話邊界控制器](/MicrosoftTeams/direct-routing-border-controllers.md)和[直接路由](/MicrosoftTeams/direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="ac821-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="ac821-117">透過 Microsoft 365 或 Office 365 中的數位線上。</span><span class="sxs-lookup"><span data-stu-id="ac821-117">Via a number homed online in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="ac821-118">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="ac821-118">Also see:</span></span>

- [<span data-ttu-id="ac821-119">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="ac821-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="ac821-120">自動接聽和路由傳送來電</span><span class="sxs-lookup"><span data-stu-id="ac821-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="ac821-121">需求</span><span class="sxs-lookup"><span data-stu-id="ac821-121">Requirements</span></span>

<span data-ttu-id="ac821-122">下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="ac821-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="ac821-123">您的需求取決於您的案例：</span><span class="sxs-lookup"><span data-stu-id="ac821-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="ac821-124">如果您已在使用 Exchange UM 線上或內部部署，且升級至商務用 Skype 2019，您將需要捕獲自動語音應答的結構，並使用雲端自動語音應答在雲端中重新建立。</span><span class="sxs-lookup"><span data-stu-id="ac821-124">If you are already using Exchange UM online or on-premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="ac821-125">如需詳細資訊，請參閱[將 EXCHANGE UM 自動語音應答或通話佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="ac821-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="ac821-126">若為雲端自動語音應答的新設定，請遵循[設定資源帳戶](configure-onprem-ra.md)中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="ac821-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="ac821-127">除了上述需求之外，還必須設定下列需求，才能連線至 Microsoft Cloud 自動語音應答服務：</span><span class="sxs-lookup"><span data-stu-id="ac821-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="ac821-128">混合連接。</span><span class="sxs-lookup"><span data-stu-id="ac821-128">Hybrid connectivity.</span></span> <span data-ttu-id="ac821-129">如果您已部署商務用 Skype Server，而且想要為您的內部部署使用者啟用雲端自動語音應答，則必須確定您的內部部署與線上環境之間已設定混合式連線能力。</span><span class="sxs-lookup"><span data-stu-id="ac821-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="ac821-130">這有時稱為分割網域設定。</span><span class="sxs-lookup"><span data-stu-id="ac821-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="ac821-131">如需詳細資訊，請參閱[規劃商務用 Skype server 與 microsoft 365 或 office 365 之間的混合](plan-hybrid-connectivity.md)式連線，以及[設定商務用 Skype server 與 Microsoft 365 或 office 365 的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="ac821-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="ac821-132">如果您要將電話號碼指派給您的自動語音應答，則需要[Office 365 企業版 E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)授權。</span><span class="sxs-lookup"><span data-stu-id="ac821-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="ac821-133">為每個自動語音應答建立線上[資源帳戶](/MicrosoftTeams/manage-resource-accounts.md)或內部部署[資源帳戶](configure-onprem-ra.md)，並指派電話號碼和授權。</span><span class="sxs-lookup"><span data-stu-id="ac821-133">Create an online [resource account](/MicrosoftTeams/manage-resource-accounts.md) or on-premises [resource account](configure-onprem-ra.md) for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="ac821-134">遷移和互通性</span><span class="sxs-lookup"><span data-stu-id="ac821-134">Migration and interoperability</span></span>

<span data-ttu-id="ac821-135">如果您計畫要部署商務用 Skype Server 2019 和/或 Exchange Server 2019，您必須仔細規劃遷移，以確保自動語音應答繼續支援。</span><span class="sxs-lookup"><span data-stu-id="ac821-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="ac821-136">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="ac821-136">Keep the following in mind:</span></span>

- <span data-ttu-id="ac821-137">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="ac821-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="ac821-138">Exchange 整合通訊處於退休模式</span><span class="sxs-lookup"><span data-stu-id="ac821-138">Exchange Unified Messaging is in retirement mode</span></span>
- <span data-ttu-id="ac821-139">商務用 Skype Server 2019 不再與 Exchange Online UM 整合</span><span class="sxs-lookup"><span data-stu-id="ac821-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="ac821-140">雲端自動語音應答可使用商務用 Skype Server 2019、2015及2013進行設定。</span><span class="sxs-lookup"><span data-stu-id="ac821-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="ac821-141">Microsoft 建議下列遷移路徑：</span><span class="sxs-lookup"><span data-stu-id="ac821-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="ac821-142">如果您要升級至商務用 Skype Server 2019，您可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果您使用 Exchange Server 2019，則必須升級至雲端自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ac821-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="ac821-143">如果您要升級至 Exchange Server 2019，而您使用舊版的 Exchange Server UM 來進行商務用 Skype Server 語音訊息，Microsoft 建議您在信箱升級之前，先升級至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="ac821-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="ac821-144">否則，語音訊息功能將會遺失。</span><span class="sxs-lookup"><span data-stu-id="ac821-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="ac821-145">如需規劃遷移的詳細資訊，請參閱[規劃商務用 Skype Server 和 Exchange Server 遷移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="ac821-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="ac821-146">遷移先前所執行的 Exchange UM 自動語音應答系統</span><span class="sxs-lookup"><span data-stu-id="ac821-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="ac821-147">目前，我們不支援在 Exchange 2013 或2016中建立的 UM 自動語音應答系統上自動遷移至雲端。</span><span class="sxs-lookup"><span data-stu-id="ac821-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="ac821-148">若要手動重新建立自動語音應答系統，您必須：</span><span class="sxs-lookup"><span data-stu-id="ac821-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="ac821-149">使用 Exchange 系統管理 powershell 命令來檢查舊自動語音應答系統的結構，包括任何嵌套的自動語音應答及通話佇列。</span><span class="sxs-lookup"><span data-stu-id="ac821-149">Use Exchange admin powershell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="ac821-150">建立與每個 UM 自動語音應答節點相關聯的文字到語音腳本或錄製的訊息複本。</span><span class="sxs-lookup"><span data-stu-id="ac821-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="ac821-151">針對每個自動語音應答節點建立內部部署端點，包括將測試電話號碼和授權指派給物件。</span><span class="sxs-lookup"><span data-stu-id="ac821-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="ac821-152">請注意，您現在可以指派線上服務（如電話系統）所使用的內部部署電話號碼授權。</span><span class="sxs-lookup"><span data-stu-id="ac821-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="ac821-153">使用商務用 Skype Online 和電話系統來執行新的雲端自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="ac821-153">Implement a new Cloud auto attendant service with Skype for Business Online and Phone System.</span></span> <span data-ttu-id="ac821-154">請參閱[設定資源帳戶](configure-onprem-ra.md)以取得執行詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac821-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="ac821-155">當您這麼做時，請上傳文字到語音的腳本或與每個 UM 自動語音應答節點相關聯的錄製郵件。</span><span class="sxs-lookup"><span data-stu-id="ac821-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="ac821-156">測試雲端自動語音應答的功能。</span><span class="sxs-lookup"><span data-stu-id="ac821-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="ac821-157">將指派給舊 Exchange UM 自動語音應答的電話號碼重新指派給新建立的主雲端自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ac821-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="ac821-158">如需這些步驟的詳細資訊，請參閱將[EXCHANGE UM 自動語音應答或通話佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="ac821-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

## <a name="additional-planning-resources"></a><span data-ttu-id="ac821-159">其他規劃資源</span><span class="sxs-lookup"><span data-stu-id="ac821-159">Additional planning resources</span></span>

<span data-ttu-id="ac821-160">名為 Small business 的教學課程[範例-設定自動](/microsoftteams/tutorial-org-aa)語音應答會透過收集使用者需求的資訊、規劃自動語音應答和使用者的結構（也可能是呼叫佇列），撰寫功能表提示，以及在小組系統管理中心中實施計畫，來進行這項處理。</span><span class="sxs-lookup"><span data-stu-id="ac821-160">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Teams admin center.</span></span> <span data-ttu-id="ac821-161">請參閱教學課程，並使用練習以建立您的計畫。</span><span class="sxs-lookup"><span data-stu-id="ac821-161">Review the tutorial and use the exercises there to create your plan.</span></span>

<span data-ttu-id="ac821-162">當您具有符合您需求的實體結構，以及可有效指導客戶有效的腳本時，請繼續[設定資源帳戶](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="ac821-162">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="ac821-163">如[KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)中所述，不鼓勵將 Exchange UM 自動語音應答從伺服器2015建立至執行伺服器2019的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ac821-163">As mentioned in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="ac821-164">在這段時間內，您必須將其保留在 coexistance 模式中執行的商務用 Skype Server 2015 集區。</span><span class="sxs-lookup"><span data-stu-id="ac821-164">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac821-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ac821-165">See Also</span></span>

[<span data-ttu-id="ac821-166">規劃商務用 Skype Server 和 Exchange Server 遷移</span><span class="sxs-lookup"><span data-stu-id="ac821-166">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="ac821-167">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="ac821-167">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="ac821-168">使用電話使用者介面錄製自訂提示</span><span class="sxs-lookup"><span data-stu-id="ac821-168">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="ac821-169">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="ac821-169">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="ac821-170">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="ac821-170">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="ac821-171">Exchange UM：[自動接聽和路由傳送來電](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="ac821-171">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="ac821-172">規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="ac821-172">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="ac821-173">設定商務用 Skype Server 與 Microsoft 365 或 Office 365 的混合式連線</span><span class="sxs-lookup"><span data-stu-id="ac821-173">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="ac821-174">KB4480742：將連絡人物件移至商務用 Skype Server 2019 後，對訂閱者存取或自動語音應答的呼叫會失敗，並會出現「快速忙碌」和「500伺服器內部」錯誤。</span><span class="sxs-lookup"><span data-stu-id="ac821-174">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
