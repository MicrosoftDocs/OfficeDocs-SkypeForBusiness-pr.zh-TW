---
title: Lync Server 2013：啟用或停用同盟與公用 IM 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="7157f-102">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7157f-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7157f-103">_**主題上次修改日期：** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="7157f-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="7157f-104">必須具備同盟的支援，才能讓擁有受信任的客戶或合作夥伴組織帳戶的使用者，包括您所支援之公用立即訊息（IM）提供者的合作夥伴網域和使用者與您在其中的使用者共同作業。機構.</span><span class="sxs-lookup"><span data-stu-id="7157f-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="7157f-105">必須具備同盟，才能使用託管 Exchange 服務提供者來提供語音信箱給企業語音使用者，其信箱位於託管 Exchange 服務（例如 Microsoft Exchange Online）。</span><span class="sxs-lookup"><span data-stu-id="7157f-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="7157f-106">當您與這些外部網域建立信任關係時，您可以授權這些網域中的使用者存取您的部署並參與 Lync Server 通訊。</span><span class="sxs-lookup"><span data-stu-id="7157f-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="7157f-107">這個信任關係稱為聯合體，它與 Active Directory 信任關係無關，或不依賴。</span><span class="sxs-lookup"><span data-stu-id="7157f-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="7157f-108">若要支援受聯盟網域使用者的存取，您必須啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="7157f-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="7157f-109">如果您為組織啟用同盟，您也必須指定是否要實施下列選項：</span><span class="sxs-lookup"><span data-stu-id="7157f-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="7157f-110">**[啟用合作夥伴網域探索**   ] 如果您啟用這個選項，Lync Server 會使用網域名稱系統（DNS）記錄來嘗試找出未列于 [允許的網域] 清單中的網域，自動評估已探索的同盟夥伴的傳入流量，以及限制或封鎖該流量（根據信任層級、流量數量及管理員設定）。</span><span class="sxs-lookup"><span data-stu-id="7157f-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="7157f-111">如果您沒有選取此選項，即會針對您在 [允許的網域] 清單中所包含的網域中的使用者啟用 [聯盟使用者存取]。</span><span class="sxs-lookup"><span data-stu-id="7157f-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="7157f-112">不論您是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制對執行聯盟網域中之存取邊緣服務之特定伺服器的存取權。</span><span class="sxs-lookup"><span data-stu-id="7157f-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="7157f-113">如需控制聯盟網域存取權的詳細資料，請參閱[在 Lync Server 2013 中設定允許的外部網域支援](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="7157f-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="7157f-114">**將封存免責聲明傳送給聯盟**   夥伴將會傳送給聯盟夥伴，讓您的部署中的歸檔已就緒。</span><span class="sxs-lookup"><span data-stu-id="7157f-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="7157f-115">如果您支援與同盟夥伴網域進行外部通訊的存檔，您應該啟用 [封存放棄免責聲明通知]，警告合作夥伴他們的郵件正在封存。</span><span class="sxs-lookup"><span data-stu-id="7157f-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="7157f-116">如果您稍後想要暫時或永久避免受聯盟網域的使用者存取，您可以針對貴組織停用同盟。</span><span class="sxs-lookup"><span data-stu-id="7157f-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="7157f-117">您可以使用本節中的程式來啟用或停用貴組織的同盟使用者存取權，包括指定貴組織支援的適當聯盟選項。</span><span class="sxs-lookup"><span data-stu-id="7157f-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7157f-118">為您的組織啟用同盟時，只會指定執行存取邊緣服務的伺服器支援路由到聯盟網域。</span><span class="sxs-lookup"><span data-stu-id="7157f-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="7157f-119">聯盟網域中的使用者無法參與您組織中的 IM 或會議，除非您也將至少一個策略設定為支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="7157f-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="7157f-120">公用 IM 服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您也將至少一個原則設定為支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="7157f-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="7157f-121">Lync Server 無法使用託管 Exchange 服務來提供呼叫應答、Outlook 語音存取（包括語音信箱），或針對其信箱位於託管 Exchange 服務的使用者的自動助理服務，直到您設定託管的語音信箱原則為止提供路由資訊的。</span><span class="sxs-lookup"><span data-stu-id="7157f-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="7157f-122">如需有關設定與其他組織中聯盟網域之使用者通訊的原則的詳細資訊，請參閱在作業檔中<A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">管理您的組織在 Lync Server 2013 中的 SIP 聯盟網域</A>。</span><span class="sxs-lookup"><span data-stu-id="7157f-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="7157f-123">此外，如果您想要支援與 IM 服務提供者的使用者進行通訊，您必須設定支援它的原則，同時還要針對您想要支援的個別服務提供者設定支援。</span><span class="sxs-lookup"><span data-stu-id="7157f-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="7157f-124">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">管理您的組織在 Lync Server 2013 中的 SIP 聯盟提供者</A>。</span><span class="sxs-lookup"><span data-stu-id="7157f-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="7157f-125">如需有關建立託管語音信箱原則的詳細資訊，請參閱在部署檔中<A href="lync-server-2013-manage-hosted-voice-mail-policies.md">管理 Lync Server 2013 中的託管語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="7157f-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="7157f-126">若要啟用或停用貴組織的聯盟使用者存取權</span><span class="sxs-lookup"><span data-stu-id="7157f-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="7157f-127">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7157f-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7157f-128">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7157f-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7157f-129">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7157f-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7157f-130">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="7157f-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="7157f-131">在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="7157f-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7157f-132">在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="7157f-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="7157f-133">若要為您的組織啟用聯盟使用者存取，請選取 [**啟用與同盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7157f-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="7157f-134">若要停用貴組織的聯盟使用者存取，請清除 [**啟用與同盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7157f-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="7157f-135">如果您選取 [**啟用與聯盟使用者的通訊**] 核取方塊，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7157f-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="7157f-136">如果您想要支援自動探索合作夥伴網域，請選取 [**啟用合作夥伴網域探索**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7157f-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="7157f-137">如果您的組織支援外部通訊的封存，請選取 [將封存**放棄免責聲明傳送給聯盟合作夥伴**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7157f-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="7157f-138">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7157f-138">Click **Commit**.</span></span>

<span data-ttu-id="7157f-139">若要讓聯盟使用者在 Lync Server 2013 部署中與使用者共同作業，您也必須至少設定一個外部存取原則來支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="7157f-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="7157f-140">如需詳細資訊，請參閱在部署檔或作業檔中，[設定在 Lync Server 2013 中控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7157f-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="7157f-141">若要控制特定聯盟網域的存取權，請參閱在部署檔或操作檔中的[Lync Server 2013 中設定允許的外部網域支援](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="7157f-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7157f-142">使用 Windows PowerShell Cmdlet 啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7157f-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7157f-143">您也可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="7157f-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="7157f-144">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="7157f-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7157f-145">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="7157f-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="7157f-146">啟用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7157f-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="7157f-147">若要啟用同盟與公用 IM 連線，請將**AllowFederatedUsers**屬性的值設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="7157f-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="7157f-148">停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7157f-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="7157f-149">若要停用同盟與公用 IM 連線，請將**AllowFederatedUsers**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="7157f-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

