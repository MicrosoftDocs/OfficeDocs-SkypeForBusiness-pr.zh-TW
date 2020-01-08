---
title: Lync Server 2013：在伺服器上設定 Kerberos 驗證帳戶密碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc4eefe4c1ef804b1deb06d056bfbd61ade35eb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="f5032-102">在 Lync Server 2013 中於伺服器上設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="f5032-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5032-103">_**主題上次修改日期：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="f5032-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="f5032-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="f5032-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="f5032-105">您必須針對每個擁有前端伺服器、標準版伺服器和控制器的網站，在 Kerberos 帳戶上設定密碼。</span><span class="sxs-lookup"><span data-stu-id="f5032-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="f5032-106">您可以在網站中的一個伺服器（例如，一個前端伺服器）上執行**設定 CsKerberosAccountPassword** 的 Windows PowerShell Cmdlet，以設定密碼。</span><span class="sxs-lookup"><span data-stu-id="f5032-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="f5032-107">針對每個網站，您必須執行**CsKerberosAccountPassword** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f5032-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="f5032-108">Cmdlet 會針對 Web 服務服務設定網際網路資訊服務（IIS），然後在 Active Directory 網域服務的電腦帳戶上設定密碼。</span><span class="sxs-lookup"><span data-stu-id="f5032-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="f5032-109">根據與 Cmdlet 搭配使用的參數，替代方法是在一台伺服器上設定 IIS，而您使用的是另一台已設定為 Kerberos 帳戶密碼來源的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f5032-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="f5032-110">當您使用**CsKerberosAccountPassword** Cmdlet 設定密碼時，Kerberos 會將密碼設定為隨機產生的字串。</span><span class="sxs-lookup"><span data-stu-id="f5032-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="f5032-111">這個 Cmdlet 會在指派這個帳戶的所有 Lync Server 2013 中央網站中，聯絡所有 IIS 實例。</span><span class="sxs-lookup"><span data-stu-id="f5032-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="f5032-112">若要設定 Kerberos 驗證帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="f5032-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="f5032-113">使用 Lync Server 管理命令介面，以 RTCUniversalServerAdmins 群組成員的身分登入任何網域電腦。</span><span class="sxs-lookup"><span data-stu-id="f5032-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f5032-114">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f5032-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f5032-115">從命令列執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="f5032-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="f5032-116">例如：</span><span class="sxs-lookup"><span data-stu-id="f5032-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5032-117">您必須使用 [Domain\User] 格式指定 UserAccount 參數。</span><span class="sxs-lookup"><span data-stu-id="f5032-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="f5032-118">不支援 User@Domain 副檔名格式，以參照為 Kerberos 驗證目的所建立的電腦物件。</span><span class="sxs-lookup"><span data-stu-id="f5032-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f5032-119">在對 Kerberos 驗證進行任何變更之後（例如新增帳戶或移除帳戶），您必須從 Lync Server Management Shell 命令提示字元執行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="f5032-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

