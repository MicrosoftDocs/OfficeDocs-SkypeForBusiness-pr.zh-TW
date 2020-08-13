---
title: Lync Server 2013：啟用或停用同盟和公用 IM 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad7e1ecce7c292b4022f15075635a5473417db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="34d17-102">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="34d17-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34d17-103">_**主題上次修改日期：** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="34d17-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="34d17-104">必須具備同盟的支援，才能讓具有信任之客戶或夥伴組織之帳戶的使用者（包括夥伴網域和公用立即訊息 (IM) 提供者使用者）與組織中的使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="34d17-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="34d17-105">同盟也是使用主控 Exchange 服務供應商提供語音信箱給 Enterprise Voice 使用者的使用者，這些使用者的信箱位於主控 Exchange 服務（如 Microsoft Exchange Online）。</span><span class="sxs-lookup"><span data-stu-id="34d17-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="34d17-106">當您建立與這些外部網域的信任關係時，您可以授權這些網域中的使用者存取您的部署，並參與 Lync Server 通訊。</span><span class="sxs-lookup"><span data-stu-id="34d17-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="34d17-107">此信任關係稱為同盟，它與 Active Directory 信任關聯或無關。</span><span class="sxs-lookup"><span data-stu-id="34d17-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="34d17-108">若要支援同盟網域使用者的存取，您必須啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="34d17-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="34d17-109">如果您為組織啟用同盟，您也必須指定是否要執行下列選項：</span><span class="sxs-lookup"><span data-stu-id="34d17-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="34d17-110">**啟用夥伴網域探索**    如果您啟用此選項，Lync Server 會使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。</span><span class="sxs-lookup"><span data-stu-id="34d17-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="34d17-111">如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="34d17-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="34d17-112">不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。</span><span class="sxs-lookup"><span data-stu-id="34d17-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="34d17-113">如需如何透過同盟網域控制存取的詳細資訊，請參閱[Configure support for 允許的外部網域 In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="34d17-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="34d17-114">**將封存免責聲明傳送給同盟夥伴**    免責聲明通知會傳送給同盟協力廠商，以在您的部署中進行封存。</span><span class="sxs-lookup"><span data-stu-id="34d17-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="34d17-115">如果您支援與同盟協力廠商網域的外部通訊封存，您應該啟用封存免責聲明通知，以警告協力廠商郵件正在封存。</span><span class="sxs-lookup"><span data-stu-id="34d17-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="34d17-116">如果您稍後想要暫時或永久防止同盟網域的使用者進行存取，您可以停用組織的同盟。</span><span class="sxs-lookup"><span data-stu-id="34d17-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="34d17-117">使用本節中的程式來啟用或停用組織的同盟使用者存取，包括指定您的組織支援的適當同盟選項。</span><span class="sxs-lookup"><span data-stu-id="34d17-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34d17-118">為您的組織啟用同盟，只會指定執行 Access Edge service 的伺服器支援路由傳送至同盟網域。</span><span class="sxs-lookup"><span data-stu-id="34d17-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="34d17-119">除非您也設定至少一個原則以支援同盟使用者存取，否則同盟網域中的使用者無法參與您組織中的 IM 或會議。</span><span class="sxs-lookup"><span data-stu-id="34d17-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="34d17-120">公用 IM 服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您也設定至少一個原則來支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="34d17-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="34d17-121">Lync Server 無法使用主控 Exchange 服務提供呼叫回應、Outlook Voice Access (包括語音信箱) 或自動語音應答服務，以供信箱位於裝載 Exchange 服務上的使用者，直到您設定可提供路由資訊的主控語音信箱原則為止。</span><span class="sxs-lookup"><span data-stu-id="34d17-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="34d17-122">如需設定策略以與其他組織中同盟網域的使用者進行通訊的詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 中管理組織的 SIP 同盟網域</A>。</span><span class="sxs-lookup"><span data-stu-id="34d17-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="34d17-123">此外，如果您想要支援與 IM 服務提供者的使用者進行通訊，則必須設定原則來支援它，也為您要支援的個別服務提供者設定支援。</span><span class="sxs-lookup"><span data-stu-id="34d17-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="34d17-124">如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013 中管理組織的 SIP 同盟提供者</A>。</span><span class="sxs-lookup"><span data-stu-id="34d17-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="34d17-125">如需建立主控語音信箱原則的詳細資訊，請參閱部署檔中的<A href="lync-server-2013-manage-hosted-voice-mail-policies.md">管理 Lync Server 2013 中的 hosted voice mail 原則</A>。</span><span class="sxs-lookup"><span data-stu-id="34d17-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="34d17-126">啟用或停用組織的同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="34d17-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="34d17-127">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="34d17-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34d17-128">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="34d17-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34d17-129">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="34d17-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34d17-130">在左導覽列中，按一下 [**外部使用者存取**]，然後按一下 [ **Access Edge**設定]。</span><span class="sxs-lookup"><span data-stu-id="34d17-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="34d17-131">在 [ **Access Edge**設定] 頁面上，依序按一下 [**全域**]、[**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="34d17-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="34d17-132">在 [**編輯 Access Edge**設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="34d17-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="34d17-133">若要啟用組織的同盟使用者存取，請選取 [**啟用與同盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="34d17-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="34d17-134">若要停用組織的同盟使用者存取，請清除 [**啟用與同盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="34d17-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="34d17-135">如果您選取 [**啟用與同盟使用者的通訊**] 核取方塊，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34d17-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="34d17-136">如果您想要支援自動探索夥伴網域，請選取 [**啟用夥伴網域探索**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="34d17-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="34d17-137">如果您的組織支援外部通訊的封存，請選取 [將封存**免責聲明傳送給同盟夥伴**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="34d17-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="34d17-138">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="34d17-138">Click **Commit**.</span></span>

<span data-ttu-id="34d17-139">若要讓同盟使用者與 Lync Server 2013 部署中的使用者共同作業，您也必須至少設定一個外部存取原則，以支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="34d17-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="34d17-140">如需詳細資訊，請參閱部署檔或作業檔中的[設定原則，以控制 Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)中的同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="34d17-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="34d17-141">若要控制特定同盟網域的存取權，請參閱部署檔或作業檔中的[Configure support For Lync Server 2013 中的允許外部網域](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="34d17-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="34d17-142">使用 Windows PowerShell Cmdlet 來啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="34d17-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="34d17-143">同盟和公用 IM 連線能力也可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="34d17-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="34d17-144">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="34d17-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="34d17-145">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="34d17-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="34d17-146">啟用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="34d17-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="34d17-147">若要啟用同盟和公用 IM 連線，請將**AllowFederatedUsers**屬性的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="34d17-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="34d17-148">停用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="34d17-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="34d17-149">若要停用同盟和公用 IM 連線，請將**AllowFederatedUsers**屬性的值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="34d17-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

