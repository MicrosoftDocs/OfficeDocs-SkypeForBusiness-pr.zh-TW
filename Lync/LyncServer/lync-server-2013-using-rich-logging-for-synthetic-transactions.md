---
title: Lync Server 2013： 使用綜合交易的豐富記錄
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
ms.openlocfilehash: dc43a38a1c6060827755c958ac071fa63608556f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="d4dfe-102">使用 Lync Server 2013 中的綜合交易的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="d4dfe-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4dfe-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="d4dfe-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d4dfe-104">綜合交易 （Microsoft Lync Server 2010 中引進） 提供讓系統管理員來確認使用者能夠成功完成 [登入系統、 交換立即訊息，或撥打電話到位於電話等一般工作公用交換電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d4dfe-105">可以手動進行這些測試 （這會封裝成一組 Lync Server Windows PowerShell cmdlet），由系統管理員，或他們可自動執行的應用程式，例如 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="d4dfe-106">Lync Server 2010 中的綜合交易，證明中協助識別系統問題的系統管理員非常有用。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="d4dfe-107">例如， **Test-csregistration** cmdlet 無法發出警示系統管理員一些使用者已有困難註冊搭配 Lync Server 的事實。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="d4dfe-108">然而，如果綜合交易是比較沒有幫助判斷為什麼這些使用者已困難註冊搭配 Lync Server 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="d4dfe-109">這已經因為綜合交易未提供可協助您遇到了 Lync Server 系統管理員的詳細的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="d4dfe-110">綜合交易的詳細資訊輸出充其量只能提供逐步資訊，讓系統管理員能夠根據經驗來猜測可能發生問題的地方。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="d4dfe-111">在 [Microsoft Lync Server 2013，綜合交易都已重新架構提供豐富的記錄。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="d4dfe-112">「豐富的記錄」表示將針對綜合交易所進行的每個活動記錄如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="d4dfe-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="d4dfe-113">活動開始時間</span><span class="sxs-lookup"><span data-stu-id="d4dfe-113">The time that the activity started</span></span>

  - <span data-ttu-id="d4dfe-114">活動完成時間</span><span class="sxs-lookup"><span data-stu-id="d4dfe-114">The time that the activity finished</span></span>

  - <span data-ttu-id="d4dfe-115">已執行的動作 （例如，建立、 加入或離開會議; 登入 Lync Server; 傳送立即訊息; 等等）</span><span class="sxs-lookup"><span data-stu-id="d4dfe-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="d4dfe-116">活動執行時所產生的資訊、詳細資料、警告或錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="d4dfe-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="d4dfe-117">SIP 登錄訊息</span><span class="sxs-lookup"><span data-stu-id="d4dfe-117">SIP registration messages</span></span>

  - <span data-ttu-id="d4dfe-118">活動執行時所產生的例外狀況記錄或診斷碼</span><span class="sxs-lookup"><span data-stu-id="d4dfe-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="d4dfe-119">執行活動的最終結果</span><span class="sxs-lookup"><span data-stu-id="d4dfe-119">The net result of running the activity</span></span>

<span data-ttu-id="d4dfe-120">這項資訊會自動產生每次執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="d4dfe-121">不過，資訊不會自動顯示，或儲存記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d4dfe-122">相反地，手動執行的綜合交易的系統管理員可以使用之後包含 OutLoggerVariable 參數來指定的資訊會儲存在 Windows PowerShell 變數。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d4dfe-123">從那裡，系統管理員可以使用一組的方法，可讓他們儲存及/或 rtf 登入 [XML] 或 [HTML 格式的檢視。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="d4dfe-124">例如，Lync Server 2010 管理員可能會使用類似下列的命令執行**Test-csregistration** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d4dfe-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="d4dfe-125">系統管理員可以選擇在他們選擇的變數名稱之後包含 OutLoggerVariable 參數：</span><span class="sxs-lookup"><span data-stu-id="d4dfe-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="d4dfe-p105">請不要在變數名稱的開頭加上 $ 字元。請使用像是 RegistrationTest 的變數名稱，而不要使用 $RegistrationTest。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="d4dfe-128">上述命令輸出內容如下：</span><span class="sxs-lookup"><span data-stu-id="d4dfe-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="d4dfe-p106">不過，系統會顯示更多關於此次失敗的詳細資訊，而不只是上述顯示的錯誤訊息。若要使用 HTML 格式存取該資訊，請使用類似下列的命令，以便將儲存於變數 RegistrationTest 中的資訊儲存至 HTML 檔案：</span><span class="sxs-lookup"><span data-stu-id="d4dfe-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="d4dfe-131">或者，您可以使用 ToXML() 方法，將資料儲存至 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="d4dfe-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="d4dfe-132">這些檔案然後可以使用 Internet Explorer、 Visual Studio 中或任何其他應用程式能夠開啟 HTML/XML 檔案來檢視。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="d4dfe-133">綜合交易，從執行 System Center Operations Manager 中的內容會自動產生失敗這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d4dfe-134">不過，如果執行作業失敗之前 Windows PowerShell 無法載入及執行綜合交易，就不產生這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="d4dfe-135">根據預設，Lync Server 2013 會將記錄檔儲存至未共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d4dfe-136">若要讓這些記錄檔隨時都能存取，您應該共用此資料夾 (例如， \\ \\atl-watcher-001.litwareinc.com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="d4dfe-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

