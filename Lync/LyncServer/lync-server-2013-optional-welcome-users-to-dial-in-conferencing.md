---
title: Lync Server 2013：) 歡迎使用者加入電話撥入式會議的 (選用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde04364faf306983f5008539c2ccc6f248955bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522250"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中 (選用) 歡迎使用者撥入式會議

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

設定電話撥入式會議並測試以確認其運作正常之後，您應該為使用者設定初始個人識別碼 () Pin 碼，並通知使用者有關該功能的可用性，包含諸如初始 PIN 碼和電話撥入式會議設定網頁的連結等介紹性指示。 這是選擇性的步驟。 一般來說，您可以使用 **unlock-csclientpin 指令程式** 來重設 pin，但是如果您想要使用此資訊傳送歡迎電子郵件，您可以使用本主題中的程式。 如果您不想要傳送電子郵件，您可以使用 **unlock-csclientpin** 代替。

您可以使用 **Set-CsPinSendCAWelcomeMail** 腳本來設定 PIN，並將歡迎電子郵件傳送給單一使用者。 根據預設，如果已設定 PIN 碼，腳本不會重設它，但是您可以使用 **force** 參數強制重設 pin 碼。 電子郵件會使用簡易郵件傳送通訊協定 (SMTP) 傳送。

您可以建立腳本，以反復執行 **Set-CsPinSendCAWelcomeMail** 腳本，以設定 pin 並傳送電子郵件給使用者群組。 您可以修改電子郵件範本 (，也就是 **CAWelcomeEmailTemplate.html** 檔) ，以新增更多內部網路網頁連結或修改電子郵件文字。

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>設定初始 PIN 並傳送歡迎電子郵件

1.  以 RTCUniversalServerAdmins 群組成員的身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
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
    
    **SmtpServer**    根據預設，腳本會為此參數使用保留環境變數的值 **$PSEmailServer** 。 如果未設定 **$PSEmailServer** 變數，您必須指定此參數。
    
    **認證**    腳本預設會使用目前使用者的認證。 如果目前的使用者沒有代表指定的寄件者位址傳送電子郵件的許可權，您必須指定此參數。 如果您未將電子郵件地址指定為 [寄件者] 位址，請將此參數指定為一般規則。
    
    例如：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    本範例會建立新的 PIN 碼，然後從 Marco 將歡迎電子郵件傳送至王俊元。 它會使用預設範本中的電子郵件文字，並以 HTML 格式建立電子郵件。 預設主題為「歡迎使用撥號會議」。
    
    另一個範例：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    這個範例會強制小明值為 "383042650" 的新 PIN 碼，即使王俊元已有現有的 PIN 碼，然後再將歡迎電子郵件從 Marco 傳送至王俊元。 因為已指定 Credential 參數，所以會提示執行該命令的人員輸入密碼。 使用安全通訊端層 (SSL) 傳送電子郵件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

