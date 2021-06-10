---
title: 設定自動Microsoft Teams
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
description: 瞭解如何在 Microsoft Teams 中為大型組織設定和測試自動Microsoft Teams。
ms.openlocfilehash: cc4d0de8fd1d6c643f23b6e8215f0f7a343b2a8f
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777797"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="862c4-103">設定自動話務員</span><span class="sxs-lookup"><span data-stu-id="862c4-103">Set up an auto attendant</span></span>

<span data-ttu-id="862c4-104">自動電話機可讓人打電話給您的組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。</span><span class="sxs-lookup"><span data-stu-id="862c4-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="862c4-105">您可以使用系統管理中心或 PowerShell 為貴組織Microsoft Teams自動助理。</span><span class="sxs-lookup"><span data-stu-id="862c4-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

> [!TIP]
> <span data-ttu-id="862c4-106">本文適用于大型組織。</span><span class="sxs-lookup"><span data-stu-id="862c4-106">This article is for large organizations.</span></span> <span data-ttu-id="862c4-107">如果貴組織是小型企業，請改為閱讀設定自動話務員 [- 小型企業](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 教學課程。</span><span class="sxs-lookup"><span data-stu-id="862c4-107">If your organization is a small business, read [Set up an auto attendant - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) instead.</span></span>

<span data-ttu-id="862c4-108">請務必先閱讀自動Teams[](plan-auto-attendant-call-queue.md)和通話佇列的規劃，並遵循開始使用的步驟，然後再遵循本文[](plan-auto-attendant-call-queue.md#getting-started)中的程式。</span><span class="sxs-lookup"><span data-stu-id="862c4-108">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="862c4-109">自動語音機可以根據來電者的輸入，將通話直接路由至下列其中一個目的地： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="862c4-109">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="862c4-110">**運算子** - 為自動話務員定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="862c4-110">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="862c4-111">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="862c4-111">Defining an operator is optional.</span></span> <span data-ttu-id="862c4-112">運算子可定義為此清單的其他目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-112">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="862c4-113">**組織中可以接聽** 語音通話的人。</span><span class="sxs-lookup"><span data-stu-id="862c4-113">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="862c4-114">此人可以是線上使用者，或使用內部部署託管商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="862c4-114">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="862c4-115">**語音應用程式** - 另一個自動語音留言機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="862c4-115">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="862c4-116"> (選擇此目的地時，選擇與自動電話機或通話佇列相關聯的資源帳戶。) </span><span class="sxs-lookup"><span data-stu-id="862c4-116">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="862c4-117">**語音** 信箱 - 與您指定的Microsoft 365群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="862c4-117">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span> <span data-ttu-id="862c4-118">您可以選擇是否要語音信箱字幕和「請在語音信箱後留言」。</span><span class="sxs-lookup"><span data-stu-id="862c4-118">You can choose if you want voicemail transcriptions and the "Please leave a message after the tone."</span></span> <span data-ttu-id="862c4-119">系統提示。</span><span class="sxs-lookup"><span data-stu-id="862c4-119">system prompt.</span></span>
- <span data-ttu-id="862c4-120">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="862c4-120">**External phone number** - any phone number.</span></span> <span data-ttu-id="862c4-121"> (請參閱[外部移轉技術詳細資料) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="862c4-121">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="862c4-122">**公告 (音訊)** - 播放音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="862c4-122">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="862c4-123">您上傳的錄製公告訊息，儲存為音訊。WAV、.MP3或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="862c4-123">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="862c4-124">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="862c4-124">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="862c4-125">系統會播放公告，然後返回自動助理功能表。</span><span class="sxs-lookup"><span data-stu-id="862c4-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="862c4-126">**公告 (輸入)** - 在郵件中輸入。</span><span class="sxs-lookup"><span data-stu-id="862c4-126">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="862c4-127">您希望系統讀取的文字。</span><span class="sxs-lookup"><span data-stu-id="862c4-127">Text you want the system to read.</span></span> <span data-ttu-id="862c4-128">您最多可以輸入 1000 個字元。</span><span class="sxs-lookup"><span data-stu-id="862c4-128">You can enter up to 1000 characters.</span></span> <span data-ttu-id="862c4-129">系統會播放公告，然後返回自動助理功能表。</span><span class="sxs-lookup"><span data-stu-id="862c4-129">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="862c4-130">當您設定自動語音機時，系統會提示您于各個階段選擇其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="862c4-130">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="862c4-131">若要設定自動語音Teams，請在系統管理中心展開 **語音**，選取自動語音留言，然後選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="862c4-131">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="862c4-132">影片示範</span><span class="sxs-lookup"><span data-stu-id="862c4-132">Video demonstration</span></span>

<span data-ttu-id="862c4-133">這段影片顯示如何在 Teams 中建立自動Teams。</span><span class="sxs-lookup"><span data-stu-id="862c4-133">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="862c4-134">一般資訊</span><span class="sxs-lookup"><span data-stu-id="862c4-134">General info</span></span>

![名稱、運算子、時區、語言和語音輸入的自動語音留言設定螢幕擷取畫面](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="862c4-136">在頂端方塊中輸入自動助理的名稱。</span><span class="sxs-lookup"><span data-stu-id="862c4-136">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="862c4-137">若要指定運算子，請指定撥打給接線員的目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-137">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="862c4-138">此指定為選擇性 (，但建議使用) 。</span><span class="sxs-lookup"><span data-stu-id="862c4-138">This designation is optional (but recommended).</span></span> <span data-ttu-id="862c4-139">設定運算子 **選項** ，讓來電者離開功能表，與指定的人員通話。</span><span class="sxs-lookup"><span data-stu-id="862c4-139">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="862c4-140">指定此自動助理的時區。</span><span class="sxs-lookup"><span data-stu-id="862c4-140">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="862c4-141">如果您為小時後建立個別的通話流程，則時區會用來 [計算上班時間](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="862c4-141">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="862c4-142">指定此 [自動翻譯](create-a-phone-system-auto-attendant-languages.md) 的支援語言。</span><span class="sxs-lookup"><span data-stu-id="862c4-142">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="862c4-143">這是系統產生的語音提示所使用的語言。</span><span class="sxs-lookup"><span data-stu-id="862c4-143">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="862c4-144">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="862c4-144">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="862c4-145">啟用時，每個功能表選項的名稱會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="862c4-145">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="862c4-146">例如，來電者可以說「One」，以選取對應到按鍵 1 的功能表選項，或說「銷售」以選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="862c4-146">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

   > [!NOTE]
   > <span data-ttu-id="862c4-147">如果您在步驟 4 中選擇不支援語音輸入的語言，此選項將會停用。</span><span class="sxs-lookup"><span data-stu-id="862c4-147">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="862c4-148">選取 下 **一個**。</span><span class="sxs-lookup"><span data-stu-id="862c4-148">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="862c4-149">通話流程</span><span class="sxs-lookup"><span data-stu-id="862c4-149">Call flow</span></span>

![問候語訊息設定螢幕擷取畫面](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="862c4-151">選擇當自動回應接聽來電時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="862c4-151">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="862c4-152">如果您選取 **播放音訊檔案**，您可以使用 Upload **按鈕** 上傳儲存為音訊的錄製問候語訊息。WAV、.MP3或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="862c4-152">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="862c4-153">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="862c4-153">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="862c4-154">如果您選取輸入 **問候語訊息** ，當自動 (接聽來電時，系統會朗讀您輸入 (最多 1000 個字元的文字) 自動回應接聽來電。</span><span class="sxs-lookup"><span data-stu-id="862c4-154">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話路由設定螢幕擷取畫面](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="862c4-156">選擇通話的路由方式。</span><span class="sxs-lookup"><span data-stu-id="862c4-156">Choose how you want to route the call.</span></span>

<span data-ttu-id="862c4-157">如果您選取中斷 **連接**，自動電話機會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="862c4-157">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="862c4-158">如果您選取 **重新導向通話**，您可以選擇其中一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-158">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="862c4-159">如果您選取了 **播放功能表選項**，您可以選擇播放音訊檔案或輸入問候語訊息，然後選擇功能表選項和目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="862c4-159">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="862c4-160">功能表選項</span><span class="sxs-lookup"><span data-stu-id="862c4-160">Menu options</span></span>

![撥號鍵選項的螢幕擷取畫面](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="862c4-162">針對撥號選項，將電話鍵臺上的 0-9 鍵指派給其中一個撥號路由目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-162">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="862c4-163"> (系統 (重複)  (返回) 按鍵，且無法重新指派 \* \# 。) </span><span class="sxs-lookup"><span data-stu-id="862c4-163">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="862c4-164">鍵的映射不必是連續的。</span><span class="sxs-lookup"><span data-stu-id="862c4-164">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="862c4-165">雖然沒有使用數位 2 鍵，但可以建立對應到選項的按鍵 0、1 和 3 的功能表。</span><span class="sxs-lookup"><span data-stu-id="862c4-165">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="862c4-166">如果您已經配置零鍵，建議您將零鍵與運算子進行比對。</span><span class="sxs-lookup"><span data-stu-id="862c4-166">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="862c4-167">如果運算子未設定為任何按鍵，語音命令「運算子」也會停用。</span><span class="sxs-lookup"><span data-stu-id="862c4-167">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="862c4-168">針對每個功能表選項，指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="862c4-168">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="862c4-169">**撥號鍵** - 電話鍵臺上的按鍵，以存取此選項。</span><span class="sxs-lookup"><span data-stu-id="862c4-169">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="862c4-170">如果語音輸入可用，來電者也可以說這個號碼來存取選項。</span><span class="sxs-lookup"><span data-stu-id="862c4-170">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="862c4-171">**Voice 命令** - 定義來電者可以給予的語音命令以存取此選項 ，如果已啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="862c4-171">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="862c4-172">它可以包含多個字詞，例如「客戶服務」或「營運與理由」。</span><span class="sxs-lookup"><span data-stu-id="862c4-172">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="862c4-173">例如，來電者可以按 2，說出「兩」，或說「銷售」以選取對應到兩個按鍵的選項。</span><span class="sxs-lookup"><span data-stu-id="862c4-173">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="862c4-174">此文字也會以文字呈現為服務確認提示的文字，例如「將通話轉接至銷售」。</span><span class="sxs-lookup"><span data-stu-id="862c4-174">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="862c4-175">**重新導向** 至 - 當來電者選擇此選項時所使用的通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-175">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="862c4-176">如果您要重新導向到自動電話機或通話佇列，請選擇與其相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="862c4-176">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="862c4-177">目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="862c4-177">Directory search</span></span>

<span data-ttu-id="862c4-178">如果您將撥號鍵指派給目的地，建議您選擇 **目錄搜尋的\*\*\*\*無**。</span><span class="sxs-lookup"><span data-stu-id="862c4-178">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="862c4-179">如果來電者嘗試使用指派給特定目的地的按鍵撥號名稱或分機，他們可能會在您輸入名稱或分機之前，意外路由到目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-179">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="862c4-180">建議您為目錄搜尋建立個別的自動總機，並擁有使用撥號鍵的自動總機連結。</span><span class="sxs-lookup"><span data-stu-id="862c4-180">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="862c4-181">如果您沒有指派撥號鍵，請選擇目錄 **搜尋的選項**。</span><span class="sxs-lookup"><span data-stu-id="862c4-181">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="862c4-182">**按名稱** 撥號 - 如果您啟用此選項，來電者可以說出使用者的名稱，或在電話鍵盤上輸入。</span><span class="sxs-lookup"><span data-stu-id="862c4-182">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="862c4-183">任何線上使用者或任何使用 商務用 Skype Server 託管于內部部署的使用者，都是合格的使用者，而且可以使用撥號名稱找到。</span><span class="sxs-lookup"><span data-stu-id="862c4-183">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="862c4-184"> (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="862c4-184">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="862c4-185">**分機撥號** - 如果您啟用此選項，來電者可以撥打其電話分機，與貴組織的使用者聯繫。</span><span class="sxs-lookup"><span data-stu-id="862c4-185">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="862c4-186">任何線上使用者或任何使用 商務用 Skype Server 託管于內部部署的使用者，都是合格的使用者，而且可以使用 **分機撥號找到**。</span><span class="sxs-lookup"><span data-stu-id="862c4-186">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="862c4-187"> (您可以設定撥號範圍頁面上的目錄中包含和不包含哪些人。) [](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="862c4-187">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="862c4-188">您想要提供撥號分機的使用者，需要將分機指定為 Active Directory 或 Azure Active Directory (中定義的下列其中一個電話屬性的一部分Azure Active Directory (請參閱個別或大量[](/microsoft-365/admin/add-users/add-users)新增使用者以瞭解更多資訊。) </span><span class="sxs-lookup"><span data-stu-id="862c4-188">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="862c4-189">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="862c4-189">OfficePhone</span></span>
- <span data-ttu-id="862c4-190">家用電話</span><span class="sxs-lookup"><span data-stu-id="862c4-190">HomePhone</span></span>
- <span data-ttu-id="862c4-191">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="862c4-191">Mobile/MobilePhone</span></span>
- <span data-ttu-id="862c4-192">PhoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="862c4-192">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="862c4-193">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="862c4-193">OtherTelephone</span></span>

<span data-ttu-id="862c4-194">在使用者電話號碼欄位中輸入分機所需的格式可以是下列其中一種格式：</span><span class="sxs-lookup"><span data-stu-id="862c4-194">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="862c4-195">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="862c4-195">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="862c4-196">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="862c4-196">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="862c4-197">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="862c4-197">*x\<extension>*</span></span>

- <span data-ttu-id="862c4-198">範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber"+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="862c4-198">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="862c4-199">範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="862c4-199">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="862c4-200">範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="862c4-200">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="862c4-201">您可以在系統管理中心或系統管理[Microsoft 365設定](https://admin.microsoft.com/)[Azure Active Directory副檔名](https://aad.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="862c4-201">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="862c4-202">自動電話機和通話佇列最多可能需要 12 小時才能進行變更。</span><span class="sxs-lookup"><span data-stu-id="862c4-202">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="862c4-203">如果您想要同時使用名稱撥號和分機撥號功能，您可以在主自動電話機上指派撥號鍵，以到達啟用名稱撥號的自動總 **機**。</span><span class="sxs-lookup"><span data-stu-id="862c4-203">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="862c4-204">您可以在該自動話務員中指派 1 個按鍵 (沒有與其關聯的字母，) **分機** 自動總機撥號。</span><span class="sxs-lookup"><span data-stu-id="862c4-204">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="862c4-205">選取目錄搜尋選項之後，請選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="862c4-205">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="862c4-206">數小時後的通話流程</span><span class="sxs-lookup"><span data-stu-id="862c4-206">Call flow for after hours</span></span>

![日與時數設定後小時數的螢幕擷取畫面](media/auto-attendant-business-hours.png)

<span data-ttu-id="862c4-208">您可以針對每個自動話務員設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="862c4-208">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="862c4-209">如果未設定上班時間，則一天中所有的天數和所有時數會視為上班時間，因為預設會設定 24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="862c4-209">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="862c4-210">工作時間可以設定為一天中的休息時間，所有未設定為上班時間的時數會視為工作時間之後。</span><span class="sxs-lookup"><span data-stu-id="862c4-210">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="862c4-211">您可以為工作時間設定不同的來電處理選項和問候語。</span><span class="sxs-lookup"><span data-stu-id="862c4-211">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="862c4-212">根據您如何配置自動電話機和通話佇列，您可能只需要為具有直接電話號碼的自動電話機指定後通話路由。</span><span class="sxs-lookup"><span data-stu-id="862c4-212">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="862c4-213">如果您想要為非工作時間的來電者個別進行通話路由，請為每天指定您的上班時間。</span><span class="sxs-lookup"><span data-stu-id="862c4-213">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="862c4-214">選取 **新增時間** 以指定指定一天的陣列時數，例如，指定午餐休息時間。</span><span class="sxs-lookup"><span data-stu-id="862c4-214">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="862c4-215">指定上班時間之後，請選擇您的通話路由選項，以在數小時後使用。</span><span class="sxs-lookup"><span data-stu-id="862c4-215">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="862c4-216">上述指定的上班時間通話路由也提供相同的選項。</span><span class="sxs-lookup"><span data-stu-id="862c4-216">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="862c4-217">完成後 **，** 請選取下一步。</span><span class="sxs-lookup"><span data-stu-id="862c4-217">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="862c4-218">假日期間通話流程</span><span class="sxs-lookup"><span data-stu-id="862c4-218">Call flows during holidays</span></span>

![假日和假日問候語設定螢幕擷取畫面](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="862c4-220">您的自動電話機可以針對您設定的每個 [假日有通話流程](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="862c4-220">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="862c4-221">您最多可以將 20 個排定的假日加到每個自動乘務員。</span><span class="sxs-lookup"><span data-stu-id="862c4-221">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="862c4-222">在假日通話設定頁面上 **，選取** 新增 。</span><span class="sxs-lookup"><span data-stu-id="862c4-222">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="862c4-223">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="862c4-223">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="862c4-224">從假日 **下** 拉下拉，選擇您想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="862c4-224">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="862c4-225">選擇您想要使用的問候語類型。</span><span class="sxs-lookup"><span data-stu-id="862c4-225">Choose the type of greeting that you want to use.</span></span>

    ![假日通話動作設定螢幕擷取畫面](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="862c4-227">選擇是否要中斷 **連接或\*\*\*\*重新導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="862c4-227">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="862c4-228">如果您選擇重新導向，請選擇通話的呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="862c4-228">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="862c4-229">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="862c4-229">Select **Save**.</span></span>

![列出假日的假日設定螢幕擷取畫面](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="862c4-231">針對每一個額外的假日，根據需要重複此程式。</span><span class="sxs-lookup"><span data-stu-id="862c4-231">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="862c4-232">當您新增所有假日後，請選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="862c4-232">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="862c4-233">撥號範圍</span><span class="sxs-lookup"><span data-stu-id="862c4-233">Dial scope</span></span>

![撥號範圍包含及排除選項的螢幕擷取畫面](media/auto-attendant-dial-scope.png)

<span data-ttu-id="862c4-235">撥號 *範圍* 會定義當來電者使用撥號名稱或撥號分機時，哪些使用者可在目錄中使用。</span><span class="sxs-lookup"><span data-stu-id="862c4-235">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="862c4-236">預設為 **所有線上使用者**，包括貴組織的所有使用者，這些使用者都是線上使用者，或是使用內部部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="862c4-236">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="862c4-237">您可以選取在包含或排除下的自訂使用者群組，並選擇一或多個Microsoft 365群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 </span><span class="sxs-lookup"><span data-stu-id="862c4-237">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="862c4-238">例如，您可能會想要將貴組織的主管排除在撥號目錄中。</span><span class="sxs-lookup"><span data-stu-id="862c4-238">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="862c4-239"> (如果使用者同時位於這兩個清單中，就會被排除在目錄中。) </span><span class="sxs-lookup"><span data-stu-id="862c4-239">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="862c4-240">新使用者最多可能需要 36 小時，才能將名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="862c4-240">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="862c4-241">完成設定撥號範圍後，請選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="862c4-241">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="862c4-242">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="862c4-242">Resource accounts</span></span>

<span data-ttu-id="862c4-243">所有自動話務員都必須有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="862c4-243">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="862c4-244">第一層自動總機至少需要一個具有關聯服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="862c4-244">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="862c4-245">您可以根據需要，將多個資源帳戶指派給自動助理，每個帳戶都有個別的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="862c4-245">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![資源帳戶新增帳戶面板的螢幕擷取畫面](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="862c4-247">若要新增資源帳戶，請選取 **新增帳戶** ，然後搜尋您想要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="862c4-247">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="862c4-248">選取 **新增**，然後 **選取** 新增 。</span><span class="sxs-lookup"><span data-stu-id="862c4-248">Select **Add**, and then select **Add**.</span></span>

![顯示資源帳戶與已指派服務編號的資源帳戶清單螢幕擷取畫面](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="862c4-250">當您完成新增服務帳戶後，請選取 **提交** 以完成自動助理配置。</span><span class="sxs-lookup"><span data-stu-id="862c4-250">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="862c4-251">外部電話號碼傳輸 - 技術詳細資料</span><span class="sxs-lookup"><span data-stu-id="862c4-251">External phone number transfers - technical details</span></span>

<span data-ttu-id="862c4-252">請參閱 [先決條件，](plan-auto-attendant-call-queue.md#prerequisites) 以便允許自動電話機在外部轉接通話。</span><span class="sxs-lookup"><span data-stu-id="862c4-252">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="862c4-253">另外：</span><span class="sxs-lookup"><span data-stu-id="862c4-253">In addition:</span></span>

- <span data-ttu-id="862c4-254">對於具有通話方案授權的資源[](calling-plans-for-office-365.md)帳戶，外部轉接電話號碼必須以 E.164 格式輸入 (+[國家/地區代碼][區碼][電話號碼]) 。</span><span class="sxs-lookup"><span data-stu-id="862c4-254">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="862c4-255">對於具有授權電話系統直接路由線上語音路由策略的資源帳戶，外部傳輸電話號碼格式取決於會話邊界控制器[ (SBC](direct-routing-connect-the-sbc.md)) 設定。</span><span class="sxs-lookup"><span data-stu-id="862c4-255">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="862c4-256">顯示的外發電話號碼如下：</span><span class="sxs-lookup"><span data-stu-id="862c4-256">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="862c4-257">針對通話方案號碼，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="862c4-257">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="862c4-258">針對直接路由號碼，傳送的數位是根據 SBC 上的 P-Identityed-identity (PAI) 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="862c4-258">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="862c4-259">如果設為已停用，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="862c4-259">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="862c4-260">這是預設且建議的設定。</span><span class="sxs-lookup"><span data-stu-id="862c4-260">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="862c4-261">如果設為啟用，會顯示資源帳戶電話號碼。</span><span class="sxs-lookup"><span data-stu-id="862c4-261">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="862c4-262">在混合商務用 Skype環境中，若要將自動通話轉接到 PSTN，請建立一個新的內部部署使用者，將來電轉接設定為 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="862c4-262">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="862c4-263">使用者必須啟用企業語音並指派語音策略。</span><span class="sxs-lookup"><span data-stu-id="862c4-263">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="862c4-264">若要深入瞭解，請參閱[將電話自動轉接到 PSTN。](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="862c4-264">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="862c4-265">使用 PowerShell 建立自動助理</span><span class="sxs-lookup"><span data-stu-id="862c4-265">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="862c4-266">您也可以使用 PowerShell 建立和設定自動助理。</span><span class="sxs-lookup"><span data-stu-id="862c4-266">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="862c4-267">以下是管理自動話務員所需的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="862c4-267">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="862c4-268">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="862c4-268">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="862c4-269">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="862c4-269">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="862c4-270">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="862c4-270">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="862c4-271">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="862c4-271">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="862c4-272">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="862c4-272">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="862c4-273">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="862c4-273">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="862c4-274">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="862c4-274">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="862c4-275">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="862c4-275">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="862c4-276">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="862c4-276">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="862c4-277">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="862c4-277">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="862c4-278">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="862c4-278">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="862c4-279">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="862c4-279">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="862c4-280">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="862c4-280">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="862c4-281">New-CsAutoAttendantCallHandlingAsociation</span><span class="sxs-lookup"><span data-stu-id="862c4-281">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="862c4-282">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="862c4-282">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="862c4-283">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="862c4-283">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="862c4-284">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="862c4-284">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="862c4-285">相關主題</span><span class="sxs-lookup"><span data-stu-id="862c4-285">Related topics</span></span>

[<span data-ttu-id="862c4-286">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="862c4-286">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="862c4-287">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="862c4-287">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="862c4-288">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="862c4-288">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="862c4-289">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="862c4-289">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
