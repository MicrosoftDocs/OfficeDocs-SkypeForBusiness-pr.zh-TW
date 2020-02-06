---
title: 在商務用 Skype Server 中傳送歡迎電子郵件給撥入使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 摘要：瞭解如何在商務用 Skype Server 中歡迎使用者撥入式會議。
ms.openlocfilehash: 6228d0636e878ccf9a208edf9afeee3fe1e808f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818434"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>在商務用 Skype Server 中傳送歡迎電子郵件給撥入使用者
 
**摘要：** 瞭解如何在商務用 Skype Server 中歡迎使用者撥入會議。
  
在您設定電話撥入式會議並進行測試以確認其運作正常之後，您應該為使用者設定初始個人識別碼（Pin），並通知使用者該功能的可用性。 您可以加入介紹性指示（例如初始 PIN），以及 [電話撥入式會議設定] 網頁的連結。 
  
通常，您可以使用**CsClientPin** Cmdlet 來重設 pin，但如果您想要傳送帶 PIN 資訊的簡介式歡迎電子郵件，您可以使用本主題中的程式。 如果您不想傳送電子郵件，您可以改為使用 [**設定] CsClientPin** 。
  
您可以使用**CsPinSendCAWelcomeMail**腳本來設定 PIN，並將歡迎電子郵件傳送給單一使用者。 根據預設，如果已設定 PIN，腳本就不會重設它，但您可以使用 Force 參數來強制重設 PIN。 電子郵件訊息是使用簡易郵件傳輸通訊協定（SMTP）傳送。
  
您可以建立腳本，以反復執行**CsPinSendCAWelcomeMail**腳本來設定 pin，並將電子郵件傳送給一組使用者。 您可以修改電子郵件範本（也就是 CAWelcomeEmailTemplate 檔案），以新增更多 intranet 頁面連結或修改電子郵件文字。
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>設定初始 PIN 並傳送歡迎電子郵件

1. 以 RTCUniversalServerAdmins 群組成員的身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令提示字元執行下列動作：
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer**根據預設，腳本會針對此參數使用保留環境變數的值 **$PSEmailServer** 。 如果未設定 **$PSEmailServer**變數，您必須指定此參數。
    
**認證**根據預設，腳本會使用目前使用者的認證。 如果目前的使用者沒有代表指定寄件者位址傳送電子郵件的許可權，您必須指定此參數。 一般來說，如果您沒有將您的電子郵件地址指定為 [寄件者] 位址，請指定此參數。
    
下列範例會建立新的 PIN，然後將歡迎電子郵件從 Marco 傳送到 Bob。 它會使用預設範本中的電子郵件文字，並以 HTML 格式建立電子郵件訊息。 預設主旨為「歡迎使用電話撥入會議」：
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

下一個範例會針對王俊元強制值為 "383042650" 的新 PIN，即使 Bob 有現有的 PIN，然後從 Marco 傳送歡迎電子郵件給 Bob。 因為已指定 Credential 參數，所以執行命令的人員會收到輸入密碼的提示。 電子郵件是使用安全通訊端層（SSL）來傳送：
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
