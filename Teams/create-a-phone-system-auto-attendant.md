---
title: 為 Microsoft 團隊設定自動助手
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: 瞭解如何為 Microsoft 團隊設定及測試自動語音應答。
ms.openlocfilehash: 1d19483fe458c38d01a9c46c982101eeab6546c2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033001"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="d55f2-103">設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="d55f2-103">Set up an auto attendant</span></span>

<span data-ttu-id="d55f2-104">自動語音應答讓其他人打電話給您的組織，並流覽功能表系統，以與正確的部門通話、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="d55f2-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="d55f2-105">您可以使用 Microsoft 團隊系統管理中心或 PowerShell，為您的組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d55f2-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="d55f2-106">請確定您已閱讀 [小組自動語音應答] [和 [呼叫佇列](plan-auto-attendant-call-queue.md) ] 的 [規劃]，然後依照本文 [中的程式](plan-auto-attendant-call-queue.md#getting-started) 執行。</span><span class="sxs-lookup"><span data-stu-id="d55f2-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="d55f2-107">自動語音應答可以根據來電者的輸入，將呼叫定向至下列其中一個目的地： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="d55f2-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="d55f2-108">**組織中的人員** -您組織中能夠接聽語音通話的人員。</span><span class="sxs-lookup"><span data-stu-id="d55f2-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="d55f2-109">這可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="d55f2-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="d55f2-110">**語音 app** -另一個自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d55f2-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="d55f2-111"> (選擇 [選擇此目的地時，與自動語音應答或通話佇列] 相關聯的資源帳戶。 ) </span><span class="sxs-lookup"><span data-stu-id="d55f2-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="d55f2-112">**外部電話號碼** -任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="d55f2-113"> (查看 [外部轉接技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)) 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="d55f2-114">**語音信箱** -與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d55f2-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="d55f2-115">**Operator** -為自動語音應答定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="d55f2-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="d55f2-116">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="d55f2-116">Defining an operator is optional.</span></span> <span data-ttu-id="d55f2-117">操作員可以定義為此清單中的任何其他目的地。</span><span class="sxs-lookup"><span data-stu-id="d55f2-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="d55f2-118">當您設定自動語音應答時，系統會提示您在各個階段選擇其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="d55f2-119">若要設定自動語音應答，請在 [小組管理中心] 中，展開 [語音]，按一下 [ **自動\*\*\*\*語音** ]，然後按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="d55f2-119">To set up an auto attendant, in the Teams admin center, expand **Voice** , click **Auto attendants** , and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="d55f2-120">一般資訊</span><span class="sxs-lookup"><span data-stu-id="d55f2-120">General info</span></span>

