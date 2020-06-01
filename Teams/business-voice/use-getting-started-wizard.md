---
title: 使用 [快速入門精靈] 設定商務語音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443a59513d3a3151bdcc83250bf40ec4ac4398bb
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412620"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="d2242-102">使用 [快速入門精靈] 設定商務語音</span><span class="sxs-lookup"><span data-stu-id="d2242-102">Use the Getting Started wizard to set up Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2242-103">本文中的資訊僅適用於**含**通話方案的商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="d2242-104">含通話方案的商務語音只有在選取的國家和地區才能使用。</span><span class="sxs-lookup"><span data-stu-id="d2242-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="d2242-105">閱讀本文之前，請參閱[商務語音的適用國家與地區](country-region-availability.md)，以查看您的國家或地區是否支援含通話方案的商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="d2242-106">如果您的租用戶所在國家或地區不支援含通話方案的商務語音，請參閱[從 Microsoft 轉銷商或合作夥伴取得協助](reseller-partner-support.md)。</span><span class="sxs-lookup"><span data-stu-id="d2242-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="d2242-107">Microsoft 365 商務語音快速入門精靈可讓您在 Microsoft Teams 中快速設定，以撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="d2242-107">The Getting Started wizard for Microsoft 365 Business Voice gets you set up quickly to make and receive phone calls in Microsoft Teams.</span></span> <span data-ttu-id="d2242-108">如果您是剛起步的小型企業，精靈可在幾分鐘內幫助您啟動並運作電話號碼、通話功能表、問候以及更多。</span><span class="sxs-lookup"><span data-stu-id="d2242-108">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="d2242-109">如果您是已建立電話語音解決方案的較大型企業，精靈可幫助您設定試驗，因此在推行到所有人之前，可先讓少數使用者嘗試商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-109">If you're a larger business with an established telephony solution, the wizard can help you set up a pilot so a few users can try Business Voice before you roll it out for everyone.</span></span> <span data-ttu-id="d2242-110">無論是哪一種方式，精靈完成後，您就可以開始使用商務語音！</span><span class="sxs-lookup"><span data-stu-id="d2242-110">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="d2242-111">建議您在開始使用精靈之前，先閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="d2242-111">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="d2242-112">當您準備好執行精靈時，請在[開始使用 Microsoft 365 商務語音](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice)頁面選取 **[開始使用]**。</span><span class="sxs-lookup"><span data-stu-id="d2242-112">When you're ready to run the wizard, select **Get started** on the [Get started with Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) page.</span></span> <span data-ttu-id="d2242-113">請使用建立訂閱所用的帳戶登入，或其他全域系統管理員的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="d2242-113">Sign in by using the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2242-114">只有當您的使用者信箱位於 Microsoft 365 中時，才能使用 Microsoft Teams 和商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-114">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="d2242-115">不支援內部部署 Exchange Server 上的信箱。</span><span class="sxs-lookup"><span data-stu-id="d2242-115">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="d2242-116">[快速入門] 精靈不支援商務用 Skype 混合式部署。</span><span class="sxs-lookup"><span data-stu-id="d2242-116">The Getting Started Wizard doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="d2242-117">如果您擁有商務用 Skype 混合式部署，且想要設定 Business Voice，請參閱[在組織中設定電話系統](../setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="d2242-117">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

<span data-ttu-id="d2242-118">如果不想立即自訂任何內容，就大功告成了！</span><span class="sxs-lookup"><span data-stu-id="d2242-118">If you don't want to customize anything immediately, you're done!</span></span> <span data-ttu-id="d2242-119">您可以立即開始使用商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-119">You can start using Business Voice right away.</span></span>

## <a name="emergency-services-location"></a><span data-ttu-id="d2242-120">緊急服務位置</span><span class="sxs-lookup"><span data-stu-id="d2242-120">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="d2242-121">如果需要變更緊急地址，請按一下 <b>[編輯]</b>，然後輸入新地址。</span><span class="sxs-lookup"><span data-stu-id="d2242-121">If you want to change the emergency address, click <b>Edit</b>, and then enter a new address.</span></span> <span data-ttu-id="d2242-122">您提供的地址需經過驗證，以確認其合法性且格式正確，可供緊急回應服務時使用。</span><span class="sxs-lookup"><span data-stu-id="d2242-122">The address that you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="d2242-123">然後，此地址會指派給在下一個步驟中指派號碼的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d2242-123">This address is then assigned to all users that you assign a number to in the next step.</span></span> <span data-ttu-id="d2242-124">如果您有位於超過單一位置的員工，請參閱<a href="./customize-business-voice.md">商務語音設計自訂</a>，了解如何在準備 [快速入門精靈] 後，新增並指派更多緊急地址。</span><span class="sxs-lookup"><span data-stu-id="d2242-124">If you have employees in more than one location, see <a href="./customize-business-voice.md">Business Voice design customization</a> to add and assign more emergency addresses after you prepare the Getting Started wizard.</span></span></td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

