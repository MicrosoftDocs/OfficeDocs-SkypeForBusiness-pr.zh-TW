---
title: 設定 Microsoft Teams 的自動 Attendant
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
description: 瞭解如何設定和測試 Microsoft Teams 的自動 Attendant。
ms.openlocfilehash: bffe66fc59dfeb2f7028f2d5520b45930d753d07
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196627"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="bceb5-103">設定自動 Attendant</span><span class="sxs-lookup"><span data-stu-id="bceb5-103">Set up an auto attendant</span></span>

<span data-ttu-id="bceb5-104">自動 attendants 可讓人打電話給您的組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。</span><span class="sxs-lookup"><span data-stu-id="bceb5-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="bceb5-105">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 為貴組織建立自動 Attendant。</span><span class="sxs-lookup"><span data-stu-id="bceb5-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="bceb5-106">遵循本文中的程式之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動 Attendant 和[](plan-auto-attendant-call-queue.md#getting-started)通話佇列的規劃，並遵循開始使用的步驟。</span><span class="sxs-lookup"><span data-stu-id="bceb5-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="bceb5-107">自動語音機可以根據來電者的輸入，將通話引導至下列其中一個目的地： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="bceb5-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="bceb5-108">**組織中可以接聽** 語音電話的人。</span><span class="sxs-lookup"><span data-stu-id="bceb5-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="bceb5-109">這可以是線上使用者，或使用商務用 Skype Server 託管于內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="bceb5-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="bceb5-110">**語音應用程式** - 另一個自動語音留言機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="bceb5-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="bceb5-111"> (選擇此目的地.) </span><span class="sxs-lookup"><span data-stu-id="bceb5-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="bceb5-112">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bceb5-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="bceb5-113"> (外部[移轉技術詳細資料) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="bceb5-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="bceb5-114">**語音** 信箱 - 與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="bceb5-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="bceb5-115">**運算子** - 為自動 attendant 定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="bceb5-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="bceb5-116">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="bceb5-116">Defining an operator is optional.</span></span> <span data-ttu-id="bceb5-117">運算子可以定義為清單中任何其他目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="bceb5-118">當您設定自動語音回應時，系統會提示您于不同階段選擇其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="bceb5-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="bceb5-119">若要設定自動語音留言，請在 Teams 系統管理中心展開 **語音**，按一下 [自動 **語音** 留言機，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="bceb5-120">一般資訊</span><span class="sxs-lookup"><span data-stu-id="bceb5-120">General info</span></span>

![名稱、運算子、時區、語言和語音輸入的自動語音機設定螢幕擷取畫面](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="bceb5-122">在頂端方塊中輸入自動 attendant 的名稱。</span><span class="sxs-lookup"><span data-stu-id="bceb5-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="bceb5-123">如果您想要指定運算子，請指定撥打給該運算子的目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="bceb5-124">這是選擇性選項 (，但建議您) 。</span><span class="sxs-lookup"><span data-stu-id="bceb5-124">This is optional (but recommended).</span></span> <span data-ttu-id="bceb5-125">您可以 **設定運算子選項** ，讓來電者離開功能表，並和指定的人員通話。</span><span class="sxs-lookup"><span data-stu-id="bceb5-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="bceb5-126">指定此自動 Attendant 的時區。</span><span class="sxs-lookup"><span data-stu-id="bceb5-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="bceb5-127">如果您為上班時間建立個別的通話流程，時區會用來 [計算上班時間](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="bceb5-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="bceb5-128">指定 [此自動 Attendant](create-a-phone-system-auto-attendant-languages.md) 的支援語言。</span><span class="sxs-lookup"><span data-stu-id="bceb5-128">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="bceb5-129">這是系統產生的語音提示所使用的語言。</span><span class="sxs-lookup"><span data-stu-id="bceb5-129">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="bceb5-130">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="bceb5-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="bceb5-131">啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="bceb5-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="bceb5-132">例如，來電者可以說「One」以選取對應到按鍵 1 的功能表選項，或說「銷售」以選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="bceb5-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="bceb5-133">如果您在步驟 4 中選擇不支援語音輸入的語言，此選項將會停用。</span><span class="sxs-lookup"><span data-stu-id="bceb5-133">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="bceb5-134">按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-134">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="bceb5-135">通話流程</span><span class="sxs-lookup"><span data-stu-id="bceb5-135">Call flow</span></span>

![問候語訊息設定螢幕擷取畫面](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="bceb5-137">選擇當自動回應接聽來電時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="bceb5-137">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="bceb5-138">如果您選取了 **播放音訊檔案，** 您可以使用上傳 **檔案按鈕來** 上傳儲存為音訊的錄製問候語訊息。Wav。MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="bceb5-138">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="bceb5-139">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="bceb5-139">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="bceb5-140">如果您選取了輸入問候語 **訊息** ，當自動 (自動回應接聽來電時) 會朗讀您輸入的文字。</span><span class="sxs-lookup"><span data-stu-id="bceb5-140">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話路由設定螢幕擷取畫面](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="bceb5-142">選擇通話的路由方式。</span><span class="sxs-lookup"><span data-stu-id="bceb5-142">Choose how you want to route the call.</span></span>

<span data-ttu-id="bceb5-143">如果您選取中斷 **連接**，自動通話機會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="bceb5-143">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="bceb5-144">如果您選取重新 **導向通話**，您可以選擇其中一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-144">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="bceb5-145">如果您選取了播放 **功能表選項**，您可以選擇播放音訊檔案或輸入問候語 **訊息**，然後選擇功能表選項和目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="bceb5-145">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="bceb5-146">功能表選項</span><span class="sxs-lookup"><span data-stu-id="bceb5-146">Menu options</span></span>

![撥號鍵選項的螢幕擷取畫面](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="bceb5-148">針對撥號選項，您可以將電話鍵臺上的 0-9 鍵指派給其中一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-148">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="bceb5-149"> (系統 (重複)  (Back) 的按鍵，且無法重新指派 \* \# 。) </span><span class="sxs-lookup"><span data-stu-id="bceb5-149">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="bceb5-150">金鑰映射不必是連續的。</span><span class="sxs-lookup"><span data-stu-id="bceb5-150">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="bceb5-151">例如，建立一個功能表時，可能會將按鍵 0、1 和 3 對應到選項，而未使用 2 鍵。</span><span class="sxs-lookup"><span data-stu-id="bceb5-151">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="bceb5-152">如果您已經將 0 鍵與運算子進行配置，建議您將 0 鍵與運算子進行比對。</span><span class="sxs-lookup"><span data-stu-id="bceb5-152">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="bceb5-153">如果運算子未設定為任何按鍵，語音命令 「運算子」也會停用。</span><span class="sxs-lookup"><span data-stu-id="bceb5-153">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="bceb5-154">針對每個功能表選項，指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="bceb5-154">For each menu option, specify the following:</span></span>

- <span data-ttu-id="bceb5-155">**撥號鍵** - 電話鍵臺上的按鍵，可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="bceb5-155">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="bceb5-156">如果語音輸入可以使用，來電者也可以說出這個號碼來存取選項。</span><span class="sxs-lookup"><span data-stu-id="bceb5-156">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="bceb5-157">**語音命令** - 定義來電者可給予存取此選項的語音命令 ，如果已啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="bceb5-157">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="bceb5-158">它可以包含多個字詞，例如「客戶服務」或「營運與理由」。</span><span class="sxs-lookup"><span data-stu-id="bceb5-158">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="bceb5-159">例如，來電者可以按 2，說出「2」，或說「銷售」以選取對應到 2 鍵的選項。</span><span class="sxs-lookup"><span data-stu-id="bceb5-159">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="bceb5-160">此文字也會以服務確認提示的文字轉語音顯示，例如「將通話轉接至銷售」。</span><span class="sxs-lookup"><span data-stu-id="bceb5-160">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="bceb5-161">**重新導向** 至 - 來電者選擇此選項時所使用的通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-161">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="bceb5-162">如果您要重新導向到自動 Attendant 或通話佇列，請選擇與其相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="bceb5-162">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="bceb5-163">目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="bceb5-163">Directory search</span></span>

<span data-ttu-id="bceb5-164">如果您將撥號鍵指派給目的地，建議您選擇搜尋 **目錄** 時選擇 **None。**</span><span class="sxs-lookup"><span data-stu-id="bceb5-164">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="bceb5-165">如果來電者嘗試使用指派給特定目的地的按鍵撥打名稱或分機，他們可能會在您輸入完名稱或分機之前，未預期地路由至目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-165">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="bceb5-166">建議您為目錄搜尋建立個別的自動 Attendant，並透過撥號鍵提供主要的自動總機連結。</span><span class="sxs-lookup"><span data-stu-id="bceb5-166">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="bceb5-167">如果您未指派撥號鍵，請選擇目錄 **搜尋選項**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-167">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="bceb5-168">**按名稱撥號** - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵台輸入。</span><span class="sxs-lookup"><span data-stu-id="bceb5-168">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="bceb5-169">任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，而且可以使用撥號名稱找到。</span><span class="sxs-lookup"><span data-stu-id="bceb5-169">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="bceb5-170"> (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="bceb5-170">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="bceb5-171">**分機號碼** - 如果您啟用此選項，來電者可以撥打其電話分機，與貴組織的使用者聯繫。</span><span class="sxs-lookup"><span data-stu-id="bceb5-171">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="bceb5-172">任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，而且可撥打分機 **號碼。**</span><span class="sxs-lookup"><span data-stu-id="bceb5-172">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="bceb5-173"> (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="bceb5-173">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="bceb5-174">想要提供撥號分機服務的使用者，必須擁有在 Active Directory 或 Azure Active Directory 中定義的下列其中一個電話屬性的擴充功能 (請參閱個別或大量[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)新增使用者以瞭解更多資訊。) </span><span class="sxs-lookup"><span data-stu-id="bceb5-174">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="bceb5-175">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="bceb5-175">OfficePhone</span></span>
- <span data-ttu-id="bceb5-176">HomePhone</span><span class="sxs-lookup"><span data-stu-id="bceb5-176">HomePhone</span></span>
- <span data-ttu-id="bceb5-177">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="bceb5-177">Mobile/MobilePhone</span></span>
- <span data-ttu-id="bceb5-178">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="bceb5-178">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="bceb5-179">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="bceb5-179">OtherTelephone</span></span>

<span data-ttu-id="bceb5-180">在使用者電話號碼欄位中輸入分機所需的格式為：</span><span class="sxs-lookup"><span data-stu-id="bceb5-180">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="bceb5-181">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="bceb5-181">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="bceb5-182">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="bceb5-182">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="bceb5-183">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="bceb5-183">*x\<extension>*</span></span>

- <span data-ttu-id="bceb5-184">範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="bceb5-184">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="bceb5-185">範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="bceb5-185">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="bceb5-186">範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="bceb5-186">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="bceb5-187">您可以在 [Microsoft 365](https://admin.microsoft.com/) 系統管理中心或 Azure [Active Directory](https://aad.portal.azure.com)系統管理中心設定擴充功能。</span><span class="sxs-lookup"><span data-stu-id="bceb5-187">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="bceb5-188">最多可能需要 12 小時，自動電話機和通話佇列才能使用變更。</span><span class="sxs-lookup"><span data-stu-id="bceb5-188">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="bceb5-189">如果您想要同時使用按名稱撥號和按分機撥號的功能，您可以在主自動轉音器上指派撥號鍵，以使用已啟用撥號名稱的自動轉 **音機**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-189">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="bceb5-190">您可以在該自動 attendant 中指派 1 個按鍵 (沒有與其相關聯的字母，) **分機自動** 總機。</span><span class="sxs-lookup"><span data-stu-id="bceb5-190">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="bceb5-191">選取目錄 **搜尋選項後** ，請按一下 [下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="bceb5-192">數小時後的通話流程</span><span class="sxs-lookup"><span data-stu-id="bceb5-192">Call flow for after hours</span></span>

![小時後日與時間設定之螢幕擷取畫面](media/auto-attendant-business-hours.png)

<span data-ttu-id="bceb5-194">您可以針對每個自動 Attendant 設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="bceb5-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="bceb5-195">如果未設定上班時間，則一天中所有的天和小時都視為上班時間，因為預設會設定 24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="bceb5-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="bceb5-196">上班時間可以設定為一天中的休息時間，而未設定為上班時間的所有時數會視為上班時間。</span><span class="sxs-lookup"><span data-stu-id="bceb5-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="bceb5-197">您可以為上班時間設定不同的來電處理選項和問候語。</span><span class="sxs-lookup"><span data-stu-id="bceb5-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="bceb5-198">根據您如何配置自動電話機和通話佇列，您可能只需要為具有直接電話號碼的自動電話機指定後通話路由。</span><span class="sxs-lookup"><span data-stu-id="bceb5-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="bceb5-199">如果您想要為上班時間來電者分別進行通話路由，請指定每天的上班時間。</span><span class="sxs-lookup"><span data-stu-id="bceb5-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="bceb5-200">例如 **，按一下 [新增時間** 以指定指定一天的多組時數，以指定午餐時間。</span><span class="sxs-lookup"><span data-stu-id="bceb5-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="bceb5-201">指定上班時間之後，請選擇您的通話路由選項。</span><span class="sxs-lookup"><span data-stu-id="bceb5-201">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="bceb5-202">這些選項與上述指定的上班時間通話路由相同。</span><span class="sxs-lookup"><span data-stu-id="bceb5-202">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="bceb5-203">完成 **時** 按一下 [下一步。</span><span class="sxs-lookup"><span data-stu-id="bceb5-203">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="bceb5-204">假日期間通話流量</span><span class="sxs-lookup"><span data-stu-id="bceb5-204">Call flows during holidays</span></span>

![假日和假日問候語設定螢幕擷取畫面](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="bceb5-206">您的自動電話機可以針對您設定的每個 [假日提供通話流程](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bceb5-206">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="bceb5-207">您可以新增最多 20 個排定的假日到每個自動 attendant。</span><span class="sxs-lookup"><span data-stu-id="bceb5-207">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="bceb5-208">在 [假日通話設定> 頁面上，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-208">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="bceb5-209">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="bceb5-209">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="bceb5-210">從 **假日** 下拉拉，選擇您想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="bceb5-210">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="bceb5-211">選擇您想要使用的問候語類型。</span><span class="sxs-lookup"><span data-stu-id="bceb5-211">Choose the type of greeting that you want to use.</span></span>

    ![假日通話動作設定螢幕擷取畫面](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="bceb5-213">選擇是否要中斷 **連接或\*\*\*\*重新導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="bceb5-213">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="bceb5-214">如果您選擇重新導向，請選擇通話的呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="bceb5-214">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="bceb5-215">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-215">Click **Save**.</span></span>

![已列出假日的假日設定螢幕擷取畫面](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="bceb5-217">針對每一個額外的假日，請根據需要重複這個程式。</span><span class="sxs-lookup"><span data-stu-id="bceb5-217">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="bceb5-218">新增所有假日後，請按一下 [下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-218">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="bceb5-219">撥號範圍</span><span class="sxs-lookup"><span data-stu-id="bceb5-219">Dial scope</span></span>

![撥號範圍包含和排除選項的螢幕擷取畫面](media/auto-attendant-dial-scope.png)

<span data-ttu-id="bceb5-221">撥號 *範圍* 會定義當來電者使用撥號或分機號碼時，哪些使用者可以在目錄中使用。</span><span class="sxs-lookup"><span data-stu-id="bceb5-221">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="bceb5-222">根據預設 **，所有線上** 使用者會包含貴組織的所有使用者，這些使用者都是線上使用者，或是使用商務用 Skype Server 託管于內部部署。</span><span class="sxs-lookup"><span data-stu-id="bceb5-222">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="bceb5-223">您可以在包含或排除下選取自訂使用者群組，並選擇一或多個Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 </span><span class="sxs-lookup"><span data-stu-id="bceb5-223">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="bceb5-224">例如，您可能會想要將貴組織的高主管排除在撥號目錄中。</span><span class="sxs-lookup"><span data-stu-id="bceb5-224">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="bceb5-225"> (如果使用者同時在兩個清單中，就會從目錄.) </span><span class="sxs-lookup"><span data-stu-id="bceb5-225">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="bceb5-226">新使用者最多可能需要 36 小時，才能將他們的名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="bceb5-226">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="bceb5-227">設定好撥號範圍後，請按一下 [下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-227">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="bceb5-228">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="bceb5-228">Resource accounts</span></span>

<span data-ttu-id="bceb5-229">所有自動 attendant 都必須有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="bceb5-229">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="bceb5-230">第一層自動 attendant 至少需要一個擁有相關聯服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="bceb5-230">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="bceb5-231">您可以根據需要，將多個資源帳戶指派給一個自動 Attendant，每個帳戶都有個別的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="bceb5-231">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![資源帳戶新增帳戶面板的螢幕擷取畫面](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="bceb5-233">若要新增資源帳戶，請按一下 **[新增帳戶** 並搜尋您想要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bceb5-233">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="bceb5-234">按一下 **[新增**，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-234">Click **Add**, and then click **Add**.</span></span>

![顯示資源帳戶與已指派服務編號的資源帳戶清單螢幕擷取畫面](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="bceb5-236">完成新增服務帳戶後，請按一下 **[提交**。</span><span class="sxs-lookup"><span data-stu-id="bceb5-236">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="bceb5-237">這完成自動 attendant 的組配置。</span><span class="sxs-lookup"><span data-stu-id="bceb5-237">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="bceb5-238">外部電話號碼傳輸 - 技術詳細資料</span><span class="sxs-lookup"><span data-stu-id="bceb5-238">External phone number transfers - technical details</span></span>

<span data-ttu-id="bceb5-239">請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以允許自動電話機將電話轉接至外部。</span><span class="sxs-lookup"><span data-stu-id="bceb5-239">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="bceb5-240">另外：</span><span class="sxs-lookup"><span data-stu-id="bceb5-240">In addition:</span></span>

- <span data-ttu-id="bceb5-241">對於具有通話方案號碼的資源[](calling-plans-for-office-365.md)帳戶，外部轉接電話號碼必須以 E.164 格式輸入 (+[國碼][區碼][電話號碼]) 。</span><span class="sxs-lookup"><span data-stu-id="bceb5-241">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="bceb5-242">對於具有直接路由號碼的資源帳戶，外部轉接電話號碼格式是在會話邊界控制器或 [SBC ](direct-routing-connect-the-sbc.md) (設定) 格式。</span><span class="sxs-lookup"><span data-stu-id="bceb5-242">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="bceb5-243">顯示外發電話號碼的判定方式如下：</span><span class="sxs-lookup"><span data-stu-id="bceb5-243">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="bceb5-244">針對通話方案號碼，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bceb5-244">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="bceb5-245">針對直接路由號碼，傳送的號碼是根據 SBC 上的 P-就地識別 (PAI) 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bceb5-245">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="bceb5-246">如果設為停用，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bceb5-246">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="bceb5-247">這是預設及建議設定。</span><span class="sxs-lookup"><span data-stu-id="bceb5-247">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="bceb5-248">如果設為啟用，會顯示資源帳戶電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bceb5-248">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="bceb5-249">在商務用 Skype 混合式環境中，若要將自動 attendant 通話轉接到 PSTN，請建立一個新的內部部署使用者，將來電轉接設定為 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="bceb5-249">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="bceb5-250">使用者必須啟用企業語音，並指派語音策略。</span><span class="sxs-lookup"><span data-stu-id="bceb5-250">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="bceb5-251">若要深入瞭解，請參閱[自動將電話轉接到 PSTN。](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="bceb5-251">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="bceb5-252">使用 PowerShell 建立自動 Attendant</span><span class="sxs-lookup"><span data-stu-id="bceb5-252">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="bceb5-253">您也可以使用 PowerShell 來建立和設定自動 Attendant。</span><span class="sxs-lookup"><span data-stu-id="bceb5-253">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="bceb5-254">以下是管理自動 attendant 所需的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bceb5-254">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="bceb5-255">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bceb5-255">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="bceb5-256">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bceb5-256">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="bceb5-257">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bceb5-257">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="bceb5-258">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="bceb5-258">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="bceb5-259">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="bceb5-259">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="bceb5-260">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="bceb5-260">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="bceb5-261">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="bceb5-261">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="bceb5-262">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="bceb5-262">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="bceb5-263">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="bceb5-263">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="bceb5-264">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="bceb5-264">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="bceb5-265">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="bceb5-265">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="bceb5-266">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="bceb5-266">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="bceb5-267">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="bceb5-267">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="bceb5-268">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="bceb5-268">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="bceb5-269">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="bceb5-269">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="bceb5-270">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="bceb5-270">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="bceb5-271">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="bceb5-271">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="bceb5-272">相關主題</span><span class="sxs-lookup"><span data-stu-id="bceb5-272">Related topics</span></span>

[<span data-ttu-id="bceb5-273">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="bceb5-273">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="bceb5-274">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="bceb5-274">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="bceb5-275">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="bceb5-275">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="bceb5-276">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="bceb5-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
