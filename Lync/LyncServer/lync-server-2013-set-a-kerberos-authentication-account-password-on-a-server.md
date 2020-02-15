---
title: Lync Server 2013： 在伺服器上設定 Kerberos 驗證帳戶密碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9799be0fda2b1a3c5b7765774b1f9e3199cc61f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="99f2f-102">在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="99f2f-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99f2f-103">_**主題上次修改日期：** 2012年-01-16_</span><span class="sxs-lookup"><span data-stu-id="99f2f-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="99f2f-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="99f2f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="99f2f-105">您必須設定上有前端伺服器、 Standard Edition server 和 Director 每個網站的 Kerberos 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="99f2f-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="99f2f-106">您可以藉由執行**Set-cskerberosaccountpassword**設定密碼 網站 （例如，一部前端伺服器） 中的一部伺服器上的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="99f2f-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="99f2f-107">對於每個網站，您必須執行**Set-cskerberosaccountpassword** 指令程式。</span><span class="sxs-lookup"><span data-stu-id="99f2f-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="99f2f-108">指令程式的 Web 服務 」 服務，設定網際網路資訊服務 (IIS)，並接著在 Active Directory 網域服務中的電腦帳戶上設定的密碼。</span><span class="sxs-lookup"><span data-stu-id="99f2f-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="99f2f-109">使用已設定為來源的 Kerberos 帳戶密碼的另一部伺服器時，替代方法，根據哪一個參數可搭配指令程式，可設定 IIS 一部伺服器上。</span><span class="sxs-lookup"><span data-stu-id="99f2f-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="99f2f-110">當您使用**Set-cskerberosaccountpassword** cmdlet 來設定密碼時，Kerberos 會將密碼設為隨機產生的字串。</span><span class="sxs-lookup"><span data-stu-id="99f2f-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="99f2f-111">此指令程式的連絡人中所有指派給此帳戶的 Lync Server 2013 管理中心網站的所有 IIS 執行個體。</span><span class="sxs-lookup"><span data-stu-id="99f2f-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="99f2f-112">若要設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="99f2f-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="99f2f-113">使用 Lync Server 管理命令介面安裝 RTCUniversalServerAdmins 群組成員身分登入網域的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="99f2f-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="99f2f-114">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="99f2f-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="99f2f-115">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="99f2f-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="99f2f-116">例如：</span><span class="sxs-lookup"><span data-stu-id="99f2f-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99f2f-117">您必須使用 Domain\User 格式指定 UserAccount 參數。</span><span class="sxs-lookup"><span data-stu-id="99f2f-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="99f2f-118">User@Domain.extension 格式不是支援參照建立用於 Kerberos 驗證的電腦物件。</span><span class="sxs-lookup"><span data-stu-id="99f2f-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="99f2f-119">對 Kerberos 驗證，如新增帳戶或移除帳戶進行任何變更之後您必須從 Lync Server 管理命令介面命令提示字元執行<STRONG>Enable-cstopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="99f2f-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

