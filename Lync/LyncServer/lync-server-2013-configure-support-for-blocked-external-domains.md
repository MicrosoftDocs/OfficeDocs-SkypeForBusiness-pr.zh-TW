---
title: Lync Server 2013：為封鎖的外部網域設定支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be998071bc0cad49d3e96c3c82cf395b2da7ca1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515680"
---
# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="57ac3-102">在 Lync Server 2013 中為封鎖的外部網域設定支援</span><span class="sxs-lookup"><span data-stu-id="57ac3-102">Configure support for blocked external domains in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57ac3-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="57ac3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="57ac3-104">如果您已設定同盟協力廠商的支援，可以管理要禁止哪些網域與您的組織建立同盟。</span><span class="sxs-lookup"><span data-stu-id="57ac3-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="57ac3-105">如果您啟用此選項，封鎖網域清單將作為封鎖清單 (不被允許的明確項目清單)，並套用於同盟網域探索中。</span><span class="sxs-lookup"><span data-stu-id="57ac3-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="57ac3-106">如需詳細資訊，請參閱 [啟用或停用 Lync Server 2013 中的同盟](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)協力廠商探索。</span><span class="sxs-lookup"><span data-stu-id="57ac3-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="57ac3-p102">封鎖一個或多個外部網域，不讓它們連線至您的組織。若要這樣做，請將網域新增至封鎖網域清單。</span><span class="sxs-lookup"><span data-stu-id="57ac3-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="57ac3-109">將外部網域新增至封鎖網域清單</span><span class="sxs-lookup"><span data-stu-id="57ac3-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="57ac3-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="57ac3-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57ac3-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="57ac3-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57ac3-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="57ac3-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="57ac3-113">在左導覽列中，按一下 **[外部使用者存取]**。</span><span class="sxs-lookup"><span data-stu-id="57ac3-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="57ac3-114">依序按一下 **[同盟網域]**、**[新增]** 和 **[封鎖網域]**。</span><span class="sxs-lookup"><span data-stu-id="57ac3-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="57ac3-115">在 \*\*[新增同盟網域] \*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57ac3-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="57ac3-116">在 **[網域名稱 (或 FQDN)]** 中，輸入您要封鎖的同盟協力廠商網域名稱。</span><span class="sxs-lookup"><span data-stu-id="57ac3-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="57ac3-117">名稱長度不可超過 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="57ac3-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="57ac3-p104">搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 <STRONG>contoso.com</STRONG>，搜尋也會傳回網域 <STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="57ac3-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="57ac3-120">不能同時封鎖又允許同一個同盟協力廠商網域。</span><span class="sxs-lookup"><span data-stu-id="57ac3-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="57ac3-121">Lync Server 2013 避免發生這種情況，因此您不需要同步處理清單。</span><span class="sxs-lookup"><span data-stu-id="57ac3-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="57ac3-122">(選用) 在 **[註解]** 中，輸入您想與其他系統管理員分享的此設定相關資訊。</span><span class="sxs-lookup"><span data-stu-id="57ac3-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="57ac3-123">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="57ac3-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="57ac3-124">為您要封鎖的每個同盟協力廠商重複步驟 4 到 6。</span><span class="sxs-lookup"><span data-stu-id="57ac3-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="57ac3-125">若要啟用同盟使用者存取，您也必須在組織中啟用同盟使用者存取支援。</span><span class="sxs-lookup"><span data-stu-id="57ac3-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="57ac3-126">如需詳細資訊，請參閱 [Enable or disable remote user access In Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="57ac3-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="57ac3-127">此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="57ac3-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="57ac3-128">如需詳細資訊，請參閱 [Configure 原則 to control 同盟 user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="57ac3-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