![[名稱]、[操作員]、[時區]、[語言] 和 [語音輸入] 的自動助理設定的螢幕擷取畫面](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="d55f2-122">在頂端方塊中輸入自動語音應答的名稱。</span><span class="sxs-lookup"><span data-stu-id="d55f2-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="d55f2-123">如果您想要指派運算子，請指定呼叫操作員的目的地。</span><span class="sxs-lookup"><span data-stu-id="d55f2-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="d55f2-124">這是選擇性 (但建議) 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-124">This is optional (but recommended).</span></span> <span data-ttu-id="d55f2-125">您可以設定 [ **運算子** ] 選項，讓呼叫者中斷功能表並向指定的人朗讀。</span><span class="sxs-lookup"><span data-stu-id="d55f2-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="d55f2-126">指定此自動語音應答的時區。</span><span class="sxs-lookup"><span data-stu-id="d55f2-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="d55f2-127">如果您在 [下班後建立單獨的通話流程](#call-flow-for-after-hours)，則會使用時區來計算上班時間。</span><span class="sxs-lookup"><span data-stu-id="d55f2-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="d55f2-128">指定此自動語音應答的語言。</span><span class="sxs-lookup"><span data-stu-id="d55f2-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="d55f2-129">這是將用於系統產生的語音提示的語言。</span><span class="sxs-lookup"><span data-stu-id="d55f2-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="d55f2-130">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="d55f2-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="d55f2-131">啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d55f2-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="d55f2-132">例如，來電者可以說「一」，選取對應至鍵1的功能表選項，或者說「銷售」來選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="d55f2-133">按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="d55f2-134">通話流程</span><span class="sxs-lookup"><span data-stu-id="d55f2-134">Call flow</span></span>

![問候訊息設定的螢幕擷取畫面](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="d55f2-136">選擇當自動語音接聽來電時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="d55f2-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="d55f2-137">如果您選取 [ **播放音訊** 檔]，您可以使用 [ **上傳** 檔案] 按鈕，上傳儲存為音訊的錄製問候語訊息。WAV，。[MP3] 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="d55f2-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="d55f2-138">錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="d55f2-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="d55f2-139">如果您選取 [ **輸入問候語** ]，系統將會朗讀您在其中輸入文字的文字， (最多1000個字元) 當自動語音接聽來電時。</span><span class="sxs-lookup"><span data-stu-id="d55f2-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![呼叫路由設定的螢幕擷取畫面](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="d55f2-141">選擇您要路由通話的方式。</span><span class="sxs-lookup"><span data-stu-id="d55f2-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="d55f2-142">如果您選取 **[中斷連線]** ，自動語音應答就會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="d55f2-142">If you select **Disconnect** , the auto attendant will hang up the call.</span></span>

<span data-ttu-id="d55f2-143">如果您選取 [重新 **導向通話** ]，您可以選擇其中一個呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="d55f2-143">If you select **Redirect call** , you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="d55f2-144">如果您選取 [ **播放] 功能表選項** ，您可以選擇 **播放音訊** 檔案或 **輸入問候語** ，然後選擇 [功能表選項] 和 [目錄搜尋]。</span><span class="sxs-lookup"><span data-stu-id="d55f2-144">If you select **Play menu options** , you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="d55f2-145">功能表選項</span><span class="sxs-lookup"><span data-stu-id="d55f2-145">Menu options</span></span>

![[撥號鍵] 選項的螢幕擷取畫面](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="d55f2-147">針對撥號選項，您可以將電話鍵台的0-9 金鑰指派給其中一個呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="d55f2-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="d55f2-148"> (按鍵 \* (重複) ，而 \# (返回) 是由系統保留，且無法重新指派。 ) </span><span class="sxs-lookup"><span data-stu-id="d55f2-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="d55f2-149">金鑰組應不一定是連續的。</span><span class="sxs-lookup"><span data-stu-id="d55f2-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="d55f2-150">例如，您可以建立一個鍵0、1及3對應至選項的功能表，而不使用2鍵。</span><span class="sxs-lookup"><span data-stu-id="d55f2-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="d55f2-151">如果您已設定一個，我們建議將0鍵對應至運算子。</span><span class="sxs-lookup"><span data-stu-id="d55f2-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="d55f2-152">如果運算子未設定為任何鍵，語音命令 "Operator" 也會停用。</span><span class="sxs-lookup"><span data-stu-id="d55f2-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="d55f2-153">針對每個功能表選項，指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="d55f2-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="d55f2-154">**撥號鍵** -電話鍵臺上的按鍵可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="d55f2-155">如果有可用的語音輸入，呼叫者也可以說此號碼來存取此選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="d55f2-156">**Voice 命令** -定義來電者可提供的語音命令來存取此選項（如果已啟用語音輸入）。</span><span class="sxs-lookup"><span data-stu-id="d55f2-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="d55f2-157">它可以包含多個字詞，例如「客戶服務」或「作業與不限」。</span><span class="sxs-lookup"><span data-stu-id="d55f2-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="d55f2-158">例如，來電者可以按2、說「二」或說「銷售」，選取對應至2鍵的選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="d55f2-159">此文字也會由針對服務確認提示的文字轉換語音，可能是「將您的電話轉接到銷售」之類的內容。</span><span class="sxs-lookup"><span data-stu-id="d55f2-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="d55f2-160">[ **重定向至** ]-呼叫路由目的地（在來電者選擇此選項時使用）。</span><span class="sxs-lookup"><span data-stu-id="d55f2-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="d55f2-161">如果您要重新導向自動語音應答或通話佇列，請選擇與其關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d55f2-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="d55f2-162">目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="d55f2-162">Directory search</span></span>

<span data-ttu-id="d55f2-163">如果您指派撥號鍵至目的地，我們建議您選擇 [ **無** ] 進行 **目錄搜尋** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="d55f2-164">如果來電者嘗試使用指派給特定目的地的金鑰來撥打名稱或分機，可能會在完成輸入名稱或副檔名之前，意外地路由到目的地。</span><span class="sxs-lookup"><span data-stu-id="d55f2-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="d55f2-165">我們建議您為目錄搜尋建立一個單獨的自動語音應答，並透過撥號鍵讓您的主要自動語音應答連結。</span><span class="sxs-lookup"><span data-stu-id="d55f2-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="d55f2-166">如果您沒有指派撥號鍵，請選擇 [ **目錄搜尋** ] 的選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="d55f2-167">**依名稱撥號** -如果您啟用此選項，則呼叫者可以說出使用者的名稱，或在電話鍵臺上輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="d55f2-168">使用電話系統授權的任何線上使用者，或任何使用商務用 Skype Server 主機內部部署的使用者，都是合格的使用者，而且可以使用 [撥號者名稱] 找到。</span><span class="sxs-lookup"><span data-stu-id="d55f2-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="d55f2-169"> (您可以在 [ [撥號作用域](#dial-scope) ] 頁面上設定目錄中的人員，且不會包含在目錄中。 ) </span><span class="sxs-lookup"><span data-stu-id="d55f2-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="d55f2-170">[透過 **分機撥號** ]-如果您啟用此選項，則呼叫者可以撥打電話給您組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="d55f2-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="d55f2-171">使用電話系統授權的任何線上使用者，或任何使用商務用 Skype Server 主機內部部署的使用者，都是符合資格的使用者，而且可透過 **分機** 找到。</span><span class="sxs-lookup"><span data-stu-id="d55f2-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="d55f2-172"> (您可以在 [ [撥號作用域](#dial-scope) ] 頁面上設定目錄中的人員，且不會包含在目錄中。 ) </span><span class="sxs-lookup"><span data-stu-id="d55f2-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="d55f2-173">您想要讓撥打電話使用的使用者必須將延伸指定為下列其中一個電話屬性（在 Active Directory 或 Azure Active Directory 中定義），如需詳細資訊，請參閱 [新增使用者或大量](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) (。 ) </span><span class="sxs-lookup"><span data-stu-id="d55f2-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="d55f2-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="d55f2-174">OfficePhone</span></span>
- <span data-ttu-id="d55f2-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="d55f2-175">HomePhone</span></span>
- <span data-ttu-id="d55f2-176">行動/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="d55f2-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="d55f2-177">Telephonenumber 相同/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="d55f2-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="d55f2-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="d55f2-178">OtherTelephone</span></span>

<span data-ttu-id="d55f2-179">在 [使用者電話號碼] 欄位中輸入副檔名所需的格式是 *+ \<phone number> ext = \<extension>* 或 *+ \<phone number> x \<extension>* 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-179">The required format to enter the extension in the user phone number field is either *+\<phone number>ext=\<extension>* or *+\<phone number>x\<extension>*.</span></span>

<span data-ttu-id="d55f2-180">您可以在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/) 或 [Azure Active Directory 系統管理中心](https://aad.portal.azure.com)中設定延伸。</span><span class="sxs-lookup"><span data-stu-id="d55f2-180">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="d55f2-181">[自動語音應答] 和 [呼叫佇列] 可使用變更前需要12小時的時間。</span><span class="sxs-lookup"><span data-stu-id="d55f2-181">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="d55f2-182">如果您想要同時使用 [ **撥號者名稱** ] 和 [透過 **撥** 打電話] 功能，您可以在主自動語音應答上指派撥號鍵，即可透過 **名稱撥打** 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d55f2-182">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="d55f2-183">在該自動語音應答中，您可以將沒有任何與它相關聯之字母的1金鑰 (指派) 來透過分機自動語音應答來取得 **撥號** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-183">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="d55f2-184">選取 **目錄搜尋** 選項之後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-184">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="d55f2-185">下班時間的通話流程</span><span class="sxs-lookup"><span data-stu-id="d55f2-185">Call flow for after hours</span></span>

![[時間] 和 [時間] 設定的螢幕擷取畫面](media/auto-attendant-business-hours.png)

<span data-ttu-id="d55f2-187">每個自動語音應答的上班時間都可以設定。</span><span class="sxs-lookup"><span data-stu-id="d55f2-187">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="d55f2-188">如果未設定上班時間，則當天的所有日期和所有的時間都被視為「上班時間」，因為預設會設定24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="d55f2-188">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="d55f2-189">您可以在一天中使用時段來設定上班時間，而且所有未設為「上班時間」的小時都會被視為時間。</span><span class="sxs-lookup"><span data-stu-id="d55f2-189">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="d55f2-190">您可以設定不同的來電處理選項和問候語（在下班後）。</span><span class="sxs-lookup"><span data-stu-id="d55f2-190">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="d55f2-191">視您設定自動語音應答及呼叫佇列的方式而定，您可能只需要使用直接電話號碼，指定自動語音接聽的時間呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d55f2-191">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="d55f2-192">如果您想要在下班後的呼叫者單獨撥打通話路線，請指定每天的上班時間。</span><span class="sxs-lookup"><span data-stu-id="d55f2-192">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="d55f2-193">按一下 [ **新增時間** ]，為指定日期指定多組小時數（例如指定午餐時間）。</span><span class="sxs-lookup"><span data-stu-id="d55f2-193">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="d55f2-194">指定上班時間之後，請選擇您的通話路線選項，以供下班時間使用。</span><span class="sxs-lookup"><span data-stu-id="d55f2-194">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="d55f2-195">對於您在上述指定的商務時間呼叫路由，您可以使用相同的選項。</span><span class="sxs-lookup"><span data-stu-id="d55f2-195">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="d55f2-196">完成後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-196">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="d55f2-197">假日期間的通話流程</span><span class="sxs-lookup"><span data-stu-id="d55f2-197">Call flows during holidays</span></span>

![假日和假日問候語設定的螢幕擷取畫面](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="d55f2-199">您的自動語音應答可以針對 [您設定](set-up-holidays-in-teams.md)的每一個假日進行通話流程。</span><span class="sxs-lookup"><span data-stu-id="d55f2-199">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="d55f2-200">您最多可以將20個排定的假日新增至每個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d55f2-200">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="d55f2-201">在 [假日通話設定] 頁面上，按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="d55f2-201">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="d55f2-202">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="d55f2-202">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="d55f2-203">從 [ **假日** ] 下拉式清單中，選擇您要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="d55f2-203">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="d55f2-204">選擇您要使用的問候類型。</span><span class="sxs-lookup"><span data-stu-id="d55f2-204">Choose the type of greeting that you want to use.</span></span>

    ![假日通話動作設定的螢幕擷取畫面](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="d55f2-206">選擇您是否要 **中斷** 連線，或重新 **導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="d55f2-206">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="d55f2-207">如果您選擇 [重新導向]，請選擇通話的呼叫傳送目的地。</span><span class="sxs-lookup"><span data-stu-id="d55f2-207">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="d55f2-208">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="d55f2-208">Click **Save**.</span></span>

![[假日] 設定的螢幕擷取畫面，其中列出假日](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="d55f2-210">視需要針對每個額外的假日重複程式。</span><span class="sxs-lookup"><span data-stu-id="d55f2-210">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="d55f2-211">當您新增完所有假日之後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-211">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="d55f2-212">撥號作用中</span><span class="sxs-lookup"><span data-stu-id="d55f2-212">Dial scope</span></span>

![[撥號作用中包括] 和 [排除] 選項的螢幕擷取畫面](media/auto-attendant-dial-scope.png)

<span data-ttu-id="d55f2-214">*撥號作用* 中定義來電者使用按名稱撥號或撥號延伸時，在目錄中可使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="d55f2-214">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="d55f2-215">**所有線上使用者** 的預設值都是您組織中所有以電話系統授權或主機內部部署的使用者（使用商務用 Skype 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="d55f2-215">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="d55f2-216">您可以選取 [ **包括** ] 或 [ **排除** ] 底下的 [ **自訂使用者組** ]，然後選擇一或多個 Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="d55f2-216">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="d55f2-217">例如，您可能想要將貴組織中的主管從撥號目錄中排除。</span><span class="sxs-lookup"><span data-stu-id="d55f2-217">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="d55f2-218"> (如果使用者同時位於兩個清單中，則會將其從目錄中排除。 ) </span><span class="sxs-lookup"><span data-stu-id="d55f2-218">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="d55f2-219">最多可能需要36小時，才能讓新使用者將其名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="d55f2-219">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="d55f2-220">完成設定撥號作用中的範圍之後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="d55f2-220">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="d55f2-221">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d55f2-221">Resource accounts</span></span>

<span data-ttu-id="d55f2-222">所有自動語音應答都必須有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d55f2-222">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="d55f2-223">第一層自動語音應答將至少需要一個有相關服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d55f2-223">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="d55f2-224">如果您想要的話，您可以將多個資源帳戶指派給自動語音應答，每個都有不同的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-224">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![資源帳戶 [新增帳戶] 面板的螢幕擷取畫面](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="d55f2-226">若要新增資源帳戶，請按一下 [ **新增帳戶** ]，然後搜尋您要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d55f2-226">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="d55f2-227">按一下 [ **新增** ]，然後按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="d55f2-227">Click **Add** , and then click **Add**.</span></span>

![[資源帳戶] 清單的螢幕擷取畫面，其中顯示已指派服務號碼的資源帳戶](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="d55f2-229">完成新增服務帳戶後，請按一下 [ **提交** ]。</span><span class="sxs-lookup"><span data-stu-id="d55f2-229">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="d55f2-230">這會完成自動助理設定。</span><span class="sxs-lookup"><span data-stu-id="d55f2-230">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="d55f2-231">外部電話號碼傳輸-技術詳細資料</span><span class="sxs-lookup"><span data-stu-id="d55f2-231">External phone number transfers - technical details</span></span>

<span data-ttu-id="d55f2-232">請參閱 [必備元件](plan-auto-attendant-call-queue.md#prerequisites) ，以允許自動語音接聽外部轉接來電。</span><span class="sxs-lookup"><span data-stu-id="d55f2-232">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="d55f2-233">另外：</span><span class="sxs-lookup"><span data-stu-id="d55f2-233">In addition:</span></span>

- <span data-ttu-id="d55f2-234">針對含有 [通話方案](calling-plans-for-office-365.md) 編號的資源帳戶，必須以 (+ [國家/地區碼] [區號] [電話號碼] ) ，以164格式輸入外部轉接電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-234">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="d55f2-235">對於擁有直接傳送號碼的資源帳戶，外部轉接電話號碼格式是由 [ (SBC) 設定的會話邊界控制器 ](direct-routing-connect-the-sbc.md) 所依賴。</span><span class="sxs-lookup"><span data-stu-id="d55f2-235">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="d55f2-236">顯示的輸出電話號碼是由以下所示：</span><span class="sxs-lookup"><span data-stu-id="d55f2-236">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="d55f2-237">針對通話方案編號，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-237">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="d55f2-238">針對直接銀行代號，傳送的數位是以 P 斷言身分識別 (PAI 在 SBC 上) 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d55f2-238">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="d55f2-239">如果設定為 [停用]，則會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-239">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="d55f2-240">這是預設及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="d55f2-240">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="d55f2-241">如果設定為 [啟用]，則會顯示資源帳戶的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-241">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="d55f2-242">在商務用 Skype 混合式環境中，若要將自動語音來電轉接到 PSTN，請建立一個新的內部部署使用者，並將 [來電轉接] 設定為 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="d55f2-242">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="d55f2-243">使用者必須啟用企業語音並指派語音原則。</span><span class="sxs-lookup"><span data-stu-id="d55f2-243">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="d55f2-244">若要深入瞭解，請參閱 [自動通話轉接至 PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。</span><span class="sxs-lookup"><span data-stu-id="d55f2-244">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="d55f2-245">使用 PowerShell 建立自動助理</span><span class="sxs-lookup"><span data-stu-id="d55f2-245">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="d55f2-246">您也可以使用 PowerShell 來建立及設定自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d55f2-246">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="d55f2-247">以下是您需要管理自動語音應答的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d55f2-247">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="d55f2-248">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d55f2-248">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="d55f2-249">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d55f2-249">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="d55f2-250">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d55f2-250">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="d55f2-251">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d55f2-251">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="d55f2-252">移除-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="d55f2-252">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="d55f2-253">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="d55f2-253">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="d55f2-254">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="d55f2-254">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="d55f2-255">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="d55f2-255">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="d55f2-256">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d55f2-256">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="d55f2-257">新-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="d55f2-257">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="d55f2-258">新-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="d55f2-258">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="d55f2-259">新-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="d55f2-259">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="d55f2-260">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="d55f2-260">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="d55f2-261">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="d55f2-261">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="d55f2-262">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="d55f2-262">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="d55f2-263">匯入-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="d55f2-263">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="d55f2-264">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="d55f2-264">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a><span data-ttu-id="d55f2-265">相關主題</span><span class="sxs-lookup"><span data-stu-id="d55f2-265">Related topics</span></span>

[<span data-ttu-id="d55f2-266">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="d55f2-266">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="d55f2-267">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="d55f2-267">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="d55f2-268">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="d55f2-268">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="d55f2-269">小型企業範例-設定自動助手</span><span class="sxs-lookup"><span data-stu-id="d55f2-269">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="d55f2-270">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="d55f2-270">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
