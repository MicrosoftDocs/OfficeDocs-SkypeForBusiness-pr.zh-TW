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
ms.openlocfilehash: 6ac4ccea48e70a8bba5e11511379fef5c5a2a861
ms.sourcegitcommit: e89c2234fc5aa8f7eeef66ba1ae093a0f7beda85
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2019
ms.locfileid: "37349246"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="2a7ee-103">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="2a7ee-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="2a7ee-104">自動語音應答讓撥入您組織的人員，並流覽功能表系統，以取得正確的部門、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="2a7ee-105">您可以使用 Microsoft 團隊系統管理中心，為您的組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="2a7ee-106">若要建立新的自動語音應答，請移至左側導覽中的 [**語音**]，然後選取 [**自動助理** > **新增**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="2a7ee-107">如果您想要深入瞭解自動語音應答，請參閱[什麼是雲端自動](/microsoftteams/what-are-phone-system-auto-attendants)語音應答？</span><span class="sxs-lookup"><span data-stu-id="2a7ee-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="2a7ee-108">本文適用于 Microsoft 團隊和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="2a7ee-109">步驟1：快速入門</span><span class="sxs-lookup"><span data-stu-id="2a7ee-109">Step 1 — Get started</span></span>

- <span data-ttu-id="2a7ee-110">必須有一個自動語音應答，才能擁有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="2a7ee-111">如需資源帳戶及所有所需授權的詳細資料，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="2a7ee-112">若要將來電重新導向給以**電話系統**授權為線上使用者的操作員或功能表選項，您必須啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="2a7ee-113">請參閱[指派商務用 Skype 授權](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="2a7ee-114">您也可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="2a7ee-115">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="2a7ee-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="2a7ee-116">步驟2：建立新的自動語音應答</span><span class="sxs-lookup"><span data-stu-id="2a7ee-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a7ee-117">每個自動語音應答都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="2a7ee-118">您必須先建立資源帳戶，然後才能將它與自動語音應答建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2a7ee-119">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="2a7ee-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2a7ee-120">在**Microsoft [團隊管理中心**] 中，按一下 [**語音** > **自動**語音應答]，然後按一下 [ **+ 新增**]：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="2a7ee-121">一般資訊頁面</span><span class="sxs-lookup"><span data-stu-id="2a7ee-121">General info page</span></span>

![[我的自動助理] 頁面的螢幕擷取畫面](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="2a7ee-124">**名稱**輸入您自動語音應答的描述性顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="2a7ee-125">名稱是必要的，而且最多可以包含64個字元，包括空格。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="2a7ee-126">它會列在 [**自動**語音應答] 索引標籤的 [**名稱**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="2a7ee-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="2a7ee-128"></span></span>

<span data-ttu-id="2a7ee-129">**資源帳戶**按一下此按鈕以選取一或多個資源帳戶以連線到您的新自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="2a7ee-130">必須有所有自動語音應答，才能擁有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="2a7ee-131">資源帳戶可以有一個與該帳戶相關聯的電話號碼，但不需要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="2a7ee-132">最上層的自動語音應答通常會有一個已指派電話號碼的資源帳戶，但嵌套的自動語音應答（用來做為第一級自動語音應答所連接的層級），可能不會有指派給其資源帳戶的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="2a7ee-133">![在前一個螢幕擷取畫面](media/sfbcallout3.png)
 <a name="timezone"></a>中參照標注的數位3圖示</span><span class="sxs-lookup"><span data-stu-id="2a7ee-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="2a7ee-134">**時區**您必須為自動語音應答設定時區，但不需要對應給您組織的主要位址時區。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="2a7ee-135">每個自動語音應答都可以有不同的時區，而且會根據您在此處選取的時區，設定自動語音應答的上班時間設定。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="2a7ee-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="2a7ee-137"></span></span>

<span data-ttu-id="2a7ee-138">**語言**從列出的任何可用語言中，選取您要用於自動語音應答的語言。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="2a7ee-139">您在這裡設定的語言是自動語音助理用來與呼叫此自動語音應答的人員互動的語言，且所有系統提示都會以這種語言播放。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位5圖示](media/sfbcallout5.png)

<span data-ttu-id="2a7ee-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="2a7ee-141"></span></span>

<span data-ttu-id="2a7ee-142">**運算子**這是選擇性的，但您可以設定**運算子**選項，以允許呼叫者中斷功能表並向人員朗讀。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="2a7ee-143">預設會將0按鍵指派給接線員。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="2a7ee-144">如果您設定一個運算子，您也必須在 [商務用時**通話處理**] 頁面上的 [**編輯] 功能表選項**中，告訴誰呼叫有關該選項的人員。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="2a7ee-145">如果您在自動語音應答上設定操作員，您必須在 [**呼叫者會聽到**] 方塊中輸入對應的提示文字，或變更您的音訊檔案，以包含此選項。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="2a7ee-146">例如，"For 運算子，請按零。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="2a7ee-147">您有幾種方式可以設定運算子：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="2a7ee-148">**貴公司中的人員**，在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="2a7ee-149">**貴公司中的人員**可以是線上使用者，或使用商務用 Skype server 2015 或 Lync server 2013 主機內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="2a7ee-150">**語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="2a7ee-151">您可以設定它，讓呼叫者傳送至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="2a7ee-152">若要這樣做，請選取**貴公司中的人員**，並將此人的來電設定為直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位6圖示](media/sfbcallout6.png)

<span data-ttu-id="2a7ee-154">**啟用語音輸入**如果選取此選項，就可以使用語音辨識。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="2a7ee-155">通話中的人員可以使用[您所設定之語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的語音輸入。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="2a7ee-156">如果您只想讓人員使用電話鍵台，您可以將語音辨識設定為 [關閉] 來停用。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="2a7ee-157">當您完成選取專案時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="2a7ee-158">[上班時間] 頁面</span><span class="sxs-lookup"><span data-stu-id="2a7ee-158">Business hours page</span></span>

<span data-ttu-id="2a7ee-159">根據預設，上班時間會設定為 9:00 am 5:00 到星期五下午，星期一到星期五。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="2a7ee-160">在上班時間之後，所有不包含在上班時間的時間都會被認為是在上班時間之後。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="2a7ee-161">您可以按一下 [**選取 24/7** ]，以完成所有的上班時間。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="2a7ee-162">除非您選取 [**選取 24/7** ] 選項，否則將會使用 [**下班後通話設定**] 頁面來設定自動語音應答在商務時間之後的通話處理規則。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![[上班時間] 頁面的螢幕擷取畫面](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="2a7ee-165">根據預設，上班時間設定為週一至週五，即 9:00 am-5:00 pm。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="2a7ee-166">選取 [**清除所有時間**] 選項，以取消選取排程中的所有時間。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="2a7ee-167">當您選取 [**重設為預設值**] 時，系統會將 [上班時間] 重設為 [週一至週五]，即 9:00 am-5:00</span><span class="sxs-lookup"><span data-stu-id="2a7ee-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="2a7ee-169">若要變更上班時間，請在 [行事曆] 中，醒目提示您要設定的上班時間。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="2a7ee-170">行事曆可讓您以30分鐘的間隔來選取上班時間，您在此選取的上班時間是以您在 [**一般資訊**] 頁面上所設定的時區為基礎。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="2a7ee-171">若要設定工間休息（例如午餐），請取消選取或拖曳以取消選取行事曆上的時間。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="2a7ee-172">您可以在上班時間內設定多個工間休息。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="2a7ee-173">當您完成選取專案時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="2a7ee-174">商務時間通話設定</span><span class="sxs-lookup"><span data-stu-id="2a7ee-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="2a7ee-175">如果您使用自訂的上班時間排程，您也必須在上班時間之後，使用 [**下班後通話處理**] 頁面來設定通話處理，這會提供與 [**商務時間通話] 設定**相同的選項。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="2a7ee-176">您可以設定問候語、提示和功能表，讓使用者在營業期間聽到連結到貴組織的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="2a7ee-177">![[上班時間通話處理] 頁面問候區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![螢幕擷取畫面顯示 [上班時間通話處理] 頁面動作區段的螢幕擷取畫面](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="2a7ee-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="2a7ee-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="2a7ee-179"></span></span>

<span data-ttu-id="2a7ee-180">**問候語**商務時間問候語是選擇性的，而且可以設定為 [**無問候語**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="2a7ee-181">在此情況下，來電程式在由您選取的其中一個動作處理之前，不會聽到訊息或問候。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="2a7ee-182">您也可以上傳音訊檔案（.wav、mp3 或 .wma 格式），或使用文字轉換語音來建立自訂問候語。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="2a7ee-183">**上傳音訊**檔案如果您選擇此選項，請錄製問候語，然後上傳音訊檔案（以 .wav、mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="2a7ee-184">**輸入問候訊息**如果您選擇此選項，請輸入您想要系統讀取的文字（最多1000個字元）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="2a7ee-185">例如，您可以輸入「歡迎使用 Contoso。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="2a7ee-186">您的通話對我們很重要。」</span><span class="sxs-lookup"><span data-stu-id="2a7ee-186">Your call is important to us."</span></span> <span data-ttu-id="2a7ee-187">在 [**呼叫者將會聽到**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-187">in the **Callers will hear** box.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="2a7ee-189">您可以選取在上班時間內到貨的通話情況。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="2a7ee-190">您可以從下列動作中選擇：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-190">You can chose from the following actions:</span></span>

<span data-ttu-id="2a7ee-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="2a7ee-191"></span></span>

- <span data-ttu-id="2a7ee-192">**中斷**連線如果您選取它，在聽到上班時間的問候之後，通話中的人員將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="2a7ee-193">重新**導向通話**這可以用來將來電自動傳送至：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="2a7ee-194">**公司中的人員**，在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="2a7ee-195">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="2a7ee-196">若要這樣做，請選取 [**公司中的人員**]，並將 [此人] 設為 [將來電直接轉寄給語音信箱]</span><span class="sxs-lookup"><span data-stu-id="2a7ee-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="2a7ee-197">**公司中的人員**可以是線上使用者，或者是使用商務用 Skype server 2015 或 Lync server 2013 的使用者託管內部部署。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="2a7ee-198">其他**自動助理**</span><span class="sxs-lookup"><span data-stu-id="2a7ee-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="2a7ee-199">您可以使用現有的自動助手來建立包含子功能表的第二層功能表選項。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="2a7ee-200">這些稱為嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-200">These are called nested auto attendants.</span></span> <span data-ttu-id="2a7ee-201">若要將呼叫傳送至嵌套的自動語音應答，請選取 [**公司] 中**的 [人員] 並指派已有關聯自動語音應答的人員，或在建立完此自動語音應答之後，就會與自動語音助理建立關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="2a7ee-202">您也可以使用 [**播放] 功能表選項**，讓您設定您想要播放的提示。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

<span data-ttu-id="2a7ee-204">**功能表提示**若要建立主功能表提示，您可以使用文字轉換語音或上傳音訊檔案（.wav、mp3 或 .wma）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="2a7ee-205">您可以在 [**設定您的呼叫者的功能表流覽**] 方塊中輸入提示，或錄製音訊檔案，例如：「銷售」，比如說或按下或說出1。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="2a7ee-206">針對 [服務]，請按或說出 [2]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-206">For Services, press or say 2.</span></span> <span data-ttu-id="2a7ee-207">如需客戶支援，請按或說出3。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="2a7ee-208">針對運算子，請按或說出 [0]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-208">For the operator, press or say 0.</span></span> <span data-ttu-id="2a7ee-209">若要再次聆聽此功能表，請按星號鍵或說 [重複]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="2a7ee-210">**輸入問候訊息**如果您選擇這個選項，就應該輸入您想要系統讀取的文字（最多1000個字元）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="2a7ee-211">**上傳音訊**檔案如果您選擇此選項，您將需要錄製問候語，然後上傳音訊檔案（以 .wav、mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="2a7ee-213">**功能表選項設定**您可以新增或移除鍵盤上使用按鍵按鈕的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="2a7ee-214">若要新增功能表選項，請按 **+ 指派撥號鍵**。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="2a7ee-215">對應列的選項會顯示在下方。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="2a7ee-216">若要刪除功能表選項，只需按一下 [小鍵盤] 控制項上對應鍵的左側，然後按一下上方的 [刪除] 圖示。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="2a7ee-217">將會移除 [鍵對應] 列。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="2a7ee-218">在新增至移除選項時，您必須更新功能表提示文字，或重新錄製音訊，因為現有的功能表提示不會自動完成。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="2a7ee-219">任何順序都可以新增或移除任何功能表選項，而且鍵對應不一定是連續的。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="2a7ee-220">例如，您可以建立一個含有鍵0、1和3的功能表，並對應至選項，而不使用鍵2。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="2a7ee-221">按鍵\* （重複）及\# （背面）是由系統所保留，而且無法重新指派。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="2a7ee-222">如果已啟用語音辨識功能，按下 \* 將與 "Repeat" 相對應，且 # 會與 "Back" 聲音命令相對應。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="2a7ee-223">若要設定功能表選項，請在選取撥號鍵之後，您必須：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="2a7ee-224">輸入選項的 [**語音] 命令**。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="2a7ee-225">最多可包含64個字元，而且可以包含多個字，例如「客戶服務」或「作業與使用中」。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="2a7ee-226">如果已啟用語音辨識功能，就會自動辨識名稱，而撥入的人員就可以按3，說出「三」，或者說「客戶服務」，選取對應至鍵3的選項。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="2a7ee-227">如果按下對應的按鍵，或使用語音辨識來選取此選項，請選取要傳送通話的位置。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="2a7ee-228">通話可以傳送至：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-228">The call can be sent to:</span></span>

  - <span data-ttu-id="2a7ee-229">**運算子**如果已設定運算子，就會自動對應到 key 0，但是也可以將它刪除或重新指派給不同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="2a7ee-230">如果運算子未設為任何鍵，語音命令 "Operator" 也將停用。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="2a7ee-231">**貴公司中的人員**，在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="2a7ee-232">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="2a7ee-233">若要這樣做，請選取**貴公司中的人員**，並將其來電設定為直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="2a7ee-234">**貴公司中的人員**可以是線上使用者，或使用商務用 Skype Server 或 Lync server 2013 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>
    - <span data-ttu-id="2a7ee-235">其他**自動助理**</span><span class="sxs-lookup"><span data-stu-id="2a7ee-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="2a7ee-236">您可以使用現有的自動助手來建立包含子功能表的第二層功能表選項。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="2a7ee-237">這些稱為嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-237">These are called nested auto attendants.</span></span> <span data-ttu-id="2a7ee-238">若要將呼叫傳送至嵌套的自動語音應答，請選取 [**公司] 中**的 [人員] 並指派已有關聯自動語音應答的人員，或在建立完此自動語音應答之後，就會與自動語音助理建立關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="2a7ee-239">也會使用嵌套（或第二層）自動語音應答的**商務時間**，包括從其他已設定的自動語音應答所傳送的通話。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-239">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

       - <span data-ttu-id="2a7ee-240">**語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-240">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位5圖示](media/sfbcallout5.png)

<span data-ttu-id="2a7ee-242">**依名稱撥號**如果您選擇這個選項，這會讓打電話給您的人員使用 [目錄搜尋] 搜尋貴組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-242">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="2a7ee-243">您可以在 [**撥號作用**中] 頁面上設定這些選項，以選取哪些人員將被列為 [可用] 或 [無法供撥號使用]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-243">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="2a7ee-244">使用**電話系統**授權的任何線上使用者，或任何使用商務用 Skype Server 或 Lync server 2013 的使用者，都可以透過名稱來找到。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-244">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="2a7ee-245">當您完成選取專案時，請按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-245">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="2a7ee-246">假日通話設定</span><span class="sxs-lookup"><span data-stu-id="2a7ee-246">Holiday call settings</span></span>

<span data-ttu-id="2a7ee-247">您最多可以將20個排定的假日新增至每個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="2a7ee-248">您可以在**組織內設定** > **假日**移至畫面來建立假日，或者您可以建立新的呼叫處理常式的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![[假日通話設定] 頁面的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="2a7ee-251">如果您已經建立其他自動語音應答，您可能會看到一個選項，您可以在此清單中使用或編輯您需要的專案。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="2a7ee-252">如果不是，您將需要建立新的呼叫處理常式。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="2a7ee-253">若要新增呼叫處理常式，請按一下 [ **+ 新呼叫處理常式**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![顯示新增呼叫處理常式的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="2a7ee-256">在新視窗中，在畫面頂端輸入新呼叫處理常式的名稱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="2a7ee-258">如果您的假日名稱已存在於 [**假日**] 下拉式清單中，您可以使用它。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="2a7ee-259">如果您所需的假日名稱還不存在，請在下拉式清單中選取 [**建立新假日**]，然後在出現的新畫面中指定新假日的名稱和日期。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="2a7ee-260">準備就緒時，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="2a7ee-261">假日名稱最多可包含64個字元，且對於相同的自動語音應答必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="2a7ee-262">例如，在同一個自動語音應答中，您不能使用兩個名為 "感恩節" 的假日。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

<span data-ttu-id="2a7ee-264">**問候語**問候語是選擇性的，而且可以設定為 [**無問候語**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="2a7ee-265">在這種情況下，在您選取的其中一個選項處理呼叫前，來電者將不會聽到任何訊息或問候語。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="2a7ee-266">您也可以上傳音訊檔案（.wav、mp3 或 .wma 格式），或使用文字轉換語音來建立自訂問候語。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="2a7ee-267">**沒有問候語**在人員撥入自動語音應答電話號碼時，不會播放任何問候語。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="2a7ee-268">**上傳音訊**檔案如果您選擇此選項，請錄製假日問候語，然後上傳音訊檔案（以 .wav、mp3 或 .wma 格式）</span><span class="sxs-lookup"><span data-stu-id="2a7ee-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="2a7ee-269">**輸入問候訊息**如果您選擇此選項，請輸入您想要系統讀取的文字（最多1000個字元）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="2a7ee-270">例如，您可以輸入「新年快樂！</span><span class="sxs-lookup"><span data-stu-id="2a7ee-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="2a7ee-271">我們的辦公室目前已關閉。」</span><span class="sxs-lookup"><span data-stu-id="2a7ee-271">Our offices are currently closed."</span></span> <span data-ttu-id="2a7ee-272">在 [**輸入問候訊息**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-272">in the **Type a greeting message** box.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="2a7ee-274">**動作**您可以選取在此假日期間到達的通話情況。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="2a7ee-275">您可以從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-275">You can chose from the following options:</span></span>

- <span data-ttu-id="2a7ee-276">**中斷**連線在聽到假日問候語之後撥入的人員將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="2a7ee-277">重新**導向通話**這可以用來將來電自動傳送至：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="2a7ee-278">**貴公司中**擁有在 Office 365 中啟用企業語音或指派通話方案的**電話系統**授權的人員。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="2a7ee-279">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="2a7ee-280">若要這樣做，請選取**貴公司中的人員**，並將此人設定為讓其呼叫直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="2a7ee-281">**貴公司中的人員**可以是線上使用者，或使用商務用 Skype server 2015 或 Lync server 2013 主機內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="2a7ee-282">**語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="2a7ee-283">根據預設，假期期間內的所有來電都會設定為在問候語（如果有的話）之後中斷連線，因此您必須指定重新導向（如果有其他行為的話）。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="2a7ee-284">選取 [撥號作用域] 頁面</span><span class="sxs-lookup"><span data-stu-id="2a7ee-284">Select dial scope page</span></span>

<span data-ttu-id="2a7ee-285">在此頁面上，您可以設定貴組織中的哪些使用者會列在您的目錄中，並可在撥入您組織的人員時，透過名稱撥號。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![顯示 [撥號作用中] 頁面的螢幕擷取畫面](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="2a7ee-287">![數位1的圖示，參照前一個螢幕擷取畫面](media/sfbcallout1.png)中的標注使用 [**包括**] 選項，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="2a7ee-288">**所有的線上使用者**使用這個選項可讓您組織中的所有人員都包含在目錄搜尋中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="2a7ee-289">所有具備**電話系統**授權的線上使用者，以及使用商務用 Skype Server 或 Lync 2013 server （在 Office 365 中有通話方案）的使用者主機內部部署的使用者，都會列在其中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="2a7ee-290">**自訂使用者群組**如果您使用這個選項，您可以搜尋已在您的組織中建立的 Office 365 群組、通訊群組清單或安全性群組，以及新增至此 Office 365 群組、通訊群組清單或安全性群組的人員，這些人必須**具備**使用商務用 Skype server 2015 或 Lync server 2013 的電話系統授權或主機內部部署。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="2a7ee-291">您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="2a7ee-293">使用 [**排除**] 選項，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="2a7ee-294">**None**使用這個選項，即表示不會從目錄搜尋中排除任何線上使用者。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="2a7ee-295">**自訂使用者群組**如果您使用這個選項，您可以搜尋已在貴組織中建立的 Office 365 群組、通訊群組清單或安全性群組，而且所有新增至此 Office 365 群組、通訊群組清單或安全性群組的人員將會從目錄搜尋中排除。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="2a7ee-296">您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="2a7ee-297">當有人透過語音辨識以名稱使用撥號時，最多可能需要36小時才能讓新的使用者將其名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="2a7ee-298">輸入所有必要的欄位並設定 [通話處理] 功能表和選項之後，請按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="2a7ee-299">編輯及測試自動語音應答</span><span class="sxs-lookup"><span data-stu-id="2a7ee-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="2a7ee-300">在您儲存了自動語音應答之後，它會列在 [**自動**語音應答] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="2a7ee-301">這可讓您快速查看一些已設定的選項，包括姓名、電話號碼、語言和狀態。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="2a7ee-302">如果您想要變更自動語音應答，請選取 [自動語音應答]，然後在 [動作] 窗格中按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="2a7ee-303">您也可以使用 [動作] 窗格中的 [**測試**] 按鈕，快速地將測試呼叫放到您的自動語音應答中。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="2a7ee-304">自動語音應答 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2a7ee-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="2a7ee-305">您也可以使用 Windows PowerShell 來建立及設定自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="2a7ee-306">以下是您需要管理自動語音應答的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="2a7ee-307">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2a7ee-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="2a7ee-308">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2a7ee-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="2a7ee-309">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2a7ee-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="2a7ee-310">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="2a7ee-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="2a7ee-311">移除-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2a7ee-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="2a7ee-312">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="2a7ee-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="2a7ee-313">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="2a7ee-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="2a7ee-314">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="2a7ee-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="2a7ee-315">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="2a7ee-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="2a7ee-316">新-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="2a7ee-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="2a7ee-317">新-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="2a7ee-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="2a7ee-318">新-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="2a7ee-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="2a7ee-319">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="2a7ee-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="2a7ee-320">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="2a7ee-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="2a7ee-321">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="2a7ee-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="2a7ee-322">匯入-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="2a7ee-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="2a7ee-323">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="2a7ee-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="2a7ee-324">深入瞭解 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a7ee-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="2a7ee-325">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2a7ee-326">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和 Microsoft 團隊，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="2a7ee-327">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="2a7ee-328">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="2a7ee-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="2a7ee-329">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a7ee-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="2a7ee-330">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="2a7ee-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="2a7ee-331">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="2a7ee-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="2a7ee-332">使用 Office 365 PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="2a7ee-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="2a7ee-333">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="2a7ee-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="2a7ee-334">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a7ee-334">Related topics</span></span>

[<span data-ttu-id="2a7ee-335">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="2a7ee-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="2a7ee-336">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="2a7ee-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="2a7ee-337">適用于音訊會議與通話方案的國家和地區可用性</span><span class="sxs-lookup"><span data-stu-id="2a7ee-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="2a7ee-338">新-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="2a7ee-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="2a7ee-339">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="2a7ee-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="2a7ee-340">小型企業範例-設定自動助手</span><span class="sxs-lookup"><span data-stu-id="2a7ee-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
