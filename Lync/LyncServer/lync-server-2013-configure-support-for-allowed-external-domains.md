---
title: Lync Server 2013：針對允許的外部網域設定支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eaa9da579561464c46776662cacaca80dafe016
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517680"
---
# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="4f280-102">在 Lync Server 2013 中為允許的外部網域設定支援</span><span class="sxs-lookup"><span data-stu-id="4f280-102">Configure support for allowed external domains in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f280-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4f280-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4f280-p101">如果已設定對同盟協力廠商的支援，則可以管理哪些特定網域可以與您的組織進行同盟。設定一個或多個特定的外部網域作為允許的同盟網域。若要這樣做，請將每個所需網域新增至允許網域清單。如果網域是可能需要與您超過 1,000 位使用者通訊或每秒傳送超過 20 封訊息的同盟協力廠商，則即使您的組織已啟用協力廠商探索，也建議您這樣做。如果您的組織未啟用協力廠商探索，則只有已新增至允許網域清單的外部網域的使用者，才能和您組織內的使用者進行 IM 和會議通訊。如果您要將同盟網域的存取限制於同盟協力廠商執行 Access Edge Service 的特定伺服器，可以針對允許網域清單中的每個網域，指定執行 Access Edge Service 之伺服器的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="4f280-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f280-110">此程序說明如何設定特定網域的支援，但實作同盟使用者的支援還需要您的組織啟用同盟使用者的支援，以及設定和套用原則以控制哪些使用者可以與同盟使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="4f280-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="4f280-111">如需啟用同盟使用者支援的詳細資訊，請參閱 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="4f280-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="4f280-112">如需設定控制同盟之原則的詳細資訊，請參閱 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</A>。</span><span class="sxs-lookup"><span data-stu-id="4f280-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="4f280-113">若要將外部網域新增至允許網域清單</span><span class="sxs-lookup"><span data-stu-id="4f280-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="4f280-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f280-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f280-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4f280-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f280-116">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4f280-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4f280-117">在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[同盟網域]**。</span><span class="sxs-lookup"><span data-stu-id="4f280-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="4f280-118">在 **[同盟網域]** 頁面上，依序按一下 **[新增]** 和 **[允許的網域]**。</span><span class="sxs-lookup"><span data-stu-id="4f280-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="4f280-119">在 **[新增同盟網域]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4f280-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="4f280-120">在 **[網域名稱 (或 FQDN)]** 中，輸入同盟協力廠商網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="4f280-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4f280-p104">此名稱必須是唯一的，而且不能已存在作為這個執行 Access Edge Service 的伺服器的允許網域。此外，名稱長度不可超過 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="4f280-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="4f280-p105">搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 <STRONG>contoso.com</STRONG>，搜尋也會傳回網域 <STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4f280-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="4f280-125">不能同時封鎖又允許同一個同盟協力廠商網域。</span><span class="sxs-lookup"><span data-stu-id="4f280-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="4f280-126">Lync Server 2013 避免發生這種情況，因此您不需要同步處理清單。</span><span class="sxs-lookup"><span data-stu-id="4f280-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="4f280-127">如果您要將同盟網域的存取限制於執行 Access Edge Service 之特定伺服器的使用者，可以在 **[Access Edge Service (FQDN)]** 中輸入執行 Access Edge Service 之同盟網域伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4f280-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="4f280-128">如果您要提供其他資訊，請在 **[註解]** 中輸入您想與其他系統管理員分享有關此設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="4f280-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="4f280-129">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="4f280-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="4f280-130">為您要允許的每個同盟協力廠商網域重複步驟 4 到 6。</span><span class="sxs-lookup"><span data-stu-id="4f280-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="4f280-131">若要啟用同盟使用者存取，您也必須在組織中啟用對同盟使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="4f280-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="4f280-132">如需詳細資訊，請參閱 [Enable or disable remote user access In Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4f280-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="4f280-133">此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="4f280-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="4f280-134">如需詳細資訊，請參閱 [Configure 原則 to control 同盟 user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4f280-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

