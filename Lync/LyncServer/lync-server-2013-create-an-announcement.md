---
title: Lync Server 2013：建立宣告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80210787a8261d122fa7508807ab995279c7d0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>在 Lync Server 2013 中建立公告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

若要建立新的宣告，您必須執行下列步驟：

1.  針對音訊提示，請使用您最愛的 [錄音] 應用程式錄製音訊檔案。

2.  針對音訊提示，請執行匯**入-CsAnnouncementFile** Cmdlet，將音訊檔案的內容匯入到檔案存放區。

3.  執行**新的 CsAnnouncement** Cmdlet 來建立並命名宣告。 執行此步驟以建立含音訊提示、文字轉換語音（TTS）提示或無提示的宣告。
    
    <div>
    

    > [!TIP]  
    > 您可能會想要建立沒有提示的宣告（例如，如果您想要將來電轉接至特定目的地，而不播放郵件）。

    
    </div>

4.  將新宣告指派至 [未指定的數位] 資料表中的數位範圍。

本主題說明如何匯入及建立公告。 如需在 [未指定的數位] 資料表中指派宣告的詳細資料，請參閱[在 Lync Server 2013 中設定 [未指定的號碼] 資料表](lync-server-2013-configure-the-unassigned-number-table.md)

<div>

## <a name="to-create-a-new-announcement"></a>若要建立新的宣告

1.  針對音訊提示，請建立音訊檔。

2.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

3.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  針對音訊提示，請執行：
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  用盡
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    若要將來電轉接到語音信箱，請在 [sip： username@domainname] 中輸入 SIPAddress; 不透明 = app：語音信箱（例如 sip： bob@contoso .com; 不透明 = app：語音信箱）。 若要將來電轉接至電話號碼，請在 [sip： number@domainname] 中輸入 SIPAddress; 使用者 = 電話（例如，sip： + 14255550121@contoso .com; 使用者 = 電話）。
    
    例如，若要指定音訊提示：
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    例如，若要指定 TTS 提示：
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    如需這些 Cmdlet 的詳細資訊，以及若要查看在**TextToSpeechPrompt**參數中使用的語言代碼清單，請參閱[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。

</div>

<div>

## <a name="see-also"></a>請參閱


[匯入-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[新-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[在 Lync Server 2013 中設定未指派號碼表](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

