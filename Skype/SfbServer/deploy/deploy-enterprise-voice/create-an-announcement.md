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
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或刪除公告

在商務用 Skype Server Enterprise Voice 中建立或刪除宣告應用程式的宣告。 這會影響如何處理未指派數位的呼叫。

當您設定宣告時, 您將會真正設定您想要如何處理未指派號碼的呼叫。 您可以播放提示, 可以是音訊檔案或文字轉換語音 (TTS) 檔案, 或者您可以直接將來電轉接到指定的目的地, 而不需播放提示。

您必須先建立宣告, 才能定義 [未指定的數位] 資料表。 您必須針對使用音訊提示、TTS 提示或無提示的所有宣告執行此步驟。

本主題說明如何匯入及建立公告。 如需在 [未指定的數位] 資料表中指派宣告的詳細資料, 請參閱[設定未指定的數位資料表](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)。

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>為未指定的號碼建立新的宣告

若要建立新的宣告, 您必須執行下列步驟:

1. 針對音訊提示, 請使用您最愛的 [錄音] 應用程式錄製音訊檔案。

2. 針對音訊提示, 請執行匯**入-CsAnnouncementFile** Cmdlet, 將音訊檔案的內容匯入到檔案存放區。

3. 執行**新的 CsAnnouncement** Cmdlet 來建立並命名宣告。 執行此步驟以建立含音訊提示、文字轉換語音 (TTS) 提示或無提示的宣告。

    > [!TIP]
    > 您可能會想要建立沒有提示的宣告 (例如, 如果您想要將來電轉接至特定目的地, 而不播放郵件)。

4. 將新宣告指派至 [未指定的數位] 資料表中的數位範圍。

### <a name="to-create-a-new-announcement"></a>若要建立新的宣告

1. 針對音訊提示, 請建立音訊檔。

2. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。

3. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

4. 針對音訊提示, 請執行:

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 用盡

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    若要將來電轉接到語音信箱, 請在 [sip: username] @ 功能變數名稱; 不透明 = app: 語音信箱 (例如 sip: bob@contoso.com; 不透明 = app: 語音信箱) 中輸入 SIPAddress。 若要將來電轉接到電話號碼, 請在 [sip: 號碼 @ 功能變數名稱] 中輸入 SIPAddress, 然後輸入使用者 = phone (例如, sip: + 14255550121@contoso.com; user = phone)。

    例如, 若要指定音訊提示:

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    例如, 若要指定 TTS 提示:

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   如需這些 Cmdlet 的詳細資訊, 以及若要查看在**TextToSpeechPrompt**參數中使用的語言代碼清單, 請參閱[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)。

## <a name="delete-an-announcement-for-unassigned-numbers"></a>刪除未指定編號的宣告

### <a name="to-delete-an-announcement"></a>刪除公告

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。

2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

3. 列出貴組織中的所有宣告。 在命令列上執行:

   ```
   Get-CsAnnouncement
   ```

4. 在產生的清單中, 找出您要刪除的宣告, 然後複製 GUID。 然後, 在命令列上執行:

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    例如：

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > 如需更多選項的詳細資訊, 請參閱[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)及[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立或刪除公告](create-an-announcement.md)

[匯入-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[新-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[移除-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

