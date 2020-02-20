---
title: 'Lync Server 2013: （選用） 歡迎使用者使用電話撥入式會議'
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
ms.openlocfilehash: d3a949d1de2c3237e1cd432297a1ce1e1a7f3543
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>（選用）歡迎使用者使用 Lync Server 2013 中的電話撥入式會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-30_

設定電話撥入式會議及測試來確認正常運作之後，您應該為使用者設定初始個人識別碼 (Pin)，並通知使用者有關的功能，包括簡介指示這類的可用性為初始 PIN 和電話撥入式會議設定網頁的連結。 此步驟是選用的。 一般而言，您可以使用**Set-CsClientPin**指令程式來重設 pin 碼，但您可以使用此程序本主題中第一次如果您想要傳送歡迎電子郵件的資訊。 如果您不想要傳送電子郵件，您可以改為使用**Set-CsClientPin** 。

您可以設定 pin 碼，並將歡迎使用電子郵件傳送給單一使用者使用**Set-cspinsendcawelcomemail**指令碼。 根據預設，指令碼不會重設 pin 碼如果已設定，但您可以使用**強制**參數來強制重設 pin 碼。 使用簡易郵件傳送通訊協定 (SMTP) 傳送電子郵件訊息。

您可以建立指令碼反覆執行**Set-cspinsendcawelcomemail**指令碼以設定 pin 碼，並將電子郵件傳送給一群使用者。 您可以修改電子郵件範本 （也就是**CAWelcomeEmailTemplate.html**檔案） 將更多連結新增至內部網路頁面或修改電子郵件的文字。

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>若要設定初始 PIN 及傳送歡迎電子郵件

1.  使用 RTCUniversalServerAdmins 群組成員身分登入。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

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
    
    **SmtpServer**   依預設，指令碼，請使用此參數的保留的環境變數 **$PSEmailServer**的值。 如果未設定 **$PSEmailServer**變數，您必須指定此參數。
    
    **認證**   預設情況下，指令碼會使用目前使用者的認證。 如果目前的使用者沒有權限可傳送電子郵件，代表指定的地址，您必須指定此參數。 一般而言，指定此參數，如果您未指定 From 地址為您的電子郵件地址。
    
    例如：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    本範例會建立新的 pin 碼，並再從 Marco 傳送歡迎電子郵件給 Bob。 它會使用預設的範本中的電子郵件文字，並建立電子郵件訊息以 HTML 格式。 預設值主旨為 「 歡迎使用至撥號對應表中會議 」。
    
    另一個範例：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    本範例會在即使 Bob 有現有的 pin 碼，並再從 Marco 傳送歡迎電子郵件給 Bob，會強制 Bob、 的值為 「 383042650 」 的新 PIN。 因為指定 Credential 參數，則執行命令的人員會提示您輸入密碼。 使用 Secure Sockets Layer (SSL) 會傳送電子郵件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

