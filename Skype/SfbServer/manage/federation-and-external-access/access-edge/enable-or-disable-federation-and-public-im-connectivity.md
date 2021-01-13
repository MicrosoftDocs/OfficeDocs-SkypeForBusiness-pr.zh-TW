---
title: 啟用或停用同盟和公用 IM 連線
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 必須具備同盟的支援，才能讓具有信任之客戶或夥伴組織之帳戶的使用者（包括夥伴網域和公用立即訊息 (IM) 提供者使用者）與組織中的使用者共同作業。
ms.openlocfilehash: 390b23a92f91d762c3703a36c063dde54dff1de1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817413"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a><span data-ttu-id="ba834-103">在商務用 Skype Server 中啟用或停用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ba834-103">Enable or disable federation and public IM connectivity in Skype for Business Server</span></span>

<span data-ttu-id="ba834-104">必須具備同盟的支援，才能讓具有信任之客戶或夥伴組織之帳戶的使用者（包括夥伴網域和公用立即訊息 (IM) 提供者使用者）與組織中的使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="ba834-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="ba834-105">同盟也是使用主控 Exchange 服務供應商提供語音信箱給 Enterprise Voice 使用者的使用者，這些使用者的信箱位於主控 Exchange 服務（如 Microsoft Exchange Online）。</span><span class="sxs-lookup"><span data-stu-id="ba834-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="ba834-106">當您建立與這些外部網域的信任關係時，您可以授權這些網域中的使用者存取您的部署，並參與商務用 Skype 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="ba834-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Skype for Business Server communications.</span></span> <span data-ttu-id="ba834-107">此信任關係稱為同盟，它與 Active Directory 信任關聯或無關。</span><span class="sxs-lookup"><span data-stu-id="ba834-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="ba834-108">若要支援同盟網域使用者的存取，您必須啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="ba834-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="ba834-109">如果您為組織啟用同盟，您也必須指定是否要執行下列選項：</span><span class="sxs-lookup"><span data-stu-id="ba834-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="ba834-110">**啟用夥伴網域探索**   如果您啟用此選項，則商務用 Skype 伺服器會使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。</span><span class="sxs-lookup"><span data-stu-id="ba834-110">**Enable partner domain discovery**   If you enable this option, Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="ba834-111">如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ba834-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="ba834-112">不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。</span><span class="sxs-lookup"><span data-stu-id="ba834-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="ba834-113">如需如何透過同盟網域來控制存取的詳細資訊，請參閱 [Configure support for 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="ba834-113">For details about controlling access by federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>

  - <span data-ttu-id="ba834-114">**將封存免責聲明傳送給同盟夥伴**    免責聲明通知會傳送給同盟協力廠商，以在您的部署中進行封存。</span><span class="sxs-lookup"><span data-stu-id="ba834-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="ba834-115">如果您支援與同盟協力廠商網域的外部通訊封存，您應該啟用封存免責聲明通知，以警告協力廠商郵件正在封存。</span><span class="sxs-lookup"><span data-stu-id="ba834-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="ba834-116">如果您稍後想要暫時或永久防止同盟網域的使用者進行存取，您可以停用組織的同盟。</span><span class="sxs-lookup"><span data-stu-id="ba834-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="ba834-117">使用本節中的程式來啟用或停用組織的同盟使用者存取，包括指定您的組織支援的適當同盟選項。</span><span class="sxs-lookup"><span data-stu-id="ba834-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="ba834-118">為您的組織啟用同盟，只會指定執行 Access Edge service 的伺服器支援路由傳送至同盟網域。</span><span class="sxs-lookup"><span data-stu-id="ba834-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="ba834-119">除非您也設定至少一個原則以支援同盟使用者存取，否則同盟網域中的使用者無法參與您組織中的 IM 或會議。</span><span class="sxs-lookup"><span data-stu-id="ba834-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="ba834-120">公用 IM 服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您也設定至少一個原則來支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="ba834-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="ba834-121">商務用 Skype 伺服器無法使用主控 Exchange 服務提供呼叫回應、Outlook Voice Access (包括語音信箱) 或自動語音應答服務，讓其信箱位於裝載 Exchange 服務上的使用者，直到您設定可提供路由資訊的主控語音信箱原則為止。</span><span class="sxs-lookup"><span data-stu-id="ba834-121">Skype for Business Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="ba834-122">如需設定策略以與其他組織中同盟網域的使用者進行通訊的詳細資訊，請參閱 [管理組織的 SIP 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ba834-122">For details about configuring policies for communication with users of federated domains in other organizations, see [Manage SIP federated domains for your organization](../sip-domains/manage-sip-federated-domains-for-your-organization.md).</span></span> <span data-ttu-id="ba834-123">此外，如果您想要支援與 IM 服務提供者的使用者進行通訊，則必須設定原則來支援它，也為您要支援的個別服務提供者設定支援。</span><span class="sxs-lookup"><span data-stu-id="ba834-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="ba834-124">如需詳細資訊，請參閱   [管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ba834-124">For details, see   [Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="ba834-125">啟用或停用組織的同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="ba834-125">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="ba834-126">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ba834-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba834-127">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ba834-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba834-128">在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge** 設定]。</span><span class="sxs-lookup"><span data-stu-id="ba834-128">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="ba834-129">在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ba834-129">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ba834-130">在 [ **編輯 Access Edge** 設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ba834-130">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="ba834-131">若要啟用組織的同盟使用者存取，請選取 [ **啟用與同盟使用者的通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ba834-131">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="ba834-132">若要停用組織的同盟使用者存取，請清除 [ **啟用與同盟使用者的通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ba834-132">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="ba834-133">如果您選取 [ **啟用與同盟使用者的通訊** ] 核取方塊，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ba834-133">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="ba834-134">如果您想要支援自動探索夥伴網域，請選取 [ **啟用夥伴網域探索** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ba834-134">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="ba834-135">如果您的組織支援外部通訊的封存，請選取 [將封存 **免責聲明傳送給同盟夥伴** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ba834-135">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="ba834-136">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ba834-136">Click **Commit**.</span></span>

<span data-ttu-id="ba834-137">若要讓同盟使用者與商務用 Skype Server 部署中的使用者共同作業，您也必須至少設定一個外部存取原則，以支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ba834-137">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="ba834-138">如需詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ba834-138">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="ba834-139">若要控制特定同盟網域的存取權，請參閱 [Configure support for 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="ba834-139">To control access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ba834-140">使用 Windows PowerShell Cmdlet 來啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ba834-140">Enabling or disabling federation and public IM connectivity by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ba834-141">同盟和公用 IM 連線能力也可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="ba834-141">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="ba834-142">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ba834-142">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="ba834-143">啟用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ba834-143">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="ba834-144">若要啟用同盟和公用 IM 連線，請將 **AllowFederatedUsers** 屬性的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="ba834-144">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="ba834-145">停用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ba834-145">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="ba834-146">若要停用同盟和公用 IM 連線，請將 **AllowFederatedUsers** 屬性的值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="ba834-146">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

