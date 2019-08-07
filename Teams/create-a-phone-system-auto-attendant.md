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
ms.openlocfilehash: 939d1ac17007e3d823b0588f9949330e24555449
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36185004"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="6ae98-103">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="6ae98-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="6ae98-104">自動語音應答讓撥入您組織的人員, 並流覽功能表系統, 以取得正確的部門、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="6ae98-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="6ae98-105">您可以使用 Microsoft 團隊系統管理中心, 為您的組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="6ae98-106">若要建立新的自動語音應答, 請移至左側導覽中的 [**語音**], 然後選取 [**自動助理** > **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="6ae98-107">如果您想要深入瞭解自動語音應答, 請參閱[什麼是雲端自動](/microsoftteams/what-are-phone-system-auto-attendants)語音應答？</span><span class="sxs-lookup"><span data-stu-id="6ae98-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="6ae98-108">本文適用于 Microsoft 團隊和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="6ae98-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="6ae98-109">步驟 1-快速入門</span><span class="sxs-lookup"><span data-stu-id="6ae98-109">Step 1 - Get started</span></span>

- <span data-ttu-id="6ae98-110">必須有一個自動語音應答, 才能擁有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ae98-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="6ae98-111">如需資源帳戶及所有所需授權的詳細資料, 請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="6ae98-112">若要將來電重新導向給以**電話系統**授權為線上使用者的操作員或功能表選項, 您必須啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="6ae98-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="6ae98-113">請參閱[指派商務用 Skype 授權](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="6ae98-114">您也可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6ae98-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="6ae98-115">例如, 執行:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="6ae98-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="6ae98-116">步驟 2-建立新的自動語音應答</span><span class="sxs-lookup"><span data-stu-id="6ae98-116">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ae98-117">每個自動語音應答都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="6ae98-118">您必須先建立資源帳戶, 然後才能將它與自動語音應答建立關聯。</span><span class="sxs-lookup"><span data-stu-id="6ae98-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6ae98-119">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6ae98-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6ae98-120">在**Microsoft [團隊管理中心**] 中, 按一下 [**語音** > **自動**語音應答], 然後按一下 [ **+ 新增**]:</span><span class="sxs-lookup"><span data-stu-id="6ae98-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="6ae98-121">一般資訊頁面</span><span class="sxs-lookup"><span data-stu-id="6ae98-121">General info page</span></span>

![[我的自動助理] 頁面的螢幕擷取畫面](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="6ae98-124">**名稱**輸入您自動語音應答的描述性顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="6ae98-125">名稱是必要的, 而且最多可以包含64個字元, 包括空格。</span><span class="sxs-lookup"><span data-stu-id="6ae98-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="6ae98-126">它會列于 [**自動**語音應答] 索引標籤上的 [**名稱**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-126">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="6ae98-128">**資源帳戶**按一下此按鈕以選取一或多個資源帳戶以連線到您的新自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-128">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="6ae98-129">必須有所有自動語音應答, 才能擁有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ae98-129">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="6ae98-130">資源帳戶可以有一個與該帳戶相關聯的電話號碼, 但可能不會。</span><span class="sxs-lookup"><span data-stu-id="6ae98-130">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="6ae98-131">最上層的自動語音應答通常會有一個已指派電話號碼的資源帳戶, 但嵌套的自動語音應答 (用來做為第一個層級自動助理所連接到的層級) 可能沒有指派電話號碼給其資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ae98-131">A top-level auto attendant usually have a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

<span data-ttu-id="6ae98-133">**時區**您必須為自動語音應答設定時區, 但不需要對應給您組織的主要位址時區。</span><span class="sxs-lookup"><span data-stu-id="6ae98-133">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="6ae98-134">每個自動語音應答都可以有不同的時區, 而且會根據您在此處選取的時區, 設定自動語音應答的上班時間設定。</span><span class="sxs-lookup"><span data-stu-id="6ae98-134">Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="6ae98-136">**語言**從列出的任何可用語言中, 選取您要用於自動語音應答的語言。</span><span class="sxs-lookup"><span data-stu-id="6ae98-136">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="6ae98-137">您在這裡設定的語言是自動語音應答將用來與呼叫此自動語音應答的人員互動的語言, 且系統會以這種語言來播放所有系統提示。</span><span class="sxs-lookup"><span data-stu-id="6ae98-137">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位5圖示](media/sfbcallout5.png)

