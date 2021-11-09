---
title: 將歡迎電子郵件傳送至商務用 Skype Server 中的撥入使用者
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 摘要：瞭解如何在商務用 Skype Server 中歡迎使用者使用電話撥入式會議。
ms.openlocfilehash: 672e386c223e2b5b9f872334634ac315c9e900e1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848536"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>將歡迎電子郵件傳送至商務用 Skype Server 中的撥入使用者
 
**摘要：** 瞭解如何在商務用 Skype Server 中歡迎使用者使用電話撥入式會議。
  
設定電話撥入式會議並測試以確認其運作正常之後，您應該為使用者 (Pin) 設定初始個人識別碼，並通知使用者有關該功能的可用性。 您可以加入簡介（如初始 PIN）和電話撥入式會議設定網頁的連結。 
  
一般來說，您可以使用 **unlock-csclientpin 指令程式** 來重設 pin，但是如果您想要使用 PIN 資訊傳送簡介的歡迎電子郵件，您可以使用本主題中的程式。 如果您不想要傳送電子郵件，您可以使用 **unlock-csclientpin** 代替。
  
您可以使用 **Set-CsPinSendCAWelcomeMail** 腳本來設定 PIN，並將歡迎電子郵件傳送給單一使用者。 根據預設，如果已設定 PIN 碼，腳本不會重設它，但是您可以使用 Force 參數強制重設 PIN 碼。 電子郵件會使用簡易郵件傳送通訊協定 (SMTP) 傳送。
  
您可以建立腳本，以反復執行 **Set-CsPinSendCAWelcomeMail** 腳本，以設定 pin 並傳送電子郵件給使用者群組。 您可以修改電子郵件範本 (也就是 CAWelcomeEmailTemplate.html 檔) ，以新增更多內部網路頁面連結或修改電子郵件文字。
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>設定初始 PIN 碼並傳送歡迎電子郵件

1. 以 RTCUniversalServerAdmins 群組成員的身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 在命令提示字元中執行下列命令：
    
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

**SmtpServer** 根據預設，腳本會為此參數使用保留環境變數的值 **$PSEmailServer** 。 如果未設定 **$PSEmailServer** 變數，您必須指定此參數。
    
**認證** 腳本預設會使用目前使用者的認證。 如果目前的使用者沒有代表指定的寄件者位址傳送電子郵件的許可權，您必須指定此參數。 如果您未將電子郵件地址指定為 [寄件者] 位址，請將此參數指定為一般規則。
    
下列範例會建立新的 PIN 碼，然後從 Marco 將歡迎電子郵件傳送至王俊元。 它會使用預設範本中的電子郵件文字，並以 HTML 格式建立電子郵件。 預設主題為「歡迎使用撥號對應表」：
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

下一個範例會強制小明值為 "383042650" 的新 PIN 碼，即使王俊元已有現有的 PIN 碼，然後再將歡迎電子郵件從 Marco 傳送至王俊元。 因為已指定 Credential 參數，所以會提示執行該命令的人員輸入密碼。 使用安全通訊端層 (SSL) 傳送電子郵件：
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
