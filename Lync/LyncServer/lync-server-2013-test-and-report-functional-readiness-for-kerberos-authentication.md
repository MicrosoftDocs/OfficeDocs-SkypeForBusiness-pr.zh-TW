---
title: 測試和報告 Kerberos 驗證的功能整備狀態
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
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="7c4bd-102">在 Lync Server 2013 中測試和報告 Kerberos 驗證的功能整備狀態</span><span class="sxs-lookup"><span data-stu-id="7c4bd-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c4bd-103">_**主題上次修改日期：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="7c4bd-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="7c4bd-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="7c4bd-105">您可以使用**CsKerberosAccountAssignment** Windows PowerShell Cmdlet 來測試和報告 Kerberos 驗證的網站分派的功能準備就緒情況。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="7c4bd-106">這個命令會查詢在所需身分識別參數中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="7c4bd-107">選用的報表參數會使 Cmdlet 在執行命令的電腦上，將\\HTML 報表寫入 C：記錄。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="7c4bd-108">選擇性的詳細參數會將活動資訊報告到畫面。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="7c4bd-109">針對網站的 Kerberos 驗證測試和報告功能就緒性準備</span><span class="sxs-lookup"><span data-stu-id="7c4bd-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="7c4bd-110">如果您是 RTCUniversalServerAdmins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="7c4bd-111">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="7c4bd-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7c4bd-112">從命令列執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7c4bd-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="7c4bd-113">例如：</span><span class="sxs-lookup"><span data-stu-id="7c4bd-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