<span data-ttu-id="6ae98-139">**運算子**這是選擇性的, 不需要針對自動語音應答進行設定。</span><span class="sxs-lookup"><span data-stu-id="6ae98-139">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="6ae98-140">不過, 您可以為撥入的人員設定 [**操作員**] 選項, 讓他們可以中斷功能表以協助他們。</span><span class="sxs-lookup"><span data-stu-id="6ae98-140">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="6ae98-141">會自動將鍵0指派給接線員。</span><span class="sxs-lookup"><span data-stu-id="6ae98-141">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="6ae98-142">如果您已設定這個選項, 您也需要告訴在 [**商務時間通話處理**] 頁面上的 [編輯]**功能表選項**中, 這是一個可用的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae98-142">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="6ae98-143">如果您在自動語音應答上設定操作員, 您必須在 [**呼叫者會聽到**] 方塊中輸入對應的提示文字, 或將您的音訊檔案改為包含此選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-143">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="6ae98-144">例如, "For 運算子, 請按零。</span><span class="sxs-lookup"><span data-stu-id="6ae98-144">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="6ae98-145">您可以將下列其中一個做為運算子:</span><span class="sxs-lookup"><span data-stu-id="6ae98-145">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="6ae98-146">**貴公司中的人員**, 在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。</span><span class="sxs-lookup"><span data-stu-id="6ae98-146">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="6ae98-147">**貴公司中的人員**可以是線上使用者, 或使用商務用 Skype server 2015 或 Lync server 2013 主機內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae98-147">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="6ae98-148">您已設定的**通話佇列**。</span><span class="sxs-lookup"><span data-stu-id="6ae98-148">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="6ae98-149">您可以設定它, 讓呼叫者會傳送至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-149">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="6ae98-150">若要這樣做, 請選取**貴公司中的人員**, 並將此人的來電設定為直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-150">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位6圖示](media/sfbcallout6.png)

