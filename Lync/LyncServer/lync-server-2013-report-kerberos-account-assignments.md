---
title: Lync Server 2013：報告 Kerberos 帳戶指派
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="52796-102">在 Lync Server 2013 中報告 Kerberos 帳戶指派</span><span class="sxs-lookup"><span data-stu-id="52796-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52796-103">_**主題上次修改日期：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="52796-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="52796-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="52796-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="52796-105">您可以使用**CsKerberosAccountAssignment** Cmdlet 來查詢有關 Kerberos 驗證帳戶指派的資訊，並報告部署中目前作業的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="52796-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="52796-106">查詢網站的 Kerberos 驗證帳戶指派</span><span class="sxs-lookup"><span data-stu-id="52796-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="52796-107">如果您是 RTCUniversalServerAdmins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="52796-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="52796-108">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="52796-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="52796-109">從命令列執行下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="52796-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="52796-110">若要查詢貴組織中的所有 Kerberos 驗證帳戶指派，並傳回每個使用者的指派資訊，請執行不含任何參數的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="52796-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="52796-111">若要查詢您部署中的所有 Kerberos 驗證帳戶指派並傳回每個 Kerberos 驗證帳戶的指派資訊，請使用身分識別參數執行 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="52796-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="52796-112">例如：</span><span class="sxs-lookup"><span data-stu-id="52796-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="52796-113">若要在單一網站中查詢所有 Kerberos 驗證帳戶指派，並傳回每個使用者的作業資訊，請使用 Filter 參數執行 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="52796-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="52796-114">例如：</span><span class="sxs-lookup"><span data-stu-id="52796-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="52796-115">針對篩選參數指定 \* SiteName，會傳回包含指定網站名稱之所有網站的相關資訊（例如，在網站識別碼中包含字串雷蒙德的所有網站）。</span><span class="sxs-lookup"><span data-stu-id="52796-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

