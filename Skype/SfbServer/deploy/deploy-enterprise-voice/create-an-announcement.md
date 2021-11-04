---
title: 在商務用 Skype Server 中建立或刪除宣告
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 在商務用 Skype Server 企業語音中建立或刪除宣告應用程式的宣告。 這會影響如何處理未指派號碼的呼叫。
ms.openlocfilehash: 3a5fdbcb5f9c4e72790f35f73cef791868634ce9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765921"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或刪除宣告

在商務用 Skype Server 企業語音中建立或刪除宣告應用程式的宣告。 這會影響如何處理未指派號碼的呼叫。

當您設定宣告時，實際上是設定您要如何處理未指派號碼的呼叫。 您可以播放提示，可以是音訊檔或文字語音 (TTS) 檔案，也可以只將來電轉接至指定的目的地，而不需要播放提示。

您必須先建立宣告，再定義未指派的號碼表。 您必須對使用音訊提示、TTS 提示或無提示的所有宣告執行此步驟。

本主題說明如何匯入和建立宣告。 如需在未指派號碼表中指派宣告的詳細資訊，請參閱 [Configure The 未指派號碼表格](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table)。

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>建立未指派號碼的新宣告

若要建立新的宣告，您必須執行下列步驟：

1. 若為音訊提示，請使用您最喜歡的音訊錄製應用程式，錄製音訊檔。

2. 若為音訊提示，請執行 **Import-CsAnnouncementFile** Cmdlet，將音訊檔的內容匯入至檔案存放區。

3. 執行 **New-CsAnnouncement** Cmdlet 來建立及命名宣告。 執行此步驟以透過音訊提示來建立宣告、文字語音 (TTS) 提示或沒有提示。

    > [!TIP]
    > 您可能想要建立無提示的宣告 (例如，如果您想要將來電轉接至特定目的地，但不播放郵件) 。

4. 將新的宣告指派給未指派號碼表中的號碼範圍。

### <a name="to-create-a-new-announcement"></a>若要建立新的宣告

1. 若為音訊提示，請建立音訊檔。

2. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。

3. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

4. 若為音訊提示，請執行：

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 運行：

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    若要將來電轉接至語音信箱，請輸入 SIPAddress 格式的 sip： username@domainname; 不透明 = 應用程式：語音信箱 (例如： sip： bob@contoso .com; 不透明 = 應用程式：語音信箱) 。 若要將來電轉接至電話號碼，請輸入 sip： number@domainname; user = phone (的 SIPAddress，例如，sip： + 14255550121@contoso .com; user = phone) 。

    例如，若要指定音訊提示：

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    例如，若要指定 TTS 提示：

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   如需這些 Cmdlet 的詳細資訊，以及若要查看在 **TextToSpeechPrompt** 參數中使用的語言代碼清單，請參閱 [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)。

## <a name="delete-an-announcement-for-unassigned-numbers"></a>刪除未指派號碼的宣告

### <a name="to-delete-an-announcement"></a>刪除宣告

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。

2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3. 列出組織中的所有宣告。在命令列中執行：

   ```powershell
   Get-CsAnnouncement
   ```

4. 在結果清單中，找出您要刪除的宣告，並複製 GUID。然後在命令列中執行：

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    例如：

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > 如需更多選項的詳細資訊，請參閱 [CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) 和 [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立或刪除宣告](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)