<span data-ttu-id="6ae98-152">**啟用語音輸入**如果選取此選項, 就可以使用語音辨識。</span><span class="sxs-lookup"><span data-stu-id="6ae98-152">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="6ae98-153">通話中的人員可以使用[您所設定之語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的語音輸入。</span><span class="sxs-lookup"><span data-stu-id="6ae98-153">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="6ae98-154">如果您只想讓使用者使用電話鍵台, 您可以停用語音辨識, 只要將它設為 [關閉] 即可。</span><span class="sxs-lookup"><span data-stu-id="6ae98-154">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="6ae98-155">當您完成選取專案時, 請按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ae98-155">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="6ae98-156">[上班時間] 頁面</span><span class="sxs-lookup"><span data-stu-id="6ae98-156">Business hours page</span></span>

<span data-ttu-id="6ae98-157">根據預設, 從星期一到星期五, 上班時間設定為上午9點到下午。</span><span class="sxs-lookup"><span data-stu-id="6ae98-157">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="6ae98-158">在上班時間之後, 不會考慮上班時間所包含的所有時間。</span><span class="sxs-lookup"><span data-stu-id="6ae98-158">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="6ae98-159">您可以按一下 [**選取 24/7** ], 以完成所有的上班時間。</span><span class="sxs-lookup"><span data-stu-id="6ae98-159">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="6ae98-160">除非您選取 [**選取 24/7** ] 選項, 否則將會使用 [**下班後通話設定**] 頁面來設定自動語音應答在商務時間之後的通話處理。</span><span class="sxs-lookup"><span data-stu-id="6ae98-160">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![[上班時間] 頁面的螢幕擷取畫面](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="6ae98-163">根據預設, 上班時間設定為週一至週五, 即 9:00 am-5:00 pm。</span><span class="sxs-lookup"><span data-stu-id="6ae98-163">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="6ae98-164">選取 [**清除所有時間**] 選項, 以取消選取排程中的所有小時數。</span><span class="sxs-lookup"><span data-stu-id="6ae98-164">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="6ae98-165">當您選取 [**重設為預設值**] 時, 系統會將 [上班時間] 重設為 [週一至週五], 即 9:00 am-5:00 pm</span><span class="sxs-lookup"><span data-stu-id="6ae98-165">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="6ae98-167">若要變更上班時間, 請將您要使用行事曆設定的上班時間醒目提示。</span><span class="sxs-lookup"><span data-stu-id="6ae98-167">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="6ae98-168">行事曆可讓您以30分鐘的間隔來選取上班時間, 您在此選取的上班時間將根據您在 [**一般資訊**] 頁面上設定的時區進行設定。</span><span class="sxs-lookup"><span data-stu-id="6ae98-168">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="6ae98-169">若要設定工間休息 (例如午餐), 請取消選取或拖曳以取消選取行事曆上的時間。</span><span class="sxs-lookup"><span data-stu-id="6ae98-169">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="6ae98-170">您可以在上班時間內設定多個工間休息。</span><span class="sxs-lookup"><span data-stu-id="6ae98-170">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="6ae98-171">當您完成選取專案時, 請按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ae98-171">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="6ae98-172">商務時間通話設定</span><span class="sxs-lookup"><span data-stu-id="6ae98-172">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="6ae98-173">如果您使用自訂的上班時間排程, 您也必須在上班時間之後, 使用 [**下班後通話處理**] 頁面來設定通話處理, 這會提供與 [**商務時間通話] 設定**相同的選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-173">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="6ae98-174">您可以設定在商務時間內, 來電給組織自動語音應答電話號碼之人的問候、提示及功能表。</span><span class="sxs-lookup"><span data-stu-id="6ae98-174">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="6ae98-175">![[上班時間通話處理] 頁面問候區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![螢幕擷取畫面顯示 [上班時間通話處理] 頁面動作區段的螢幕擷取畫面](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="6ae98-175">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="6ae98-177">**問候語**商務時間問候語是選擇性的, 而且可以設定為 [**無問候語**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-177">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="6ae98-178">在這種情況下, 在您選取的其中一個動作處理呼叫前, 來電者將不會聽到任何訊息或問候語。</span><span class="sxs-lookup"><span data-stu-id="6ae98-178">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="6ae98-179">您也可以上傳音訊檔案 (.wav、mp3 或 .wma 格式), 或使用文字轉換語音來建立自訂問候語。</span><span class="sxs-lookup"><span data-stu-id="6ae98-179">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="6ae98-180">**沒有問候語**在人員撥入自動語音應答電話號碼時, 不會播放任何問候語。</span><span class="sxs-lookup"><span data-stu-id="6ae98-180">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="6ae98-181">**上傳音訊**檔案如果您選擇此選項, 請錄製問候語, 然後上傳音訊檔案 (以 .wav、mp3 或 .wma 格式)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-181">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="6ae98-182">**輸入問候訊息**如果您選擇此選項, 請輸入您想要系統讀取的文字 (最多1000個字元)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-182">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="6ae98-183">例如, 您可以輸入「歡迎使用 Contoso。</span><span class="sxs-lookup"><span data-stu-id="6ae98-183">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="6ae98-184">您的通話對我們很重要。」</span><span class="sxs-lookup"><span data-stu-id="6ae98-184">Your call is important to us."</span></span> <span data-ttu-id="6ae98-185">在 [**呼叫者將會聽到**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-185">in the **Callers will hear** box.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="6ae98-187">您可以選取在上班時間內到貨的通話情況。</span><span class="sxs-lookup"><span data-stu-id="6ae98-187">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="6ae98-188">您可以從下列動作中選擇:</span><span class="sxs-lookup"><span data-stu-id="6ae98-188">You can chose from the following actions:</span></span>

- <span data-ttu-id="6ae98-189">**中斷**連線如果您選取它, 在聽到上班時間的問候之後, 通話中的人員將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="6ae98-189">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="6ae98-190">重新**導向通話**這可以用來將來電自動傳送至:</span><span class="sxs-lookup"><span data-stu-id="6ae98-190">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="6ae98-191">**公司中的人員**, 在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。</span><span class="sxs-lookup"><span data-stu-id="6ae98-191">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="6ae98-192">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-192">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="6ae98-193">若要這樣做, 請選取 [**公司中的人員**], 並將 [此人] 設為 [將來電直接轉寄給語音信箱]</span><span class="sxs-lookup"><span data-stu-id="6ae98-193">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="6ae98-194">**公司中的人員**可以是線上使用者, 或者是使用商務用 Skype server 2015 或 Lync server 2013 的使用者託管內部部署。</span><span class="sxs-lookup"><span data-stu-id="6ae98-194">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="6ae98-195">其他**自動助理**</span><span class="sxs-lookup"><span data-stu-id="6ae98-195">Another **Auto attendant**</span></span>

   <span data-ttu-id="6ae98-196">您可以使用現有的自動助手來建立包含子功能表的第二層功能表選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-196">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="6ae98-197">這些稱為嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-197">These are called nested auto attendants.</span></span> <span data-ttu-id="6ae98-198">若要將呼叫傳送至嵌套的自動語音應答, 請選取 [**公司] 中**的 [人員] 並指派已有關聯自動語音應答的人員, 或在建立完此自動語音應答之後, 就會與自動語音助理建立關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ae98-198">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="6ae98-199">您也可以使用 [**播放] 功能表選項**, 讓您設定您想要播放的提示。</span><span class="sxs-lookup"><span data-stu-id="6ae98-199">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

<span data-ttu-id="6ae98-201">**功能表提示**若要建立主功能表提示, 您可以使用文字轉換語音或上傳音訊檔案 (.wav、mp3 或 .wma)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-201">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="6ae98-202">您可以在 [**設定您的呼叫者的功能表流覽**] 方塊中輸入提示, 或錄製音訊檔案, 例如: 「銷售」, 比如說或按下或說出1。</span><span class="sxs-lookup"><span data-stu-id="6ae98-202">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="6ae98-203">針對 [服務], 請按或說出 [2]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-203">For Services, press or say 2.</span></span> <span data-ttu-id="6ae98-204">如需客戶支援, 請按或說出3。</span><span class="sxs-lookup"><span data-stu-id="6ae98-204">For Customer Support, press or say 3.</span></span> <span data-ttu-id="6ae98-205">針對運算子, 請按或說出 [0]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-205">For the operator, press or say 0.</span></span> <span data-ttu-id="6ae98-206">若要再次聆聽此功能表, 請按星號鍵或說 [重複]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-206">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="6ae98-207">**輸入問候訊息**如果您選擇這個選項, 就應該輸入您想要系統讀取的文字 (最多1000個字元)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-207">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="6ae98-208">**上傳音訊**檔案如果您選擇此選項, 您將需要錄製問候語, 然後上傳音訊檔案 (以 .wav、mp3 或 .wma 格式)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-208">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="6ae98-210">**功能表選項設定**您可以新增或移除鍵盤上使用按鍵按鈕的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-210">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="6ae98-211">若要新增功能表選項, 請按 **+ 指派撥號鍵**。</span><span class="sxs-lookup"><span data-stu-id="6ae98-211">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="6ae98-212">對應列的選項會顯示在下方。</span><span class="sxs-lookup"><span data-stu-id="6ae98-212">A corresponding row of options will appear below.</span></span> <span data-ttu-id="6ae98-213">若要刪除功能表選項, 只需按一下 [小鍵盤] 控制項上對應鍵的左側, 然後按一下上方的 [刪除] 圖示。</span><span class="sxs-lookup"><span data-stu-id="6ae98-213">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="6ae98-214">將會移除 [鍵對應] 列。</span><span class="sxs-lookup"><span data-stu-id="6ae98-214">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="6ae98-215">在新增至移除選項時, 您必須更新功能表提示文字, 或重新錄製音訊, 因為現有的功能表提示不會自動完成。</span><span class="sxs-lookup"><span data-stu-id="6ae98-215">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="6ae98-216">任何順序都可以新增或移除任何功能表選項, 而且鍵對應不一定是連續的。</span><span class="sxs-lookup"><span data-stu-id="6ae98-216">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="6ae98-217">例如, 您可以建立一個含有鍵0、1和3的功能表, 並對應至選項, 而不使用鍵2。</span><span class="sxs-lookup"><span data-stu-id="6ae98-217">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="6ae98-218">按鍵\* (重複) 及\# (背面) 是由系統所保留, 而且無法重新指派。</span><span class="sxs-lookup"><span data-stu-id="6ae98-218">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="6ae98-219">如果已啟用語音辨識功能, 按下 \* 將與 "Repeat" 相對應, 且 # 會與 "Back" 聲音命令相對應。</span><span class="sxs-lookup"><span data-stu-id="6ae98-219">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="6ae98-220">若要設定功能表選項, 請在選取撥號鍵之後, 您必須:</span><span class="sxs-lookup"><span data-stu-id="6ae98-220">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="6ae98-221">輸入選項的 [**語音] 命令**。</span><span class="sxs-lookup"><span data-stu-id="6ae98-221">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="6ae98-222">最多可包含64個字元, 而且可以包含多個字, 例如「客戶服務」或「作業與使用中」。</span><span class="sxs-lookup"><span data-stu-id="6ae98-222">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="6ae98-223">如果已啟用語音辨識功能, 就會自動辨識名稱, 而撥入的人員就可以按 3, 說出「三」, 或者說「客戶服務」, 選取對應至鍵3的選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-223">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="6ae98-224">如果按下對應的按鍵, 或使用語音辨識來選取此選項, 請選取要傳送通話的位置。</span><span class="sxs-lookup"><span data-stu-id="6ae98-224">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="6ae98-225">通話可以傳送至:</span><span class="sxs-lookup"><span data-stu-id="6ae98-225">The call can be sent to:</span></span>

  - <span data-ttu-id="6ae98-226">**運算子**如果已設定運算子, 就會自動對應到 key 0, 但是也可以將它刪除或重新指派給不同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="6ae98-226">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="6ae98-227">如果運算子未設為任何鍵, 語音命令 "Operator" 也將停用。</span><span class="sxs-lookup"><span data-stu-id="6ae98-227">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="6ae98-228">**貴公司中的人員**, 在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。</span><span class="sxs-lookup"><span data-stu-id="6ae98-228">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="6ae98-229">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-229">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="6ae98-230">若要這樣做, 請選取**貴公司中的人員**, 並將其來電設定為直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-230">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="6ae98-231">**貴公司中的人員**可以是線上使用者, 或使用商務用 Skype Server 或 Lync server 2013 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae98-231">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>
    - <span data-ttu-id="6ae98-232">其他**自動助理**</span><span class="sxs-lookup"><span data-stu-id="6ae98-232">Another **Auto attendant**</span></span>

       <span data-ttu-id="6ae98-233">您可以使用現有的自動助手來建立包含子功能表的第二層功能表選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-233">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="6ae98-234">這些稱為嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-234">These are called nested auto attendants.</span></span> <span data-ttu-id="6ae98-235">若要將呼叫傳送至嵌套的自動語音應答, 請選取 [**公司] 中**的 [人員] 並指派已有關聯自動語音應答的人員, 或在建立完此自動語音應答之後, 就會與自動語音助理建立關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ae98-235">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="6ae98-236">也會使用嵌套 (或第二層) 自動語音應答的**商務時間**, 包括從其他已設定的自動語音應答所傳送的通話。</span><span class="sxs-lookup"><span data-stu-id="6ae98-236">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

     - <span data-ttu-id="6ae98-237">**通話佇列**使用 [通話佇列] 選項可將來電轉接到您已設定的現有通話佇列。</span><span class="sxs-lookup"><span data-stu-id="6ae98-237">**call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up.</span></span> 

* * *

![在前一個螢幕擷取畫面中參照標注的數位5圖示](media/sfbcallout5.png)

<span data-ttu-id="6ae98-239">**依名稱撥號**如果您選擇這個選項, 這會讓打電話給您的人員使用 [目錄搜尋] 搜尋貴組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="6ae98-239">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="6ae98-240">您可以在 [**撥號作用**中] 頁面上設定這些選項, 以選取哪些人員將被列為 [可用] 或 [無法供撥號使用]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-240">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="6ae98-241">使用**電話系統**授權的任何線上使用者, 或任何使用商務用 Skype Server 或 Lync server 2013 的使用者, 都可以透過名稱來找到。</span><span class="sxs-lookup"><span data-stu-id="6ae98-241">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="6ae98-242">當您完成選取專案時, 請按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ae98-242">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="6ae98-243">假日通話設定</span><span class="sxs-lookup"><span data-stu-id="6ae98-243">Holiday call settings</span></span>

<span data-ttu-id="6ae98-244">您最多可以將20個排定的假日新增至每個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-244">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="6ae98-245">您可以在**組織內設定** > **假日**移至畫面來建立假日, 或者您可以建立新的呼叫處理常式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6ae98-245">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![[假日通話設定] 頁面的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="6ae98-248">如果您已經建立其他自動語音應答, 您可能會看到一個選項, 您可以在此清單中使用或編輯您需要的專案。</span><span class="sxs-lookup"><span data-stu-id="6ae98-248">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="6ae98-249">如果不是, 您將需要建立新的呼叫處理常式。</span><span class="sxs-lookup"><span data-stu-id="6ae98-249">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="6ae98-250">若要新增呼叫處理常式, 請按一下 [ **+ 新呼叫處理常式**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-250">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![顯示新增呼叫處理常式的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="6ae98-253">在新視窗中, 在畫面頂端輸入新呼叫處理常式的名稱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-253">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="6ae98-255">如果您的假日名稱已存在於 [**假日**] 下拉式清單中, 您可以使用它。</span><span class="sxs-lookup"><span data-stu-id="6ae98-255">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="6ae98-256">如果您所需的假日名稱還不存在, 請在下拉式清單中選取 [**建立新假日**], 然後在出現的新畫面中指定新假日的名稱和日期。</span><span class="sxs-lookup"><span data-stu-id="6ae98-256">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="6ae98-257">準備就緒時, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-257">Click on **Save** when ready.</span></span>

<span data-ttu-id="6ae98-258">假日名稱最多可包含64個字元, 且對於相同的自動語音應答必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6ae98-258">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="6ae98-259">例如, 在同一個自動語音應答中, 您不能使用兩個名為 "感恩節" 的假日。</span><span class="sxs-lookup"><span data-stu-id="6ae98-259">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

<span data-ttu-id="6ae98-261">**問候語**問候語是選擇性的, 而且可以設定為 [**無問候語**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-261">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="6ae98-262">在這種情況下, 在您選取的其中一個選項處理呼叫前, 來電者將不會聽到任何訊息或問候語。</span><span class="sxs-lookup"><span data-stu-id="6ae98-262">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="6ae98-263">您也可以上傳音訊檔案 (.wav、mp3 或 .wma 格式), 或使用文字轉換語音來建立自訂問候語。</span><span class="sxs-lookup"><span data-stu-id="6ae98-263">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="6ae98-264">**沒有問候語**在人員撥入自動語音應答電話號碼時, 不會播放任何問候語。</span><span class="sxs-lookup"><span data-stu-id="6ae98-264">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="6ae98-265">**上傳音訊**檔案如果您選擇此選項, 請錄製假日問候語, 然後上傳音訊檔案 (以 .wav、mp3 或 .wma 格式)</span><span class="sxs-lookup"><span data-stu-id="6ae98-265">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="6ae98-266">**輸入問候訊息**如果您選擇此選項, 請輸入您想要系統讀取的文字 (最多1000個字元)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-266">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="6ae98-267">例如, 您可以輸入「新年快樂!</span><span class="sxs-lookup"><span data-stu-id="6ae98-267">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="6ae98-268">我們的辦公室目前已關閉。」</span><span class="sxs-lookup"><span data-stu-id="6ae98-268">Our offices are currently closed."</span></span> <span data-ttu-id="6ae98-269">在 [**輸入問候訊息**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-269">in the **Type a greeting message** box.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="6ae98-271">**動作**您可以選取在此假日期間到達的通話情況。</span><span class="sxs-lookup"><span data-stu-id="6ae98-271">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="6ae98-272">您可以從下列選項中選擇:</span><span class="sxs-lookup"><span data-stu-id="6ae98-272">You can chose from the following options:</span></span>

- <span data-ttu-id="6ae98-273">**中斷**連線在聽到假日問候語之後撥入的人員將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="6ae98-273">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="6ae98-274">重新**導向通話**這可以用來將來電自動傳送至:</span><span class="sxs-lookup"><span data-stu-id="6ae98-274">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="6ae98-275">**貴公司中**擁有在 Office 365 中啟用企業語音或指派通話方案的**電話系統**授權的人員。</span><span class="sxs-lookup"><span data-stu-id="6ae98-275">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="6ae98-276">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-276">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="6ae98-277">若要這樣做, 請選取**貴公司中的人員**, 並將此人設定為讓其呼叫直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6ae98-277">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="6ae98-278">**貴公司中的人員**可以是線上使用者, 或使用商務用 Skype server 2015 或 Lync server 2013 主機內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae98-278">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

  - <span data-ttu-id="6ae98-279">[**通話佇列**] 可將來電轉接到您已設定的現有通話佇列。</span><span class="sxs-lookup"><span data-stu-id="6ae98-279">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="6ae98-280">另一個**自動**語音應答, 可建立包含子功能表的第二層功能表選項。</span><span class="sxs-lookup"><span data-stu-id="6ae98-280">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="6ae98-281">這些稱為嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-281">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="6ae98-282">根據預設, 假期期間內的所有來電都會設定為在問候語 (如果有的話) 之後中斷連線, 因此您必須指定重新導向 (如果有其他行為的話)。</span><span class="sxs-lookup"><span data-stu-id="6ae98-282">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="6ae98-283">選取 [撥號作用域] 頁面</span><span class="sxs-lookup"><span data-stu-id="6ae98-283">Select dial scope page</span></span>

<span data-ttu-id="6ae98-284">在此頁面上, 您可以設定貴組織中的哪些使用者會列在您的目錄中, 並可在撥入您組織的人員時, 透過名稱撥號。</span><span class="sxs-lookup"><span data-stu-id="6ae98-284">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![顯示 [撥號作用中] 頁面的螢幕擷取畫面](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="6ae98-286">![數位1的圖示, 參照前一個螢幕擷取畫面](media/sfbcallout1.png)中的標注使用 [**包括**] 選項, 您有兩個選項:</span><span class="sxs-lookup"><span data-stu-id="6ae98-286">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="6ae98-287">**所有的線上使用者**使用這個選項可讓您組織中的所有人員都包含在目錄搜尋中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-287">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="6ae98-288">所有具備**電話系統**授權的線上使用者, 以及使用商務用 Skype Server 或 Lync 2013 server (在 Office 365 中有通話方案) 的使用者主機內部部署的使用者, 都會列在其中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-288">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="6ae98-289">**自訂使用者群組**如果您使用這個選項, 您可以搜尋已在您的組織中建立的 Office 365 群組、通訊群組清單或安全性群組, 以及新增至此 Office 365 群組、通訊群組清單或安全性群組的人員, 這些人必須**具備**使用商務用 Skype server 2015 或 Lync server 2013 的電話系統授權或主機內部部署。</span><span class="sxs-lookup"><span data-stu-id="6ae98-289">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="6ae98-290">您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="6ae98-290">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="6ae98-292">使用 [**排除**] 選項, 您有兩個選項:</span><span class="sxs-lookup"><span data-stu-id="6ae98-292">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="6ae98-293">**None**使用這個選項, 即表示不會從目錄搜尋中排除任何線上使用者。</span><span class="sxs-lookup"><span data-stu-id="6ae98-293">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="6ae98-294">**自訂使用者群組**如果您使用這個選項, 您可以搜尋已在貴組織中建立的 Office 365 群組、通訊群組清單或安全性群組, 而且所有新增至此 Office 365 群組、通訊群組清單或安全性群組的人員將會從目錄搜尋中排除。</span><span class="sxs-lookup"><span data-stu-id="6ae98-294">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="6ae98-295">您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="6ae98-295">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="6ae98-296">當有人透過語音辨識以名稱使用撥號時, 最多可能需要36小時才能讓新的使用者將其名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-296">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="6ae98-297">輸入所有必要的欄位並設定 [通話處理] 功能表和選項之後, 請按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-297">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="6ae98-298">編輯及測試自動語音應答</span><span class="sxs-lookup"><span data-stu-id="6ae98-298">Editing and testing auto attendants</span></span>

<span data-ttu-id="6ae98-299">在您儲存了自動語音應答之後, 它會列在 [**自動**語音應答] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="6ae98-299">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="6ae98-300">這可讓您快速查看一些已設定的選項, 包括姓名、電話號碼、語言和狀態。</span><span class="sxs-lookup"><span data-stu-id="6ae98-300">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="6ae98-301">如果您想要變更自動語音應答, 請選取 [自動語音應答], 然後在 [動作] 窗格中按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6ae98-301">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="6ae98-302">您也可以使用 [動作] 窗格中的 [**測試**] 按鈕, 快速地將測試呼叫放到您的自動語音應答中。</span><span class="sxs-lookup"><span data-stu-id="6ae98-302">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="6ae98-303">自動語音應答 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6ae98-303">Auto attendant cmdlets</span></span>

<span data-ttu-id="6ae98-304">您也可以使用 Windows PowerShell 來建立及設定自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="6ae98-304">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="6ae98-305">以下是您需要管理自動語音應答的 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6ae98-305">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="6ae98-306">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ae98-306">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="6ae98-307">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ae98-307">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="6ae98-308">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ae98-308">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="6ae98-309">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="6ae98-309">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="6ae98-310">移除-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ae98-310">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="6ae98-311">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="6ae98-311">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="6ae98-312">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="6ae98-312">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="6ae98-313">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="6ae98-313">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="6ae98-314">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="6ae98-314">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="6ae98-315">新-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="6ae98-315">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="6ae98-316">新-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="6ae98-316">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="6ae98-317">新-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="6ae98-317">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="6ae98-318">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="6ae98-318">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="6ae98-319">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="6ae98-319">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="6ae98-320">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="6ae98-320">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="6ae98-321">匯入-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="6ae98-321">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="6ae98-322">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="6ae98-322">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="6ae98-323">深入瞭解 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ae98-323">More about Windows PowerShell</span></span>

- <span data-ttu-id="6ae98-324">Windows PowerShell 全部說明如何管理使用者, 以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="6ae98-324">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6ae98-325">在 Windows PowerShell 中, 您可以使用單一管理點管理 Office 365 和 Microsoft 團隊, 當您有多個工作需要執行時, 可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="6ae98-325">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6ae98-326">若要開始使用 Windows PowerShell, 請參閱以下主題:</span><span class="sxs-lookup"><span data-stu-id="6ae98-326">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6ae98-327">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="6ae98-327">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="6ae98-328">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ae98-328">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="6ae98-329">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點, 只是使用 Microsoft 365 系統管理中心, 例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="6ae98-329">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6ae98-330">請參閱下列主題, 瞭解這些優點:</span><span class="sxs-lookup"><span data-stu-id="6ae98-330">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="6ae98-331">使用 Office 365 PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="6ae98-331">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="6ae98-332">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6ae98-332">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="6ae98-333">相關主題</span><span class="sxs-lookup"><span data-stu-id="6ae98-333">Related topics</span></span>

[<span data-ttu-id="6ae98-334">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="6ae98-334">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="6ae98-335">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="6ae98-335">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="6ae98-336">適用于音訊會議與通話方案的國家和地區可用性</span><span class="sxs-lookup"><span data-stu-id="6ae98-336">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="6ae98-337">新-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="6ae98-337">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="6ae98-338">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="6ae98-338">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="6ae98-339">小型企業範例-設定自動助手</span><span class="sxs-lookup"><span data-stu-id="6ae98-339">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
