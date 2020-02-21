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
ms.openlocfilehash: 4698484c240322623760f1fd308398192bfb928f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="3ca67-102">（選用）歡迎使用者使用 Lync Server 2013 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="3ca67-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ca67-103">_**主題上次修改日期：** 2012年-09-30_</span><span class="sxs-lookup"><span data-stu-id="3ca67-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="3ca67-104">設定電話撥入式會議及測試來確認正常運作之後，您應該為使用者設定初始個人識別碼 (Pin)，並通知使用者有關的功能，包括簡介指示這類的可用性為初始 PIN 和電話撥入式會議設定網頁的連結。</span><span class="sxs-lookup"><span data-stu-id="3ca67-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="3ca67-105">此步驟是選用的。</span><span class="sxs-lookup"><span data-stu-id="3ca67-105">This step is optional.</span></span> <span data-ttu-id="3ca67-106">一般而言，您可以使用**Set-CsClientPin**指令程式來重設 pin 碼，但您可以使用此程序本主題中第一次如果您想要傳送歡迎電子郵件的資訊。</span><span class="sxs-lookup"><span data-stu-id="3ca67-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="3ca67-107">如果您不想要傳送電子郵件，您可以改為使用**Set-CsClientPin** 。</span><span class="sxs-lookup"><span data-stu-id="3ca67-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="3ca67-108">您可以設定 pin 碼，並將歡迎使用電子郵件傳送給單一使用者使用**Set-cspinsendcawelcomemail**指令碼。</span><span class="sxs-lookup"><span data-stu-id="3ca67-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="3ca67-109">根據預設，指令碼不會重設 pin 碼如果已設定，但您可以使用**強制**參數來強制重設 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="3ca67-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="3ca67-110">使用簡易郵件傳送通訊協定 (SMTP) 傳送電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="3ca67-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="3ca67-111">您可以建立指令碼反覆執行**Set-cspinsendcawelcomemail**指令碼以設定 pin 碼，並將電子郵件傳送給一群使用者。</span><span class="sxs-lookup"><span data-stu-id="3ca67-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="3ca67-112">您可以修改電子郵件範本 （也就是**CAWelcomeEmailTemplate.html**檔案） 將更多連結新增至內部網路頁面或修改電子郵件的文字。</span><span class="sxs-lookup"><span data-stu-id="3ca67-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="3ca67-113">若要設定初始 PIN 及傳送歡迎電子郵件</span><span class="sxs-lookup"><span data-stu-id="3ca67-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="3ca67-114">使用 RTCUniversalServerAdmins 群組成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="3ca67-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3ca67-115">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="3ca67-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3ca67-116">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3ca67-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="3ca67-117">**SmtpServer**   依預設，指令碼，請使用此參數的保留的環境變數 **$PSEmailServer**的值。</span><span class="sxs-lookup"><span data-stu-id="3ca67-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="3ca67-118">如果未設定 **$PSEmailServer**變數，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="3ca67-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="3ca67-119">**認證**   預設情況下，指令碼會使用目前使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="3ca67-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="3ca67-120">如果目前的使用者沒有權限可傳送電子郵件，代表指定的地址，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="3ca67-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="3ca67-121">一般而言，指定此參數，如果您未指定 From 地址為您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3ca67-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="3ca67-122">例如：</span><span class="sxs-lookup"><span data-stu-id="3ca67-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="3ca67-123">本範例會建立新的 pin 碼，並再從 Marco 傳送歡迎電子郵件給 Bob。</span><span class="sxs-lookup"><span data-stu-id="3ca67-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="3ca67-124">它會使用預設的範本中的電子郵件文字，並建立電子郵件訊息以 HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="3ca67-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="3ca67-125">預設值主旨為 「 歡迎使用至撥號對應表中會議 」。</span><span class="sxs-lookup"><span data-stu-id="3ca67-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="3ca67-126">另一個範例：</span><span class="sxs-lookup"><span data-stu-id="3ca67-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="3ca67-127">本範例會在即使 Bob 有現有的 pin 碼，並再從 Marco 傳送歡迎電子郵件給 Bob，會強制 Bob、 的值為 「 383042650 」 的新 PIN。</span><span class="sxs-lookup"><span data-stu-id="3ca67-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="3ca67-128">因為指定 Credential 參數，則執行命令的人員會提示您輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="3ca67-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="3ca67-129">使用 Secure Sockets Layer (SSL) 會傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3ca67-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

