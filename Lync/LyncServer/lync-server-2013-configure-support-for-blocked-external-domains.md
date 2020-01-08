---
title: Lync Server 2013：為封鎖的外部網域設定支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="96cad-102">在 Lync Server 2013 中為封鎖的外部網域設定支援</span><span class="sxs-lookup"><span data-stu-id="96cad-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96cad-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="96cad-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="96cad-104">如果您已設定聯盟夥伴的支援，您可以管理哪些網域將被封鎖，無法與您的組織進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="96cad-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="96cad-105">封鎖的網域清單會充當封鎖清單（不允許的明確專案清單），如果您已啟用此選項，就會套用到聯盟網域探索中。</span><span class="sxs-lookup"><span data-stu-id="96cad-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="96cad-106">如需詳細資訊，請參閱[啟用或停用 Lync Server 2013 中的同盟合作夥伴探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="96cad-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="96cad-107">封鎖一或多個外部網域以連線到您的組織。</span><span class="sxs-lookup"><span data-stu-id="96cad-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="96cad-108">若要這樣做，請將網域新增到封鎖網域的清單中。</span><span class="sxs-lookup"><span data-stu-id="96cad-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="96cad-109">將外部網域新增至封鎖的網域清單</span><span class="sxs-lookup"><span data-stu-id="96cad-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="96cad-110">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96cad-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96cad-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="96cad-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96cad-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="96cad-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96cad-113">在左側導覽列中，按一下 [**外部使用者存取**]。</span><span class="sxs-lookup"><span data-stu-id="96cad-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="96cad-114">按一下 [**聯盟網域**]，按一下 [**新增**]，然後按一下 [**封鎖的網域**]。</span><span class="sxs-lookup"><span data-stu-id="96cad-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="96cad-115">在**新的聯盟網域**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="96cad-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="96cad-116">在 **[Domain name （或 FQDN）**] 中，輸入您要封鎖的聯盟夥伴網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="96cad-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="96cad-117">名稱長度不能超過256個字元。</span><span class="sxs-lookup"><span data-stu-id="96cad-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="96cad-118">在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。</span><span class="sxs-lookup"><span data-stu-id="96cad-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="96cad-119">例如，如果您輸入<STRONG>contoso.com</STRONG>，則搜尋也會傳回網域<STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="96cad-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="96cad-120">聯盟夥伴網域不能同時封鎖及允許。</span><span class="sxs-lookup"><span data-stu-id="96cad-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="96cad-121">Lync Server 2013 避免發生這種情況，因此您不需要同步處理您的清單。</span><span class="sxs-lookup"><span data-stu-id="96cad-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="96cad-122">可選在 [**批註**] 中，輸入您要與其他系統管理員共用這項設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="96cad-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="96cad-123">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96cad-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="96cad-124">針對您要封鎖的每個聯盟夥伴，重複步驟4到6。</span><span class="sxs-lookup"><span data-stu-id="96cad-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="96cad-125">若要啟用同盟使用者存取，您也必須在組織中啟用聯盟使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="96cad-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="96cad-126">如需詳細資訊，請參閱[啟用或停用 Lync Server 2013 中的遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="96cad-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="96cad-127">此外，您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="96cad-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="96cad-128">如需詳細資訊，請參閱[在 Lync Server 2013 中設定控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="96cad-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

