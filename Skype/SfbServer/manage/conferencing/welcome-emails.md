---
title: 在商務用 Skype Server 中將歡迎電子郵件傳送至撥入使用者
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 摘要：瞭解如何在商務用 Skype Server 中歡迎使用者使用電話撥入式會議。
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817493"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="ff8d4-103">在商務用 Skype Server 中將歡迎電子郵件傳送至撥入使用者</span><span class="sxs-lookup"><span data-stu-id="ff8d4-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="ff8d4-104">**摘要：** 瞭解如何在商務用 Skype Server 中歡迎使用者使用電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="ff8d4-105">設定電話撥入式會議並測試以確認其運作正常之後，您應該為使用者 (Pin) 設定初始個人識別碼，並通知使用者有關該功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="ff8d4-106">您可以加入簡介說明，例如初始 PIN 碼，以及撥入式會議設定網頁的連結。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="ff8d4-107">一般來說，您可以使用 **unlock-csclientpin 指令程式** 來重設 pin，但是如果您想要使用 PIN 資訊傳送簡介的歡迎電子郵件，您可以使用本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="ff8d4-108">如果您不想要傳送電子郵件，您可以使用 **unlock-csclientpin** 代替。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="ff8d4-109">您可以使用 **Set-CsPinSendCAWelcomeMail** 腳本來設定 PIN，並將歡迎電子郵件傳送給單一使用者。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="ff8d4-110">根據預設，如果已設定 PIN 碼，腳本不會重設它，但是您可以使用 Force 參數強制重設 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="ff8d4-111">電子郵件會使用簡易郵件傳送通訊協定 (SMTP) 傳送。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="ff8d4-112">您可以建立腳本，以反復執行 **Set-CsPinSendCAWelcomeMail** 腳本，以設定 pin 並傳送電子郵件給使用者群組。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="ff8d4-113">您可以修改電子郵件範本 (，也就是 CAWelcomeEmailTemplate.html 檔) ，以新增更多內部網路網頁連結或修改電子郵件文字。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="ff8d4-114">設定初始 PIN 碼並傳送歡迎電子郵件</span><span class="sxs-lookup"><span data-stu-id="ff8d4-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="ff8d4-115">以 RTCUniversalServerAdmins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ff8d4-116">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ff8d4-117">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ff8d4-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="ff8d4-118">**SmtpServer** 根據預設，腳本會為此參數使用保留環境變數的值 **$PSEmailServer** 。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="ff8d4-119">如果未設定 **$PSEmailServer** 變數，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="ff8d4-120">**認證** 腳本預設會使用目前使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="ff8d4-121">如果目前的使用者沒有代表指定的寄件者位址傳送電子郵件的許可權，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="ff8d4-122">如果您未將電子郵件地址指定為 [寄件者] 位址，請將此參數指定為一般規則。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="ff8d4-123">下列範例會建立新的 PIN 碼，然後從 Marco 將歡迎電子郵件傳送至王俊元。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="ff8d4-124">它會使用預設範本中的電子郵件文字，並以 HTML 格式建立電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="ff8d4-125">預設主題為「歡迎使用撥號對應表」：</span><span class="sxs-lookup"><span data-stu-id="ff8d4-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="ff8d4-126">下一個範例會強制小明值為 "383042650" 的新 PIN 碼，即使王俊元已有現有的 PIN 碼，然後再將歡迎電子郵件從 Marco 傳送至王俊元。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="ff8d4-127">因為已指定 Credential 參數，所以會提示執行該命令的人員輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="ff8d4-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="ff8d4-128">使用安全通訊端層 (SSL) 傳送電子郵件：</span><span class="sxs-lookup"><span data-stu-id="ff8d4-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
