---
title: Lync Server 2013： 從網站移除 Kerberos 驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4f7fa1160e7ff0afbbc4d8d4cc5ec96ab08e0f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="9c4e1-102">Lync Server 2013 中從網站移除 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="9c4e1-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c4e1-103">_**主題上次修改日期：** 2012年-01-16_</span><span class="sxs-lookup"><span data-stu-id="9c4e1-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="9c4e1-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="9c4e1-105">如果您需要從網站移除 Kerberos 驗證，或淘汰網站，您必須使用**移除 CsKerberosAccountAssignment**指令程式從網站移除 Kerberos 驗證帳戶指派。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="9c4e1-106">使用下列程序來移除從網站中的所有電腦中移除工作分派的 Kerberos 驗證帳戶指派。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="9c4e1-107">如果您永久淘汰的已啟用 Kerberos 的帳戶，您應該使用 Active Directory 使用者及電腦之後您已移除工作分派從 Active Directory 網域服務刪除它。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="9c4e1-108">如果您打算在未來使用物件，您可能想要保留 Active Directory 物件。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="9c4e1-109">若要從網站移除 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="9c4e1-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="9c4e1-110">以 RTCUniversalServerAdmins 群組的成員，登入網域中執行 Lync Server 2013 或入已安裝系統管理工具的電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="9c4e1-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9c4e1-112">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9c4e1-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="9c4e1-113">例如：</span><span class="sxs-lookup"><span data-stu-id="9c4e1-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9c4e1-114">對 Kerberos 驗證，如新增帳戶或移除帳戶進行任何變更之後您必須從 Lync Server 管理命令介面命令提示字元執行<STRONG>Enable-cstopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="9c4e1-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

