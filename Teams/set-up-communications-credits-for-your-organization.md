---
title: 設定貴組織的 [通訊點數]
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
- m365initiative-voice
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
description: '瞭解如何設定 PSTN 消費 (訂閱) 使用者和組織帳單授權。 '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117101"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="05c1d-103">設定貴組織的 [通訊點數]</span><span class="sxs-lookup"><span data-stu-id="05c1d-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="05c1d-104">如果您想要在商務用 Skype 和 Microsoft Teams 中使用免付費號碼，您必須設定通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="05c1d-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="05c1d-105">此外，我們建議您為需要撥出至任何目的地之通話方案 (國內或國際) 和音訊會議使用者設定通訊 **信用額度**。</span><span class="sxs-lookup"><span data-stu-id="05c1d-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="05c1d-106">包含許多國家/地區，但部分目的地可能不包含在通話方案或音訊會議訂閱中。</span><span class="sxs-lookup"><span data-stu-id="05c1d-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="05c1d-107">如果您沒有設定通訊信用額度帳單，並指派通訊信用額度授權給使用者，而貴組織 (視您國家/地區) 的通話方案或音訊會議方案而用完通話分鐘數，這些使用者將無法撥打電話或撥出音訊會議。</span><span class="sxs-lookup"><span data-stu-id="05c1d-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="05c1d-108">您可以閱讀什麼是通訊信用額度，以取得更多資訊，包括建議的基金 [金額？](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="05c1d-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="05c1d-109">若要瞭解費用， [請參閱這裡的費率](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="05c1d-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="05c1d-110">步驟 1：指派音訊會議或通話方案授權給使用者</span><span class="sxs-lookup"><span data-stu-id="05c1d-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="05c1d-111">當您註冊時，會根據您的國家/地區獲得特定分鐘數。</span><span class="sxs-lookup"><span data-stu-id="05c1d-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="05c1d-112">您可以在音訊會議與通話方案的國家/地區可用性[](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)清單中搜尋您的國家/地區，以查看您可獲得的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="05c1d-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="05c1d-113">當您使用這些通話分鐘數後，通話將會中斷。</span><span class="sxs-lookup"><span data-stu-id="05c1d-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="05c1d-114">若要避免發生這種情況，您必須設定通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="05c1d-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="05c1d-115">若要這麼做 **，您必須指派** 音訊會議或電話系統授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="05c1d-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="05c1d-116">指派 **音訊會議授權** 給使用者。</span><span class="sxs-lookup"><span data-stu-id="05c1d-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="05c1d-117">請參閱 [指派 Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="05c1d-117">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    <span data-ttu-id="05c1d-118">指派此授權之後，您必須設定音訊會議。</span><span class="sxs-lookup"><span data-stu-id="05c1d-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="05c1d-119">有關逐步指示，請參閱在 Microsoft [365 或 Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)中試用或購買音訊會議。</span><span class="sxs-lookup"><span data-stu-id="05c1d-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="05c1d-120">指派 **電話系統** 及 **國內或** 國內及國際通話方案授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="05c1d-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="05c1d-121">請參閱 [指派 Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="05c1d-121">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="05c1d-122">雖然通訊信用額度不一樣，您仍然需要指派國內通話方案或 **國內和國際** 通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="05c1d-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="05c1d-123">指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織的人。</span><span class="sxs-lookup"><span data-stu-id="05c1d-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="05c1d-124">有關逐步指示，請參閱 [設定通話方案](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="05c1d-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="05c1d-125">詳細資訊，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="05c1d-125">For more information, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="05c1d-126">步驟 2：為貴組織設定通訊信用額度</span><span class="sxs-lookup"><span data-stu-id="05c1d-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="05c1d-127">使用公司或學校帳戶來登錄 [Microsoft 365](https://portal.office.com/Adminportal) 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="05c1d-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="05c1d-128">在 Microsoft 365 系統管理中心的左側流覽中，前往 **帳單**  >  **購買服務**。</span><span class="sxs-lookup"><span data-stu-id="05c1d-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="05c1d-129">向下卷起並選取 **附加元件**。</span><span class="sxs-lookup"><span data-stu-id="05c1d-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="05c1d-130">選取 **通訊信用額度**。</span><span class="sxs-lookup"><span data-stu-id="05c1d-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="05c1d-131">在 [**通訊信用額度訂閱**> 頁面上，填入您的資訊，然後按一下 [下 **一步：**</span><span class="sxs-lookup"><span data-stu-id="05c1d-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="05c1d-132">**新增資金** 輸入要新加到帳戶的金額。</span><span class="sxs-lookup"><span data-stu-id="05c1d-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="05c1d-133">如果您未啟用自動充值，一旦這些資金用盡，使用通訊信用額度啟用的通話功能將會中斷 (例如免付費服務) 。</span><span class="sxs-lookup"><span data-stu-id="05c1d-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="05c1d-134">為了避免每次餘額達到 0 或零 (時，) 手動補充通訊信用額度餘額，建議您啟用自動充值功能。</span><span class="sxs-lookup"><span data-stu-id="05c1d-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="05c1d-135">**自動充電** 當餘額低於您設定閾值時，啟用自動加值功能會自動重新填入您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="05c1d-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="05c1d-136">建議您使用自動充值設定，以避免通訊信用額度餘額達到 0 (零) 。</span><span class="sxs-lookup"><span data-stu-id="05c1d-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="05c1d-137">當充值交易成功、充值交易失敗 (例如過期的信用卡) ，以及您的通訊信用額度餘額達到 0 (零) 時，您就會收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="05c1d-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="05c1d-138">**充值金額** 在下列觸發金額達到觸發金額時，在您想要新加到您帳戶的加值方塊中輸入金額。</span><span class="sxs-lookup"><span data-stu-id="05c1d-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="05c1d-139">**觸發金額** 在當餘額低於方塊時輸入金額，此方塊會用來'*觸發*'自動充值。</span><span class="sxs-lookup"><span data-stu-id="05c1d-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="05c1d-140">一旦餘額低於此金額，加值金額會自動新加到您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="05c1d-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="05c1d-141">當服務使用時，資金只會以 Microsoft 發佈費率適用于通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="05c1d-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="05c1d-142">購買日期後 12 個月內未使用的任何資金將會到期並予以沒收。</span><span class="sxs-lookup"><span data-stu-id="05c1d-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="05c1d-143">只有在已使用已分配資金時，才能針對通訊信用額度按月計費，若要瞭解如何檢查每月使用量，請參閱商務用 [Skype PSTN 使用方式報告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="05c1d-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="05c1d-144">輸入您的付款資訊，然後按一下 **[下單**> 。</span><span class="sxs-lookup"><span data-stu-id="05c1d-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="05c1d-145">如果您是大量授權客戶，您可以選擇要付款的企業協定號碼。</span><span class="sxs-lookup"><span data-stu-id="05c1d-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="05c1d-146">如果您有多個企業協定編號，您可以選取要用於付款的企業協定。</span><span class="sxs-lookup"><span data-stu-id="05c1d-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="05c1d-147">如果適用，您也會有機會指定要與企業 (建立關聯的) 。</span><span class="sxs-lookup"><span data-stu-id="05c1d-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="05c1d-148">每個組織都會考慮不同的通話方案使用量和費率。</span><span class="sxs-lookup"><span data-stu-id="05c1d-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="05c1d-149">您必須從目前的服務提供者取得這類使用方式資料。</span><span class="sxs-lookup"><span data-stu-id="05c1d-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="05c1d-150">已經使用商務用 Skype Online 作為服務提供者的組織可以在 **Microsoft Teams** 系統管理中心報告  >    >  **PSTN** 使用方式詳細資料包告中查看使用方式資料。</span><span class="sxs-lookup"><span data-stu-id="05c1d-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="05c1d-151">當您設定通訊額度時，您必須調查貴組織的通話使用量，以決定您需要的金額。</span><span class="sxs-lookup"><span data-stu-id="05c1d-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="05c1d-152">您可以查看 PSTN 使用方式詳細資料包告，以取得 **通話使用方式** 資訊。</span><span class="sxs-lookup"><span data-stu-id="05c1d-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="05c1d-153">如果您需要儲存資料或建立自訂報表，此報表可讓您將通話資料記錄匯出至 Excel。</span><span class="sxs-lookup"><span data-stu-id="05c1d-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="05c1d-154">若要瞭解如何查看使用方式，請閱讀 [PSTN 使用方式報告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。</span><span class="sxs-lookup"><span data-stu-id="05c1d-154">To learn how to see usage, read [PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="05c1d-155">步驟 3：指派通訊信用額度授權給使用者</span><span class="sxs-lookup"><span data-stu-id="05c1d-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="05c1d-156">使用公司或學校帳戶來登錄 [Microsoft 365](https://portal.office.com/Adminportal) 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="05c1d-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="05c1d-157">在 Microsoft 365 系統管理中心的左側導覽中，前往使用者活動使用者，然後從清單中  >  選取使用者。</span><span class="sxs-lookup"><span data-stu-id="05c1d-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="05c1d-158">選擇 **授權與應用程式**。</span><span class="sxs-lookup"><span data-stu-id="05c1d-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="05c1d-159">將 **通訊信用額度切換** 為 **開啟** 以指派此授權， **然後選取** 儲存 。</span><span class="sxs-lookup"><span data-stu-id="05c1d-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="05c1d-160">即使您有指派企業 **版 E5** 授權的使用者，仍建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="05c1d-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="05c1d-161">您可以使用 [Powershell](/powershell/module/skype/?view=skype-ps) 以單一命令將授權和應用程式指派給多個使用者。</span><span class="sxs-lookup"><span data-stu-id="05c1d-161">You can use [Powershell](/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="05c1d-162">想要瞭解方案與價格嗎？</span><span class="sxs-lookup"><span data-stu-id="05c1d-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="05c1d-163">您可以流覽下列其中一個連結來查看方案與價格：</span><span class="sxs-lookup"><span data-stu-id="05c1d-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="05c1d-164">通話方案</span><span class="sxs-lookup"><span data-stu-id="05c1d-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="05c1d-165">音訊會議方案</span><span class="sxs-lookup"><span data-stu-id="05c1d-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="05c1d-166">電話系統方案</span><span class="sxs-lookup"><span data-stu-id="05c1d-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="05c1d-167">您也可以登錄 [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)系統管理中心，然後到帳單訂閱  >    >  **新增訂閱** 來查看資訊。</span><span class="sxs-lookup"><span data-stu-id="05c1d-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="05c1d-168">若要查看每個功能所需的授權或授權資料表，請參閱 Microsoft Teams [附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="05c1d-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="05c1d-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="05c1d-169">Related topics</span></span>

- [<span data-ttu-id="05c1d-170">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="05c1d-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="05c1d-171">設定雲端語音信箱 - 管理說明</span><span class="sxs-lookup"><span data-stu-id="05c1d-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="05c1d-172">[設定 Microsoft](set-up-calling-plans.md) [365 或 Office 365](calling-plans-for-office-365.md)的通話方案與通話方案</span><span class="sxs-lookup"><span data-stu-id="05c1d-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="05c1d-173">加值和管理通訊點數</span><span class="sxs-lookup"><span data-stu-id="05c1d-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
