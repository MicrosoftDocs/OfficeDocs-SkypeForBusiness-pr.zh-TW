---
title: Lync Server 2013：) 歡迎使用者加入電話撥入式會議的 (選用
description: Lync Server 2013： (選用) 歡迎使用者加入電話撥入式會議。
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
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546899"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="b641d-103">在 Lync Server 2013 中 (選用) 歡迎使用者撥入式會議</span><span class="sxs-lookup"><span data-stu-id="b641d-103">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b641d-104">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b641d-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b641d-105">設定電話撥入式會議並測試以確認其運作正常之後，您應該為使用者設定初始個人識別碼 () Pin 碼，並通知使用者有關該功能的可用性，包含諸如初始 PIN 碼和電話撥入式會議設定網頁的連結等介紹性指示。</span><span class="sxs-lookup"><span data-stu-id="b641d-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="b641d-106">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="b641d-106">This step is optional.</span></span> <span data-ttu-id="b641d-107">一般來說，您可以使用 **unlock-csclientpin 指令程式** 來重設 pin，但是如果您想要使用此資訊傳送歡迎電子郵件，您可以使用本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="b641d-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="b641d-108">如果您不想要傳送電子郵件，您可以使用 **unlock-csclientpin** 代替。</span><span class="sxs-lookup"><span data-stu-id="b641d-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="b641d-109">您可以使用 **Set-CsPinSendCAWelcomeMail** 腳本來設定 PIN，並將歡迎電子郵件傳送給單一使用者。</span><span class="sxs-lookup"><span data-stu-id="b641d-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="b641d-110">根據預設，如果已設定 PIN 碼，腳本不會重設它，但是您可以使用 **force** 參數強制重設 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="b641d-110">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="b641d-111">電子郵件會使用簡易郵件傳送通訊協定 (SMTP) 傳送。</span><span class="sxs-lookup"><span data-stu-id="b641d-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="b641d-112">您可以建立腳本，以反復執行 **Set-CsPinSendCAWelcomeMail** 腳本，以設定 pin 並傳送電子郵件給使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b641d-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="b641d-113">您可以修改電子郵件範本 (，也就是 **CAWelcomeEmailTemplate.html** 檔) ，以新增更多內部網路網頁連結或修改電子郵件文字。</span><span class="sxs-lookup"><span data-stu-id="b641d-113">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="b641d-114">設定初始 PIN 並傳送歡迎電子郵件</span><span class="sxs-lookup"><span data-stu-id="b641d-114">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="b641d-115">以 RTCUniversalServerAdmins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="b641d-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b641d-116">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b641d-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b641d-117">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b641d-117">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="b641d-118">**SmtpServer**    根據預設，腳本會為此參數使用保留環境變數的值 **$PSEmailServer** 。</span><span class="sxs-lookup"><span data-stu-id="b641d-118">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="b641d-119">如果未設定 **$PSEmailServer** 變數，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="b641d-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="b641d-120">**認證**    腳本預設會使用目前使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="b641d-120">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="b641d-121">如果目前的使用者沒有代表指定的寄件者位址傳送電子郵件的許可權，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="b641d-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="b641d-122">如果您未將電子郵件地址指定為 [寄件者] 位址，請將此參數指定為一般規則。</span><span class="sxs-lookup"><span data-stu-id="b641d-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="b641d-123">例如：</span><span class="sxs-lookup"><span data-stu-id="b641d-123">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="b641d-124">本範例會建立新的 PIN 碼，然後從 Marco 將歡迎電子郵件傳送至王俊元。</span><span class="sxs-lookup"><span data-stu-id="b641d-124">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="b641d-125">它會使用預設範本中的電子郵件文字，並以 HTML 格式建立電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b641d-125">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="b641d-126">預設主題為「歡迎使用撥號會議」。</span><span class="sxs-lookup"><span data-stu-id="b641d-126">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="b641d-127">另一個範例：</span><span class="sxs-lookup"><span data-stu-id="b641d-127">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="b641d-128">這個範例會強制小明值為 "383042650" 的新 PIN 碼，即使王俊元已有現有的 PIN 碼，然後再將歡迎電子郵件從 Marco 傳送至王俊元。</span><span class="sxs-lookup"><span data-stu-id="b641d-128">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="b641d-129">因為已指定 Credential 參數，所以會提示執行該命令的人員輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="b641d-129">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="b641d-130">使用安全通訊端層 (SSL) 傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b641d-130">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

