---
title: Lync Server 2013：建立宣告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108d0ed2800abcb572b7706a26fe9b0c2fab4500
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="1135c-102">在 Lync Server 2013 中建立宣告</span><span class="sxs-lookup"><span data-stu-id="1135c-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1135c-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1135c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1135c-104">若要建立新的宣告，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1135c-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="1135c-105">若為音訊提示，請使用您最喜歡的音訊錄製應用程式，錄製音訊檔。</span><span class="sxs-lookup"><span data-stu-id="1135c-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="1135c-106">若為音訊提示，請執行 **Import-CsAnnouncementFile** Cmdlet，將音訊檔的內容匯入至檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="1135c-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="1135c-107">執行 **New-CsAnnouncement** Cmdlet 來建立及命名宣告。</span><span class="sxs-lookup"><span data-stu-id="1135c-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="1135c-108">執行此步驟以透過音訊提示來建立宣告、文字語音 (TTS) 提示或沒有提示。</span><span class="sxs-lookup"><span data-stu-id="1135c-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1135c-109">您可能想要建立無提示的宣告 (例如，如果您想要將來電轉接至特定目的地，但不播放郵件) 。</span><span class="sxs-lookup"><span data-stu-id="1135c-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="1135c-110">將新的宣告指派給未指派號碼表中的號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="1135c-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="1135c-111">本主題說明如何匯入和建立宣告。</span><span class="sxs-lookup"><span data-stu-id="1135c-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="1135c-112">如需在未指派號碼表中指派宣告的詳細資訊，請參閱 [在 Lync Server 2013 中設定未指派號碼表格](lync-server-2013-configure-the-unassigned-number-table.md)。</span><span class="sxs-lookup"><span data-stu-id="1135c-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="1135c-113">若要建立新的宣告</span><span class="sxs-lookup"><span data-stu-id="1135c-113">To create a new announcement</span></span>

1.  <span data-ttu-id="1135c-114">若為音訊提示，請建立音訊檔。</span><span class="sxs-lookup"><span data-stu-id="1135c-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="1135c-115">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="1135c-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="1135c-116">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1135c-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="1135c-117">若為音訊提示，請執行：</span><span class="sxs-lookup"><span data-stu-id="1135c-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="1135c-118">執行：</span><span class="sxs-lookup"><span data-stu-id="1135c-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="1135c-119">若要將來電轉接至語音信箱，請輸入 SIPAddress 格式的 sip： username@domainname; 不透明 = 應用程式：語音信箱 (例如： sip： bob@contoso .com; 不透明 = 應用程式：語音信箱) 。</span><span class="sxs-lookup"><span data-stu-id="1135c-119">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="1135c-120">若要將來電轉接至電話號碼，請輸入 sip： number@domainname; user = phone (的 SIPAddress，例如，sip： + 14255550121@contoso .com; user = phone) 。</span><span class="sxs-lookup"><span data-stu-id="1135c-120">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="1135c-121">例如，若要指定音訊提示：</span><span class="sxs-lookup"><span data-stu-id="1135c-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="1135c-122">例如，若要指定 TTS 提示：</span><span class="sxs-lookup"><span data-stu-id="1135c-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="1135c-123">如需這些 Cmdlet 的詳細資訊，以及若要查看在 **TextToSpeechPrompt** 參數中使用的語言代碼清單，請參閱 [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。</span><span class="sxs-lookup"><span data-stu-id="1135c-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1135c-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1135c-124">See Also</span></span>


[<span data-ttu-id="1135c-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="1135c-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="1135c-126">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="1135c-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="1135c-127">在 Lync Server 2013 中設定未指派號碼表</span><span class="sxs-lookup"><span data-stu-id="1135c-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

