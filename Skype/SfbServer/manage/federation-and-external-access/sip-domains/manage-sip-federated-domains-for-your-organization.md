---
title: 管理組織的 SIP 同盟網域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解如何管理及設定可與您聯盟的 SIP 網域,
ms.openlocfilehash: 1a2f76f7f465401bae04b4defa2e0a1f5300ab0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193597"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="4687a-103">在商務用 Skype Server 中管理貴組織的 SIP 聯盟網域</span><span class="sxs-lookup"><span data-stu-id="4687a-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="4687a-104">若要管理和設定可與您聯盟的 SIP 網域, 您可以執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="4687a-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="4687a-105">建立或編輯 SIP 聯盟夥伴網域的允許網域清單。</span><span class="sxs-lookup"><span data-stu-id="4687a-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="4687a-106">建立或編輯受封鎖之 SIP 聯盟網域的網域清單。</span><span class="sxs-lookup"><span data-stu-id="4687a-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="4687a-107">在商務用 Skype Server 中設定允許的外部網域支援</span><span class="sxs-lookup"><span data-stu-id="4687a-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="4687a-108">如果您已設定聯盟夥伴的支援, 您可以管理哪些特定網域可以與您的組織聯盟。</span><span class="sxs-lookup"><span data-stu-id="4687a-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="4687a-109">您將一或多個特定外部網域設定為允許聯盟網域。</span><span class="sxs-lookup"><span data-stu-id="4687a-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="4687a-110">若要這樣做, 請將每個網域新增到允許的網域清單中。</span><span class="sxs-lookup"><span data-stu-id="4687a-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="4687a-111">即使您的組織已啟用合作夥伴探索, 如果網域是聯盟夥伴, 可能需要與超過1000的使用者通訊, 或者可能需要每秒傳送超過20封郵件。</span><span class="sxs-lookup"><span data-stu-id="4687a-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="4687a-112">如果您的組織未啟用合作夥伴探索, 則只有您新增至 [允許的網域] 清單的外部網域使用者, 才能與組織中的使用者參與 IM 和會議。</span><span class="sxs-lookup"><span data-stu-id="4687a-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="4687a-113">如果您想要將同盟網域的存取許可權制為執行同盟夥伴之存取邊緣服務的特定伺服器, 您可以在允許的網域清單中, 為每個網域指定執行 Access Edge 服務的伺服器功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="4687a-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="4687a-114">此程式說明如何針對特定網域設定支援, 但實現同盟使用者的支援也需要您針對貴組織啟用聯盟使用者支援, 以及設定及套用原則, 以控制哪些使用者可以與聯盟使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="4687a-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="4687a-115">如需有關啟用聯盟使用者支援的詳細資料, 請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="4687a-116">如需設定控制同盟的原則的詳細資料, 請參閱[設定控制聯盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="4687a-117">將外部網域新增至允許的網域清單</span><span class="sxs-lookup"><span data-stu-id="4687a-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="4687a-118">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4687a-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="4687a-119">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4687a-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="4687a-120">在左側導覽列中, 按一下 [**外部使用者存取**], 然後按一下 [**聯盟網域**]。</span><span class="sxs-lookup"><span data-stu-id="4687a-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="4687a-121">在 [**聯盟網域**] 頁面上, 按一下 [**新增**], 然後按一下 [**允許的網域**]。</span><span class="sxs-lookup"><span data-stu-id="4687a-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="4687a-122">在**新的聯盟網域**中, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="4687a-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="4687a-123">在 **[Domain name (或 FQDN)**] 中, 輸入聯盟夥伴網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="4687a-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="4687a-124">這個名稱必須是唯一的, 而且不能作為執行存取邊緣服務的此伺服器的允許網域存在。</span><span class="sxs-lookup"><span data-stu-id="4687a-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="4687a-125">名稱長度不能超過256個字元。</span><span class="sxs-lookup"><span data-stu-id="4687a-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="4687a-126">在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。</span><span class="sxs-lookup"><span data-stu-id="4687a-126">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="4687a-127">例如, 如果您輸入**contoso.com**, 則搜尋也會傳回網域**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="4687a-127">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="4687a-128">聯盟夥伴網域不能同時封鎖及允許。</span><span class="sxs-lookup"><span data-stu-id="4687a-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="4687a-129">商務用 Skype Server 無法避免這種情況, 因此您不需要同步處理您的清單。</span><span class="sxs-lookup"><span data-stu-id="4687a-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="4687a-130">如果您想要將此聯盟網域的存取許可權制為執行存取邊緣服務的特定伺服器的使用者, 請在 **[存取邊緣服務 (FQDN)**] 中, 輸入執行 [存取邊緣] 服務之聯盟網域伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4687a-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="4687a-131">如果您想要提供其他資訊, 請在 [**批註**] 中, 輸入您要與其他系統管理員共用此設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="4687a-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="4687a-132">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4687a-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="4687a-133">針對您要允許的每個聯盟夥伴網域, 重複步驟4到6。</span><span class="sxs-lookup"><span data-stu-id="4687a-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="4687a-134">若要啟用同盟使用者存取, 您也必須在組織中啟用聯盟使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="4687a-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="4687a-135">如需詳細資訊, 請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="4687a-136">此外, 您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="4687a-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="4687a-137">如需詳細資訊, 請參閱[設定控制聯盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="4687a-138">在商務用 Skype Server 中設定封鎖的外部網域支援</span><span class="sxs-lookup"><span data-stu-id="4687a-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="4687a-139">如果您已設定聯盟夥伴的支援, 您可以管理哪些網域將被封鎖, 無法與您的組織進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="4687a-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="4687a-140">封鎖的網域清單會充當封鎖清單 (不允許的明確專案清單), 如果您已啟用此選項, 就會套用到聯盟網域探索中。</span><span class="sxs-lookup"><span data-stu-id="4687a-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="4687a-141">如需詳細資訊, 請參閱[啟用或停用同盟合作夥伴的探索](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="4687a-142">封鎖一或多個外部網域以連線到您的組織。</span><span class="sxs-lookup"><span data-stu-id="4687a-142">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="4687a-143">若要這樣做, 請將網域新增到封鎖網域的清單中。</span><span class="sxs-lookup"><span data-stu-id="4687a-143">To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="4687a-144">將外部網域新增至封鎖的網域清單</span><span class="sxs-lookup"><span data-stu-id="4687a-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="4687a-145">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4687a-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="4687a-146">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4687a-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="4687a-147">在左側導覽列中, 按一下 [**外部使用者存取**]。</span><span class="sxs-lookup"><span data-stu-id="4687a-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="4687a-148">按一下 [**聯盟網域**], 按一下 [**新增**], 然後按一下 [**封鎖的網域**]。</span><span class="sxs-lookup"><span data-stu-id="4687a-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="4687a-149">在**新的聯盟網域**中, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="4687a-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="4687a-150">在 **[Domain name (或 FQDN)**] 中, 輸入您要封鎖的聯盟夥伴網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="4687a-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="4687a-151">名稱長度不能超過256個字元。</span><span class="sxs-lookup"><span data-stu-id="4687a-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="4687a-152">在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。</span><span class="sxs-lookup"><span data-stu-id="4687a-152">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="4687a-153">例如, 如果您輸入**contoso.com**, 則搜尋也會傳回網域**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="4687a-153">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="4687a-154">聯盟夥伴網域不能同時封鎖及允許。</span><span class="sxs-lookup"><span data-stu-id="4687a-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="4687a-155">商務用 Skype Server 無法避免這種情況, 因此您不需要同步處理您的清單。</span><span class="sxs-lookup"><span data-stu-id="4687a-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="4687a-156">可選在 [**批註**] 中, 輸入您要與其他系統管理員共用這項設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="4687a-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="4687a-157">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4687a-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="4687a-158">針對您要封鎖的每個聯盟夥伴, 重複步驟4到6。</span><span class="sxs-lookup"><span data-stu-id="4687a-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="4687a-159">若要啟用同盟使用者存取, 您也必須在組織中啟用聯盟使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="4687a-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="4687a-160">如需詳細資訊, 請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="4687a-161">此外, 您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="4687a-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="4687a-162">如需詳細資訊, 請參閱[設定控制聯盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4687a-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="4687a-163">請參閱</span><span class="sxs-lookup"><span data-stu-id="4687a-163">See Also</span></span>

[<span data-ttu-id="4687a-164">設定控制聯盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="4687a-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="4687a-165">啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="4687a-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="4687a-166">啟用或停用同盟合作夥伴的發現</span><span class="sxs-lookup"><span data-stu-id="4687a-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

