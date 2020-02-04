---
title: Lync Server 2013：針對綜合交易使用豐富的記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="14114-102">在 Lync Server 2013 中使用 [綜合交易] 的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="14114-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14114-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="14114-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="14114-104">綜合交易（在 Microsoft Lync Server 2010 中引進）提供一種方式，讓系統管理員確認使用者能夠成功完成一般工作，例如登入系統、交換立即訊息，或撥打電話給在公用交換電話網絡（PSTN）上。</span><span class="sxs-lookup"><span data-stu-id="14114-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="14114-105">這些測試（封裝為一組 Lync Server Windows PowerShell Cmdlet）可以由系統管理員手動執行，或由 System Center Operations Manager 等應用程式自動執行。</span><span class="sxs-lookup"><span data-stu-id="14114-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="14114-106">在 Lync Server 2010 中，綜合交易已證實在協助管理員找出系統問題時非常有用。</span><span class="sxs-lookup"><span data-stu-id="14114-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="14114-107">例如， **CsRegistration** Cmdlet 會提醒管理員，這是因為有些使用者難以在 Lync Server 註冊。</span><span class="sxs-lookup"><span data-stu-id="14114-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="14114-108">不過，綜合交易在協助管理員決定這些使用者為何無法使用 Lync Server 進行註冊，這種方式不太有用。</span><span class="sxs-lookup"><span data-stu-id="14114-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="14114-109">這是因為綜合交易不提供詳細的記錄資訊，可協助系統管理員針對 Lync Server 的問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="14114-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="14114-110">從綜合交易的詳細資料輸出中，提供的逐步資訊可能會讓系統管理員在可能的情況下，讓您有權猜到發生問題的位置。</span><span class="sxs-lookup"><span data-stu-id="14114-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="14114-111">在 Microsoft Lync Server 2013 中，已重新設計綜合交易來提供豐富的記錄。</span><span class="sxs-lookup"><span data-stu-id="14114-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="14114-112">"豐富記錄" 代表，對於綜合交易 undertakes 的每個活動，都會錄製如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="14114-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="14114-113">活動開始的時間</span><span class="sxs-lookup"><span data-stu-id="14114-113">The time that the activity started</span></span>

  - <span data-ttu-id="14114-114">活動的完成時間</span><span class="sxs-lookup"><span data-stu-id="14114-114">The time that the activity finished</span></span>

  - <span data-ttu-id="14114-115">所執行的動作（例如，建立、加入或離開會議; 登入 Lync Server; 傳送即時消息; 等等）</span><span class="sxs-lookup"><span data-stu-id="14114-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="14114-116">當活動執行時產生的資訊、詳細、警告或錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="14114-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="14114-117">SIP 註冊訊息</span><span class="sxs-lookup"><span data-stu-id="14114-117">SIP registration messages</span></span>

  - <span data-ttu-id="14114-118">在活動執行時產生的例外記錄或診斷程式代碼</span><span class="sxs-lookup"><span data-stu-id="14114-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="14114-119">執行活動的最終結果</span><span class="sxs-lookup"><span data-stu-id="14114-119">The net result of running the activity</span></span>

<span data-ttu-id="14114-120">這項資訊會在每次執行綜合交易時自動產生。</span><span class="sxs-lookup"><span data-stu-id="14114-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="14114-121">不過，資訊不會自動顯示或儲存至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="14114-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="14114-122">相反地，手動執行綜合交易的系統管理員可以使用 OutLoggerVariable 參數來指定要儲存資訊的 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="14114-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="14114-123">然後，管理員就可以使用一組方法，讓他們以 XML 或 HTML 格式儲存及/或查看豐富記錄。</span><span class="sxs-lookup"><span data-stu-id="14114-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="14114-124">例如，Lync Server 2010 系統管理員可以使用類似下列的命令來執行**CsRegistration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="14114-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="14114-125">系統管理員可以選擇包含 OutLoggerVariable 參數，後面接著其選擇的變數名稱：</span><span class="sxs-lookup"><span data-stu-id="14114-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="14114-126">請勿在變數名稱前面加上 $ 字元。</span><span class="sxs-lookup"><span data-stu-id="14114-126">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="14114-127">使用變數名稱（例如 RegistrationTest，而非 $RegistrationTest）。</span><span class="sxs-lookup"><span data-stu-id="14114-127">Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="14114-128">上述命令會輸出如下所示的內容：</span><span class="sxs-lookup"><span data-stu-id="14114-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="14114-129">不過，這項失敗的詳細資訊比上述所示的錯誤訊息更多。</span><span class="sxs-lookup"><span data-stu-id="14114-129">However, much more detailed information is available for this failure than just the error message shown above.</span></span> <span data-ttu-id="14114-130">若要以 HTML 格式存取該資訊，請使用類似以下的命令，將儲存在可變 RegistrationTest 中的資訊儲存為 HTML 檔案：</span><span class="sxs-lookup"><span data-stu-id="14114-130">To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="14114-131">或者，您也可以使用 ToXML （）方法將資料儲存至 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="14114-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="14114-132">然後，您就可以使用 Internet Explorer、Visual Studio 或任何能夠開啟 HTML/XML 檔案的任何其他應用程式來查看這些檔案。</span><span class="sxs-lookup"><span data-stu-id="14114-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="14114-133">從系統中心作業管理員內部執行的綜合交易，會自動產生這些記錄檔案，以尋找失敗。</span><span class="sxs-lookup"><span data-stu-id="14114-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="14114-134">不過，如果在 Windows PowerShell 能夠載入並執行綜合交易之前執行失敗，就不會產生這些記錄。</span><span class="sxs-lookup"><span data-stu-id="14114-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="14114-135">根據預設，Lync Server 2013 會將記錄檔案儲存到未共用的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="14114-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="14114-136">若要讓這些記錄易於存取，您應該共用此資料夾（例如\\ \\atl-觀察程式-001. litwareinc. com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="14114-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

