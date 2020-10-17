---
title: 測試和報告 Kerberos 驗證的功能準備工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac03f06a5d2c4b4989319f32a867d91614bd3a30
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519320"
---
# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="30f6b-102">在 Lync Server 2013 中測試和報告 Kerberos 驗證的功能準備就緒</span><span class="sxs-lookup"><span data-stu-id="30f6b-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30f6b-103">_**主題上次修改日期：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="30f6b-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="30f6b-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="30f6b-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="30f6b-105">您可以使用**Test-CsKerberosAccountAssignment**   Windows PowerShell Cmdlet 來測試及報告適用于 Kerberos 驗證之網站指派的功能準備工作。</span><span class="sxs-lookup"><span data-stu-id="30f6b-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="30f6b-106">這個命令會查詢必要 Identity 參數中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="30f6b-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="30f6b-107">選用的 Report 參數會使 Cmdlet 將 HTML 報告寫入 C： \\ 執行命令的電腦上的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="30f6b-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="30f6b-108">選用的 Verbose 參數會向畫面報告活動資訊。</span><span class="sxs-lookup"><span data-stu-id="30f6b-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="30f6b-109">針對網站的 Kerberos 驗證測試及報告功能準備就緒</span><span class="sxs-lookup"><span data-stu-id="30f6b-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="30f6b-110">以 RTCUniversalServerAdmins 群組成員的身分，登入執行 Lync Server 2013 之網域中的電腦，或登入安裝系統管理工具所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="30f6b-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="30f6b-111">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="30f6b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="30f6b-112">從命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="30f6b-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="30f6b-113">例如：</span><span class="sxs-lookup"><span data-stu-id="30f6b-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

