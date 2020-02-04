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
ms.openlocfilehash: 31aa2ab9db9ffccd3acda90e9651dfad20b85e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="b711e-102">在 Lync Server 2013 中針對允許的外部網域設定支援</span><span class="sxs-lookup"><span data-stu-id="b711e-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b711e-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b711e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b711e-104">如果您已設定聯盟夥伴的支援，您可以管理哪些特定網域可以與您的組織聯盟。</span><span class="sxs-lookup"><span data-stu-id="b711e-104">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="b711e-105">您將一或多個特定外部網域設定為允許聯盟網域。</span><span class="sxs-lookup"><span data-stu-id="b711e-105">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="b711e-106">若要這樣做，請將每個網域新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="b711e-106">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="b711e-107">即使您的組織已啟用合作夥伴探索，如果網域是聯盟夥伴，可能需要與超過1000的使用者通訊，或者可能需要每秒傳送超過20封郵件。</span><span class="sxs-lookup"><span data-stu-id="b711e-107">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="b711e-108">如果您的組織未啟用合作夥伴探索，則只有您新增至 [允許的網域] 清單的外部網域使用者，才能與組織中的使用者參與 IM 和會議。</span><span class="sxs-lookup"><span data-stu-id="b711e-108">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="b711e-109">如果您想要將同盟網域的存取許可權制為執行同盟夥伴之存取邊緣服務的特定伺服器，您可以在允許的網域清單中，為每個網域指定執行 Access Edge 服務的伺服器功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="b711e-109">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b711e-110">此程式說明如何針對特定網域設定支援，但實現同盟使用者的支援也需要您針對貴組織啟用聯盟使用者支援，以及設定及套用原則，以控制哪些使用者可以與聯盟使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="b711e-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="b711e-111">如需啟用聯盟使用者支援的詳細資料，請參閱<A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中啟用或停用遠端使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="b711e-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="b711e-112">如需設定控制同盟的原則的詳細資料，請參閱<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制聯盟使用者存取權的原則</A>。</span><span class="sxs-lookup"><span data-stu-id="b711e-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="b711e-113">將外部網域新增至允許的網域清單</span><span class="sxs-lookup"><span data-stu-id="b711e-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="b711e-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b711e-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b711e-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b711e-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b711e-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b711e-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b711e-117">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**聯盟網域**]。</span><span class="sxs-lookup"><span data-stu-id="b711e-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="b711e-118">在 [**聯盟網域**] 頁面上，按一下 [**新增**]，然後按一下 [**允許的網域**]。</span><span class="sxs-lookup"><span data-stu-id="b711e-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="b711e-119">在**新的聯盟網域**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b711e-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="b711e-120">在 **[Domain name （或 FQDN）**] 中，輸入聯盟夥伴網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="b711e-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b711e-121">這個名稱必須是唯一的，而且不能作為執行存取邊緣服務的此伺服器的允許網域存在。</span><span class="sxs-lookup"><span data-stu-id="b711e-121">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="b711e-122">名稱長度不能超過256個字元。</span><span class="sxs-lookup"><span data-stu-id="b711e-122">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="b711e-123">在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。</span><span class="sxs-lookup"><span data-stu-id="b711e-123">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="b711e-124">例如，如果您輸入<STRONG>contoso.com</STRONG>，則搜尋也會傳回網域<STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="b711e-124">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="b711e-125">聯盟夥伴網域不能同時封鎖及允許。</span><span class="sxs-lookup"><span data-stu-id="b711e-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="b711e-126">Lync Server 2013 避免發生這種情況，因此您不需要同步處理您的清單。</span><span class="sxs-lookup"><span data-stu-id="b711e-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="b711e-127">如果您想要將此聯盟網域的存取許可權制為執行存取邊緣服務的特定伺服器的使用者，請在 **[存取邊緣服務（FQDN）**] 中，輸入執行 [存取邊緣] 服務之聯盟網域伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b711e-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="b711e-128">如果您想要提供其他資訊，請在 [**批註**] 中，輸入您要與其他系統管理員共用此設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="b711e-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="b711e-129">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b711e-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="b711e-130">針對您要允許的每個聯盟夥伴網域，重複步驟4到6。</span><span class="sxs-lookup"><span data-stu-id="b711e-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="b711e-131">若要啟用同盟使用者存取，您也必須在組織中啟用聯盟使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="b711e-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="b711e-132">如需詳細資訊，請參閱[啟用或停用 Lync Server 2013 中的遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b711e-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="b711e-133">此外，您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="b711e-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="b711e-134">如需詳細資訊，請參閱[在 Lync Server 2013 中設定控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b711e-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

