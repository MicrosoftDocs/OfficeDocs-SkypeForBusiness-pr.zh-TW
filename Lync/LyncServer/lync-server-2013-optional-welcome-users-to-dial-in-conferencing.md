---
title: Lync Server 2013：(選用) 歡迎使用者使用電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3defde18a01ed09ac529ba9b289749f28c4cdd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="f836e-102">(選用) 在 Lync Server 2013 中歡迎使用者使用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="f836e-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f836e-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="f836e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="f836e-104">設定電話撥入式會議並測試以確認其運作正常之後，您應該為使用者設定初始個人識別碼（Pin），並通知使用者有關功能的可用性，包括介紹性指示（例如作為初始 PIN，以及 [電話撥入式會議設定] 網頁的連結。</span><span class="sxs-lookup"><span data-stu-id="f836e-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="f836e-105">此為選用步驟。</span><span class="sxs-lookup"><span data-stu-id="f836e-105">This step is optional.</span></span> <span data-ttu-id="f836e-106">通常，您可以使用**CsClientPin** Cmdlet 來重設 pin，但如果您想要傳送含資訊的歡迎電子郵件，第一次使用本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="f836e-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="f836e-107">如果您不想傳送電子郵件，您可以改為使用 [**設定] CsClientPin** 。</span><span class="sxs-lookup"><span data-stu-id="f836e-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="f836e-108">您可以使用**CsPinSendCAWelcomeMail**腳本來設定 PIN，並將歡迎電子郵件傳送給單一使用者。</span><span class="sxs-lookup"><span data-stu-id="f836e-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="f836e-109">根據預設，如果已設定 PIN，腳本就不會重設它，但您可以使用**force**參數來強制重設 pin。</span><span class="sxs-lookup"><span data-stu-id="f836e-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="f836e-110">電子郵件訊息是使用簡易郵件傳輸通訊協定（SMTP）傳送。</span><span class="sxs-lookup"><span data-stu-id="f836e-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="f836e-111">您可以建立腳本，以反復執行**CsPinSendCAWelcomeMail**腳本來設定 pin，並將電子郵件傳送給一組使用者。</span><span class="sxs-lookup"><span data-stu-id="f836e-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="f836e-112">您可以修改電子郵件範本（也就是**CAWelcomeEmailTemplate**檔案），以新增更多 intranet 頁面連結或修改電子郵件文字。</span><span class="sxs-lookup"><span data-stu-id="f836e-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="f836e-113">設定初始 PIN 並傳送歡迎電子郵件</span><span class="sxs-lookup"><span data-stu-id="f836e-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="f836e-114">以 RTCUniversalServerAdmins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="f836e-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f836e-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f836e-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f836e-116">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f836e-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="f836e-117">**SmtpServer**   根據預設，腳本會針對此參數使用保留環境變數的值 **$PSEmailServer** 。</span><span class="sxs-lookup"><span data-stu-id="f836e-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="f836e-118">如果未設定 **$PSEmailServer**變數，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="f836e-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="f836e-119">**認證**   根據預設，腳本會使用目前使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="f836e-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="f836e-120">如果目前的使用者沒有代表指定寄件者位址傳送電子郵件的許可權，您必須指定此參數。</span><span class="sxs-lookup"><span data-stu-id="f836e-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="f836e-121">一般來說，如果您沒有將您的電子郵件地址指定為 [寄件者] 位址，請指定此參數。</span><span class="sxs-lookup"><span data-stu-id="f836e-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="f836e-122">例如：</span><span class="sxs-lookup"><span data-stu-id="f836e-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="f836e-123">這個範例會建立新的 PIN，然後將歡迎電子郵件從 Marco 傳送到 Bob。</span><span class="sxs-lookup"><span data-stu-id="f836e-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="f836e-124">它會使用預設範本中的電子郵件文字，並以 HTML 格式建立電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="f836e-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="f836e-125">預設主旨為「歡迎使用電話撥入會議」。</span><span class="sxs-lookup"><span data-stu-id="f836e-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="f836e-126">另一個範例：</span><span class="sxs-lookup"><span data-stu-id="f836e-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="f836e-127">這個範例會強制 Bob 的值為 "383042650" 的新 PIN，即使 Bob 有現有的 PIN，然後從 Marco 傳送歡迎電子郵件至王俊元。</span><span class="sxs-lookup"><span data-stu-id="f836e-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="f836e-128">因為已指定 Credential 參數，所以執行命令的人員會收到輸入密碼的提示。</span><span class="sxs-lookup"><span data-stu-id="f836e-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="f836e-129">電子郵件是使用安全通訊端層（SSL）傳送。</span><span class="sxs-lookup"><span data-stu-id="f836e-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

