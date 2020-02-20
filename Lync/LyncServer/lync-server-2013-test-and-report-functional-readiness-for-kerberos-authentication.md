---
title: Kerberos 驗證的測試和報告功能就緒
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
ms.openlocfilehash: c3c5a2c83d664182226decb88ab6bd1c34d6d3a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="4aa60-102">Lync Server 2013 中的 Kerberos 驗證的測試和報告功能就緒</span><span class="sxs-lookup"><span data-stu-id="4aa60-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aa60-103">_**主題上次修改日期：** 2012年-01-16_</span><span class="sxs-lookup"><span data-stu-id="4aa60-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="4aa60-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="4aa60-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="4aa60-105">您可以使用**Test-cskerberosaccountassignment** Windows PowerShell cmdlet 來測試和報告 Kerberos 驗證的網站指派功能是否就緒。</span><span class="sxs-lookup"><span data-stu-id="4aa60-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="4aa60-106">此命令會查詢必要的 Identity 參數中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="4aa60-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="4aa60-107">選用的報表參數會導致指令程式將 HTML 報告寫入 c:\\記錄在其執行此命令之電腦上。</span><span class="sxs-lookup"><span data-stu-id="4aa60-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="4aa60-108">要在螢幕的選用 Verbose 參數報告活動資訊。</span><span class="sxs-lookup"><span data-stu-id="4aa60-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="4aa60-109">若要測試和報告網站的 Kerberos 驗證功能就緒</span><span class="sxs-lookup"><span data-stu-id="4aa60-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="4aa60-110">以 RTCUniversalServerAdmins 群組的成員，登入網域中執行 Lync Server 2013 或入電腦的系統管理工具安裝所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="4aa60-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="4aa60-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="4aa60-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4aa60-112">從命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4aa60-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="4aa60-113">例如：</span><span class="sxs-lookup"><span data-stu-id="4aa60-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

