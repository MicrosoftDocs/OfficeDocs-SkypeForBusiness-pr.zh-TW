---
title: 管理貴組織的 SIP 同盟網域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: 瞭解如何管理及設定您可以同盟的 SIP 網域，
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817213"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="f779c-103">在商務用 Skype Server 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="f779c-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="f779c-104">若要管理及設定您可以同盟的 SIP 網域，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f779c-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="f779c-105">建立或編輯 SIP 同盟協力廠商網域的允許網域清單。</span><span class="sxs-lookup"><span data-stu-id="f779c-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="f779c-106">建立或編輯 SIP 同盟網域的封鎖網域清單。</span><span class="sxs-lookup"><span data-stu-id="f779c-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="f779c-107">為商務用 Skype Server 中的允許外部網域設定支援</span><span class="sxs-lookup"><span data-stu-id="f779c-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="f779c-p101">如果已設定對同盟協力廠商的支援，則可以管理哪些特定網域可以與您的組織進行同盟。設定一個或多個特定的外部網域作為允許的同盟網域。若要這樣做，請將每個所需網域新增至允許網域清單。如果網域是可能需要與您超過 1,000 位使用者通訊或每秒傳送超過 20 封訊息的同盟協力廠商，則即使您的組織已啟用協力廠商探索，也建議您這樣做。如果您的組織未啟用協力廠商探索，則只有已新增至允許網域清單的外部網域的使用者，才能和您組織內的使用者進行 IM 和會議通訊。如果您要將同盟網域的存取限制於同盟協力廠商執行 Access Edge Service 的特定伺服器，可以針對允許網域清單中的每個網域，指定執行 Access Edge Service 之伺服器的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="f779c-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="f779c-114">此程序說明如何設定特定網域的支援，但實作同盟使用者的支援還需要您的組織啟用同盟使用者的支援，以及設定和套用原則以控制哪些使用者可以與同盟使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="f779c-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="f779c-115">如需啟用同盟使用者支援的詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f779c-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="f779c-116">如需設定控制同盟之原則的詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f779c-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="f779c-117">若要將外部網域新增至允許網域清單</span><span class="sxs-lookup"><span data-stu-id="f779c-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="f779c-118">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f779c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="f779c-119">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f779c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="f779c-120">在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[同盟網域]**。</span><span class="sxs-lookup"><span data-stu-id="f779c-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="f779c-121">在 **[同盟網域]** 頁面上，依序按一下 **[新增]** 和 **[允許的網域]**。</span><span class="sxs-lookup"><span data-stu-id="f779c-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="f779c-122">在 **[新增同盟網域]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f779c-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="f779c-123">在 **[網域名稱 (或 FQDN)]** 中，輸入同盟協力廠商網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="f779c-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="f779c-p103">此名稱必須是唯一的，而且不能已存在作為這個執行 Access Edge Service 的伺服器的允許網域。此外，名稱長度不可超過 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="f779c-p103">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="f779c-p104">搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 **contoso.com**，搜尋也會傳回網域 **it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="f779c-p104">The search on the federated partner domain name performs a suffix match. For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="f779c-128">不能同時封鎖又允許同一個同盟協力廠商網域。</span><span class="sxs-lookup"><span data-stu-id="f779c-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="f779c-129">商務用 Skype Server 避免發生這種情況，因此您不需要同步處理清單。</span><span class="sxs-lookup"><span data-stu-id="f779c-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="f779c-130">如果您要將同盟網域的存取限制於執行 Access Edge Service 之特定伺服器的使用者，可以在 **[Access Edge Service (FQDN)]** 中輸入執行 Access Edge Service 之同盟網域伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f779c-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="f779c-131">如果您要提供其他資訊，請在 **[註解]** 中輸入您想與其他系統管理員分享有關此設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="f779c-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="f779c-132">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f779c-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="f779c-133">為您要允許的每個同盟協力廠商網域重複步驟 4 到 6。</span><span class="sxs-lookup"><span data-stu-id="f779c-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="f779c-134">若要啟用同盟使用者存取，您也必須在組織中啟用對同盟使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="f779c-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="f779c-135">如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f779c-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="f779c-136">此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="f779c-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="f779c-137">如需詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f779c-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="f779c-138">在商務用 Skype Server 中為封鎖的外部網域設定支援</span><span class="sxs-lookup"><span data-stu-id="f779c-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="f779c-139">如果您已設定同盟協力廠商的支援，可以管理要禁止哪些網域與您的組織建立同盟。</span><span class="sxs-lookup"><span data-stu-id="f779c-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="f779c-140">如果您啟用此選項，封鎖網域清單將作為封鎖清單 (不被允許的明確項目清單)，並套用於同盟網域探索中。</span><span class="sxs-lookup"><span data-stu-id="f779c-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="f779c-141">如需詳細資訊，請參閱 [啟用或停用同盟](../access-edge/enable-or-disable-discovery-of-federation-partners.md)協力廠商的探索。</span><span class="sxs-lookup"><span data-stu-id="f779c-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="f779c-p109">封鎖一個或多個外部網域，不讓它們連線至您的組織。若要這樣做，請將網域新增至封鎖網域清單。</span><span class="sxs-lookup"><span data-stu-id="f779c-p109">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="f779c-144">將外部網域新增至封鎖網域清單</span><span class="sxs-lookup"><span data-stu-id="f779c-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="f779c-145">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f779c-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="f779c-146">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f779c-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="f779c-147">在左導覽列中，按一下 **[外部使用者存取]**。</span><span class="sxs-lookup"><span data-stu-id="f779c-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="f779c-148">依序按一下 **[同盟網域]**、**[新增]** 和 **[封鎖網域]**。</span><span class="sxs-lookup"><span data-stu-id="f779c-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="f779c-149">在 **[新增同盟網域]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f779c-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="f779c-150">在 **[網域名稱 (或 FQDN)]** 中，輸入您要封鎖的同盟協力廠商網域名稱。</span><span class="sxs-lookup"><span data-stu-id="f779c-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="f779c-151">名稱長度不可超過 256 個字元。</span><span class="sxs-lookup"><span data-stu-id="f779c-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="f779c-p110">搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 **contoso.com**，搜尋也會傳回網域 **it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="f779c-p110">The search on the federated partner domain name performs a suffix match. For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="f779c-154">不能同時封鎖又允許同一個同盟協力廠商網域。</span><span class="sxs-lookup"><span data-stu-id="f779c-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="f779c-155">商務用 Skype Server 避免發生這種情況，因此您不需要同步處理清單。</span><span class="sxs-lookup"><span data-stu-id="f779c-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="f779c-156">(選用) 在 **[註解]** 中，輸入您想與其他系統管理員分享的此設定相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f779c-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="f779c-157">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f779c-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="f779c-158">為您要封鎖的每個同盟協力廠商重複步驟 4 到 6。</span><span class="sxs-lookup"><span data-stu-id="f779c-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="f779c-159">若要啟用同盟使用者存取，您也必須在組織中啟用同盟使用者存取支援。</span><span class="sxs-lookup"><span data-stu-id="f779c-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="f779c-160">如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f779c-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="f779c-161">此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="f779c-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="f779c-162">如需詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f779c-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f779c-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f779c-163">See Also</span></span>

[<span data-ttu-id="f779c-164">設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="f779c-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="f779c-165">啟用或停用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f779c-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="f779c-166">啟用或停用同盟協力廠商探索</span><span class="sxs-lookup"><span data-stu-id="f779c-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

