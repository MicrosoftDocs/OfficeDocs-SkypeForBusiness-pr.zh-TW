---
title: 在商務用 Skype Server 中建立或刪除公告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 在商務用 Skype Server Enterprise Voice 中建立或刪除宣告應用程式的宣告。 這會影響如何處理未指派數位的呼叫。
ms.openlocfilehash: 6160631473a2ead839346e53f9f63294a7959289
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191350"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="486db-104">在商務用 Skype Server 中建立或刪除公告</span><span class="sxs-lookup"><span data-stu-id="486db-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="486db-105">在商務用 Skype Server Enterprise Voice 中建立或刪除宣告應用程式的宣告。</span><span class="sxs-lookup"><span data-stu-id="486db-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="486db-106">這會影響如何處理未指派數位的呼叫。</span><span class="sxs-lookup"><span data-stu-id="486db-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="486db-107">當您設定宣告時, 您將會真正設定您想要如何處理未指派號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="486db-107">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled.</span></span> <span data-ttu-id="486db-108">您可以播放提示, 可以是音訊檔案或文字轉換語音 (TTS) 檔案, 或者您可以直接將來電轉接到指定的目的地, 而不需播放提示。</span><span class="sxs-lookup"><span data-stu-id="486db-108">You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="486db-109">您必須先建立宣告, 才能定義 [未指定的數位] 資料表。</span><span class="sxs-lookup"><span data-stu-id="486db-109">You need to create announcements before you define the unassigned number table.</span></span> <span data-ttu-id="486db-110">您必須針對使用音訊提示、TTS 提示或無提示的所有宣告執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="486db-110">You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="486db-111">本主題說明如何匯入及建立公告。</span><span class="sxs-lookup"><span data-stu-id="486db-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="486db-112">如需在 [未指定的數位] 資料表中指派宣告的詳細資料, 請參閱[設定未指定的數位資料表](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="486db-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="486db-113">為未指定的號碼建立新的宣告</span><span class="sxs-lookup"><span data-stu-id="486db-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="486db-114">若要建立新的宣告, 您必須執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="486db-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="486db-115">針對音訊提示, 請使用您最愛的 [錄音] 應用程式錄製音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="486db-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="486db-116">針對音訊提示, 請執行匯**入-CsAnnouncementFile** Cmdlet, 將音訊檔案的內容匯入到檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="486db-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="486db-117">執行**新的 CsAnnouncement** Cmdlet 來建立並命名宣告。</span><span class="sxs-lookup"><span data-stu-id="486db-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="486db-118">執行此步驟以建立含音訊提示、文字轉換語音 (TTS) 提示或無提示的宣告。</span><span class="sxs-lookup"><span data-stu-id="486db-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="486db-119">您可能會想要建立沒有提示的宣告 (例如, 如果您想要將來電轉接至特定目的地, 而不播放郵件)。</span><span class="sxs-lookup"><span data-stu-id="486db-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="486db-120">將新宣告指派至 [未指定的數位] 資料表中的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="486db-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="486db-121">若要建立新的宣告</span><span class="sxs-lookup"><span data-stu-id="486db-121">To create a new announcement</span></span>

1. <span data-ttu-id="486db-122">針對音訊提示, 請建立音訊檔。</span><span class="sxs-lookup"><span data-stu-id="486db-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="486db-123">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="486db-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="486db-124">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="486db-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="486db-125">針對音訊提示, 請執行:</span><span class="sxs-lookup"><span data-stu-id="486db-125">For audio prompts, run:</span></span>

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="486db-126">用盡</span><span class="sxs-lookup"><span data-stu-id="486db-126">Run:</span></span>

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="486db-127">若要將來電轉接到語音信箱, 請在 [sip: username] @ 功能變數名稱; 不透明 = app: 語音信箱 (例如 sip: bob@contoso.com; 不透明 = app: 語音信箱) 中輸入 SIPAddress。</span><span class="sxs-lookup"><span data-stu-id="486db-127">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="486db-128">若要將來電轉接到電話號碼, 請在 [sip: 號碼 @ 功能變數名稱] 中輸入 SIPAddress, 然後輸入使用者 = phone (例如, sip: + 14255550121@contoso.com; user = phone)。</span><span class="sxs-lookup"><span data-stu-id="486db-128">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="486db-129">例如, 若要指定音訊提示:</span><span class="sxs-lookup"><span data-stu-id="486db-129">For example, to specify an audio prompt:</span></span>

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="486db-130">例如, 若要指定 TTS 提示:</span><span class="sxs-lookup"><span data-stu-id="486db-130">For example, to specify a TTS prompt:</span></span>

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="486db-131">如需這些 Cmdlet 的詳細資訊, 以及若要查看在**TextToSpeechPrompt**參數中使用的語言代碼清單, 請參閱[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="486db-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="486db-132">刪除未指定編號的宣告</span><span class="sxs-lookup"><span data-stu-id="486db-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="486db-133">刪除公告</span><span class="sxs-lookup"><span data-stu-id="486db-133">To delete an announcement</span></span>

1. <span data-ttu-id="486db-134">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="486db-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="486db-135">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="486db-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="486db-136">列出貴組織中的所有宣告。</span><span class="sxs-lookup"><span data-stu-id="486db-136">List all the announcements in your organization.</span></span> <span data-ttu-id="486db-137">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="486db-137">At the command line, run:</span></span>

   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="486db-138">在產生的清單中, 找出您要刪除的宣告, 然後複製 GUID。</span><span class="sxs-lookup"><span data-stu-id="486db-138">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="486db-139">然後, 在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="486db-139">Then, at the command line, run:</span></span>

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="486db-140">例如：</span><span class="sxs-lookup"><span data-stu-id="486db-140">For example:</span></span>

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="486db-141">如需更多選項的詳細資訊, 請參閱[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)及[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="486db-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="486db-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="486db-142">See also</span></span>

[<span data-ttu-id="486db-143">在商務用 Skype Server 中建立或刪除公告</span><span class="sxs-lookup"><span data-stu-id="486db-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="486db-144">匯入-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="486db-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="486db-145">新-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="486db-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="486db-146">移除-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="486db-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="486db-147">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="486db-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

