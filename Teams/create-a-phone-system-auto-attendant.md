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
ms.openlocfilehash: deb9bf013136bb8efd9171e5562de5e2ba1b631f
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347864"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="dce99-103">設定自動 attendant</span><span class="sxs-lookup"><span data-stu-id="dce99-103">Set up an auto attendant</span></span>

<span data-ttu-id="dce99-104">自動 attendants 可讓人打電話給您的組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。</span><span class="sxs-lookup"><span data-stu-id="dce99-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="dce99-105">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 為貴組織建立自動 Attendant。</span><span class="sxs-lookup"><span data-stu-id="dce99-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="dce99-106">遵循本文中的程式之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動 Attendant 和[](plan-auto-attendant-call-queue.md#getting-started)通話佇列的規劃，並遵循開始使用的步驟。</span><span class="sxs-lookup"><span data-stu-id="dce99-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="dce99-107">自動語音機可以根據來電者的輸入，將電話直接撥打到下列其中一個目的地： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="dce99-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="dce99-108">**運算子** - 為自動 attendant 定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="dce99-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="dce99-109">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="dce99-109">Defining an operator is optional.</span></span> <span data-ttu-id="dce99-110">運算子可以定義為清單中任何其他目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="dce99-111">**組織中可接聽** 語音通話的人。</span><span class="sxs-lookup"><span data-stu-id="dce99-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="dce99-112">這可以是線上使用者，或使用商務用 Skype Server 託管于內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="dce99-112">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="dce99-113">**語音應用程式** - 另一個自動語音留言機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="dce99-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="dce99-114"> (選擇此目的地.) </span><span class="sxs-lookup"><span data-stu-id="dce99-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="dce99-115">**語音** 信箱 - 與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dce99-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="dce99-116">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dce99-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="dce99-117"> (外部[移轉技術詳細資料) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="dce99-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="dce99-118">**宣告** - 播放音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="dce99-118">**Announcement** - Play an audio file.</span></span> <span data-ttu-id="dce99-119">您上傳的已錄製公告訊息，儲存為音訊。Wav。MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="dce99-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="dce99-120">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="dce99-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="dce99-121">系統會播放公告，然後返回自動 Attendant 功能表。</span><span class="sxs-lookup"><span data-stu-id="dce99-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="dce99-122">**公告** - 在訊息中輸入。</span><span class="sxs-lookup"><span data-stu-id="dce99-122">**Announcement** - Type in a message.</span></span> <span data-ttu-id="dce99-123">這是您希望系統朗讀的文字。</span><span class="sxs-lookup"><span data-stu-id="dce99-123">Text you want the system to read.</span></span> <span data-ttu-id="dce99-124">您可以輸入最多 1000 個字元。</span><span class="sxs-lookup"><span data-stu-id="dce99-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="dce99-125">系統會播放公告，然後返回自動 Attendant 功能表。</span><span class="sxs-lookup"><span data-stu-id="dce99-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="dce99-126">當您設定自動語音回應時，系統會提示您于不同階段選擇其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="dce99-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="dce99-127">若要設定自動語音留言，請在 Teams 系統管理中心展開 **語音**，選取 **自動語音** 機， **然後選取新增**。</span><span class="sxs-lookup"><span data-stu-id="dce99-127">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="dce99-128">一般資訊</span><span class="sxs-lookup"><span data-stu-id="dce99-128">General info</span></span>

![名稱、運算子、時區、語言和語音輸入的自動語音機設定螢幕擷取畫面](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="dce99-130">在頂端方塊中輸入自動 attendant 的名稱。</span><span class="sxs-lookup"><span data-stu-id="dce99-130">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="dce99-131">如果您想要指定運算子，請指定撥打給該運算子的目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-131">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="dce99-132">這是選擇性選項 (，但建議您) 。</span><span class="sxs-lookup"><span data-stu-id="dce99-132">This is optional (but recommended).</span></span> <span data-ttu-id="dce99-133">您可以 **設定運算子選項** ，讓來電者離開功能表，並和指定的人員通話。</span><span class="sxs-lookup"><span data-stu-id="dce99-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="dce99-134">指定此自動 Attendant 的時區。</span><span class="sxs-lookup"><span data-stu-id="dce99-134">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="dce99-135">如果您為上班時間建立個別的通話流程，時區會用來 [計算上班時間](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="dce99-135">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="dce99-136">指定 [此自動 Attendant](create-a-phone-system-auto-attendant-languages.md) 的支援語言。</span><span class="sxs-lookup"><span data-stu-id="dce99-136">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="dce99-137">這是系統產生的語音提示所使用的語言。</span><span class="sxs-lookup"><span data-stu-id="dce99-137">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="dce99-138">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="dce99-138">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="dce99-139">啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="dce99-139">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="dce99-140">例如，來電者可以說「One」以選取對應到按鍵 1 的功能表選項，或說出「銷售」以選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="dce99-140">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="dce99-141">如果您在步驟 4 中選擇不支援語音輸入的語言，此選項將會停用。</span><span class="sxs-lookup"><span data-stu-id="dce99-141">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="dce99-142">選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="dce99-142">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="dce99-143">通話流程</span><span class="sxs-lookup"><span data-stu-id="dce99-143">Call flow</span></span>

![問候語訊息設定螢幕擷取畫面](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="dce99-145">選擇當自動回應接聽來電時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="dce99-145">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="dce99-146">如果您選取了 **播放音訊檔案，** 您可以使用上傳 **檔案按鈕來** 上傳儲存為音訊的錄製問候語訊息。Wav。MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="dce99-146">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="dce99-147">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="dce99-147">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="dce99-148">如果您選取了輸入問候語 **訊息** ，當自動 (自動回應接聽來電時) 會朗讀您輸入的文字。</span><span class="sxs-lookup"><span data-stu-id="dce99-148">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話路由設定螢幕擷取畫面](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="dce99-150">選擇通話的路由方式。</span><span class="sxs-lookup"><span data-stu-id="dce99-150">Choose how you want to route the call.</span></span>

<span data-ttu-id="dce99-151">如果您選取中斷 **連接**，自動電話機會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="dce99-151">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="dce99-152">如果您選取重新 **導向通話**，您可以選擇其中一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-152">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="dce99-153">如果您選取了播放 **功能表選項**，您可以選擇播放音訊檔案或輸入問候語訊息，然後選擇功能表選項和目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="dce99-153">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="dce99-154">功能表選項</span><span class="sxs-lookup"><span data-stu-id="dce99-154">Menu options</span></span>

![撥號鍵選項的螢幕擷取畫面](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="dce99-156">針對撥號選項，您可以將電話鍵臺上的 0-9 鍵指派給其中一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-156">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="dce99-157"> (系統 (重複)  (Back) 的按鍵，且無法重新指派 \* \# 。) </span><span class="sxs-lookup"><span data-stu-id="dce99-157">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="dce99-158">金鑰映射不必是連續的。</span><span class="sxs-lookup"><span data-stu-id="dce99-158">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="dce99-159">例如，可以建立一個功能表，其中按鍵 0、1 和 3 對應到選項，而兩個按鍵則沒有使用。</span><span class="sxs-lookup"><span data-stu-id="dce99-159">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the two key isn't used.</span></span>

<span data-ttu-id="dce99-160">如果您已經將零鍵與運算子進行比對，建議您將零鍵與運算子進行比對。</span><span class="sxs-lookup"><span data-stu-id="dce99-160">We recommend mapping the zero key to the operator if you have configured one.</span></span> <span data-ttu-id="dce99-161">如果運算子未設定為任何按鍵，也會停用語音命令「運算子」。</span><span class="sxs-lookup"><span data-stu-id="dce99-161">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="dce99-162">針對每個功能表選項，指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="dce99-162">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="dce99-163">**撥號鍵** - 電話鍵臺上的按鍵，可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="dce99-163">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="dce99-164">如果語音輸入可以使用，來電者也可以說出這個號碼來存取選項。</span><span class="sxs-lookup"><span data-stu-id="dce99-164">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="dce99-165">**語音命令** - 定義來電者可給予存取此選項的語音命令 ，如果已啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="dce99-165">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="dce99-166">它可以包含多個字詞，例如「客戶服務」或「營運與理由」。</span><span class="sxs-lookup"><span data-stu-id="dce99-166">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="dce99-167">例如，來電者可以按 2、說「2」，或說「銷售」以選取對應到兩個按鍵的選項。</span><span class="sxs-lookup"><span data-stu-id="dce99-167">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two key.</span></span> <span data-ttu-id="dce99-168">此文字也會以服務確認提示的文字轉語音顯示，例如「將通話轉接至銷售」。</span><span class="sxs-lookup"><span data-stu-id="dce99-168">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="dce99-169">**重新導向** 至 - 來電者選擇此選項時所使用的通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-169">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="dce99-170">如果您要重新導向到自動 Attendant 或通話佇列，請選擇與其相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="dce99-170">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="dce99-171">目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="dce99-171">Directory search</span></span>

<span data-ttu-id="dce99-172">如果您將撥號鍵指派給目的地，建議您選擇搜尋 **目錄** 時選擇 **None。**</span><span class="sxs-lookup"><span data-stu-id="dce99-172">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="dce99-173">如果來電者嘗試使用指派給特定目的地的按鍵撥號名稱或分機，他們可能會在您完成輸入名稱或分機之前，未預期地路由至目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-173">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="dce99-174">建議您為目錄搜尋建立個別的自動 Attendant，並透過撥號鍵提供主要的自動總機連結。</span><span class="sxs-lookup"><span data-stu-id="dce99-174">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="dce99-175">如果您未指派撥號鍵，請選擇目錄 **搜尋選項**。</span><span class="sxs-lookup"><span data-stu-id="dce99-175">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="dce99-176">**按名稱** 撥號 - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵台輸入。</span><span class="sxs-lookup"><span data-stu-id="dce99-176">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="dce99-177">任何線上使用者或任何使用商務用 Skype Server 在內部部署託管的使用者，都是合格的使用者，而且可以使用撥號名稱找到。</span><span class="sxs-lookup"><span data-stu-id="dce99-177">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="dce99-178"> (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="dce99-178">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="dce99-179">**分機號碼** - 如果您啟用此選項，來電者可以撥打其電話分機，與貴組織的使用者聯繫。</span><span class="sxs-lookup"><span data-stu-id="dce99-179">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="dce99-180">任何線上使用者或任何使用商務用 Skype Server 託管于內部部署的使用者，都是符合資格的使用者，而且可撥打分機 **號碼。**</span><span class="sxs-lookup"><span data-stu-id="dce99-180">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="dce99-181"> (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="dce99-181">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="dce99-182">想要提供撥號分機服務的使用者，必須擁有在 Active Directory 或 Azure Active Directory 中定義的下列其中一個電話屬性的擴充功能 (請參閱個別或大量[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)新增使用者以瞭解更多資訊。) </span><span class="sxs-lookup"><span data-stu-id="dce99-182">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="dce99-183">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="dce99-183">OfficePhone</span></span>
- <span data-ttu-id="dce99-184">HomePhone</span><span class="sxs-lookup"><span data-stu-id="dce99-184">HomePhone</span></span>
- <span data-ttu-id="dce99-185">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="dce99-185">Mobile/MobilePhone</span></span>
- <span data-ttu-id="dce99-186">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="dce99-186">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="dce99-187">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="dce99-187">OtherTelephone</span></span>

<span data-ttu-id="dce99-188">在使用者電話號碼欄位中輸入分機所需的格式為：</span><span class="sxs-lookup"><span data-stu-id="dce99-188">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="dce99-189">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="dce99-189">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="dce99-190">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="dce99-190">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="dce99-191">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="dce99-191">*x\<extension>*</span></span>

- <span data-ttu-id="dce99-192">範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="dce99-192">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="dce99-193">範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="dce99-193">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="dce99-194">範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="dce99-194">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="dce99-195">您可以在 [Microsoft 365](https://admin.microsoft.com/) 系統管理中心或 Azure [Active Directory](https://aad.portal.azure.com)系統管理中心設定擴充功能。</span><span class="sxs-lookup"><span data-stu-id="dce99-195">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="dce99-196">最多可能需要 12 小時，自動電話機和通話佇列才能使用變更。</span><span class="sxs-lookup"><span data-stu-id="dce99-196">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="dce99-197">如果您想要同時使用按名稱撥號和按分機撥號的功能，您可以在主自動轉音器上指派撥號鍵，以使用已啟用撥號名稱的自動轉 **音機**。</span><span class="sxs-lookup"><span data-stu-id="dce99-197">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="dce99-198">您可以在該自動 attendant 中指派 1 個按鍵 (沒有與其關聯的字母，) **分機自動** 總機。</span><span class="sxs-lookup"><span data-stu-id="dce99-198">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="dce99-199">選取目錄搜尋選項 **之後** ，請選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="dce99-199">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="dce99-200">數小時後的通話流程</span><span class="sxs-lookup"><span data-stu-id="dce99-200">Call flow for after hours</span></span>

![小時後日與時間設定之螢幕擷取畫面](media/auto-attendant-business-hours.png)

<span data-ttu-id="dce99-202">您可以針對每個自動 Attendant 設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="dce99-202">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="dce99-203">如果未設定上班時間，則一天中所有天及所有時數會視為上班時間，因為預設會設定 24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="dce99-203">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="dce99-204">上班時間可以設定為一天中的休息時間，而未設定為上班時間的所有時數會視為上班時間。</span><span class="sxs-lookup"><span data-stu-id="dce99-204">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="dce99-205">您可以設定不同的來電處理選項和上班時間的問候語。</span><span class="sxs-lookup"><span data-stu-id="dce99-205">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="dce99-206">根據您如何配置自動電話機和通話佇列，您可能只需要為具有直接電話號碼的自動電話機指定後通話路由。</span><span class="sxs-lookup"><span data-stu-id="dce99-206">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="dce99-207">如果您想要為上班時間來電者分別進行通話路由，請指定每天的上班時間。</span><span class="sxs-lookup"><span data-stu-id="dce99-207">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="dce99-208">選取 **新增時間** 以指定指定一天的多組時數，例如，指定午餐休息時間。</span><span class="sxs-lookup"><span data-stu-id="dce99-208">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="dce99-209">指定上班時間後，請選擇上班時間的通話路由選項。</span><span class="sxs-lookup"><span data-stu-id="dce99-209">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="dce99-210">這些選項與上述指定的上班時間通話路由相同。</span><span class="sxs-lookup"><span data-stu-id="dce99-210">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="dce99-211">完成 **時** 選取下一步。</span><span class="sxs-lookup"><span data-stu-id="dce99-211">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="dce99-212">假日期間通話流量</span><span class="sxs-lookup"><span data-stu-id="dce99-212">Call flows during holidays</span></span>

![假日和假日問候語設定螢幕擷取畫面](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="dce99-214">您的自動電話機可以針對您設定的每個 [假日提供通話流程](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dce99-214">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="dce99-215">您可以在每個自動 Attendant 中新增最多 20 個排定的假日。</span><span class="sxs-lookup"><span data-stu-id="dce99-215">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="dce99-216">在假日通話設定頁面上 **，選取新增**。</span><span class="sxs-lookup"><span data-stu-id="dce99-216">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="dce99-217">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="dce99-217">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="dce99-218">從 **假日** 下拉拉，選擇您想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="dce99-218">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="dce99-219">選擇您想要使用的問候語類型。</span><span class="sxs-lookup"><span data-stu-id="dce99-219">Choose the type of greeting that you want to use.</span></span>

    ![假日通話動作設定螢幕擷取畫面](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="dce99-221">選擇是否要中斷 **連接或\*\*\*\*重新導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="dce99-221">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="dce99-222">如果您選擇重新導向，請選擇通話的呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="dce99-222">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="dce99-223">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="dce99-223">Select **Save**.</span></span>

![已列出假日的假日設定螢幕擷取畫面](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="dce99-225">針對每一個額外的假日，請根據需要重複這個程式。</span><span class="sxs-lookup"><span data-stu-id="dce99-225">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="dce99-226">當您新增所有假日時，請選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="dce99-226">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="dce99-227">撥號範圍</span><span class="sxs-lookup"><span data-stu-id="dce99-227">Dial scope</span></span>

![撥號範圍包含和排除選項的螢幕擷取畫面](media/auto-attendant-dial-scope.png)

<span data-ttu-id="dce99-229">撥號 *範圍* 會定義當來電者使用撥號或撥號分機時，哪些使用者可以在目錄中使用。</span><span class="sxs-lookup"><span data-stu-id="dce99-229">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="dce99-230">根據預設 **，所有線上** 使用者會包含貴組織的所有使用者，這些使用者都是線上使用者，或是使用商務用 Skype Server 託管于內部部署。</span><span class="sxs-lookup"><span data-stu-id="dce99-230">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="dce99-231">您可以選取包含或排除下的自訂使用者群組，並選擇一或多個Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 </span><span class="sxs-lookup"><span data-stu-id="dce99-231">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="dce99-232">例如，您可能會想要將貴組織的高主管排除在撥號目錄中。</span><span class="sxs-lookup"><span data-stu-id="dce99-232">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="dce99-233"> (如果使用者同時在兩個清單中，就會從目錄.) </span><span class="sxs-lookup"><span data-stu-id="dce99-233">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="dce99-234">新使用者最多可能需要 36 小時，才能將他們的名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="dce99-234">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="dce99-235">設定好撥號範圍後，請選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="dce99-235">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="dce99-236">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="dce99-236">Resource accounts</span></span>

<span data-ttu-id="dce99-237">所有自動 attendant 都必須有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="dce99-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="dce99-238">第一層自動 attendant 至少需要一個擁有相關聯服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="dce99-238">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="dce99-239">您可以根據需要，將多個資源帳戶指派給自動 Attendant，每個帳戶都有個別的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="dce99-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![資源帳戶新增帳戶面板的螢幕擷取畫面](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="dce99-241">若要新增資源帳戶，請選取 **新增帳戶** ，然後搜尋您想要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dce99-241">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="dce99-242">選取 **新增**， **然後選取新增**。</span><span class="sxs-lookup"><span data-stu-id="dce99-242">Select **Add**, and then select **Add**.</span></span>

![顯示資源帳戶與已指派服務編號的資源帳戶清單螢幕擷取畫面](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="dce99-244">完成新增服務帳戶後，請選取 **提交** 以完成自動 attendant 組選。</span><span class="sxs-lookup"><span data-stu-id="dce99-244">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="dce99-245">外部電話號碼傳輸 - 技術詳細資料</span><span class="sxs-lookup"><span data-stu-id="dce99-245">External phone number transfers - technical details</span></span>

<span data-ttu-id="dce99-246">請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以允許自動電話機將電話轉接至外部。</span><span class="sxs-lookup"><span data-stu-id="dce99-246">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="dce99-247">另外：</span><span class="sxs-lookup"><span data-stu-id="dce99-247">In addition:</span></span>

- <span data-ttu-id="dce99-248">對於具有通話方案號碼的資源[](calling-plans-for-office-365.md)帳戶，外部轉接電話號碼必須以 E.164 格式輸入 (+[國碼][區碼][電話號碼]) 。</span><span class="sxs-lookup"><span data-stu-id="dce99-248">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="dce99-249">對於具有直接路由號碼的資源帳戶，外部移轉電話號碼格式取決於會話邊界控制器 ([SBC) ](direct-routing-connect-the-sbc.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="dce99-249">For a resource account with a Direct Routing number, the external transfer phone number format is dependent on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="dce99-250">顯示外發電話號碼的判定方式如下：</span><span class="sxs-lookup"><span data-stu-id="dce99-250">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="dce99-251">針對通話方案號碼，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dce99-251">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="dce99-252">針對直接路由號碼，傳送的號碼是根據 SBC 上的 P-就地識別 (PAI) 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dce99-252">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="dce99-253">如果設為停用，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dce99-253">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="dce99-254">這是預設及建議設定。</span><span class="sxs-lookup"><span data-stu-id="dce99-254">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="dce99-255">如果設為啟用，會顯示資源帳戶電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dce99-255">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="dce99-256">在商務用 Skype 混合式環境中，若要將自動 attendant 通話轉接到 PSTN，請建立一個新的內部部署使用者，將來電轉接設定為 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="dce99-256">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="dce99-257">使用者必須啟用企業語音，並指派語音策略。</span><span class="sxs-lookup"><span data-stu-id="dce99-257">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="dce99-258">若要深入瞭解，請參閱[自動將電話轉接到 PSTN。](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="dce99-258">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="dce99-259">使用 PowerShell 建立自動 Attendant</span><span class="sxs-lookup"><span data-stu-id="dce99-259">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="dce99-260">您也可以使用 PowerShell 來建立和設定自動 Attendant。</span><span class="sxs-lookup"><span data-stu-id="dce99-260">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="dce99-261">以下是管理自動 attendant 所需的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dce99-261">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="dce99-262">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dce99-262">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="dce99-263">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dce99-263">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="dce99-264">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dce99-264">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="dce99-265">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="dce99-265">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="dce99-266">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="dce99-266">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="dce99-267">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="dce99-267">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="dce99-268">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="dce99-268">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="dce99-269">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="dce99-269">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="dce99-270">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="dce99-270">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="dce99-271">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="dce99-271">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="dce99-272">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="dce99-272">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="dce99-273">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="dce99-273">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="dce99-274">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="dce99-274">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="dce99-275">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="dce99-275">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="dce99-276">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="dce99-276">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="dce99-277">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="dce99-277">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="dce99-278">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="dce99-278">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="dce99-279">相關主題</span><span class="sxs-lookup"><span data-stu-id="dce99-279">Related topics</span></span>

[<span data-ttu-id="dce99-280">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="dce99-280">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="dce99-281">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="dce99-281">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="dce99-282">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="dce99-282">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="dce99-283">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="dce99-283">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
