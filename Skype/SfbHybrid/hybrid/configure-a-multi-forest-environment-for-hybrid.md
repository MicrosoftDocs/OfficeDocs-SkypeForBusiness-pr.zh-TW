---
title: 部署資源樹系拓撲
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 下列各節提供如何設定資源/使用者樹系模型中有多個樹系的環境，以在混合案例中供應商務用 Skype 功能的指導方針。
ms.openlocfilehash: acfca3b29407b019b87f5429906dbc72b4ef7dc3
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918682"
---
# <a name="deploy-a-resource-forest-topology"></a><span data-ttu-id="788b6-103">部署資源樹系拓撲</span><span class="sxs-lookup"><span data-stu-id="788b6-103">Deploy a resource forest topology</span></span>
 
<span data-ttu-id="788b6-104">下列各節提供如何設定資源/使用者樹系模型中有多個樹系的環境，以在混合案例中供應商務用 Skype 功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="788b6-104">The following sections provide guidance on how to configure an environment that has multiple forests in a resource/user forest model to provide Skype for Business functionality in a hybrid scenario.</span></span> 
  
![混合式的多樹系環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a><span data-ttu-id="788b6-106">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="788b6-106">Topology requirements</span></span>

<span data-ttu-id="788b6-107">支援多個使用者樹系。</span><span class="sxs-lookup"><span data-stu-id="788b6-107">Multiple user forests are supported.</span></span> <span data-ttu-id="788b6-108">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="788b6-108">Keep the following in mind:</span></span> 
    
- <span data-ttu-id="788b6-109">如需混合式設定中的支援版本的 Lync Server 和商務用 Skype Server，請參閱[規劃商務用 Skype server 與 Office 365 之間的混合](plan-hybrid-connectivity.md)式連線中的[伺服器版本需求](plan-hybrid-connectivity.md#server-version-requirements)。</span><span class="sxs-lookup"><span data-stu-id="788b6-109">For supported versions of Lync Server and Skype for Business Server in a hybrid configuration, see [Server version requirements](plan-hybrid-connectivity.md#server-version-requirements) in [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="788b6-110">Exchange Server 可以部署在一個或多個樹系中，可能包含或不包含商務用 Skype 伺服器的樹系。</span><span class="sxs-lookup"><span data-stu-id="788b6-110">Exchange Server can be deployed in one or more forests, which may or may not include the forest containing Skype for Business Server.</span></span> <span data-ttu-id="788b6-111">請確認您已套用最新的累計更新。</span><span class="sxs-lookup"><span data-stu-id="788b6-111">Make sure you have applied the latest Cumulative Update.</span></span>
    
- <span data-ttu-id="788b6-112">如需與 Exchange 伺服器共存的詳細資訊，包括在內部部署和線上的各種組合中支援的準則和限制，請參閱 Plan 中的[功能支援](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)，[以整合商務用 Skype 與 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。</span><span class="sxs-lookup"><span data-stu-id="788b6-112">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>
    
  
## <a name="user-homing-considerations"></a><span data-ttu-id="788b6-113">使用者主頁考慮</span><span class="sxs-lookup"><span data-stu-id="788b6-113">User homing considerations</span></span>

<span data-ttu-id="788b6-114">位於內部部署的商務用 Skype 使用者可以將 Exchange 置於內部部署或線上。</span><span class="sxs-lookup"><span data-stu-id="788b6-114">Skype for Business users homed on premises can have Exchange homed on premises or online.</span></span> <span data-ttu-id="788b6-115">商務用 Skype Online 使用者應使用 Exchange Online 以取得最佳的體驗。不過，這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="788b6-115">Skype for Business Online users should use Exchange Online for an optimal experience; however, this is not required.</span></span> <span data-ttu-id="788b6-116">在這兩種情況下，不需要 Exchange 內部部署即可實施商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="788b6-116">Exchange on premises is not required to implement Skype for Business in either case.</span></span>
  
## <a name="configure-forest-trusts"></a><span data-ttu-id="788b6-117">設定樹系信任</span><span class="sxs-lookup"><span data-stu-id="788b6-117">Configure forest trusts</span></span>

<span data-ttu-id="788b6-118">在資源樹系拓撲中，主控商務用 Skype 伺服器的資源樹系必須信任每個包含使用者帳戶的帳戶樹系，該樹系會存取該樹系。</span><span class="sxs-lookup"><span data-stu-id="788b6-118">In a resource forest topology, the resource forests hosting Skype for Business Server must trust each account forest that contains users' accounts that will access it.</span></span> <span data-ttu-id="788b6-119">如果您有多個使用者樹系，若要啟用跨樹系驗證，則必須為每個樹系信任啟用名稱尾碼路由。</span><span class="sxs-lookup"><span data-stu-id="788b6-119">If you have multiple user forests, to enable cross-forest authentication it is important that Name Suffix Routing is enabled for each of these forest trusts.</span></span> <span data-ttu-id="788b6-120">如需相關指示，請參閱[管理樹系信任](https://technet.microsoft.com/library/cc772440.aspx)。</span><span class="sxs-lookup"><span data-stu-id="788b6-120">For instructions, see [Managing Forest Trusts](https://technet.microsoft.com/library/cc772440.aspx).</span></span> <span data-ttu-id="788b6-121">如果您已在另一個樹系中部署 Exchange 伺服器，而且該伺服器供應商務用 Skype 使用者的功能，則主控 Exchange 的樹系必須信任主控商務用 Skype 伺服器的樹系。</span><span class="sxs-lookup"><span data-stu-id="788b6-121">If you have Exchange Server deployed in an another forest and it provides functionality for Skype for Business users, the forest hosting Exchange must trust the forest hosting Skype for Business Server.</span></span> <span data-ttu-id="788b6-122">例如，如果 Exchange 部署在帳戶樹系中，這會在該設定中有效表示帳戶和商務用 Skype 樹系之間必須有雙向信任。</span><span class="sxs-lookup"><span data-stu-id="788b6-122">For example, if Exchange were deployed in the account forest, this would effectively mean a two-way trust between account and Skype for Business forests is required in that configuration.</span></span>
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a><span data-ttu-id="788b6-123">將帳戶同步處理到主控商務用 Skype 的樹系中</span><span class="sxs-lookup"><span data-stu-id="788b6-123">Synchronize accounts into the forest hosting Skype for Business</span></span>

<span data-ttu-id="788b6-124">當商務用 Skype Server 部署在一個樹系（資源樹系）中，但為一或多個其他樹系（帳戶樹系）中的使用者提供功能時，其他樹系中的使用者必須在部署商務用 Skype 伺服器的樹系中以停用的使用者物件表示。</span><span class="sxs-lookup"><span data-stu-id="788b6-124">When Skype for Business Server is deployed in one forest (a resource forest), but provides functionality to users in one or more other forests (account forests), users in the other forests must be represented as disabled user objects in the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="788b6-125">身分識別管理產品（例如 Microsoft Identity Manager）必須部署並設定，才能將帳戶樹系中的使用者布建並同步處理至部署商務用 Skype 伺服器的樹系中。</span><span class="sxs-lookup"><span data-stu-id="788b6-125">An identity management product, such as Microsoft Identity Manager, needs to be deployed and configured to provision and synchronize the users from the account forests into the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="788b6-126">使用者必須同步處理到主控商務用 Skype 伺服器的樹系中，做為停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="788b6-126">Users must be synchronized into the forest hosting Skype for Business Server as disabled user objects.</span></span> <span data-ttu-id="788b6-127">使用者無法以 Active Directory 連絡人物件的形式進行同步處理，因為 Azure Active Directory Connect 無法將連絡人正確同步處理到 Azure AD，以與 Skype 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="788b6-127">Users cannot be synchronized as Active Directory contact objects, because Azure Active Directory Connect will not properly synchronize contacts into Azure AD for use with Skype.</span></span>
  
<span data-ttu-id="788b6-128">不論任何多樹系設定，主控商務用 Skype 伺服器的樹系也可以為存在於相同樹系中的任何已啟用使用者提供功能。</span><span class="sxs-lookup"><span data-stu-id="788b6-128">Regardless of any multi-forest configuration, the forest hosting Skype for Business Server can also provide functionality for any enabled users that exist in the same forest.</span></span>
  
<span data-ttu-id="788b6-129">若要取得適當的身分識別同步處理，必須同步處理下列屬性：</span><span class="sxs-lookup"><span data-stu-id="788b6-129">To get proper identity synchronization, the following attributes need to be synchronized:</span></span> 
  
|<span data-ttu-id="788b6-130">**使用者樹系**</span><span class="sxs-lookup"><span data-stu-id="788b6-130">**User forests**</span></span>|<span data-ttu-id="788b6-131">**資原始目錄樹**</span><span class="sxs-lookup"><span data-stu-id="788b6-131">**Resource forests**</span></span>|
|:-----|:-----|
|<span data-ttu-id="788b6-132">選擇的帳戶連結屬性</span><span class="sxs-lookup"><span data-stu-id="788b6-132">chosen account link attribute</span></span>  <br/> |<span data-ttu-id="788b6-133">選擇的帳戶連結屬性</span><span class="sxs-lookup"><span data-stu-id="788b6-133">chosen account link attribute</span></span>  <br/> |
|<span data-ttu-id="788b6-134">mail</span><span class="sxs-lookup"><span data-stu-id="788b6-134">mail</span></span>  <br/> |<span data-ttu-id="788b6-135">mail</span><span class="sxs-lookup"><span data-stu-id="788b6-135">mail</span></span>  <br/> |
|<span data-ttu-id="788b6-136">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="788b6-136">ProxyAddresses</span></span>  <br/> |<span data-ttu-id="788b6-137">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="788b6-137">ProxyAddresses</span></span>  <br/> |
|<span data-ttu-id="788b6-138">ObjectSID</span><span class="sxs-lookup"><span data-stu-id="788b6-138">ObjectSID</span></span>  <br/> |<span data-ttu-id="788b6-139">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="788b6-139">msRTCSIP-OriginatorSID</span></span>  <br/> |
   
<span data-ttu-id="788b6-140">[選取的帳戶連結屬性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)將會做為來源錨點使用。</span><span class="sxs-lookup"><span data-stu-id="788b6-140">The [chosen account link attribute](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) will be used as the Source Anchor.</span></span> <span data-ttu-id="788b6-141">如果您想要使用不同且不可變的屬性，您可以這樣做;只須確定編輯 AD FS 宣告規則，並在 AAD 連線設定期間選取屬性。</span><span class="sxs-lookup"><span data-stu-id="788b6-141">If you have a different and immutable attribute that you would prefer to use, you may do so; just be sure to edit the AD FS claims rule and select the attribute during the AAD Connect configuration.</span></span>
  
<span data-ttu-id="788b6-142">請勿同步處理樹系之間的 Upn。</span><span class="sxs-lookup"><span data-stu-id="788b6-142">Do not sync the UPNs between the forests.</span></span> <span data-ttu-id="788b6-143">我們在測試期間發現，我們需要針對每個使用者樹系使用唯一的 UPN，因為您無法在多個樹系中使用相同的 UPN。</span><span class="sxs-lookup"><span data-stu-id="788b6-143">We found during testing that we needed to use a unique UPN for each user forest, as you cannot use the same UPN across multiple forests.</span></span> <span data-ttu-id="788b6-144">因此，我們會提供兩個可能的方式，同步處理 UPN 或不同步處理。</span><span class="sxs-lookup"><span data-stu-id="788b6-144">As a result, we were presented with two possibilities, to synchronize the UPN or to not synchronize.</span></span> 
  
- <span data-ttu-id="788b6-145">如果每個使用者樹系的唯一 UPN 未同步處理至資源樹系中的關聯停用物件，則至少會中斷初次登入（SSO）的單一登入（SSO），至少要有一個登入登錄（假設使用者選取了儲存密碼的選項）。</span><span class="sxs-lookup"><span data-stu-id="788b6-145">If the unique UPN from each user forest was not synchronized to the associated disabled object in the resource forest, single sign-on (SSO) would be broken for at least the initial sign-in attempt (assuming the user selected the option to save password).</span></span> <span data-ttu-id="788b6-146">在商務用 Skype 用戶端中，我們假設 SIP/UPN 值相同。</span><span class="sxs-lookup"><span data-stu-id="788b6-146">In the Skype for Business client, we assume that the SIP/UPN values are the same.</span></span> <span data-ttu-id="788b6-147">由於此案例中的 SIP 位址是 user@company.com，但使用者樹系中已啟用之物件的 UPN 實際上是 user@contoso.company.com，所以初始登入嘗試會失敗，且系統會提示使用者輸入認證。</span><span class="sxs-lookup"><span data-stu-id="788b6-147">Since the SIP address in this scenario is user@company.com, but the UPN of the enabled object in the user forest is in fact user@contoso.company.com, the initial login attempt would fail and the user would be prompted to enter credentials.</span></span> <span data-ttu-id="788b6-148">輸入正確/實際的 UPN 後，就會針對使用者樹系中的網域控制站完成驗證要求，而且登入會成功。</span><span class="sxs-lookup"><span data-stu-id="788b6-148">Upon entering their correct/actual UPN, the authentication request would be completed against the domain controllers in the user forest, and sign-in would be successful.</span></span>
    
- <span data-ttu-id="788b6-149">如果每個使用者樹系的唯一 UPN 已同步處理至資源樹系中關聯的已停用物件，則 AD FS 驗證會失敗。</span><span class="sxs-lookup"><span data-stu-id="788b6-149">If the unique UPN from each user forest was synchronized to the associated disabled object in the resource forest, AD FS authentication would fail.</span></span> <span data-ttu-id="788b6-150">比對規則會在資源樹系中的物件上找到 UPN，該物件已停用，且無法用於驗證。</span><span class="sxs-lookup"><span data-stu-id="788b6-150">The matching rule would find the UPN on the object in the resource forest, which was disabled and could not be used for authentication.</span></span> 
    
## <a name="create-an-office-365-organization"></a><span data-ttu-id="788b6-151">建立 Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="788b6-151">Create an Office 365 organization</span></span>

<span data-ttu-id="788b6-152">接下來您必須布建 Office 365 組織，以搭配您的部署使用。</span><span class="sxs-lookup"><span data-stu-id="788b6-152">You will next need to provision an Office 365 organization to use with your deployment.</span></span> <span data-ttu-id="788b6-153">如需詳細資訊，請參閱[Microsoft 雲端供應專案的訂閱、授權、帳戶及承租人](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。</span><span class="sxs-lookup"><span data-stu-id="788b6-153">For more information, please see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings).</span></span> 
  
## <a name="configure-active-directory-federation-services"></a><span data-ttu-id="788b6-154">設定 Active Directory Federation Services</span><span class="sxs-lookup"><span data-stu-id="788b6-154">Configure Active Directory Federation Services</span></span>

<span data-ttu-id="788b6-155">當您有租使用者之後，您必須在每個使用者樹系中設定 Active Directory Federation Services （AD FS）。</span><span class="sxs-lookup"><span data-stu-id="788b6-155">Once you have a tenant, you will need to configure Active Directory Federation Services (AD FS) in each of the user forests.</span></span> <span data-ttu-id="788b6-156">這假設您每個樹系都有唯一的 SIP 及 SMTP 位址和使用者主體名稱（UPN）。</span><span class="sxs-lookup"><span data-stu-id="788b6-156">This assumes you have a unique SIP and SMTP address and User Principal Name (UPN) for each forest.</span></span> <span data-ttu-id="788b6-157">AD FS 是選用的，此處用來取得單一登入（SSO）。</span><span class="sxs-lookup"><span data-stu-id="788b6-157">AD FS is optional and is used here to get single sign-on (SSO).</span></span> <span data-ttu-id="788b6-158">也支援具有密碼同步處理的 DirSync，也可以用來取代 AD FS。</span><span class="sxs-lookup"><span data-stu-id="788b6-158">DirSync with Password Sync is also supported and can also be used in place of AD FS.</span></span> 
  
<span data-ttu-id="788b6-159">僅測試具有符合 SIP/SMTP 和 Upn 的部署。</span><span class="sxs-lookup"><span data-stu-id="788b6-159">Only deployments with matching SIP/SMTP and UPNs were tested.</span></span> <span data-ttu-id="788b6-160">不符合 SIP/SMTP/Upn 的功能可能會導致功能降低，例如 Exchange 整合和 SSO 的問題。</span><span class="sxs-lookup"><span data-stu-id="788b6-160">Not having matching SIP/SMTP/UPNs may result in reduced functionality, such as problems with Exchange integration and SSO.</span></span> 
  
<span data-ttu-id="788b6-161">除非您針對每個樹系的使用者使用唯一的 SIP/SMTP/UPN，但不論 AD FS 部署於何處，仍然可以執行 SSO 問題：</span><span class="sxs-lookup"><span data-stu-id="788b6-161">Unless you use a unique SIP/SMTP/UPN for users from each forest, you can still run into SSO problems, regardless of where AD FS is deployed:</span></span> 
  
- <span data-ttu-id="788b6-162">在每個使用者樹系中部署 AD FS 伺服器樹系的資源/使用者樹系之間的單向或雙向信任，所有使用者都共用一般 SIP/SMTP 網域，但是每個使用者樹系都有唯一的 UPN。</span><span class="sxs-lookup"><span data-stu-id="788b6-162">One-way or two-way trusts between resource/user forests with AD FS farm deployed in each user forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
- <span data-ttu-id="788b6-163">只在資源樹系中部署 AD FS 伺服器樹系的資源/使用者樹系之間的雙向信任，所有使用者都共用一般 SIP/SMTP 網域，但是每個使用者樹系都有唯一的 UPN。</span><span class="sxs-lookup"><span data-stu-id="788b6-163">Two-way trusts between resource/user forests with AD FS farm deployed only in resource forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
<span data-ttu-id="788b6-164">在每個使用者樹系中放置一個 AD FS 伺服器陣列，並針對每個樹系使用唯一的 SIP/SMTP/UPN，我們會解決這兩個問題。</span><span class="sxs-lookup"><span data-stu-id="788b6-164">By placing an AD FS farm in each user forest and using a unique SIP/SMTP/UPN for each forest, we resolve both issues.</span></span> <span data-ttu-id="788b6-165">在驗證嘗試期間，只會搜尋該特定使用者樹系中的帳戶，並將其配對。</span><span class="sxs-lookup"><span data-stu-id="788b6-165">Only the accounts in that specific user forest would be searched and matched during authentication attempts.</span></span> <span data-ttu-id="788b6-166">這將協助提供更順暢的驗證程式。</span><span class="sxs-lookup"><span data-stu-id="788b6-166">This will help provide a more seamless authentication process.</span></span> 
  
<span data-ttu-id="788b6-167">這將是 Windows Server 2012 R2 AD FS 的標準部署，在繼續之前，應正常運作。</span><span class="sxs-lookup"><span data-stu-id="788b6-167">This will be a standard deployment of the Windows Server 2012 R2 AD FS and should be working before continuing.</span></span> <span data-ttu-id="788b6-168">如需相關指示，請參閱 how [To INSTALL AD FS 2012 R2 For Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。</span><span class="sxs-lookup"><span data-stu-id="788b6-168">For instructions, see [How To Install AD FS 2012 R2 For Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx).</span></span> 
  
<span data-ttu-id="788b6-169">部署之後，您必須編輯宣告規則，使其符合先前所選取的來源錨點。</span><span class="sxs-lookup"><span data-stu-id="788b6-169">Once deployed, you then have to edit the claims rule to match the Source Anchor selected earlier.</span></span> <span data-ttu-id="788b6-170">在 [AD FS MMC] 中的 [信賴憑證者信任] 底下，以滑鼠右鍵按一下 [ **Microsoft Office 365 身分識別平臺**]，然後按一下 [**編輯宣告規則**]。</span><span class="sxs-lookup"><span data-stu-id="788b6-170">In the AD FS MMC, under Relying Party Trusts, right-click **Microsoft Office 365 Identity Platform**, and then click **Edit Claim Rules**.</span></span> <span data-ttu-id="788b6-171">編輯第一個規則，並將 ObjectSID 變更為**employeeNumber**。</span><span class="sxs-lookup"><span data-stu-id="788b6-171">Edit the first rule, and change ObjectSID to **employeeNumber**.</span></span> 
  
![多樹系編輯規則畫面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a><span data-ttu-id="788b6-173">設定 AAD Connect</span><span class="sxs-lookup"><span data-stu-id="788b6-173">Configure AAD Connect</span></span>

<span data-ttu-id="788b6-174">在資源樹系拓撲中，資源樹系和任何帳戶樹系中的使用者屬性都必須同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="788b6-174">In resource forest topologies, it’s required that user attributes from both the resource forest and any account forests(s) are synchronized into Azure AD.</span></span> <span data-ttu-id="788b6-175">執行這項作業的最簡單和建議方式是讓 Azure AD Connect 同步處理及合併*所有*已啟用使用者帳戶的樹系和包含商務用 Skype 的樹系的使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="788b6-175">The simplest and recommended way to do this is to have Azure AD Connect synchronize and merge user identities from *all* forests that have enabled user accounts and the forest that contains Skype for Business.</span></span> <span data-ttu-id="788b6-176">如需詳細資訊，請參閱[為商務用 Skype 和團隊設定 AZURE AD Connect](configure-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="788b6-176">For details see, [Configure Azure AD Connect for Skype for Business and Teams](configure-azure-ad-connect.md).</span></span>

<span data-ttu-id="788b6-177">請注意，AAD Connect 不會提供帳戶和資源樹系之間的內部部署同步處理。</span><span class="sxs-lookup"><span data-stu-id="788b6-177">Note that AAD Connect does not provide synchronization on premises between the account and resource forests.</span></span> <span data-ttu-id="788b6-178">必須依先前所述，使用 Microsoft Identity Manager 或類似產品個別設定。</span><span class="sxs-lookup"><span data-stu-id="788b6-178">That must be separately configured using Microsoft Identity Manager or similar product, as described earlier.</span></span>
  
<span data-ttu-id="788b6-179">在合併完成和 AAD 連線時，如果您查看元節中的物件，您應該會看到類似下列的內容：</span><span class="sxs-lookup"><span data-stu-id="788b6-179">When finished and AAD Connect is merging, if you look at an object in the metaverse, you should see something similar to this:</span></span> 
  
![多樹系元節物件畫面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
<span data-ttu-id="788b6-181">綠色的醒目顯示內容已從 Office 365 合併，黃色是來自使用者樹系，而藍色則來自資源樹系。</span><span class="sxs-lookup"><span data-stu-id="788b6-181">The green highlighted attributes were merged from Office 365, the yellow are from the user forest, and the blue are from the resource forest.</span></span> 
  
<span data-ttu-id="788b6-182">這是測試使用者，您可以看到 AAD 連線已識別來自使用者的 sourceAnchor 和 cloudSourceAnchor，以及來自 Office 365 的資源樹系物件，在我們的案例1101中，這是先前所選取的 employeeNumber。</span><span class="sxs-lookup"><span data-stu-id="788b6-182">This is a test user, and you can see that AAD Connect has identified the sourceAnchor and the cloudSourceAnchor from the user and the resource forest objects from Office 365, in our case 1101, which is the employeeNumber selected earlier.</span></span> <span data-ttu-id="788b6-183">然後，它就可以將此物件合併成您在上方看到的內容。</span><span class="sxs-lookup"><span data-stu-id="788b6-183">It then was able to merge this object into what you see above.</span></span> 
  
<span data-ttu-id="788b6-184">如需詳細資訊，請參閱[將您的內部部署目錄與 Azure Active Directory 整合](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)。</span><span class="sxs-lookup"><span data-stu-id="788b6-184">For more information, see [Integrate your on-premises directories with Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/).</span></span> 
  
<span data-ttu-id="788b6-185">AAD Connect 應該使用預設值安裝，但不包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="788b6-185">AAD Connect should be installed using the defaults, except for the following:</span></span> 
  
1. <span data-ttu-id="788b6-186">已部署並運作單一登入與 AD FS：選取 [不**設定**]。</span><span class="sxs-lookup"><span data-stu-id="788b6-186">Single sign-in - with AD FS already deployed and working: Select **Do not configure**.</span></span>
    
2. <span data-ttu-id="788b6-187">連接您的目錄：新增所有網域。</span><span class="sxs-lookup"><span data-stu-id="788b6-187">Connect your directories: Add all of the domains.</span></span>
    
3. <span data-ttu-id="788b6-188">在內部部署目錄中識別使用者：選取**跨越多個目錄的使用者識別碼**，然後選取**ObjectSID**及**msExchangeMasterAccountSID**屬性。</span><span class="sxs-lookup"><span data-stu-id="788b6-188">Identify users in on-premises directories: Select **User identities exist across multiple directories**, and select the **ObjectSID** and **msExchangeMasterAccountSID** attributes.</span></span>
    
4. <span data-ttu-id="788b6-189">在 Azure AD 中識別使用者：來源錨點：選取您在閱讀 [[選取好的 sourceAnchor 屬性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)、使用者主體名稱- **userPrincipalName**後所選擇的屬性。</span><span class="sxs-lookup"><span data-stu-id="788b6-189">Identify users in Azure AD: Source Anchor: Select the attribute you've chosen after reading [Selecting a good sourceAnchor attribute](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), User Principal Name - **userPrincipalName**.</span></span>
    
5.  <span data-ttu-id="788b6-190">選用功能：選取是否已部署 Exchange 混合式。</span><span class="sxs-lookup"><span data-stu-id="788b6-190">Optional features: Select whether you have Exchange hybrid deployed.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="788b6-191">如果您只有 Exchange Online，由於 CNAME 重新導向，所以自動探索期間可能會發生 OAuth 失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="788b6-191">If you have only Exchange Online, there could be an issue with OAuth failures during autodiscover because of CNAME redirection.</span></span> <span data-ttu-id="788b6-192">若要修正此錯誤，您必須從商務用 Skype Server 管理命令介面執行下列 Cmdlet 來設定 Exchange 自動探索 URL：</span><span class="sxs-lookup"><span data-stu-id="788b6-192">To correct this, you will need to set the Exchange Autodiscover URL by running the following cmdlet from the Skype for Business Server Management Shell:</span></span>
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  <span data-ttu-id="788b6-193">AD FS 伺服器陣列：選取 [**使用現有的 Windows Server 2012 R2 AD FS 伺服器陣列**]，然後輸入 AD fs 伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="788b6-193">AD FS Farm: Select **Use an existing Windows Server 2012 R2 AD FS farm** and enter the name of the AD FS server.</span></span>
    
7.  <span data-ttu-id="788b6-194">完成該嚮導並執行必要的驗證。</span><span class="sxs-lookup"><span data-stu-id="788b6-194">Finish the wizard and perform the necessary validations.</span></span>
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a><span data-ttu-id="788b6-195">設定商務用 Skype Server 的混合式連線</span><span class="sxs-lookup"><span data-stu-id="788b6-195">Configure hybrid connectivity for Skype for Business Server</span></span>

<span data-ttu-id="788b6-196">遵循設定商務用 Skype 混合式的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="788b6-196">Follow the best practices for configuring Skype for Business hybrid.</span></span> <span data-ttu-id="788b6-197">如需詳細資訊，請參閱[規劃混合](plan-hybrid-connectivity.md)式連線和[設定混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="788b6-197">For more information information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a><span data-ttu-id="788b6-198">設定 Exchange Server 的混合連接</span><span class="sxs-lookup"><span data-stu-id="788b6-198">Configure hybrid connectivity for Exchange Server</span></span>

<span data-ttu-id="788b6-199">如有必要，請遵循設定 Exchange 混合式的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="788b6-199">If necessary, follow the best practices for configuring Exchange hybrid.</span></span> <span data-ttu-id="788b6-200">如需詳細資訊，請參閱[Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="788b6-200">For more information, see [Exchange Server Hybrid Deployments](https://docs.microsoft.com/exchange/exchange-hybrid).</span></span> 
  
