---
title: Lync Server 2013：針對綜合交易使用豐富記錄
description: Lync Server 2013：針對綜合交易使用豐富記錄。
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
ms.openlocfilehash: 5fd984386985bced64265ebedfd57c56a84a4443
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580299"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="4ac9f-103">在 Lync Server 2013 中使用綜合交易記錄的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="4ac9f-103">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ac9f-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4ac9f-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4ac9f-105">綜合交易 (引進于 Microsoft Lync Server 2010 中) 提供一種方法，讓系統管理員確認使用者是否可以成功完成常見工作，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-105">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="4ac9f-106">這些測試 (會打包成一組 Lync Server Windows PowerShell Cmdlet) 可由系統管理員手動執行，也可以由系統 Center Operations Manager 等應用程式自動執行。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-106">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="4ac9f-107">在 Lync Server 2010 中，已證實綜合交易非常有用，可協助系統管理員識別系統的問題。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-107">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="4ac9f-108">例如， **Test-CsRegistration** 指令程式可能會提醒系統管理員某些使用者在使用 Lync Server 註冊時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-108">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="4ac9f-109">不過，「綜合交易」在協助系統管理員決定這些使用者在使用 Lync Server 註冊時有困難的用處稍少。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-109">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="4ac9f-110">這是因為綜合交易沒有提供詳細的記錄資訊，可協助管理員對 Lync Server 的問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-110">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="4ac9f-111">綜合交易的詳細資訊輸出充其量只能提供逐步資訊，讓系統管理員能夠根據經驗來猜測可能發生問題的地方。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-111">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="4ac9f-112">在 Microsoft Lync Server 2013 中，綜合交易已重新設計為提供豐富的記錄功能。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-112">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="4ac9f-113">「豐富的記錄」表示將針對綜合交易所進行的每個活動記錄如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="4ac9f-113">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="4ac9f-114">活動開始時間</span><span class="sxs-lookup"><span data-stu-id="4ac9f-114">The time that the activity started</span></span>

  - <span data-ttu-id="4ac9f-115">活動完成時間</span><span class="sxs-lookup"><span data-stu-id="4ac9f-115">The time that the activity finished</span></span>

  - <span data-ttu-id="4ac9f-116">執行的動作 (例如，建立、加入或離開會議）;登入 Lync 伺服器;傳送立即訊息;以此類推) </span><span class="sxs-lookup"><span data-stu-id="4ac9f-116">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="4ac9f-117">活動執行時所產生的資訊、詳細資料、警告或錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="4ac9f-117">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="4ac9f-118">SIP 登錄訊息</span><span class="sxs-lookup"><span data-stu-id="4ac9f-118">SIP registration messages</span></span>

  - <span data-ttu-id="4ac9f-119">活動執行時所產生的例外狀況記錄或診斷碼</span><span class="sxs-lookup"><span data-stu-id="4ac9f-119">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="4ac9f-120">執行活動的最終結果</span><span class="sxs-lookup"><span data-stu-id="4ac9f-120">The net result of running the activity</span></span>

<span data-ttu-id="4ac9f-121">每次執行綜合交易時，會自動產生這項資訊。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-121">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="4ac9f-122">不過，此資訊不會自動顯示或儲存至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-122">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="4ac9f-123">相反地，手動執行綜合交易的系統管理員可以使用 OutLoggerVariable 參數來指定將儲存資訊的 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-123">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="4ac9f-124">然後，系統管理員可以使用一組方法，讓他們能夠以 XML 或 HTML 格式儲存及/或查看 rtf 記錄。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-124">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="4ac9f-125">例如，Lync Server 2010 系統管理員可能會使用類似下列的命令執行 **Test-CsRegistration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4ac9f-125">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="4ac9f-126">系統管理員可以選擇在他們選擇的變數名稱之後包含 OutLoggerVariable 參數：</span><span class="sxs-lookup"><span data-stu-id="4ac9f-126">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="4ac9f-p105">請不要在變數名稱的開頭加上 $ 字元。請使用像是 RegistrationTest 的變數名稱，而不要使用 $RegistrationTest。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="4ac9f-129">上述命令輸出內容如下：</span><span class="sxs-lookup"><span data-stu-id="4ac9f-129">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="4ac9f-p106">不過，系統會顯示更多關於此次失敗的詳細資訊，而不只是上述顯示的錯誤訊息。若要使用 HTML 格式存取該資訊，請使用類似下列的命令，以便將儲存於變數 RegistrationTest 中的資訊儲存至 HTML 檔案：</span><span class="sxs-lookup"><span data-stu-id="4ac9f-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="4ac9f-132">或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="4ac9f-132">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="4ac9f-133">然後，您可以使用 Internet Explorer、Visual Studio 或任何其他能夠開啟 HTML/XML 檔案的應用程式來查看這些檔案。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-133">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="4ac9f-134">在 System Center Operations Manager 內執行的綜合交易，會自動產生這些記錄檔失敗。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-134">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="4ac9f-135">不過，如果執行失敗，Windows PowerShell 能夠載入並執行綜合交易，將不會產生這些記錄。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-135">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="4ac9f-136">Lync Server 2013 預設會將記錄檔儲存至未共用的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-136">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="4ac9f-137">若要讓這些記錄立即可供存取，您應該共用此資料夾 (例如 \\ \\ atl-觀察程式-001 litwareinc。 com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="4ac9f-137">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

