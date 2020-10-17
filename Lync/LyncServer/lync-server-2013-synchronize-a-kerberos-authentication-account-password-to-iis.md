---
title: 同步處理 Kerberos 驗證帳戶密碼至 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac886bf4eba4261a733241aa8d1d5396c4acc86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523850"
---
# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="2d7ba-102">在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS</span><span class="sxs-lookup"><span data-stu-id="2d7ba-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d7ba-103">_**主題上次修改日期：** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="2d7ba-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="2d7ba-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="2d7ba-105">在網站中，前端伺服器、Standard Edition 伺服器及 Director 可以使用 Kerberos 驗證帳戶，以驗證要求 Web 服務服務的要求。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="2d7ba-106">此程式會在已獲指派 Kerberos 帳戶的網站中，找出每一部執行 Web 服務的伺服器，並更新 Internet Information Services (IIS) 設定設定為使用 Kerberos 帳戶。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="2d7ba-107">如需詳細資訊，請參閱在 [Lync server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="2d7ba-108">若要設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="2d7ba-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="2d7ba-109">以 RTCUniversalServerAdmins 群組成員的身分登入來源電腦 (例如 fe01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2d7ba-110">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2d7ba-111">在 [Lync Server 管理命令介面] 命令列中，執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="2d7ba-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="2d7ba-112">例如：</span><span class="sxs-lookup"><span data-stu-id="2d7ba-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2d7ba-p102">來源電腦和目的地電腦的名稱必須是伺服器的完整網域名稱 (FQDN)。除非 FQDN 集區名稱與您作為來源電腦或目的地電腦使用的電腦名稱相同，否則您無法使用該集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2d7ba-115">在對 Kerberos 驗證進行任何變更（例如新增帳戶或移除帳戶）之後，您必須從 Lync Server 管理命令介面命令提示字元中執行 <STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="2d7ba-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

