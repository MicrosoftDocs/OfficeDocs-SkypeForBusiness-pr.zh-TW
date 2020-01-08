---
title: Lync Server 2013：將 Kerberos 驗證帳戶指派到網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb755f7e7b814d4ca643bd04ddfc0241b4d96d60
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40976934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="167ed-102">在 Lync Server 2013 中將 Kerberos 驗證帳戶指派到網站</span><span class="sxs-lookup"><span data-stu-id="167ed-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="167ed-103">_**主題上次修改日期：** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="167ed-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="167ed-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="167ed-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="167ed-105">建立 Kerberos 帳戶之後，您必須將它指派給網站。</span><span class="sxs-lookup"><span data-stu-id="167ed-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="167ed-106">這是 Lync Server 2013 網站，不是 Active Directory 網站。</span><span class="sxs-lookup"><span data-stu-id="167ed-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="167ed-107">您可以針對每個部署建立多個 Kerberos 驗證帳戶，但您只能將一個帳戶指派至網站。</span><span class="sxs-lookup"><span data-stu-id="167ed-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="167ed-108">使用下列程式，將先前建立的 Kerberos 驗證帳戶指派至網站。</span><span class="sxs-lookup"><span data-stu-id="167ed-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="167ed-109">如需有關建立 Kerberos 帳戶的詳細資訊，請參閱[在 Lync Server 2013 中建立 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)。</span><span class="sxs-lookup"><span data-stu-id="167ed-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="167ed-110">將 Kerberos 驗證帳戶指派給網站</span><span class="sxs-lookup"><span data-stu-id="167ed-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="167ed-111">如果您是 RTCUniversalServerAdmins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="167ed-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="167ed-112">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="167ed-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="167ed-113">從命令列執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="167ed-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="167ed-114">例如：</span><span class="sxs-lookup"><span data-stu-id="167ed-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="167ed-115">您必須使用 [Domain\User] 格式指定 UserAccount 參數。</span><span class="sxs-lookup"><span data-stu-id="167ed-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="167ed-116">在針對 Kerberos 驗證目的所建立的電腦物件上，不支援 User@Domain 副檔名格式。</span><span class="sxs-lookup"><span data-stu-id="167ed-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="167ed-117">**選用**：您可能已針對您的 WebServices 設定覆寫 FQDN （完整功能變數名稱），如[[在 Lync Server 2013 中變更 Web 服務 URL](lync-server-2013-change-the-web-services-url.md)]。</span><span class="sxs-lookup"><span data-stu-id="167ed-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="167ed-118">如果是這種情況，您也需要為此 FQDN 新增 SPN。</span><span class="sxs-lookup"><span data-stu-id="167ed-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="167ed-119">例如，如果 FQDN 是 webservices，您將會執行：</span><span class="sxs-lookup"><span data-stu-id="167ed-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="167ed-120">在對 Kerberos 驗證進行任何變更之後（例如新增帳戶或移除帳戶），您必須從 Lync Server Management Shell 命令提示字元執行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="167ed-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