<span data-ttu-id="d2242-125">如需詳細資訊，請參閱[什麼是緊急位置、地址和通話路由](../what-are-emergency-locations-addresses-and-call-routing.md)？</span><span class="sxs-lookup"><span data-stu-id="d2242-125">For more information, see [What are emergency locations, addresses, and call routing](../what-are-emergency-locations-addresses-and-call-routing.md)?</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="d2242-126">公司電話號碼</span><span class="sxs-lookup"><span data-stu-id="d2242-126">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="d2242-127">除了新的當地電話號碼以外，您還可以購買免付費電話號碼，或將現有的號碼移轉到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d2242-127">In addition to a new local phone number, you can purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="d2242-128">若要設定免付費電話號碼，您必須購買通訊點數。</span><span class="sxs-lookup"><span data-stu-id="d2242-128">To set up a toll-free number, you need to purchase Communications Credits.</span></span> <span data-ttu-id="d2242-129">若要將一或多個號碼移轉至 Microsoft 365，請在精靈完成後，前往 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="d2242-129">To port one or more numbers to Microsoft 365, go to the <a href="https://admin.teams.microsoft.com">Teams admin center</a> after the wizard finishes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="d2242-130">如果您將現有的電話號碼移轉到 Microsoft 365，您仍會在精靈中看到臨時的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2242-130">If you port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="d2242-131">這是預期行為 。</span><span class="sxs-lookup"><span data-stu-id="d2242-131">This is expected.</span></span> <span data-ttu-id="d2242-132">完成精靈及移轉程序後，預先存在的號碼將取代臨時電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2242-132">After you complete the wizard and the porting process, the temporary phone number will be replaced by the pre-existing number.</span></span>

## <a name="user-licenses"></a><span data-ttu-id="d2242-133">[使用者授權]</span><span class="sxs-lookup"><span data-stu-id="d2242-133">User licenses</span></span>

