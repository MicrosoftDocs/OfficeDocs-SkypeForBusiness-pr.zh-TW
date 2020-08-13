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

# <a name="create-an-announcement-in-lync-server-2013"></a>在 Lync Server 2013 中建立宣告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

若要建立新的宣告，您必須執行下列步驟：

1.  若為音訊提示，請使用您最喜歡的音訊錄製應用程式，錄製音訊檔。

2.  若為音訊提示，請執行 **Import-CsAnnouncementFile** Cmdlet，將音訊檔的內容匯入至檔案存放區。

3.  執行 **New-CsAnnouncement** Cmdlet 來建立及命名宣告。 執行此步驟以透過音訊提示來建立宣告、文字語音 (TTS) 提示或沒有提示。
    
    <div>
    

    > [!TIP]  
    > 您可能想要建立無提示的宣告 (例如，如果您想要將來電轉接至特定目的地，但不播放郵件) 。

    
    </div>

4.  將新的宣告指派給未指派號碼表中的號碼範圍。

本主題說明如何匯入和建立宣告。 如需在未指派號碼表中指派宣告的詳細資訊，請參閱 [在 Lync Server 2013 中設定未指派號碼表格](lync-server-2013-configure-the-unassigned-number-table.md)。

<div>

## <a name="to-create-a-new-announcement"></a>若要建立新的宣告

1.  若為音訊提示，請建立音訊檔。

2.  以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  若為音訊提示，請執行：
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  執行：
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    若要將來電轉接至語音信箱，請輸入 SIPAddress 格式的 sip： username@domainname; 不透明 = 應用程式：語音信箱 (例如： sip： bob@contoso .com; 不透明 = 應用程式：語音信箱) 。 若要將來電轉接至電話號碼，請輸入 sip： number@domainname; user = phone (的 SIPAddress，例如，sip： + 14255550121@contoso .com; user = phone) 。
    
    例如，若要指定音訊提示：
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    例如，若要指定 TTS 提示：
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    如需這些 Cmdlet 的詳細資訊，以及若要查看在 **TextToSpeechPrompt** 參數中使用的語言代碼清單，請參閱 [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[在 Lync Server 2013 中設定未指派號碼表](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

