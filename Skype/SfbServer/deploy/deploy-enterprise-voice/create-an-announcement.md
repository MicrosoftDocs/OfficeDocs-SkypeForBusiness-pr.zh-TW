---
title: 在商務用 Skype Server 中建立或刪除宣告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 在商務用 Skype Server Enterprise Voice 中建立或刪除宣告應用程式宣告。 這會影響如何處理未指派號碼的呼叫。
ms.openlocfilehash: 571dce52366430c0e13f442de4917a2c51ed056f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093281"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="96cb4-104">在商務用 Skype Server 中建立或刪除宣告</span><span class="sxs-lookup"><span data-stu-id="96cb4-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="96cb4-105">在商務用 Skype Server Enterprise Voice 中建立或刪除宣告應用程式宣告。</span><span class="sxs-lookup"><span data-stu-id="96cb4-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="96cb4-106">這會影響如何處理未指派號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="96cb4-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="96cb4-107">當您設定宣告時，實際上是設定您要如何處理未指派號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="96cb4-107">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled.</span></span> <span data-ttu-id="96cb4-108">您可以播放提示，可以是音訊檔或文字語音 (TTS) 檔案，也可以只將來電轉接至指定的目的地，而不需要播放提示。</span><span class="sxs-lookup"><span data-stu-id="96cb4-108">You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="96cb4-109">您必須先建立宣告，再定義未指派的號碼表。</span><span class="sxs-lookup"><span data-stu-id="96cb4-109">You need to create announcements before you define the unassigned number table.</span></span> <span data-ttu-id="96cb4-110">您必須對使用音訊提示、TTS 提示或無提示的所有宣告執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="96cb4-110">You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="96cb4-111">本主題說明如何匯入和建立宣告。</span><span class="sxs-lookup"><span data-stu-id="96cb4-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="96cb4-112">如需在未指派號碼表中指派宣告的詳細資訊，請參閱 [Configure The 未指派號碼表格](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table)。</span><span class="sxs-lookup"><span data-stu-id="96cb4-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="96cb4-113">建立未指派號碼的新宣告</span><span class="sxs-lookup"><span data-stu-id="96cb4-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="96cb4-114">若要建立新的宣告，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="96cb4-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="96cb4-115">若為音訊提示，請使用您最喜歡的音訊錄製應用程式，錄製音訊檔。</span><span class="sxs-lookup"><span data-stu-id="96cb4-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="96cb4-116">若為音訊提示，請執行 **Import-CsAnnouncementFile** Cmdlet，將音訊檔的內容匯入至檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="96cb4-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="96cb4-117">執行 **New-CsAnnouncement** Cmdlet 來建立及命名宣告。</span><span class="sxs-lookup"><span data-stu-id="96cb4-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="96cb4-118">執行此步驟以透過音訊提示來建立宣告、文字語音 (TTS) 提示或沒有提示。</span><span class="sxs-lookup"><span data-stu-id="96cb4-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="96cb4-119">您可能想要建立無提示的宣告 (例如，如果您想要將來電轉接至特定目的地，但不播放郵件) 。</span><span class="sxs-lookup"><span data-stu-id="96cb4-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="96cb4-120">將新的宣告指派給未指派號碼表中的號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="96cb4-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="96cb4-121">若要建立新的宣告</span><span class="sxs-lookup"><span data-stu-id="96cb4-121">To create a new announcement</span></span>

1. <span data-ttu-id="96cb4-122">若為音訊提示，請建立音訊檔。</span><span class="sxs-lookup"><span data-stu-id="96cb4-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="96cb4-123">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="96cb4-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="96cb4-124">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="96cb4-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="96cb4-125">若為音訊提示，請執行：</span><span class="sxs-lookup"><span data-stu-id="96cb4-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="96cb4-126">執行：</span><span class="sxs-lookup"><span data-stu-id="96cb4-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="96cb4-127">若要將來電轉接至語音信箱，請輸入 SIPAddress 格式的 sip： username@domainname; 不透明 = 應用程式：語音信箱 (例如： sip： bob@contoso .com; 不透明 = 應用程式：語音信箱) 。</span><span class="sxs-lookup"><span data-stu-id="96cb4-127">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="96cb4-128">若要將來電轉接至電話號碼，請輸入 sip： number@domainname; user = phone (的 SIPAddress，例如，sip： + 14255550121@contoso .com; user = phone) 。</span><span class="sxs-lookup"><span data-stu-id="96cb4-128">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="96cb4-129">例如，若要指定音訊提示：</span><span class="sxs-lookup"><span data-stu-id="96cb4-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="96cb4-130">例如，若要指定 TTS 提示：</span><span class="sxs-lookup"><span data-stu-id="96cb4-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="96cb4-131">如需這些 Cmdlet 的詳細資訊，以及若要查看在 **TextToSpeechPrompt** 參數中使用的語言代碼清單，請參閱 [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="96cb4-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="96cb4-132">刪除未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="96cb4-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="96cb4-133">刪除宣告</span><span class="sxs-lookup"><span data-stu-id="96cb4-133">To delete an announcement</span></span>

1. <span data-ttu-id="96cb4-134">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="96cb4-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="96cb4-135">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="96cb4-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="96cb4-p108">列出組織中的所有宣告。在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="96cb4-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="96cb4-p109">在結果清單中，找出您要刪除的宣告，並複製 GUID。然後在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="96cb4-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="96cb4-140">例如：</span><span class="sxs-lookup"><span data-stu-id="96cb4-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="96cb4-141">如需更多選項的詳細資訊，請參閱 [CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) 和 [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="96cb4-141">For details about more options, see [Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="96cb4-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="96cb4-142">See also</span></span>

[<span data-ttu-id="96cb4-143">在商務用 Skype Server 中建立或刪除宣告</span><span class="sxs-lookup"><span data-stu-id="96cb4-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="96cb4-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="96cb4-144">Import-CsAnnouncementFile</span></span>](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="96cb4-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="96cb4-145">New-CsAnnouncement</span></span>](/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="96cb4-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="96cb4-146">Remove-CsAnnouncement</span></span>](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="96cb4-147">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="96cb4-147">Get-CsAnnouncement</span></span>](/powershell/module/skype/get-csannouncement?view=skype-ps)