<table>
    <tr>
        <td><span data-ttu-id="d2242-134">若要指派使用者授權，請選取組織中需要撥打或接聽 Teams 外部電話 (例如與供應商通話) 的人員。</span><span class="sxs-lookup"><span data-stu-id="d2242-134">To assign user licenses, select the people in your organization who need to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="d2242-135">您只能指派可用的商務語音授權數量。</span><span class="sxs-lookup"><span data-stu-id="d2242-135">You can only assign as many Business Voices licenses as you have available.</span></span> <span data-ttu-id="d2242-136">如果需要更多，您可以在精靈完成後購買額外的授權。</span><span class="sxs-lookup"><span data-stu-id="d2242-136">If you need more, you can buy additional licenses after the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="d2242-137">在精靈完成後，您可以將現有的電話號碼移轉到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d2242-137">You can port existing phone numbers to Microsoft 365 after the wizard is finished.</span></span> <span data-ttu-id="d2242-138">完成移轉程序後，已移轉的電話號碼將取代由精靈提供的臨時電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2242-138">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers that the wizard provided.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="d2242-139">來電問候語</span><span class="sxs-lookup"><span data-stu-id="d2242-139">Incoming-call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="d2242-140">您可以上傳最多 5 Mb 的音效檔 (MP3 或 WAV) 做為來電問候語，或可以輸入您的問候語，而 Microsoft 365 會使用 [文字轉換語音] 功能將其讀給來電者。</span><span class="sxs-lookup"><span data-stu-id="d2242-140">You can upload a sound file (MP3 or WAV) of up to 5 Megabytes (MB) to use as a call greeting, or you can type your greeting, and Microsoft 365 will use text-to-speech to read it to the caller.</span></span> <span data-ttu-id="d2242-141">當來電者撥打貴公司的電話號碼時，來電者首先聽到的即是該問候語。</span><span class="sxs-lookup"><span data-stu-id="d2242-141">The greeting will be the first thing callers hear when they call your company phone number.</span></span> <span data-ttu-id="d2242-142">若為文字轉換語音，您可能需要使用拼音來正確發音。</span><span class="sxs-lookup"><span data-stu-id="d2242-142">For text-to-speech, you might need to use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="d2242-143">通話功能表和來電轉接</span><span class="sxs-lookup"><span data-stu-id="d2242-143">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="d2242-144">您可以將所有來電轉接給特定使用者，或設定來電者可選擇的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="d2242-144">You can forward all calls to a specific user, or you can set up a menu that the caller can choose options from.</span></span> <span data-ttu-id="d2242-145">如果建立通話功能表，您可以指定來電者透過語音或在電話鍵盤上按數字來選取選項。</span><span class="sxs-lookup"><span data-stu-id="d2242-145">If you create a call menu, you specify options that the caller can select by voice or by pressing a number on a phone's keypad.</span></span> <span data-ttu-id="d2242-146">每個功能表選項皆可將通話轉接給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="d2242-146">Each menu option can forward calls to a specific user.</span></span><br><br>
        <span data-ttu-id="d2242-147">您可以上傳最多 5MB 的音效檔 (MP3 或 WAV) 以提供來電者指示，或者直接輸入指示。</span><span class="sxs-lookup"><span data-stu-id="d2242-147">You can upload a sound file (MP3 or WAV) of up to 5 MB that gives instructions to the caller, or you can type the instructions.</span></span> <span data-ttu-id="d2242-148">Microsoft 365 會使用 [文字轉換語音] 將指示讀給來電者。</span><span class="sxs-lookup"><span data-stu-id="d2242-148">Microsoft 365 will use text-to-speech to read them to the caller.</span></span> <span data-ttu-id="d2242-149">您可能需要按照發音拼音字詞，以獲得正確發音。</span><span class="sxs-lookup"><span data-stu-id="d2242-149">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="d2242-150">[快速入門精靈] 可協助您設定簡單的通話功能表，讓您快速上手。</span><span class="sxs-lookup"><span data-stu-id="d2242-150">The Getting Started wizard helps you set up a simple call menu to get you up and running quickly.</span></span> <span data-ttu-id="d2242-151">如果要設定通話功能表中的多個電話號碼，或者要設定更複雜的通話功能表 (也稱為自動語音應答)，您可以在結束精靈後，參閱[設定雲端自動語音應答](set-up-auto-attendants.md)。</span><span class="sxs-lookup"><span data-stu-id="d2242-151">If you have multiple phone numbers that you want to set up call menus for or you want to set up more complex call menus (also called auto attendants), see [Set up a Cloud auto attendant](set-up-auto-attendants.md) after you finish the wizard.</span></span>

<table>
    <tr>
        <td> <p><span data-ttu-id="d2242-152">[快速入門精靈] 會使用您輸入的資訊來設定商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-152">The Getting Started wizard takes the information that you enter and sets up Business Voice.</span></span> <span data-ttu-id="d2242-153">您可以在<b>概觀</b>頁面看到指派給使用者的電話號碼、查看通話功能表，聆聽問候語等。</span><span class="sxs-lookup"><span data-stu-id="d2242-153">On the <b>Overview</b> page, you can see what phone numbers are assigned to your users, look at your call menu, listen to your greeting, and more.</span></span></p>
             <p><span data-ttu-id="d2242-154">設定需要數分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d2242-154">Setup takes several minutes.</span></span> <span data-ttu-id="d2242-155">若您選取 <b>[完成]</b>，我們會繼續在背景中設定商務語音。</span><span class="sxs-lookup"><span data-stu-id="d2242-155">If you select <b>Done</b>, we'll continue to set up Business Voice in the background.</span></span> <span data-ttu-id="d2242-156">您也可以等待設定完成。</span><span class="sxs-lookup"><span data-stu-id="d2242-156">Or just wait until setup is finished.</span></span> <span data-ttu-id="d2242-157">完成之後，請移至 <a href="https://admin.teams.microsoft.com" target="_blank">[Teams 系統管理中心]</a> 的 <b>[語音]</b>，以設定更多商務語音功能。</span><span class="sxs-lookup"><span data-stu-id="d2242-157">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
