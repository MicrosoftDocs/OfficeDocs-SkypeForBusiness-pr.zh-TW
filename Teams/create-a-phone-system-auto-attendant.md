---
title: 設定雲端自動語音應答
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 瞭解如何為 Microsoft 團隊設定及測試雲端自動語音應答。
ms.openlocfilehash: 60fce49f2c03ef674e0b1e09f5d0193bcdab7ca0
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434961"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="17dd9-103">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="17dd9-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="17dd9-104">自動語音應答讓其他人打電話給您的組織，並流覽功能表系統，以與正確的部門通話、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="17dd9-105">您可以使用 Microsoft 團隊系統管理中心或 Powershell，為您的組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="17dd9-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with Powershell.</span></span> <span data-ttu-id="17dd9-106">若要建立自動語音應答，請移至左側導覽中的 [語音]，然後選取 [**自動** > **語音**應答**新增**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-106">To create an auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="17dd9-107">如果您想要深入瞭解自動語音應答，請參閱[什麼是雲端自動](/microsoftteams/what-are-phone-system-auto-attendants)語音應答？</span><span class="sxs-lookup"><span data-stu-id="17dd9-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="17dd9-108">本文適用于 Microsoft 團隊和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="17dd9-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

<span data-ttu-id="17dd9-109">電話號碼不會直接指派給自動語音應答，而是與自動語音助理相關聯的[資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="17dd9-109">Phone numbers are not directly assigned to the auto attendant, but rather to a [resource account](manage-resource-accounts.md) that is associated to the auto attendant.</span></span>

<span data-ttu-id="17dd9-110">自動語音應答的實現通常會涉及數個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="17dd9-110">Auto attendant implementations often involve several auto attendants.</span></span> <span data-ttu-id="17dd9-111">*第一層*自動語音應答通常會有一個已指派電話號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dd9-111">A *first-level* auto attendant usually has a resource account with an assigned phone number.</span></span> <span data-ttu-id="17dd9-112">嵌套的自動語音應答是用來做為第二級功能表，*第一層*的自動語音應答會連線為通話。</span><span class="sxs-lookup"><span data-stu-id="17dd9-112">A nested auto attendant is used as a second-level menu that the *first-level* auto attendant connects  as call to.</span></span> <span data-ttu-id="17dd9-113">*嵌套*的自動語音應答不需要將電話號碼指派給其資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dd9-113">A *nested* auto attendant isn't required to  have a phone number assigned to its resource account.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="17dd9-114">步驟1：快速入門</span><span class="sxs-lookup"><span data-stu-id="17dd9-114">Step 1 — Get started</span></span>

- <span data-ttu-id="17dd9-115">必須有一個自動語音應答，才能擁有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dd9-115">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="17dd9-116">如需資源帳戶及所有所需授權的詳細資料，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="17dd9-116">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span> 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> <span data-ttu-id="17dd9-117">若要將來電重新導向給以電話系統授權為線上使用者的操作員或功能表選項，您必須啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="17dd9-117">To redirect calls to an operator or a menu option that is an Online user with a Phone System license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="17dd9-118">請參閱[指派商務用 Skype 授權](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="17dd9-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="17dd9-119">您也可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="17dd9-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="17dd9-120">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="17dd9-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-auto-attendants"></a><span data-ttu-id="17dd9-121">步驟2：建立自動語音應答</span><span class="sxs-lookup"><span data-stu-id="17dd9-121">Step 2 — Create auto attendants</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17dd9-122">每個自動語音應答都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="17dd9-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="17dd9-123">您必須先建立資源帳戶，然後才能將它與自動語音應答建立關聯。</span><span class="sxs-lookup"><span data-stu-id="17dd9-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="with-the-microsoft-teams-admin-center"></a><span data-ttu-id="17dd9-124">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="17dd9-124">With the Microsoft Teams admin center</span></span>

<span data-ttu-id="17dd9-125">在**Microsoft [團隊管理中心**] 中，按一下 [**語音** > **自動**語音應答]，然後按一下 [ **+ 新增**]：</span><span class="sxs-lookup"><span data-stu-id="17dd9-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ Add**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="17dd9-126">一般資訊頁面</span><span class="sxs-lookup"><span data-stu-id="17dd9-126">General info page</span></span>

![[我的自動助理] 頁面的螢幕擷取畫面](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

<span data-ttu-id="17dd9-128">![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)
**名稱**中的標注輸入自動語音應答的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="17dd9-128">![Icon of the number 1, a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a display name for your auto attendant.</span></span> <span data-ttu-id="17dd9-129">名稱是必要的，而且最多可以包含64個字元，包括空格。</span><span class="sxs-lookup"><span data-stu-id="17dd9-129">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="17dd9-130">您在此處指定的**名稱**會列在 [**自動**語音應答] 索引標籤的欄中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-130">The **Name** you designate here is listed in a column on the **Auto attendants** tab.</span></span>

<span data-ttu-id="17dd9-131"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-131"></span></span>

* * *

<span data-ttu-id="17dd9-132">![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)
 <a name="operator"></a> 
**操作員**中的標注這是選擇性的（但建議使用）。</span><span class="sxs-lookup"><span data-stu-id="17dd9-132">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png)
<a name="operator"> </a>
**Operator** This is optional (but recommended).</span></span> <span data-ttu-id="17dd9-133">您可以設定 [**運算子**] 選項，讓呼叫者中斷功能表並向指定的人朗讀。</span><span class="sxs-lookup"><span data-stu-id="17dd9-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

<span data-ttu-id="17dd9-134">預設會將0按鍵指派給接線員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-134">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="17dd9-135">如果您設定一個運算子，請在 [**通話流程**] 頁面上的 [**編輯] 功能表選項**中，告訴給有關該選項的人員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-135">If you set an Operator, tell people who call about the option in **Edit menu options** on the **Call flow** page.</span></span> <span data-ttu-id="17dd9-136">如果您在自動語音應答上設定操作員，您可以在 [**呼叫者會聽到**] 方塊中輸入對應的提示文字，或變更您的音訊檔案，以包含此選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-136">If you set an operator on your auto attendant, you enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="17dd9-137">例如，"For 運算子，請按零。</span><span class="sxs-lookup"><span data-stu-id="17dd9-137">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="17dd9-138">您有幾種方式可以設定運算子：</span><span class="sxs-lookup"><span data-stu-id="17dd9-138">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="17dd9-139">[**無] 運算子**會停用「運算子」和「按0」選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-139">**No operator** disables the "Operator" and "Press 0" options.</span></span> <span data-ttu-id="17dd9-140">這是目前的預設值。</span><span class="sxs-lookup"><span data-stu-id="17dd9-140">This is the current default.</span></span>
- <span data-ttu-id="17dd9-141">**貴組織中的人員**會為 Office 365 中已啟用企業語音或指派通話方案的電話系統授權指派人員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-141">**Person in your organization** assigns a person with a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="17dd9-142">您也可以將呼叫者設定為傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="17dd9-142">You can also set it up so the caller is sent to voicemail.</span></span> <span data-ttu-id="17dd9-143">若要傳送來電者至語音信箱，請選取**貴組織中的人員**，並將該帳戶的設定設為直接傳送來電給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="17dd9-143">To send a caller to voicemail, select **Person in your organization** and set that account's settings to send calls directly to voicemail.</span></span>

     > [!Note]
     > <span data-ttu-id="17dd9-144">**貴組織中的人員**可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="17dd9-144">**Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

- <span data-ttu-id="17dd9-145">**語音應用程式** 選取連結到已建立之自動語音應答或通話佇列之資源帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="17dd9-145">**Voice app**  Select the name of the resource account linked to an auto attendant or call queue that has already been created.</span></span> <span data-ttu-id="17dd9-146">要求操作員的呼叫者會被重新導向。</span><span class="sxs-lookup"><span data-stu-id="17dd9-146">Callers that request an operator are redirected there.</span></span>  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<span data-ttu-id="17dd9-147"><a name="timezone"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-147"></span></span>

<span data-ttu-id="17dd9-148">![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png) **時區**中的標注，您必須為自動語音應答設定時區。</span><span class="sxs-lookup"><span data-stu-id="17dd9-148">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Time zone** You are required to set the time zone for your auto attendant.</span></span> <span data-ttu-id="17dd9-149">此設定可以與您組織的主要位址時區，或其他時區相同。</span><span class="sxs-lookup"><span data-stu-id="17dd9-149">The setting can be the same as the time zone of the main address listed for your organization, or a different time zone.</span></span> <span data-ttu-id="17dd9-150">每個自動助理都可以有不同的時區。</span><span class="sxs-lookup"><span data-stu-id="17dd9-150">Each auto attendant can have a different time zone.</span></span> <span data-ttu-id="17dd9-151">自動語音應答的 [上班時間] 設定也會使用 [此時區]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-151">The business hours set for the auto attendant also use this time zone.</span></span>

* * *

<span data-ttu-id="17dd9-152">![數位4的圖示，前一個螢幕擷取畫面](media/teamscallout4.png)
 <a name="language"></a> 
**語言**中的標注選取您要用於自動語音應答的語言。</span><span class="sxs-lookup"><span data-stu-id="17dd9-152">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)
<a name="language"> </a>
**Language** Select the language that you want to use for your auto attendant.</span></span> <span data-ttu-id="17dd9-153">自動語音應答會將該語言用於呼叫者，且系統會以這種語言來播放所有系統提示。</span><span class="sxs-lookup"><span data-stu-id="17dd9-153">The auto attendant uses that language with callers, and all system prompts are played in this language.</span></span>

 * * *

<span data-ttu-id="17dd9-154">![# 5 的圖示，在選取此選項時，前](media/teamscallout5.png)
一個螢幕擷取畫面中的標注會**啟用語音輸入**語音辨識功能。</span><span class="sxs-lookup"><span data-stu-id="17dd9-154">![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png)
**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="17dd9-155">呼叫者可以使用[您所設定之語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的語音輸入。</span><span class="sxs-lookup"><span data-stu-id="17dd9-155">Callers can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="17dd9-156">如果您只想讓其他人使用電話鍵進行選取，您可以將語音辨識設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-156">If you want to only let people use their phone keypad to make selections, you can leave speech recognition set to **Off**.</span></span>

* * *  

<span data-ttu-id="17dd9-157">完成選取後，請按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-157">When you finish with your selections, click **Next**.</span></span>

#### <a name="call-flow"></a><span data-ttu-id="17dd9-158">通話流程</span><span class="sxs-lookup"><span data-stu-id="17dd9-158">Call flow</span></span>

<span data-ttu-id="17dd9-159"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-159"></span></span>

> [!TIP]
> <span data-ttu-id="17dd9-160">您可以選擇設定自訂的上班時間排程，並在上班時間期間和之後進行不同的通話流程行為。</span><span class="sxs-lookup"><span data-stu-id="17dd9-160">You can choose to set up a custom business hours schedule, with different call flow behaviors during and after business hours.</span></span> <span data-ttu-id="17dd9-161">若要設定自訂排程，請設定[下班後的選擇性通話流程](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="17dd9-161">To set a custom schedule, set the optional [Call flow for after hours](#call-flow-for-after-hours).</span></span> <span data-ttu-id="17dd9-162">根據預設，自動語音應答會使用上班時間通話流程。</span><span class="sxs-lookup"><span data-stu-id="17dd9-162">By default, an auto attendant uses business hours call flows.</span></span>

<span data-ttu-id="17dd9-163">您可以設定自訂的問候語、提示及功能表，讓使用者在到達您的自動語音時聽到。</span><span class="sxs-lookup"><span data-stu-id="17dd9-163">You can set up customized greetings, prompts, and menus that people hear when they reach your auto attendant.</span></span>

![螢幕擷取畫面： [呼叫處理] 頁面問候區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

<span data-ttu-id="17dd9-165">**第一次播放問候訊息**問候語是選擇性的，可以設定為 [**沒有問候語**]、[**播放音訊**檔] 或 [**輸入問候] 訊息**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-165">**First play a greeting message** A greeting is optional and can be set to **No greeting**, **Play an audio file**, or **Type a greeting message**.</span></span>

> [!NOTE]
> <span data-ttu-id="17dd9-166">對第一層自動語音應答而言，問候非常重要。</span><span class="sxs-lookup"><span data-stu-id="17dd9-166">A greeting is most valuable for a first-level auto attendant.</span></span> <span data-ttu-id="17dd9-167">嵌套的自動語音助手通常不需要問候語。</span><span class="sxs-lookup"><span data-stu-id="17dd9-167">A nested auto attendant often doesn't need a greeting.</span></span>

<span data-ttu-id="17dd9-168">![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注如果您選取 [**沒有問候語**]，來電程式在由您稍後選取的其中一個動作前，就沒有聽到訊息或問候語。</span><span class="sxs-lookup"><span data-stu-id="17dd9-168">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) If you select **No Greeting**, the caller doesn't hear a message or greeting before the call is handled by one of the actions you select later.</span></span> 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

<span data-ttu-id="17dd9-169">![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注如果您選取 [**播放音訊**檔]，您可以使用 [**上傳**檔案] 按鈕上傳儲存為音訊的錄製問候語訊息。WAV，。[MP3] 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="17dd9-169">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="17dd9-170">錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="17dd9-170">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="17dd9-171">![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注輸入**問候訊息**：如果您選擇這個選項，請在提供的欄位中輸入您想要系統讀取的文字（最多1000個字元）。</span><span class="sxs-lookup"><span data-stu-id="17dd9-171">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="17dd9-172">例如，輸入「歡迎使用 Contoso。</span><span class="sxs-lookup"><span data-stu-id="17dd9-172">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="17dd9-173">您的通話對我們很重要。」</span><span class="sxs-lookup"><span data-stu-id="17dd9-173">Your call is important to us."</span></span> <span data-ttu-id="17dd9-174">[輸出] 是由文字到語音軟體所建立。</span><span class="sxs-lookup"><span data-stu-id="17dd9-174">Output is created by text-to-voice software.</span></span>

* * *

<span data-ttu-id="17dd9-175">您可以在 [從下列動作**傳送通話**] 區段中，選取 [呼叫] 旁的選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-175">You can select what happens next to calls from the following actions in the  **Then route the call** section.</span></span> <span data-ttu-id="17dd9-176">設定為 **[中斷連線]、[** 重新**導向通話**] 或 [**播放] 功能表選項**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-176">Settings are **Disconnect**, **Redirect call**, or **Play menu options**.</span></span>

<span data-ttu-id="17dd9-177">如果您選取 **[中斷連線]**，則會在問候語播放之後中斷呼叫者的連線。</span><span class="sxs-lookup"><span data-stu-id="17dd9-177">If you select **Disconnect**, the caller is disconnected after the greeting plays.</span></span> 

<span data-ttu-id="17dd9-178"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-178"></span></span>

<span data-ttu-id="17dd9-179">![數位4的圖示，前一個螢幕擷取畫面](media/teamscallout4.png)中的標注會重新**導向呼叫**將來電者傳送給所選的目的地，而不需選擇 [從選項]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-179">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png) **Redirect call** sends the caller to the chosen destination without choosing from options.</span></span> <span data-ttu-id="17dd9-180">可能的設定為：</span><span class="sxs-lookup"><span data-stu-id="17dd9-180">The possible settings are:</span></span>

  - <span data-ttu-id="17dd9-181">**組織中的人員**您選擇的帳戶必須具備企業語音的電話系統授權，或是在 Office 365 中有已指派的通話方案。</span><span class="sxs-lookup"><span data-stu-id="17dd9-181">**Person in organization** The account you choose must have a Phone System license enabled for Enterprise Voice or have an assigned Calling Plan in Office 365.</span></span> <span data-ttu-id="17dd9-182">您可以將其設定為將呼叫者傳送至語音信箱：選取 [**組織中的人員**]，然後將該帳戶設定為 [讓來電直接轉接至語音信箱]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-182">You can set it up so the caller can be sent to voicemail: select **Person in organization** and set that account to have calls forwarded directly to voicemail.</span></span>

  > [!Note]
  > <span data-ttu-id="17dd9-183">**組織中的人員**可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="17dd9-183">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

  - <span data-ttu-id="17dd9-184">**語音應用程式**選取已設定的自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="17dd9-184">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="17dd9-185">您可以依與服務相關聯之資源帳戶的名稱來搜尋自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="17dd9-185">You search for the auto attendant or call queue by the name of the resource account associated with the service.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant.
- **Call queue** Select the name of an auto attendant that has already been created.
- **External phone number** routes the caller to a phone number outside your local system.
- **Operator** directs the call to a user you designate as an Operator. If you haven't previously set up an operator, an option to create one now shows up. The 0 key is assigned to Operator by default. Options for setting an Operator are:

  - **No operator** disables the "Operator" and "Press 0" options.
  - **Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server. They must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. Search for the operator in the **Destination for your operator** field.
  - **Auto attendant** lets you choose the name of an existing auto attendant.
  - **Call queue** lets you select an existing call queue.
  - **Group Voicemail** routes the call to a voicemail box that you select. -->

 * * *

![螢幕擷取畫面： [呼叫處理頁面動作] 區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

<span data-ttu-id="17dd9-187">![數位1的圖示，當您選取 [**播放] 功能表選項**時，在先前的螢幕擷取畫面](media/teamscallout1.png)中，您可以選取是使用音訊檔案，還是要將轉譯成文字的文字轉換成語音，以向呼叫者提供撥號鍵台功能表選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-187">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) When you select **Play menu options** You can select whether to use an audio file or enter text that will be rendered as text to speech to give dialpad menu options to callers.</span></span> <span data-ttu-id="17dd9-188">選取此選項，而不是 [重新**導向呼叫** **] 或 [中斷連線]** 選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-188">Select this instead of the **Redirect call to** or **Disconnect** options.</span></span>


<span data-ttu-id="17dd9-189">![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注會**播放音訊**檔，讓您設定來電者選擇的提示和選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-189">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Play an audio file** lets you set up a prompts and options for the caller to choose.</span></span> 
- <span data-ttu-id="17dd9-190">如果您選取 [**播放音訊**檔]，您可以使用 [**上傳**檔案] 按鈕，上傳儲存為音訊的錄製問候語訊息。WAV，。[MP3] 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="17dd9-190">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="17dd9-191">錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="17dd9-191">The recording can be no larger than 5 MB.</span></span>

- <span data-ttu-id="17dd9-192">**輸入問候訊息**如果您選擇此選項，請在提供的欄位中輸入您想要系統讀取的文字（最多1000個字元）。</span><span class="sxs-lookup"><span data-stu-id="17dd9-192">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="17dd9-193">例如，輸入「歡迎使用 Contoso。</span><span class="sxs-lookup"><span data-stu-id="17dd9-193">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="17dd9-194">您的通話對我們很重要。」</span><span class="sxs-lookup"><span data-stu-id="17dd9-194">Your call is important to us."</span></span> <span data-ttu-id="17dd9-195">[輸出] 是由文字到語音軟體所建立。</span><span class="sxs-lookup"><span data-stu-id="17dd9-195">Output is created by text-to-voice software.</span></span>

<span data-ttu-id="17dd9-196">[**設定] 功能表選項**您可以在此對話方塊中新增或移除電話鍵台或語音命令。</span><span class="sxs-lookup"><span data-stu-id="17dd9-196">**Set menu options** Telephone keypad or voice commands can be added or removed in this dialog.</span></span> <span data-ttu-id="17dd9-197">若要刪除功能表選項，請移除語音命令專案，然後將 [重新**導向**] 設定為 [返回] 進行**選取**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-197">To delete a menu option, remove the voice command entry and set **Redirect to** back to **Select**.</span></span>

> [!TIP]
> <span data-ttu-id="17dd9-198">更新功能表提示文字，或在移除選項時重新錄製音訊提示。</span><span class="sxs-lookup"><span data-stu-id="17dd9-198">Update menu prompt text or re-record the audio prompts when you remove options.</span></span> <span data-ttu-id="17dd9-199">為呼叫者播放的功能表提示不會自動更新。</span><span class="sxs-lookup"><span data-stu-id="17dd9-199">The menu prompt played for callers isn't automatically updated.</span></span>  
>
> <span data-ttu-id="17dd9-200">任何順序都可以新增或移除任何功能表選項，而且鍵對應不一定是連續的。</span><span class="sxs-lookup"><span data-stu-id="17dd9-200">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="17dd9-201">例如，您可以建立一個含有鍵0、1和3的功能表，並對應至選項，而不使用鍵2。</span><span class="sxs-lookup"><span data-stu-id="17dd9-201">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="17dd9-202">按鍵\* （重複）及\# （背面）是由系統所保留，而且無法重新指派。</span><span class="sxs-lookup"><span data-stu-id="17dd9-202">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="17dd9-203">如果已啟用語音辨識功能，按下 \* 將與 "Repeat" 相對應，且 # 會與 "Back" 聲音命令相對應。</span><span class="sxs-lookup"><span data-stu-id="17dd9-203">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="17dd9-204">![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注若要設定功能表選項，請按一下 [ **+ 指派撥號鍵**]，然後輸入下列選項的資訊：</span><span class="sxs-lookup"><span data-stu-id="17dd9-204">![Icon of the number 3, a callout in the previous screenshot](media/teamscallout3.png) To set up a menu option, click on the  **+Assign a dial key** and enter information for the following options:</span></span>

<span data-ttu-id="17dd9-205">![數位4的圖示，在前一個螢幕擷取畫面](media/teamscallout4.png)中的 [語音]**命令**欄中，選項最多可包含64個字元，而且可以包含多個字，例如「客戶服務」或「作業與使用中」。  </span><span class="sxs-lookup"><span data-stu-id="17dd9-205">![Icon of the number 4, a callout in the previous screenshot](media/teamscallout4.png)  **Voice command** column for an option can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="17dd9-206">如果已啟用語音辨識功能，系統會自動辨識名稱，而且呼叫者可以按3、說「三」，或者說「客戶服務」，選取對應至鍵3的選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-206">If speech recognition is enabled, the name is automatically recognized, and the caller is able to press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span> <span data-ttu-id="17dd9-207">此文字也會由針對服務確認提示的文字轉換語音，這可能是「將您的通話轉移到操作員」之類的內容。</span><span class="sxs-lookup"><span data-stu-id="17dd9-207">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to the Operator."</span></span>

<span data-ttu-id="17dd9-208">![數位5的圖示，前一個螢幕擷取畫面](media/teamscallout5.png)中的標注： [**重定向至**] 選項會在您按下對應的按鍵時，或使用語音辨識選取選項時，進行呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="17dd9-208">![Icon of the number 5, a callout in the previous screenshot](media/teamscallout5.png)  The **Redirect to** option sets where the call goes if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="17dd9-209">通話可以傳送至：</span><span class="sxs-lookup"><span data-stu-id="17dd9-209">The call can be sent to:</span></span>

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- <span data-ttu-id="17dd9-210">**運算子**如果已設定操作員，該選項會自動對應到 key 0，但是也可以刪除或重新指派給不同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="17dd9-210">**Operator** If an operator is already set up, the option is automatically mapped to key 0, but can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="17dd9-211">選取此選項的來電者會傳送至指定的操作員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-211">The caller who selects this option is sent to the designated Operator.</span></span> <span data-ttu-id="17dd9-212">如果運算子未設為任何鍵，語音命令 "Operator" 也會停用。</span><span class="sxs-lookup"><span data-stu-id="17dd9-212">If Operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 
- <span data-ttu-id="17dd9-213">**組織中的人員**可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="17dd9-213">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="17dd9-214">使用者必須具備在 Office 365 中啟用企業語音或指派通話方案的電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="17dd9-214">The user must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="17dd9-215">在 [**依名稱搜尋**] 欄位中搜尋人員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-215">Search for the person in the **Search by name** field.</span></span>

  - <span data-ttu-id="17dd9-216">**語音應用程式**選取已設定的自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="17dd9-216">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="17dd9-217">您可以依與應用程式相關聯之資源帳戶的名稱來搜尋自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="17dd9-217">You search for the auto attendant or call queue by the name of the resource account associated with the application.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

<span data-ttu-id="17dd9-218">![數位6的圖示，在此區段的前一個螢幕](media/teamscallout6.png)快照**目錄搜尋**中，您可以啟用 [透過**名稱撥號**]，並以 [撥打自動語音應答的**方式撥號**] 進行撥號。  </span><span class="sxs-lookup"><span data-stu-id="17dd9-218">![Icon of the number 6, a callout in the previous screenshot](media/teamscallout6.png)  **Directory search** In this section, you can enable **Dial by name** and **Dial by Extension** for the auto attendant.</span></span> <span data-ttu-id="17dd9-219">您可以在 [選用的撥號作用域] 頁面中，設定這些服務中和不包含的人員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-219">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="17dd9-220">[目錄搜尋] 預設會設定為 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-220">Directory search is set to **None** by default.</span></span>

<span data-ttu-id="17dd9-221">**依名稱撥號**如果您啟用這個選項，來電者就可以使用 [透過**名稱撥號**] 搜尋貴組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-221">**Dial by name** If you enable this option, callers can search for people in your organization using **Dial by name**.</span></span> <span data-ttu-id="17dd9-222">他們會說出使用者的名稱和語音辨識會與使用者相符。</span><span class="sxs-lookup"><span data-stu-id="17dd9-222">They say the user's name and voice recognition matches them to a user.</span></span> <span data-ttu-id="17dd9-223">您可以在 [選用的撥號作用域] 頁面中，設定這些服務中和不包含的人員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-223">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="17dd9-224">使用電話系統授權的任何線上使用者，或任何使用商務用 Skype Server 主機內部部署的使用者，都是合格的使用者，而且可以使用 [撥號者名稱] 找到。</span><span class="sxs-lookup"><span data-stu-id="17dd9-224">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span>

<span data-ttu-id="17dd9-225">透過**分機撥打電話**如果您啟用此選項，則如果**您已設定使用延伸的撥號方案**，來電者就可以透過您的組織中的使用者來連線。</span><span class="sxs-lookup"><span data-stu-id="17dd9-225">**Dial by extension** If you enable this option, callers can connect with users in your organization by entering their phone extension **provided you have configured a Dial plan that uses extensions**.</span></span> <span data-ttu-id="17dd9-226">您可以在 [選用撥號作用中] 頁面中，選取哪些使用者列為 [可供**撥號**] 或 [無法使用]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-226">You can select which users are listed as available or not available for **Dial by extension** in the optional dial scope page.</span></span> <span data-ttu-id="17dd9-227">使用電話系統授權的任何線上使用者，或任何使用商務用 Skype Server 主機內部部署的使用者，都是符合資格的使用者，而且可透過分機找到。</span><span class="sxs-lookup"><span data-stu-id="17dd9-227">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by extension.</span></span>

> [!NOTE]
> <span data-ttu-id="17dd9-228">如果您想要同時使用 [透過**名稱撥號**]**和 [透過撥號撥打**] 功能，您可以建立主自動語音應答（透過**名稱撥號**），提示來電者選擇功能表選項3（如果他們知道使用者的副檔名），並將 option 3 設定為 [事務]。sfer 電話撥打電話給已啟用 [透過分機撥打電話] 的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="17dd9-228">If you want to use both the **Dial by name** and **Dial by extension** features, you can create  main auto attendant (enabled for **Dial by name**) that prompts callers to choose a menu option 3 if they know the extension of the user, and set option 3 to transfer the call to an auto attendant enabled for Dial by extension.</span></span> 

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

<span data-ttu-id="17dd9-229">當您完成選取專案時，如果您想要變更高級設定，請按一下 **[下一步]** ，如果您想要使用預設設定，請按一下 [**提交**] （例如：</span><span class="sxs-lookup"><span data-stu-id="17dd9-229">When you are finished with your selections, you can click **Next** if you want to change advanced settings, or click **Submit** if you want to use default settings for things like:</span></span>
- <span data-ttu-id="17dd9-230">下班時間的通話流程</span><span class="sxs-lookup"><span data-stu-id="17dd9-230">Call flow for after hours</span></span>
- <span data-ttu-id="17dd9-231">假日的通話流程</span><span class="sxs-lookup"><span data-stu-id="17dd9-231">Call flow for holidays</span></span>
- <span data-ttu-id="17dd9-232">撥號作用中</span><span class="sxs-lookup"><span data-stu-id="17dd9-232">Dial Scope</span></span>
- <span data-ttu-id="17dd9-233">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="17dd9-233">Resource accounts</span></span>

<span data-ttu-id="17dd9-234">由於您必須具備自動語音應答才能擁有資源帳戶，因此您可以選擇繼續至 [**資源帳戶**] 頁面，並關聯您已設定的資源帳戶，或建立資源帳戶並將其與自動關聯在[Microsoft 團隊中的 [管理資源帳戶](manage-resource-accounts.md)] 中所述的 [助理]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-234">Since your auto attendant is required to have a resource account, you have a choice of proceeding to the **Resource account** page and associating a resource account you've already configured, or creating a resource account and associating it to the auto attendant as described in [Manage resource accounts in Microsoft Teams](manage-resource-accounts.md).</span></span> <span data-ttu-id="17dd9-235">您將無法使用此自動語音應答，除非它已與資源帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="17dd9-235">You won't be able to use this auto attendant until it has been associated to a resource account.</span></span> <span data-ttu-id="17dd9-236">若要這樣做，請按一下畫面底部的 **[下一步]** 按鈕，然後按一下左側導覽中的 [**資源帳戶**]，即可直接移至 [資源帳戶] 頁面，並將您的自動助手與資源帳戶建立關聯。</span><span class="sxs-lookup"><span data-stu-id="17dd9-236">to do this, click the **Next** button at the bottom of the screen and then click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="advanced-settings-optional"></a><span data-ttu-id="17dd9-237">[高級設定] （選用）</span><span class="sxs-lookup"><span data-stu-id="17dd9-237">Advanced settings (optional)</span></span>

<span data-ttu-id="17dd9-238">您可以在四個額外的螢幕上設定或保留您選擇的預設值。</span><span class="sxs-lookup"><span data-stu-id="17dd9-238">There are four additional screens that you can configure or leave at defaults as you choose.</span></span>

##### <a name="call-flow-for-after-hours"></a><span data-ttu-id="17dd9-239">下班時間的通話流程</span><span class="sxs-lookup"><span data-stu-id="17dd9-239">Call flow for after hours</span></span>

<span data-ttu-id="17dd9-240">根據預設，自動語音應答的上班時間設定為上午9點，星期一到星期五</span><span class="sxs-lookup"><span data-stu-id="17dd9-240">By default, an auto attendant's business hours are set to 9am-5pm, Monday to Friday</span></span>  <!--24/7--><span data-ttu-id="17dd9-241">，且停用*下班時間之後*的通話流程選項，因為所有的時間都被視為「*上班時間*」。</span><span class="sxs-lookup"><span data-stu-id="17dd9-241">, and the call flow options for *after hours* calls are disabled because all hours are considered *business hours*.</span></span> <span data-ttu-id="17dd9-242">當您選取 [**設定自訂工作時間**] 選項時，[**下班時間之後的通話流程**] 頁面會設定自動回應在下班後所使用的通話處理規則。</span><span class="sxs-lookup"><span data-stu-id="17dd9-242">When you select the **Setup custom business hours** option, the **Call flow for after hours** page configures the call handling rules used by the auto attendant after hours.</span></span> <span data-ttu-id="17dd9-243">可用的選項是相同的，而差異就是為不同的功能表和行為設定排程的能力。</span><span class="sxs-lookup"><span data-stu-id="17dd9-243">The options available are the same, the difference is the ability to set a schedule for different menus and behaviors.</span></span>

<span data-ttu-id="17dd9-244">自動語音應答的系統可能只需要設定第一層自動語音應答的下班時間呼叫處理行為。</span><span class="sxs-lookup"><span data-stu-id="17dd9-244">A system of auto attendants may only need to set after hours call handling behavior for the first-level auto attendant.</span></span> <span data-ttu-id="17dd9-245">嵌套式自動語音應答甚至可能無法由第一層自動語音應答呼叫，但系統可以為它所使用的每個自動語音應答定義時間（以時間為單位）行為。</span><span class="sxs-lookup"><span data-stu-id="17dd9-245">Nested auto attendants may not even be called by the first-level auto attendant, but alternately the system can define after-hours behavior for each auto attendant it uses.</span></span>

<span data-ttu-id="17dd9-246">從最初起，上班時間定義為從 12:00 am 開始，到 12:00 pm，從星期日到星期六結束。</span><span class="sxs-lookup"><span data-stu-id="17dd9-246">Initially, the business hours are defined to start at 12:00 am and end at 12:00 pm, Sunday through Saturday.</span></span> <span data-ttu-id="17dd9-247">在上班時間以外的所有時間，都是*在下班後*。</span><span class="sxs-lookup"><span data-stu-id="17dd9-247">All hours that aren't during business hours are considered *after hours*.</span></span>


![[下班後通話流程] 設定的螢幕擷取畫面](media/aa-afterhour.png)
 * * *

<span data-ttu-id="17dd9-249">![數位1的圖示，在前一個螢幕擷取畫面](media/teamscallout1.png)中，您可以按一下 [**選取 24/7** ]，以完成此自動語音應答的所有上班時間。</span><span class="sxs-lookup"><span data-stu-id="17dd9-249">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) You can click **Select 24/7** to make all hours business hours for this auto attendant.</span></span>

<span data-ttu-id="17dd9-250">![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注選取 [**重設為預設值**] 選項，以還原排程中的所有變更，並傳回 9:00 am 到 5:00 pm 的預設定義（星期一到星期五）。</span><span class="sxs-lookup"><span data-stu-id="17dd9-250">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) Select the **Reset to default** option to revert all changes in the schedule and return to the default definition of business hours as 9:00 am to 5:00 pm Monday to Friday.</span></span>

<span data-ttu-id="17dd9-251">![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注選取 [**清除所有時間**] 來完全清除排程。</span><span class="sxs-lookup"><span data-stu-id="17dd9-251">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) Select **Clear all hours** to completely clear the schedule.</span></span> <span data-ttu-id="17dd9-252">我們不建議您選取此選項並保留未設的時間，因此請只在您想要完全重新執行工作時間時才使用這個選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-252">Selecting this and leaving the hours unset is not recommended, so use this option only if you want to completely redo your business hours.</span></span>

<span data-ttu-id="17dd9-253">![數位4的圖示（編號5的前一個螢幕擷取畫面](media/teamscallout4.png)  ![圖示中的標注），前一個螢幕擷取畫面](media/teamscallout5.png)中的標注可自訂周中某天的開始或結束時間，請按一下您想要重設的 [**開始**] 或 [**結束**] 時間，然後從顯示的清單中選取新的時間。</span><span class="sxs-lookup"><span data-stu-id="17dd9-253">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)  ![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png) To customize start or end time for a day of the week, click on **Start at** or **End at** time you wish to reset and select the new time from the list that appears.</span></span> <span data-ttu-id="17dd9-254">此清單可讓您以15分鐘的間隔來選取 [上班時間]，而您在此選取的上班時間是以您在 [**一般資訊**] 頁面上所設定的時區為基礎。</span><span class="sxs-lookup"><span data-stu-id="17dd9-254">The list allows you to select business hours in 15-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span>

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

<span data-ttu-id="17dd9-255">![數位6的圖示，前一個螢幕擷取畫面](media/teamscallout6.png)中的標注若要設定工間休息（例如午餐），請選取 [新增**時間**]，以建立新的表格列，然後選取 [新的開始] 和 [結束] 時間。</span><span class="sxs-lookup"><span data-stu-id="17dd9-255">![Icon of the number 6,  a callout in the previous screenshot](media/teamscallout6.png)  To set up a break (a lunch break, for example), select **Add new time** for that day of the week to create anew table row, and select new start and end times.</span></span> <span data-ttu-id="17dd9-256">您可以在上班時間內設定多個工間休息。</span><span class="sxs-lookup"><span data-stu-id="17dd9-256">You can set multiple breaks within business hours.</span></span>

<span data-ttu-id="17dd9-257">下班時間之後所提供的[通話流程](#call-flow)選項，與在上班時間期間提供的選項相同。</span><span class="sxs-lookup"><span data-stu-id="17dd9-257">The [Call flow](#call-flow) options available after hours are the same as the options available during business hours.</span></span> <span data-ttu-id="17dd9-258">向下滾動 [資訊輸入] 頁面，設定 [下班後通話流程] 選項。</span><span class="sxs-lookup"><span data-stu-id="17dd9-258">Scroll down on the information entry page to set after hours call flow options.</span></span>

* * *

<span data-ttu-id="17dd9-259">當您完成選取專案時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-259">When you are finished with your selections, click **Next**.</span></span> <span data-ttu-id="17dd9-260">您也可以按一下左側導覽中的 [**資源帳戶**]，直接移至 [資源帳戶] 頁面，並將您的自動語音助理與資源帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="17dd9-260">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

##### <a name="call-flow-during-holidays"></a><span data-ttu-id="17dd9-261">假日期間的通話流程</span><span class="sxs-lookup"><span data-stu-id="17dd9-261">Call flow during holidays</span></span>

<span data-ttu-id="17dd9-262"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-262"></span></span>

<span data-ttu-id="17dd9-263">您最多可以將20個排定的假日新增至每個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="17dd9-263">You can add up to 20 scheduled holidays to each auto attendant.</span></span> <span data-ttu-id="17dd9-264">您的組織可能已經定義了假日，如在[Microsoft 團隊中設定假日](set-up-holidays-in-teams.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="17dd9-264">Your organization may already have defined holidays as described in [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="17dd9-265">如果不是，您會看到下列畫面：</span><span class="sxs-lookup"><span data-stu-id="17dd9-265">If not you will see the following screen:</span></span> 

![螢幕擷取畫面：未設定假日](media/aa-no-holidays.png)

<span data-ttu-id="17dd9-267">![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注，在自動語音應答中設定假日的自訂通話流程，按一下 [ **+** 新增] [查看**新假日通話流程**] 畫面。</span><span class="sxs-lookup"><span data-stu-id="17dd9-267">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To set a custom call flow for a holiday on the auto attendant, click **+ Add** the see the **New holiday call flow** screen.</span></span>
> [!TIP]
> <span data-ttu-id="17dd9-268">若要建立假日，您可以在**組織內設定** > **假日**移至畫面上。</span><span class="sxs-lookup"><span data-stu-id="17dd9-268">To create Holidays you can  go to the screen at **Org-wide settings** > **Holidays**.</span></span>  



![螢幕擷取畫面：新增通話處理常式](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

<span data-ttu-id="17dd9-270">![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注會輸入新通話流程的**名稱**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-270">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png)  Enter a **Name** for your new call flow.</span></span>

<span data-ttu-id="17dd9-271">![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注如果您已建立假日，您會在 [**假日**] 下拉式功能表中看到這些專案，然後加以選取。</span><span class="sxs-lookup"><span data-stu-id="17dd9-271">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you've already created holidays, you'll see them in the **Holiday** pull-down menu and can select them.</span></span> <span data-ttu-id="17dd9-272">您可能會看到一個未使用的選項，您可以在需要的情況中進行編輯。</span><span class="sxs-lookup"><span data-stu-id="17dd9-272">You might see an unused option that you can edit into what you need.</span></span> <span data-ttu-id="17dd9-273">如果不是，請按一下下拉式清單底部的 [**新增**]，以建立新的假日。</span><span class="sxs-lookup"><span data-stu-id="17dd9-273">If not, click on **Add** at the bottom of the pull-down list to create a new Holiday.</span></span>  <span data-ttu-id="17dd9-274">如需建立假日的步驟，請參閱[在 Microsoft 團隊中設定假日](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="17dd9-274">See [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md) for the steps used to create a holiday.</span></span> 

<span data-ttu-id="17dd9-275">假日通話流程名稱最多可以有64個字元，且對於組織而言必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="17dd9-275">A holiday call flow name can be up to 64 characters long and must be unique for the organization.</span></span> <span data-ttu-id="17dd9-276">例如，在同一個組織中，您無法將兩個假期通話流程命名為「感恩節」。</span><span class="sxs-lookup"><span data-stu-id="17dd9-276">For example, you can't have two holiday call flows named "Thanksgiving" in the same organization.</span></span> <span data-ttu-id="17dd9-277">您的自動語音應答可以針對您設定的每個假日進行通話流程，但您可能會想要在自訂的問候語以外的一組常見行為中進行。</span><span class="sxs-lookup"><span data-stu-id="17dd9-277">Your auto attendant can have a call flow for each Holiday you've set up, but you might want to have a common set of behaviors planned other than a customized greeting.</span></span>

<span data-ttu-id="17dd9-278">![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注：假日通話流程的[問候](#call-flow)選項與上班時間內提供的選項相同。</span><span class="sxs-lookup"><span data-stu-id="17dd9-278">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) The [Greetings](#call-flow) options available for a holiday call flow are the same as the options available during business hours.</span></span> <span data-ttu-id="17dd9-279">在播放問候語之後所執行的**動作**也類似，只是在您唯一可用的動作是 **[中斷連線]** 或 [重新**導向**]，以及選擇 [**重定向至**] 選項時，操作員不是其中一個可用的選項.</span><span class="sxs-lookup"><span data-stu-id="17dd9-279">The **Actions** performed after the greeting plays is also similar, except that the only available actions are to **Disconnect** or **Redirect to**, and when choosing the **Redirect to** option the Operator is not one of the available choices.</span></span> <span data-ttu-id="17dd9-280">您無法設定假日流程專用的功能表。</span><span class="sxs-lookup"><span data-stu-id="17dd9-280">You can't set up a menu specific to a Holiday flow.</span></span>

> [!NOTE]
> <span data-ttu-id="17dd9-281">根據預設，在假日期間收到的所有來電都設定為在問候語（如果有的話）之後**中斷**連線，因此，如果您想要自訂行為，您必須指定重新導向。</span><span class="sxs-lookup"><span data-stu-id="17dd9-281">By default, all calls received during a holiday period are set to **Disconnect** after the greeting (if any), so you must specify a redirect if you want a custom behavior.</span></span>

![[假日] 頁面中通話流程的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

<span data-ttu-id="17dd9-283">按一下 [儲存] 以完成假日通話流程的建立。</span><span class="sxs-lookup"><span data-stu-id="17dd9-283">Click on Save to finish creating the Holiday call flow.</span></span> <span data-ttu-id="17dd9-284">在您建立假日通話流程之後，它會顯示在 [假日] 畫面的**通話流程中**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-284">Once you have created a Holiday call flow, it will show up on the **Call Flows during holidays** screen.</span></span>

<span data-ttu-id="17dd9-285">按一下 [設定撥號作用中 **]、[** **返回**]，然後在經過一個小時的通話流程之後進行變更，並在完成後**提交**。</span><span class="sxs-lookup"><span data-stu-id="17dd9-285">Click on **Next** to set Dial scope, **Back** to make changes to after hour call flows, and **Submit** if you are finished.</span></span> <span data-ttu-id="17dd9-286">您也可以按一下左側導覽中的 [**資源帳戶**]，直接移至 [資源帳戶] 頁面，並將您的自動語音助理與資源帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="17dd9-286">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="dial-scope"></a><span data-ttu-id="17dd9-287">撥號作用中</span><span class="sxs-lookup"><span data-stu-id="17dd9-287">Dial scope</span></span>

<span data-ttu-id="17dd9-288"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-288"></span></span>

![顯示 [撥號作用中] 頁面的螢幕擷取畫面](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

<span data-ttu-id="17dd9-290">在此頁面上，您可以設定您的目錄中所列的人員，並在人員呼叫您的組織時可使用 [撥號]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-290">On this page, you can set who is listed in your directory and available for Dial by Name when a person calls your organization.</span></span> <span data-ttu-id="17dd9-291">[依名稱撥號] 預設會在先前的畫面中設為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-291">Dial by name is set to **Off** by default in an earlier screen.</span></span> <span data-ttu-id="17dd9-292">如果您已建立撥號方案，則會在先前選取 [**依副檔名撥號**] 時，才可使用副檔名為的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="17dd9-292">If you have created Dial plans, all users with an extension will be available if **Dial by extension** was selected earlier.</span></span>

<span data-ttu-id="17dd9-293">![數位1的圖示，前面螢幕](media/teamscallout1.png)快照中的標注包括本區段中的選項，**包括\*\*\*\*所有線上使用者**或**自訂使用者群組**</span><span class="sxs-lookup"><span data-stu-id="17dd9-293">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) **Include** The options in this section are either **All online users** or **Custom user groups**</span></span>

<span data-ttu-id="17dd9-294">如果您選取 [**所有線上使用者**]，所有符合資格的使用者都會包含在目錄搜尋中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-294">If you select **All online users**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="17dd9-295">**自訂使用者群組**這個選項可讓您搜尋並選取您組織中已建立的 Office 365 群組、通訊群組清單或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="17dd9-295">**Custom user groups** This option lets you search for and select an Office 365 Group, distribution list, or security group already created in your organization.</span></span> <span data-ttu-id="17dd9-296">如果使用者位於所選的 Office 365 群組、通訊群組清單或安全群組中，而且他們是使用**電話系統授權的線上使用者**，或是使用商務用 Skype Server 主機內部部署的使用者，就會新增到目錄中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-296">Users are added to the directory if they are in the chosen Office 365 Group, distribution list, or security group and they are **Online users with a Phone System license** or hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="17dd9-297">您可以將多個 Office 365 群組、通訊群組清單和安全性群組新增到目錄中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-297">You can add multiple Office 365 Groups, distribution lists, and security groups to the directory.</span></span>

<span data-ttu-id="17dd9-298"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="17dd9-298"></span></span>

<span data-ttu-id="17dd9-299">在此頁面上，您可以設定貴組織中的哪些使用者會列在您的目錄中，並可在撥入您組織的人員時，透過名稱撥號。</span><span class="sxs-lookup"><span data-stu-id="17dd9-299">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

<span data-ttu-id="17dd9-300">![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注會**排除**此區段中的選項，讓您可以從組織的目錄中排除特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="17dd9-300">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Exclude** The options in this section let you exclude specific users or groups of users from the organization's directory.</span></span>

<span data-ttu-id="17dd9-301">如果您選取 [**無**]，所有符合資格的使用者都會包含在目錄搜尋中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-301">If you select **None**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="17dd9-302">**自訂使用者群組**您可以搜尋已在貴組織中建立的 Office 365 群組、通訊群組清單或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="17dd9-302">**Custom user group** You can search for an Office 365 Group, distribution list, or security group that has been created in your organization.</span></span> <span data-ttu-id="17dd9-303">該群組中的使用者會從 [目錄搜尋] 中排除。</span><span class="sxs-lookup"><span data-stu-id="17dd9-303">Users in that group are excluded from directory search.</span></span> <span data-ttu-id="17dd9-304">您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="17dd9-304">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>


<span data-ttu-id="17dd9-305">如果啟用 [依名稱撥號] 時，系統會將設定保留為預設值，則所有符合資格的使用者都會包含在目錄搜尋中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-305">If you leave settings at their default when Dial by Name is enabled, all eligible users are included in directory search.</span></span>

> [!NOTE]
> <span data-ttu-id="17dd9-306">最多可能需要36小時，才能讓新使用者將其名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-306">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span> <span data-ttu-id="17dd9-307">當有人使用 [透過名稱撥打撥號] 語音辨識時，可能無法使用此功能的新帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dd9-307">When someone uses Dial by Name with speech recognition, new accounts may not be available for this feature.</span></span>

<span data-ttu-id="17dd9-308">輸入所有必要的欄位並設定 [呼叫處理] 功能表和選項之後，請按 **[下一步]** 以繼續關聯資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dd9-308">After you enter all the required fields and set up call handling menus and options, click **Next** to proceed to associating a resource account.</span></span>

#### <a name="resource-accounts"></a><span data-ttu-id="17dd9-309">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="17dd9-309">Resource accounts</span></span>

<span data-ttu-id="17dd9-310">所有自動語音應答都必須有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="17dd9-310">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="17dd9-311">第一層自動語音應答絕對必須至少有一個資源帳戶有關聯的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="17dd9-311">First level auto attendants will definitely need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="17dd9-312">如果您想要的話，您可以將多個資源帳戶指派給自動語音應答，每個都有不同的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="17dd9-312">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="17dd9-313">如果您尚未將資源帳戶設定為自動語音應答，您會看到下列畫面：</span><span class="sxs-lookup"><span data-stu-id="17dd9-313">If you haven't already configured a resource account to your auto attendant, you would see the following screen:</span></span> 

![螢幕擷取畫面：選用資源帳戶管理](media/aa-ra-optional.png) 

<span data-ttu-id="17dd9-315">![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注若要將一或多個現有且未分派的資源帳戶新增到自動語音應答，請按一下 [**新增帳戶**]，然後從提供的對話方塊中選取它們。</span><span class="sxs-lookup"><span data-stu-id="17dd9-315">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add one or more existing and unassigned resource accounts to the auto attendant, click **Add accounts** and search and select them from the provided dialogs.</span></span>

![新的 [助理摘要] 視圖的螢幕擷取畫面](media/aa-assigned.png)

<span data-ttu-id="17dd9-317">![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注若要新增額外的資源帳戶，請按一下 [ **+ 新增帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-317">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add an additional resource account, click on **+ Add account**.</span></span>

![數位2的圖示，前一個螢幕擷取畫面中有一個標注](media/teamscallout2.png) <span data-ttu-id="17dd9-319">指派給此自動語音應答的資源帳戶或帳戶會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="17dd9-319">The resource account or accounts assigned to this auto attendant are shown in a list.</span></span>

## <a name="edit-auto-attendants"></a><span data-ttu-id="17dd9-320">編輯自動語音應答</span><span class="sxs-lookup"><span data-stu-id="17dd9-320">Edit auto attendants</span></span>

<span data-ttu-id="17dd9-321">儲存新的自動語音應答之後，它會列在 [**自動**語音應答] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="17dd9-321">After you save your new auto attendant, it is listed on the **Auto attendants** page.</span></span> <span data-ttu-id="17dd9-322">此頁面可讓您快速查看已設定的部分選項，包括名稱、相關聯的資源帳戶、語言及已指派的操作員。</span><span class="sxs-lookup"><span data-stu-id="17dd9-322">That page allows you to quickly see some of the options that you have set up, including the name, associated resource account, language, and assigned Operator.</span></span>

![[助理] 清單的螢幕擷取畫面](media/aa-list.png)

<span data-ttu-id="17dd9-324">如果您想要變更自動助理設定，請選取自動語音應答，然後在 [動作] 窗格中按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="17dd9-324">If you want to change auto attendant settings, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="17dd9-325">使用 Powershell 建立自動助理</span><span class="sxs-lookup"><span data-stu-id="17dd9-325">Create an auto attendant with Powershell</span></span>

<span data-ttu-id="17dd9-326">您也可以使用 PowerShell 來建立及設定自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="17dd9-326">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="17dd9-327">以下是您需要管理自動語音應答的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="17dd9-327">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="17dd9-328">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="17dd9-328">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="17dd9-329">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="17dd9-329">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="17dd9-330">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="17dd9-330">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="17dd9-331">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="17dd9-331">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="17dd9-332">移除-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="17dd9-332">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="17dd9-333">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="17dd9-333">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="17dd9-334">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="17dd9-334">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="17dd9-335">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="17dd9-335">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="17dd9-336">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="17dd9-336">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="17dd9-337">新-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="17dd9-337">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="17dd9-338">新-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="17dd9-338">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="17dd9-339">新-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="17dd9-339">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="17dd9-340">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="17dd9-340">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="17dd9-341">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="17dd9-341">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="17dd9-342">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="17dd9-342">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="17dd9-343">匯入-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="17dd9-343">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="17dd9-344">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="17dd9-344">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="17dd9-345">深入瞭解 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17dd9-345">More about Windows PowerShell</span></span>

- <span data-ttu-id="17dd9-346">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="17dd9-346">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="17dd9-347">在 Windows PowerShell 中，您可以從單一管理點管理 Office 365 和 Microsoft 團隊，以簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="17dd9-347">With Windows PowerShell, you can manage Office 365 and Microsoft Teams from a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="17dd9-348">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="17dd9-348">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="17dd9-349">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="17dd9-349">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="17dd9-350">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="17dd9-350">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="17dd9-351">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如一次為多個使用者進行設定變更。</span><span class="sxs-lookup"><span data-stu-id="17dd9-351">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as making setting changes for many users at once.</span></span> <span data-ttu-id="17dd9-352">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="17dd9-352">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="17dd9-353">使用 Office 365 PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="17dd9-353">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="17dd9-354">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="17dd9-354">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="17dd9-355">相關主題</span><span class="sxs-lookup"><span data-stu-id="17dd9-355">Related topics</span></span>

[<span data-ttu-id="17dd9-356">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="17dd9-356">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="17dd9-357">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="17dd9-357">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="17dd9-358">適用于音訊會議與通話方案的國家和地區可用性</span><span class="sxs-lookup"><span data-stu-id="17dd9-358">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="17dd9-359">新-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="17dd9-359">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="17dd9-360">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="17dd9-360">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="17dd9-361">小型企業範例-設定自動助手</span><span class="sxs-lookup"><span data-stu-id="17dd9-361">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
