---
title: Lync Server 2013：將 Kerberos 驗證帳戶指派到網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6137224f313238dae33462298931167ba7bb810
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529520"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="3c9fb-102">在 Lync Server 2013 中指派 Kerberos 驗證帳戶至網站</span><span class="sxs-lookup"><span data-stu-id="3c9fb-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c9fb-103">_**主題上次修改日期：** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="3c9fb-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="3c9fb-104">若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="3c9fb-105">建立 Kerberos 帳戶之後，您必須將它指派給網站。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="3c9fb-106">這是 Lync Server 2013 網站，而非 Active Directory 網站。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="3c9fb-107">每個部署可以建立多個 Kerberos 驗證帳戶，但只能指派一個帳戶給一個網站。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="3c9fb-108">使用下列程序，可指派先前建立的 Kerberos 驗證帳戶給網站。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="3c9fb-109">如需建立 Kerberos 帳戶的詳細資訊，請參閱 [在 Lync Server 2013 中建立 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="3c9fb-110">若要指派 Kerberos 驗證帳戶給網站</span><span class="sxs-lookup"><span data-stu-id="3c9fb-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="3c9fb-111">以 RTCUniversalServerAdmins 群組成員的身分，登入執行 Lync Server 2013 的網域中的電腦，或登入已安裝系統管理工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="3c9fb-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3c9fb-113">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c9fb-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="3c9fb-114">例如：</span><span class="sxs-lookup"><span data-stu-id="3c9fb-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="3c9fb-p102">您必須使用 Domain\User 格式指定 UserAccount 參數。不支援以 User@Domain.extension 格式來指稱基於 Kerberos 驗證目的而建立的電腦物件。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="3c9fb-117">**選用**：您可以為 WebServices 設定覆寫的 FQDN (完整功能變數名稱) ，如 [每次 [變更 Lync Server 2013 中的 Web 服務 URL](lync-server-2013-change-the-web-services-url.md)]。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="3c9fb-118">如果是這種情況，您也必須為此 FQDN 新增 SPN。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="3c9fb-119">例如，如果 FQDN 是 webservices，您會執行：</span><span class="sxs-lookup"><span data-stu-id="3c9fb-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3c9fb-120">在對 Kerberos 驗證進行任何變更（例如新增帳戶或移除帳戶）之後，您必須從 Lync Server 管理命令介面命令提示字元中執行 <STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="3c9fb-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

