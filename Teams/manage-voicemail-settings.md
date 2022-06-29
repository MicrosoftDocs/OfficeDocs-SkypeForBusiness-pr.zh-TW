---
title: 管理雲端語音信箱設定
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理使用者的語音信箱設定。
ms.openlocfilehash: 80dad0b2088518c9d6f08ee005eba25cc1e10e2b
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494838"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>管理使用者的雲端語音信箱設定

語音信箱設定可讓您為個別使用者設定語音信箱設定。

在為使用者設定語音信箱設定之前，您應該先閱讀[設定雲端語音信箱](set-up-phone-system-voicemail.md)。 如需設定使用者群組原則的相關資訊，請參閱 [管理語音信箱原則](manage-voicemail-policies.md)。

雲端語音信箱的預設設定為：

- 語音信箱已啟用。
- 提示語言會設定為使用者的慣用語言。
- 不在辦公室問候語已停用。
- 在 Outlook 中設定自動回復時，[不在辦公室] 問候語會停用。
- 當 Outlook 中的行事曆顯示 [不在辦公室] 時，[不在辦公室] 問候語會停用。
- 我們已停用與服務共用語音信箱和轉譯資料以進行訓練及改善準確性之目的。
- 通話接聽規則設定為一般語音信箱。
- 未設定預設的問候語提示覆寫。
- 未設定預設的不在辦公室問候語提示覆寫。
- 未設定傳輸目標。


若要管理使用者雲端語音信箱功能，您可以使用 Teams 系統管理中心或 PowerShell。 請注意，您的使用者也可以在 Teams 用戶端中設定這些設定，方法是移至 [ **設定] -> [通話] -> [設定語音信箱]。**

## <a name="use-teams-admin-center"></a>使用 Teams 系統管理中心

在 Teams 系統管理中心：

1.  在左側導覽中，移至 [ **使用者] > [管理使用者** ]，然後選取該使用者。

2.  在 [使用者詳細資料] 頁面上，移至 **[語音信箱] 索引卷** 標。

3.  變更設定。

4.  選取 [儲存 **]**。


## <a name="use-powershell"></a>使用 PowerShell

您也可以使用 PowerShell 來管理語音信箱設定，如下所示：

- 若要管理個別使用者的雲端語音信箱設定，請使用[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) Cmdlet。 

- 若要檢視設定，請使用 [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) Cmdlet。

- 您可以使用[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) Cmdlet，並將 VoicemailEnabled 參數設為$false，來停用使用者的雲端語音信箱。 

## <a name="voicemail-settings"></a>語音信箱設定

- **已啟用語音信箱**- 此設定會控制使用者是否已啟用雲端語音信箱。 如果設定為 False，使用者將無法使用雲端語音信箱服務，也不會錄製使用者的語音信箱。

- **提示語言**- 此設定會指定雲端語音信箱中提示所使用的語言。 如需詳細資訊，請參閱 [變更問候語和電子郵件的預設語言](change-the-default-language-for-greetings-and-emails.md)。

- **問候語設定**- 雲端語音信箱能夠播放使用者在辦公室以及使用者不在辦公室時的特定問候語。 使用者可以錄製這兩個問候語，也可以使用文字轉換語音問候語。

  - **預設問候語提示字元覆寫** - 指定在使用者未錄製問候語時會播放的文字轉換語音問候語。

  - **啟用問候語** ： 指定不論 Outlook 設定為何，在語音信箱存取案例中是否都播放了不在辦公室問候語。

  - **Oof Greeting Follow Automatic Replies Enabled** - 指定是否要在使用者在 Outlook 中設定自動回復時，于語音信箱存款案例中播放不在辦公室問候語。

  - **Oof Greeting Follow Calendar Enabled** - 指定當使用者在行事曆中設定不在辦公室時，是否要在語音信箱存款案例中播放不在辦公室問候語。

  - **預設的問候語提示覆寫** - 指定在使用者不在辦公室且未錄製不在辦公室問候語時會播放的文字轉換語音問候語。

- **通話接聽規則** - 此設定會指定通話接聽規則。 規則可以是：
  - 服務拒絕通話而沒有訊息。
  - 只會播放一般或不在辦公室)  (相關的問候語。
  - 系統會播放一般或不在辦公室 (的相關問候語) ，並將來電者轉接到指定的使用者或電話號碼。
  -  系統會播放一般或不在辦公室 (相關的問候語) ，而來電者可以離開語音信箱。
  - 系統會播放一般或不在辦公室)  (相關的問候語，來電者可以離開語音信箱，並允許按 0 移轉至指定的使用者或電話號碼。

- **共用資料以改善服務** - 指定是否要與服務共用語音信箱和轉譯資料，以進行訓練並提高準確度。 如果設為 False，無論使用者選擇何種，語音信箱資料都不會共用。

- **來電轉接** - 指定轉接來電者的使用者或電話號碼。


