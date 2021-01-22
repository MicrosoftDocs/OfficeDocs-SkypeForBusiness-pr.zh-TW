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
ms.openlocfilehash: 4809965eaad0f8cd81b59823d3890bd895998906
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919027"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="0f3d4-103">設定自動 Attendant</span><span class="sxs-lookup"><span data-stu-id="0f3d4-103">Set up an auto attendant</span></span>

<span data-ttu-id="0f3d4-104">自動有聲人員可打電話給貴組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="0f3d4-105">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 為貴組織建立自動 Attendant。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="0f3d4-106">按照本文中的程式進行之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動撥打和通話[](plan-auto-attendant-call-queue.md#getting-started)佇列的規劃，並遵循入門步驟。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="0f3d4-107">自動語音回應可以根據來電者的輸入，將電話直接撥打至下列其中一個目的地： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="0f3d4-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="0f3d4-108">**組織中可以接聽** 語音通話的人，這是貴組織的人。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="0f3d4-109">這可以是線上使用者，或使用商務用 Skype Server 託管于內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="0f3d4-110">**語音應用程式** - 另一個自動語音語音機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="0f3d4-111"> (選擇此目的地.) </span><span class="sxs-lookup"><span data-stu-id="0f3d4-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="0f3d4-112">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="0f3d4-113"> (外部[移轉技術詳細資料，) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="0f3d4-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="0f3d4-114">**語音** 信箱 - 與所指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="0f3d4-115">**運算子** - 自動 Attendant 所定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="0f3d4-116">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-116">Defining an operator is optional.</span></span> <span data-ttu-id="0f3d4-117">運算子可以定義為此清單中的其他任何目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="0f3d4-118">當您設定自動語音機時，系統會提示您在各種階段選擇其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="0f3d4-119">若要設定自動語音留言，請在 Teams 系統管理中心展開[語音 **，按一下自動** 語音語音，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="0f3d4-120">一般資訊</span><span class="sxs-lookup"><span data-stu-id="0f3d4-120">General info</span></span>

![名稱、運算子、時區、語言和語音輸入的自動語音留言設定螢幕擷取畫面](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="0f3d4-122">在頂端的方塊中輸入自動參與人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="0f3d4-123">如果您要指定運算子，請指定該運算子的通話目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="0f3d4-124">這是選擇性選項 (，但建議您) 。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-124">This is optional (but recommended).</span></span> <span data-ttu-id="0f3d4-125">您可以設定 **運算子** 選項，讓來電者離開功能表，與指定的人員通話。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="0f3d4-126">指定此自動 Attendant 的時區。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="0f3d4-127">如果您為後半小時另外建立一個通話流程，時區會用於 [計算上班時間](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="0f3d4-128">指定此自動翻譯人員的語言。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="0f3d4-129">這是系統產生語音提示時所會使用的語言。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="0f3d4-130">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="0f3d4-131">啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="0f3d4-132">例如，來電者可以說「一」以選取對應到按鍵 1 的功能表選項，或說出「銷售」以選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="0f3d4-133">按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="0f3d4-134">通話流程</span><span class="sxs-lookup"><span data-stu-id="0f3d4-134">Call flow</span></span>

![問候語訊息設定螢幕擷取畫面](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="0f3d4-136">選擇當自動回應接聽電話時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="0f3d4-137">如果您選取了 **播放音訊檔案，** 您可以使用上傳檔案按鈕來上傳儲存為音訊的錄製問候語訊息。Wav。MP3 或 .WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="0f3d4-138">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="0f3d4-139">如果您選取了輸入問候語訊息，當自動 (接聽電話時，系統就會讀出您輸入的文字) 最多 1000 個字元。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話路由設定螢幕擷取畫面](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="0f3d4-141">選擇通話路由方式。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="0f3d4-142">如果您選取了中斷 **連接**，自動電話機會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-142">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="0f3d4-143">如果您選取重新 **導向通話**，您可以選擇其中一個通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-143">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="0f3d4-144">如果您選取了播放 **功能表選項**，您可以選擇播放音訊檔案或輸入問候語，然後選擇功能表選項和目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-144">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="0f3d4-145">功能表選項</span><span class="sxs-lookup"><span data-stu-id="0f3d4-145">Menu options</span></span>

![撥號鍵選項的螢幕擷取畫面](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="0f3d4-147">針對撥號選項，您可以將電話鍵盤上的 0-9 鍵指派給其中一個通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="0f3d4-148"> (系統 (重複 \*)  (上) 的按鍵，且無法重新指派。) \#</span><span class="sxs-lookup"><span data-stu-id="0f3d4-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="0f3d4-149">金鑰映射表不必是連續的。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="0f3d4-150">例如，建立一個功能表時，有按鍵 0、1 和 3 對應到選項，而 2 個按鍵則沒有使用。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="0f3d4-151">建議您將 0 鍵與運算子進行比對操作 。如果您已經進行一項安裝，建議您將 0 鍵與運算子進行比對。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="0f3d4-152">如果運算子未設定為任何按鍵，語音命令「運算子」也會停用。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="0f3d4-153">請為每個功能表選項指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="0f3d4-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="0f3d4-154">**撥號鍵** - 電話鍵盤上的按鍵，可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="0f3d4-155">如果可以使用語音輸入，來電者也可以說出這個號碼來存取選項。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="0f3d4-156">**語音** 命令 - 定義來電者可給予存取此選項的語音命令 ，如果已啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="0f3d4-157">它可以包含多個字詞，例如「客戶服務」或「營運與訂單」。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="0f3d4-158">例如，來電者可以按 2，說「兩」或說「銷售」以選取對應到 2 鍵的選項。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="0f3d4-159">系統也會以服務確認提示的文字到語音轉場呈現此文字，例如「將通話轉接至銷售」。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="0f3d4-160">**重新導向** 至 - 來電者選擇此選項時所使用的通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="0f3d4-161">如果您要重新導向至自動有回應或通話佇列，請選擇與其相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="0f3d4-162">目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="0f3d4-162">Directory search</span></span>

<span data-ttu-id="0f3d4-163">如果您將撥號鍵指派給目的地，我們建議您針對目錄搜尋選擇 **None。**</span><span class="sxs-lookup"><span data-stu-id="0f3d4-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="0f3d4-164">如果來電者嘗試使用指定給特定目的地的金鑰撥打名稱或分機，他們可能會在您輸入完名稱或分機前，意外路由至目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="0f3d4-165">建議您為目錄搜尋建立個別的自動 Attendant，並透過撥號鍵讓主要自動 Attendant 連結連至該人員。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="0f3d4-166">如果您未指派撥號鍵，請選擇一個目錄 **搜尋選項**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="0f3d4-167">**按名稱** 撥號 - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵盤上輸入。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="0f3d4-168">任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，您可以使用 Dial 的名稱找到。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-168">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="0f3d4-169"> (您可以在撥號範圍頁面上設定哪些人不在目錄中) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="0f3d4-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="0f3d4-170">**分機號碼** - 如果您啟用此選項，來電者可以撥打分機號碼，與貴組織的使用者聯繫。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="0f3d4-171">任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，而且可以使用 **分機號碼撥號。**</span><span class="sxs-lookup"><span data-stu-id="0f3d4-171">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="0f3d4-172"> (您可以在撥號範圍頁面上設定哪些人不在目錄中) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="0f3d4-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="0f3d4-173">若要提供撥號指定分機功能的使用者，其擴充功能必須做為 Active Directory 或 Azure Active Directory 中定義的下列其中一個電話屬性的一部分來[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)指定 (請參閱個別或大量新增使用者以瞭解更多資訊。) </span><span class="sxs-lookup"><span data-stu-id="0f3d4-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="0f3d4-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="0f3d4-174">OfficePhone</span></span>
- <span data-ttu-id="0f3d4-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="0f3d4-175">HomePhone</span></span>
- <span data-ttu-id="0f3d4-176">行動/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="0f3d4-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="0f3d4-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="0f3d4-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="0f3d4-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="0f3d4-178">OtherTelephone</span></span>

<span data-ttu-id="0f3d4-179">在使用者電話號碼欄位中輸入分機所需的格式為：</span><span class="sxs-lookup"><span data-stu-id="0f3d4-179">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="0f3d4-180">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="0f3d4-180">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="0f3d4-181">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="0f3d4-181">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="0f3d4-182">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="0f3d4-182">*x\<extension>*</span></span>

- <span data-ttu-id="0f3d4-183">範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="0f3d4-183">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="0f3d4-184">範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="0f3d4-184">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="0f3d4-185">範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="0f3d4-185">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="0f3d4-186">您可以在 [Microsoft 365](https://admin.microsoft.com/) 系統管理中心或 Azure [Active Directory](https://aad.portal.azure.com)系統管理中心設定擴充功能。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-186">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="0f3d4-187">最多可能需要 12 小時，才能讓自動參與人員與通話佇列使用變更。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-187">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="0f3d4-188">如果您想要同時使用撥號者名稱及撥號者分機功能，您可以指派主自動 Attendant 上的撥號鍵，以撥打名稱啟用的自動 **attendant。**</span><span class="sxs-lookup"><span data-stu-id="0f3d4-188">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="0f3d4-189">您可以在該自動 attendant 中，指派 1 鍵按鍵 (該按鍵沒有關聯的字母，) 撥打 **分機** 自動 attendant。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-189">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="0f3d4-190">選取目錄 **搜尋選項後** ，請按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-190">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="0f3d4-191">數小時後的通話流程</span><span class="sxs-lookup"><span data-stu-id="0f3d4-191">Call flow for after hours</span></span>

![小時之後日與時間設定螢幕擷取畫面](media/auto-attendant-business-hours.png)

<span data-ttu-id="0f3d4-193">您可以針對每個自動 Attendant 設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-193">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="0f3d4-194">如果未設定上班時間，則一天中所有的天和小時會被視為上班時間，這是因為預設會設定 24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-194">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="0f3d4-195">您可以設定上班時間與一天中的時間，未設定為上班時間的所有小時會被視為後半小時。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-195">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="0f3d4-196">您可以為後半小時設定不同的來電處理選項和問候語。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-196">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="0f3d4-197">根據您為自動撥打的號碼和通話佇列的配置，您可能只需要使用直接電話號碼指定自動電話機的後半小時通話路由。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-197">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="0f3d4-198">如果您想要為後半小時來電者進行個別的通話路由，請指定每天的上班時間。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-198">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="0f3d4-199">例如 **，按一下 [新增時間** 以指定指定一天的多組時數，以指定午餐時間。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-199">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="0f3d4-200">指定上班時間之後，再選擇數小時的通話路由選項。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-200">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="0f3d4-201">這些選項與上述指定的上班時間通話路由選項相同。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-201">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="0f3d4-202">完成 **時** 按一下 [下一步。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-202">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="0f3d4-203">在假日期間通話流程</span><span class="sxs-lookup"><span data-stu-id="0f3d4-203">Call flows during holidays</span></span>

![假日和假日問候語設定螢幕擷取畫面](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="0f3d4-205">您的自動助理可以針對您設定的每個假日安排 [通話流程](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-205">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="0f3d4-206">您最多可以將 20 個排程的假日加到每個自動 Attendant 中。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-206">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="0f3d4-207">在 [假日通話設定> 頁面上，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-207">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="0f3d4-208">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-208">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="0f3d4-209">從 **假日下** 拉選，選擇您想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-209">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="0f3d4-210">選擇您想要使用的問候語類型。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-210">Choose the type of greeting that you want to use.</span></span>

    ![假日通話動作設定螢幕擷取畫面](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="0f3d4-212">選擇您是否要中斷 **連接** 或 **重新導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-212">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="0f3d4-213">如果您選擇重新導向，請選擇通話的通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-213">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="0f3d4-214">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-214">Click **Save**.</span></span>

![已列出假日的假日設定螢幕擷取畫面](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="0f3d4-216">針對每一個額外的假日，根據需要重複此程式。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-216">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="0f3d4-217">當您新增所有的假日時，按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-217">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="0f3d4-218">撥號範圍</span><span class="sxs-lookup"><span data-stu-id="0f3d4-218">Dial scope</span></span>

![撥號範圍包含與排除選項的螢幕擷取畫面](media/auto-attendant-dial-scope.png)

<span data-ttu-id="0f3d4-220">撥號 *範圍* 會定義當來電者使用電話撥入式名稱或按分機號碼時，哪些使用者可以在目錄中使用。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-220">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="0f3d4-221">根據預設 **，所有線上使用者** 會包含貴組織的所有使用者，這些使用者都是線上使用者，或是使用商務用 Skype Server 託管于內部部署。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-221">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="0f3d4-222">您可以在包含或排除下選取自訂使用者群組，並選擇一或多個Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 </span><span class="sxs-lookup"><span data-stu-id="0f3d4-222">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="0f3d4-223">例如，您可能會想要將貴組織高主管排除在撥號目錄中。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-223">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="0f3d4-224"> (如果使用者同時位於這兩個清單中，他們將從目錄.) </span><span class="sxs-lookup"><span data-stu-id="0f3d4-224">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="0f3d4-225">新使用者最多可能需要 36 小時，才能將名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-225">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="0f3d4-226">設定完撥號範圍之後，請按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-226">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="0f3d4-227">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="0f3d4-227">Resource accounts</span></span>

<span data-ttu-id="0f3d4-228">所有自動 attendants 都必須有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-228">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="0f3d4-229">第一層自動出席者至少需要一個擁有相關聯服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-229">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="0f3d4-230">如果您想要的話，您可以將數個資源帳戶指派給自動 Attendant，每個帳戶都有個別的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-230">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![資源帳戶新增帳戶面板的螢幕擷取畫面](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="0f3d4-232">若要新增資源帳戶，請按一下 [ **新增** 帳戶，然後搜尋您想要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-232">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="0f3d4-233">按一下 **[新增**，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-233">Click **Add**, and then click **Add**.</span></span>

![顯示有已指派服務編號之資源帳戶清單的螢幕擷取畫面](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="0f3d4-235">完成新增服務帳戶後，請按一下 **[提交**。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-235">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="0f3d4-236">這會完成自動 attendant 的安裝。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-236">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="0f3d4-237">外部電話號碼轉接 - 技術詳細資料</span><span class="sxs-lookup"><span data-stu-id="0f3d4-237">External phone number transfers - technical details</span></span>

<span data-ttu-id="0f3d4-238">請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以允許自動 Attendant 將電話轉接至外部。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-238">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="0f3d4-239">另外：</span><span class="sxs-lookup"><span data-stu-id="0f3d4-239">In addition:</span></span>

- <span data-ttu-id="0f3d4-240">對於有通話方案號碼的資源[](calling-plans-for-office-365.md)帳戶，外部轉接電話號碼必須以 E.164 格式輸入 (+[國碼][區碼][電話號碼]) 。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-240">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="0f3d4-241">針對具有直接路由號碼的資源帳戶，外部轉接電話號碼格式會設定在會話邊界控制器上 ([SBC) ](direct-routing-connect-the-sbc.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-241">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="0f3d4-242">顯示的電話號碼會以以下方式判斷：</span><span class="sxs-lookup"><span data-stu-id="0f3d4-242">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="0f3d4-243">針對通話方案號碼，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-243">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="0f3d4-244">針對直接路由號碼，傳送的號碼是根據 SBC (PAI) 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f3d4-244">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="0f3d4-245">如果設為停用，則會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-245">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="0f3d4-246">這是預設且建議使用的設定。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-246">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="0f3d4-247">如果設為已啟用，則會顯示資源帳戶電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-247">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="0f3d4-248">在商務用 Skype 混合式環境中，若要將自動參與通話轉接到 PSTN，請建立一個新的內部部署使用者，將來電轉接設定為 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-248">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="0f3d4-249">使用者必須啟用企業語音，並指派語音策略。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-249">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="0f3d4-250">若要深入瞭解，請參閱自動 [將電話轉接到 PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)的自動 Attendant 通話。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-250">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="0f3d4-251">使用 PowerShell 建立自動 Attendant</span><span class="sxs-lookup"><span data-stu-id="0f3d4-251">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="0f3d4-252">您也可以使用 PowerShell 來建立及設定自動 Attendant。</span><span class="sxs-lookup"><span data-stu-id="0f3d4-252">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="0f3d4-253">以下是管理自動 attendant 時所需的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0f3d4-253">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="0f3d4-254">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0f3d4-254">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="0f3d4-255">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0f3d4-255">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="0f3d4-256">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0f3d4-256">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="0f3d4-257">Get-CsAutoAttendant一idays</span><span class="sxs-lookup"><span data-stu-id="0f3d4-257">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="0f3d4-258">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="0f3d4-258">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="0f3d4-259">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="0f3d4-259">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="0f3d4-260">New-CsOnline在一起</span><span class="sxs-lookup"><span data-stu-id="0f3d4-260">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="0f3d4-261">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="0f3d4-261">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="0f3d4-262">Export-CsAutoAttendant一idays</span><span class="sxs-lookup"><span data-stu-id="0f3d4-262">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="0f3d4-263">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="0f3d4-263">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="0f3d4-264">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="0f3d4-264">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="0f3d4-265">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="0f3d4-265">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="0f3d4-266">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="0f3d4-266">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="0f3d4-267">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="0f3d4-267">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="0f3d4-268">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="0f3d4-268">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="0f3d4-269">Import-CsAutoAttendant一idays</span><span class="sxs-lookup"><span data-stu-id="0f3d4-269">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="0f3d4-270">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="0f3d4-270">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="0f3d4-271">相關主題</span><span class="sxs-lookup"><span data-stu-id="0f3d4-271">Related topics</span></span>

[<span data-ttu-id="0f3d4-272">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="0f3d4-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="0f3d4-273">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="0f3d4-273">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="0f3d4-274">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="0f3d4-274">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="0f3d4-275">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="0f3d4-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
