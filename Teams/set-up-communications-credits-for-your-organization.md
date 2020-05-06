---
title: 設定貴組織的通訊點數
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: '瞭解如何為您的使用者和組織設定通訊點數（PSTN 消費）帳單授權。 '
ms.openlocfilehash: 5fb963bbea97a41b6dbd6b68d5d7e0c162dc5a05
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042940"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="5c06e-103">設定貴組織的通訊點數</span><span class="sxs-lookup"><span data-stu-id="5c06e-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="5c06e-104">如果您想要在商務用 Skype 和 Microsoft 團隊中使用免付費電話號碼，就必須設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="5c06e-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="5c06e-105">此外，建議您針對您的通話方案（國內或國際）及需要撥出至**任何目的地**的音訊會議使用者設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="5c06e-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="5c06e-106">包含許多國家/地區，但某些目的地可能不會包含在您的通話方案或音訊會議訂閱中。</span><span class="sxs-lookup"><span data-stu-id="5c06e-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="5c06e-107">如果您沒有設定通訊信用帳單，並將**通訊點數**授權指派給您的使用者，而您的組織時間卻超出了幾分鐘（視您所在國家/地區的通話方案或音訊會議方案而定），這些使用者將無法撥打電話或撥出音訊會議會議。</span><span class="sxs-lookup"><span data-stu-id="5c06e-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="5c06e-108">您可以透過閱讀通訊點數來取得詳細資訊（包括建議的融資金額）[嗎？](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="5c06e-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c06e-109">若要瞭解成本多少，請[參閱這裡的速度](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="5c06e-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="5c06e-110">步驟1：將音訊會議或通話方案授權指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="5c06e-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="5c06e-111">當您註冊時，視您的國家/地區而定，您會收到特定的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="5c06e-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="5c06e-112">您可以在 [國家或地區可用性] 清單中搜尋您的國家或地區，以取得[音訊會議與通話方案](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization)，以查看您會收到的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="5c06e-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="5c06e-113">在您使用這些分鐘數之後，通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="5c06e-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="5c06e-114">若要避免發生這種情況，您必須設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="5c06e-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="5c06e-115">若要這樣做，**您必須將音訊會議或電話系統授權指派**給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="5c06e-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="5c06e-116">將**音訊會議**授權指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="5c06e-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="5c06e-117">請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-117">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
    
    <span data-ttu-id="5c06e-118">指派此授權之後，您將需要設定音訊會議。</span><span class="sxs-lookup"><span data-stu-id="5c06e-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="5c06e-119">如需逐步指示，請參閱[在 Office 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="5c06e-120">為您的使用者指派**電話系統**和**國內或國內和國際**通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="5c06e-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="5c06e-121">請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-121">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c06e-122">雖然通訊點數不需要，但您仍需要指派**國內通話方案**或**國內與國際通話方案**授權。</span><span class="sxs-lookup"><span data-stu-id="5c06e-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="5c06e-123">指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="5c06e-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5c06e-124">如需逐步指示，請參閱[設定通話方案](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="5c06e-125">如需詳細資訊，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="5c06e-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="5c06e-126">步驟2：為您的組織設定通訊點數</span><span class="sxs-lookup"><span data-stu-id="5c06e-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="5c06e-127">使用您的公司或學校帳戶登入新的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="5c06e-127">Sign in to the new Microsoft 365 admin center with your work or school account.</span></span>
    
2. <span data-ttu-id="5c06e-128">在 Microsoft 365 系統管理中心的左導覽中，前往 [**帳單** > **購買服務**]。</span><span class="sxs-lookup"><span data-stu-id="5c06e-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="5c06e-129">向下滾動，然後選取 [**附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="5c06e-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="5c06e-130">選取 [**通訊點數**]。</span><span class="sxs-lookup"><span data-stu-id="5c06e-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="5c06e-131">在 [**通訊點數**訂閱] 頁面上，填入您的資訊，然後按 **[下一步]**：</span><span class="sxs-lookup"><span data-stu-id="5c06e-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="5c06e-132">**新增基金**輸入您要新增至帳戶的金額。</span><span class="sxs-lookup"><span data-stu-id="5c06e-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="5c06e-133">如果您沒有啟用自動加值，在這些資金耗盡之後，使用通訊點數啟用的通話功能將會中斷（例如輸入免付費服務）。</span><span class="sxs-lookup"><span data-stu-id="5c06e-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="5c06e-134">為了避免必須在每次餘額達到0（零）時，手動補充通訊點數餘額，我們建議您啟用自動加值功能。</span><span class="sxs-lookup"><span data-stu-id="5c06e-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="5c06e-135">**自動充電**啟用自動加值功能會在餘額低於您所設定的閾值時自動重填您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5c06e-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="5c06e-136">建議您使用**自動**加值設定，避免您的通訊點數達到0（零）時的任何服務中斷。</span><span class="sxs-lookup"><span data-stu-id="5c06e-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="5c06e-137">當您在充電交易失敗時，您會收到電子郵件，當您將交易失效時（例如已過期的信用卡），以及通訊點數平衡達到0（零）時。</span><span class="sxs-lookup"><span data-stu-id="5c06e-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="5c06e-138">重新**充電金額**輸入您想要在**您的帳戶**達到下列觸發金額之後，將 [要新增至] 方塊中的金額。</span><span class="sxs-lookup"><span data-stu-id="5c06e-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="5c06e-139">**觸發金額**在 **[餘額低於**] 方塊中輸入要用來「*觸發*」自動加值的金額。</span><span class="sxs-lookup"><span data-stu-id="5c06e-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="5c06e-140">當您的餘額低於此金額時，會自動將自動加上的金額新增到您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5c06e-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="5c06e-141">在使用服務時，基金將只會套用至 Microsoft 已發佈費率的通訊點數。</span><span class="sxs-lookup"><span data-stu-id="5c06e-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="5c06e-142">在購買日期的12個月內未使用的任何資金將到期並 forfeited。</span><span class="sxs-lookup"><span data-stu-id="5c06e-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="5c06e-143">只有在使用 alloted 基金時，才會套用 [每月帳單]，以瞭解如何檢查您的每月使用方式，請參閱[商務用 SKYPE PSTN 使用報告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="5c06e-144">輸入您的付款資訊，然後按一下 [**下單**]。</span><span class="sxs-lookup"><span data-stu-id="5c06e-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="5c06e-145">如果您是大量授權客戶，您可以選擇要付款的企業協定號碼。</span><span class="sxs-lookup"><span data-stu-id="5c06e-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="5c06e-146">如果您有多個企業協定編號，您可以選取要用來進行付款的企業協定。</span><span class="sxs-lookup"><span data-stu-id="5c06e-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="5c06e-147">您也可以指定要與企業協定編號（如果適用）關聯的採購訂單編號的機會。</span><span class="sxs-lookup"><span data-stu-id="5c06e-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="5c06e-148">每個組織將會有不同的通話方案成交量和比率使用方式。</span><span class="sxs-lookup"><span data-stu-id="5c06e-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="5c06e-149">您必須從目前的服務提供者取得這種類型的使用資料。</span><span class="sxs-lookup"><span data-stu-id="5c06e-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="5c06e-150">已在使用商務用 skype Online 的組織已經在**商務用 skype 系統管理中心** > **報告** > **PSTN 使用狀況詳細**資料包告，以取得使用方式資料。</span><span class="sxs-lookup"><span data-stu-id="5c06e-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="5c06e-151">當您設定通訊點數時，您需要調查貴組織的通話使用量，以判斷您需要的金額。</span><span class="sxs-lookup"><span data-stu-id="5c06e-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="5c06e-152">您可以透過查看**PSTN 使用狀況詳細資料**報告來取得通話使用狀況的資訊。</span><span class="sxs-lookup"><span data-stu-id="5c06e-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="5c06e-153">如果您需要儲存資料或建立自訂報表，此報告可讓您將通話資料記錄匯出至 Excel。</span><span class="sxs-lookup"><span data-stu-id="5c06e-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="5c06e-154">若要瞭解使用方式，請參閱[商務用 SKYPE PSTN 使用報告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-154">To learn how to see usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="5c06e-155">步驟3：指派通訊點數授權給使用者</span><span class="sxs-lookup"><span data-stu-id="5c06e-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="5c06e-156">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="5c06e-156">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="5c06e-157">在 Microsoft 365 系統管理中心的左導覽中，移至 [**使用者** > 作用中的**使用者**]，然後從清單中選取一個或多位使用者。</span><span class="sxs-lookup"><span data-stu-id="5c06e-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="5c06e-158">選擇 [**授權及應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="5c06e-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="5c06e-159">將**通訊點數**切換至 [**開啟**] 以指派此授權，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="5c06e-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c06e-160">即使您有指派**企業版 E5**授權的使用者，仍建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="5c06e-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="5c06e-161">想要瞭解方案和價格？</span><span class="sxs-lookup"><span data-stu-id="5c06e-161">Want to know about plans and pricing?</span></span>

<span data-ttu-id="5c06e-162">您可以造訪下列其中一個連結來查看方案和定價：</span><span class="sxs-lookup"><span data-stu-id="5c06e-162">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="5c06e-163">通話方案</span><span class="sxs-lookup"><span data-stu-id="5c06e-163">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="5c06e-164">音訊會議方案</span><span class="sxs-lookup"><span data-stu-id="5c06e-164">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="5c06e-165">電話系統方案</span><span class="sxs-lookup"><span data-stu-id="5c06e-165">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="5c06e-166">您也可以登[入 Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)並移至**帳單** > **訂閱** > 的 [**新增訂閱**]，以查看資訊。</span><span class="sxs-lookup"><span data-stu-id="5c06e-166">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="5c06e-167">若要查看含有每個功能所需的授權或授權的表格，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="5c06e-167">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5c06e-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="5c06e-168">Related topics</span></span>

- [<span data-ttu-id="5c06e-169">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5c06e-169">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="5c06e-170">設定雲端語音信箱 - 管理說明</span><span class="sxs-lookup"><span data-stu-id="5c06e-170">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="5c06e-171">設定[Office 365 的](calling-plans-for-office-365.md)[通話方案](set-up-calling-plans.md)和通話方案</span><span class="sxs-lookup"><span data-stu-id="5c06e-171">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="5c06e-172">加值和管理通訊點數</span><span class="sxs-lookup"><span data-stu-id="5c06e-172">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
