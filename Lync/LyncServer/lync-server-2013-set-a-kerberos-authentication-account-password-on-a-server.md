---
title: Lync Server 2013：在伺服器上設定 Kerberos 驗證帳戶密碼
description: Lync Server 2013：在伺服器上設定 Kerberos 驗證帳戶密碼。
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
ms.openlocfilehash: 723392e670ca0b4bc9796cd62dab3b1a61f99dd1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574839"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="529d7-103">在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="529d7-103">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="529d7-104">_**主題上次修改日期：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="529d7-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="529d7-105">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="529d7-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="529d7-106">您必須針對每個具有前端伺服器、Standard Edition 伺服器及 Director 的網站，在 Kerberos 帳戶上設定密碼。</span><span class="sxs-lookup"><span data-stu-id="529d7-106">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="529d7-107">您可以在**Set-CsKerberosAccountPassword**   網站中的一部伺服器上執行 Set-CsKerberosAccountPassword Windows PowerShell Cmdlet，以設定密碼 (例如，一部前端伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="529d7-107">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="529d7-108">您必須針對每個網站執行**Set-CsKerberosAccountPassword**   Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="529d7-108">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="529d7-109">Cmdlet 會為 Web 服務服務設定網際網路資訊服務 (IIS) ，然後在 Active Directory 網域服務中設定電腦帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="529d7-109">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="529d7-110">另一種方法是根據使用 Cmdlet 的參數，在一部伺服器上設定 IIS，使用另一部已設定為 Kerberos 帳戶密碼來源的伺服器。</span><span class="sxs-lookup"><span data-stu-id="529d7-110">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="529d7-111">當您使用 **Set-CsKerberosAccountPassword** Cmdlet 來設定密碼時，Kerberos 會將密碼設定為隨機產生的字串。</span><span class="sxs-lookup"><span data-stu-id="529d7-111">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="529d7-112">此 Cmdlet 會聯繫指派此帳戶的所有 Lync Server 2013 中央網站中的所有 IIS 實例。</span><span class="sxs-lookup"><span data-stu-id="529d7-112">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="529d7-113">若要設定 Kerberos 驗證帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="529d7-113">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="529d7-114">以 RTCUniversalServerAdmins 群組成員的身分登入安裝了 Lync Server 管理命令介面的任何網域電腦。</span><span class="sxs-lookup"><span data-stu-id="529d7-114">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="529d7-115">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="529d7-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="529d7-116">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="529d7-116">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="529d7-117">例如：</span><span class="sxs-lookup"><span data-stu-id="529d7-117">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="529d7-118">您必須使用 Domain\User 格式指定 UserAccount 參數。</span><span class="sxs-lookup"><span data-stu-id="529d7-118">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="529d7-119">User@Domain 副檔名格式不支援參照為 Kerberos 驗證目的所建立的電腦物件。</span><span class="sxs-lookup"><span data-stu-id="529d7-119">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="529d7-120">在對 Kerberos 驗證進行任何變更（例如新增帳戶或移除帳戶）之後，您必須從 Lync Server 管理命令介面命令提示字元中執行 <STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="529d7-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

