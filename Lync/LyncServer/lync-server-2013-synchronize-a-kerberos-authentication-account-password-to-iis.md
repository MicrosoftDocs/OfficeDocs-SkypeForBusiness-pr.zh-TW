---
title: 同步處理 Kerberos 驗證帳戶密碼至 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="5a22d-102">在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS</span><span class="sxs-lookup"><span data-stu-id="5a22d-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a22d-103">_**主題上次修改日期：** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="5a22d-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="5a22d-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="5a22d-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="5a22d-105">在網站、前端伺服器、標準版伺服器和控制器上，都可以使用 Kerberos 驗證帳戶來驗證要求至 Web 服務服務的需求。</span><span class="sxs-lookup"><span data-stu-id="5a22d-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="5a22d-106">這個程式會在已指派 Kerberos 帳戶的網站中，尋找每個執行 Web 服務的伺服器，並更新 Internet Information Services （IIS）設定，以使用 Kerberos 帳戶。</span><span class="sxs-lookup"><span data-stu-id="5a22d-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="5a22d-107">如需詳細資訊，請參閱在[Lync server 2013 的伺服器上設定 Kerberos 驗證帳戶密碼](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5a22d-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="5a22d-108">設定和設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="5a22d-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="5a22d-109">以 RTCUniversalServerAdmins 群組成員的身分登入來源電腦（例如 fe01.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="5a22d-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="5a22d-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="5a22d-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a22d-111">從 Lync Server Management Shell 命令列，執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="5a22d-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="5a22d-112">例如：</span><span class="sxs-lookup"><span data-stu-id="5a22d-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5a22d-113">來源電腦和目的電腦的名稱必須是伺服器的完整功能變數名稱（FQDN）名稱。</span><span class="sxs-lookup"><span data-stu-id="5a22d-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="5a22d-114">除非 [池名稱] 與您用來做為來源電腦或目的電腦的電腦名稱稱相同，否則您無法使用 [池 FQDN]。</span><span class="sxs-lookup"><span data-stu-id="5a22d-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5a22d-115">在對 Kerberos 驗證進行任何變更之後（例如新增帳戶或移除帳戶），您必須從 Lync Server Management Shell 命令提示字元執行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="5a22d-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

