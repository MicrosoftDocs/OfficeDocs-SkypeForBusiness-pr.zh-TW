---
title: Lync Server 2013： 報告 Kerberos 帳戶指派項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c742e6e7e5cedc773e0275700a738afd26a6777d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="62770-102">Lync Server 2013 中的報告 Kerberos 帳戶指派</span><span class="sxs-lookup"><span data-stu-id="62770-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62770-103">_**主題上次修改日期：** 2012年-01-16_</span><span class="sxs-lookup"><span data-stu-id="62770-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="62770-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="62770-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="62770-105">您可以使用 **Get-CsKerberosAccountAssignment** Cmdlet 查詢 Kerberos 驗證帳戶指派項目相關資訊，並回報部署中目前指派項目相關資訊。</span><span class="sxs-lookup"><span data-stu-id="62770-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="62770-106">若要查詢網站的 Kerberos 驗證帳戶指派項目</span><span class="sxs-lookup"><span data-stu-id="62770-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="62770-107">以 RTCUniversalServerAdmins 群組的成員，登入網域中執行 Lync Server 2013 或入已安裝系統管理工具的電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="62770-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="62770-108">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="62770-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="62770-109">從命令列中執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="62770-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="62770-110">若要查詢組織裡所有 Kerberos 驗證帳戶指派項目，並傳回這些項目的個別指派資訊，請執行不含任何參數的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="62770-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="62770-111">若要查詢部署中所有 Kerberos 驗證帳戶指派項目，並傳回這些項目的個別網站指派資訊，請執行含 Identity 參數的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="62770-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="62770-112">例如：</span><span class="sxs-lookup"><span data-stu-id="62770-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="62770-113">若要查詢單一網站中所有 Kerberos 驗證帳戶指派項目，並傳回這些項目的指派資訊，請執行含 Filter 參數的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="62770-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="62770-114">例如：</span><span class="sxs-lookup"><span data-stu-id="62770-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="62770-115">指定 Filter 參數的 \*SiteName 會傳回在網站識別元的任意位置包含指定網站名稱之所有網站 (例如，在網站識別元中包含 Redmond 字串的所有網站) 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="62770-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

