---
title: 部署資源林拓撲
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 下列各節提供如何設定在資源/使用者目錄林模型中有多個目錄林的環境, 以提供混合式案例中的商務用 Skype 功能的指導方針。
ms.openlocfilehash: 7ef895648c044dc5d1f3f907ad4f75d950a4253a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185479"
---
# <a name="deploy-a-resource-forest-topology"></a><span data-ttu-id="2d80b-103">部署資源林拓撲</span><span class="sxs-lookup"><span data-stu-id="2d80b-103">Deploy a resource forest topology</span></span>
 
<span data-ttu-id="2d80b-104">下列各節提供如何設定在資源/使用者目錄林模型中有多個目錄林的環境, 以提供混合式案例中的商務用 Skype 功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="2d80b-104">The following sections provide guidance on how to configure an environment that has multiple forests in a resource/user forest model to provide Skype for Business functionality in a hybrid scenario.</span></span> 
  
![混合式多林環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a><span data-ttu-id="2d80b-106">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="2d80b-106">Topology requirements</span></span>

<span data-ttu-id="2d80b-107">支援多個使用者目錄林。</span><span class="sxs-lookup"><span data-stu-id="2d80b-107">Multiple user forests are supported.</span></span> <span data-ttu-id="2d80b-108">請記住下列事項:</span><span class="sxs-lookup"><span data-stu-id="2d80b-108">Keep the following in mind:</span></span> 
    
- <span data-ttu-id="2d80b-109">在混合式設定中, 如需 Lync Server 和商務用 Skype Server 的支援版本, 請參閱在[商務用 Skype server 和 Office 365 之間規劃混合式連接](plan-hybrid-connectivity.md)的[伺服器版本需求](plan-hybrid-connectivity.md#server-version-requirements)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-109">For supported versions of Lync Server and Skype for Business Server in a hybrid configuration, see [Server version requirements](plan-hybrid-connectivity.md#server-version-requirements) in [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="2d80b-110">Exchange Server 可以部署在一個或多個林中, 這些目錄林中可能包含或不包含商務用 Skype Server 的林。</span><span class="sxs-lookup"><span data-stu-id="2d80b-110">Exchange Server can be deployed in one or more forests, which may or may not include the forest containing Skype for Business Server.</span></span> <span data-ttu-id="2d80b-111">請確定您已套用最新的累加更新。</span><span class="sxs-lookup"><span data-stu-id="2d80b-111">Make sure you have applied the latest Cumulative Update.</span></span>
    
- <span data-ttu-id="2d80b-112">如需與 Exchange Server 共存的詳細資料, 包括各種內部部署和線上結合的支援準則與限制, 請參閱規劃中的[功能支援](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support),[以整合商務用 Skype 與 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-112">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>
    
  
## <a name="user-homing-considerations"></a><span data-ttu-id="2d80b-113">使用者引導的考慮</span><span class="sxs-lookup"><span data-stu-id="2d80b-113">User homing considerations</span></span>

<span data-ttu-id="2d80b-114">駐留在內部部署的商務用 Skype 使用者可以將 Exchange 駐留在內部部署或線上。</span><span class="sxs-lookup"><span data-stu-id="2d80b-114">Skype for Business users homed on premises can have Exchange homed on premises or online.</span></span> <span data-ttu-id="2d80b-115">商務用 Skype Online 使用者應該使用 Exchange Online 來獲得最佳體驗;不過, 這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="2d80b-115">Skype for Business Online users should use Exchange Online for an optimal experience; however, this is not required.</span></span> <span data-ttu-id="2d80b-116">在任何情況下, 都不需要在內部部署中實現商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="2d80b-116">Exchange on premises is not required to implement Skype for Business in either case.</span></span>
  
## <a name="configure-forest-trusts"></a><span data-ttu-id="2d80b-117">設定林信任</span><span class="sxs-lookup"><span data-stu-id="2d80b-117">Configure forest trusts</span></span>

<span data-ttu-id="2d80b-118">在資原始目錄林拓朴中, 託管商務用 Skype Server 的資原始目錄林必須信任每個帳戶目錄林, 其中包含可存取該帳戶的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2d80b-118">In a resource forest topology, the resource forests hosting Skype for Business Server must trust each account forest that contains users' accounts that will access it.</span></span> <span data-ttu-id="2d80b-119">如果您有多個使用者目錄林, 若要啟用跨目錄林驗證, 請務必針對這些目錄林信任啟用名稱尾碼路由。</span><span class="sxs-lookup"><span data-stu-id="2d80b-119">If you have multiple user forests, to enable cross-forest authentication it is important that Name Suffix Routing is enabled for each of these forest trusts.</span></span> <span data-ttu-id="2d80b-120">如需相關指示, 請參閱[管理林信任](https://technet.microsoft.com/en-us/library/cc772440.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-120">For instructions, see [Managing Forest Trusts](https://technet.microsoft.com/en-us/library/cc772440.aspx).</span></span> <span data-ttu-id="2d80b-121">如果您已在另一個目錄林中部署 Exchange 伺服器, 且它供應商務用 Skype 使用者的功能, 那麼託管 Exchange 的林就必須信任託管商務用 Skype 伺服器的目錄林。</span><span class="sxs-lookup"><span data-stu-id="2d80b-121">If you have Exchange Server deployed in an another forest and it provides functionality for Skype for Business users, the forest hosting Exchange must trust the forest hosting Skype for Business Server.</span></span> <span data-ttu-id="2d80b-122">例如, 如果 Exchange 是部署在帳戶目錄林中, 這會在該設定中有效表示客戶與商務用 Skype 目錄林之間的雙向信任。</span><span class="sxs-lookup"><span data-stu-id="2d80b-122">For example, if Exchange were deployed in the account forest, this would effectively mean a two-way trust between account and Skype for Business forests is required in that configuration.</span></span>
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a><span data-ttu-id="2d80b-123">將帳戶同步處理到主持商務用 Skype 的林中</span><span class="sxs-lookup"><span data-stu-id="2d80b-123">Synchronize accounts into the forest hosting Skype for Business</span></span>

<span data-ttu-id="2d80b-124">當商務用 Skype Server 部署在一個目錄林中 (資原始目錄林中), 但在一或多個其他目錄林 (帳戶目錄林) 中提供給使用者的功能, 其他林中的使用者必須在您的 Skype 適用的林中以停用的使用者物件表示已部署商務伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d80b-124">When Skype for Business Server is deployed in one forest (a resource forest), but provides functionality to users in one or more other forests (account forests), users in the other forests must be represented as disabled user objects in the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="2d80b-125">必須部署並設定身分識別管理產品 (例如 Microsoft 身分識別管理員), 才能將帳戶林的使用者設定並同步處理到部署商務用 Skype Server 的林中。</span><span class="sxs-lookup"><span data-stu-id="2d80b-125">An identity management product, such as Microsoft Identity Manager, needs to be deployed and configured to provision and synchronize the users from the account forests into the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="2d80b-126">使用者必須同步處理到主持商務用 Skype Server 的林中, 即已停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="2d80b-126">Users must be synchronized into the forest hosting Skype for Business Server as disabled user objects.</span></span> <span data-ttu-id="2d80b-127">使用者無法同步處理為 Active Directory 連絡人物件, 因為 Azure Active Directory Connect 將無法正確同步處理連絡人至 Azure AD, 以便與 Skype 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2d80b-127">Users cannot be synchronized as Active Directory contact objects, because Azure Active Directory Connect will not properly synchronize contacts into Azure AD for use with Skype.</span></span>
  
<span data-ttu-id="2d80b-128">無論任何多重目錄林設定為何, 託管商務用 Skype 伺服器的林也可以提供任何位於相同林中的已啟用使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="2d80b-128">Regardless of any multi-forest configuration, the forest hosting Skype for Business Server can also provide functionality for any enabled users that exist in the same forest.</span></span>
  
<span data-ttu-id="2d80b-129">若要取得正確的身分識別同步處理, 必須同步處理下列屬性:</span><span class="sxs-lookup"><span data-stu-id="2d80b-129">To get proper identity synchronization, the following attributes need to be synchronized:</span></span> 
  
|<span data-ttu-id="2d80b-130">**使用者目錄林**</span><span class="sxs-lookup"><span data-stu-id="2d80b-130">**User forests**</span></span>|<span data-ttu-id="2d80b-131">**資原始目錄林**</span><span class="sxs-lookup"><span data-stu-id="2d80b-131">**Resource forests**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d80b-132">[選取的帳戶] 連結屬性</span><span class="sxs-lookup"><span data-stu-id="2d80b-132">chosen account link attribute</span></span>  <br/> |<span data-ttu-id="2d80b-133">[選取的帳戶] 連結屬性</span><span class="sxs-lookup"><span data-stu-id="2d80b-133">chosen account link attribute</span></span>  <br/> |
|<span data-ttu-id="2d80b-134">郵遞</span><span class="sxs-lookup"><span data-stu-id="2d80b-134">mail</span></span>  <br/> |<span data-ttu-id="2d80b-135">郵遞</span><span class="sxs-lookup"><span data-stu-id="2d80b-135">mail</span></span>  <br/> |
|<span data-ttu-id="2d80b-136">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2d80b-136">ProxyAddresses</span></span>  <br/> |<span data-ttu-id="2d80b-137">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2d80b-137">ProxyAddresses</span></span>  <br/> |
|<span data-ttu-id="2d80b-138">ObjectSID</span><span class="sxs-lookup"><span data-stu-id="2d80b-138">ObjectSID</span></span>  <br/> |<span data-ttu-id="2d80b-139">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="2d80b-139">msRTCSIP-OriginatorSID</span></span>  <br/> |
   
<span data-ttu-id="2d80b-140">所[選的帳戶連結屬性](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/)將會用來做為來源錨點。</span><span class="sxs-lookup"><span data-stu-id="2d80b-140">The [chosen account link attribute](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) will be used as the Source Anchor.</span></span> <span data-ttu-id="2d80b-141">如果您想要使用不同且不可變的屬性, 您可以執行此動作。只要確認編輯 AD FS 聲明規則, 並在 AAD 連線設定期間選取屬性即可。</span><span class="sxs-lookup"><span data-stu-id="2d80b-141">If you have a different and immutable attribute that you would prefer to use, you may do so; just be sure to edit the AD FS claims rule and select the attribute during the AAD Connect configuration.</span></span>
  
<span data-ttu-id="2d80b-142">請勿在目錄林之間同步處理 Upn。</span><span class="sxs-lookup"><span data-stu-id="2d80b-142">Do not sync the UPNs between the forests.</span></span> <span data-ttu-id="2d80b-143">我們在測試期間發現我們需要針對每個使用者林使用唯一的 UPN, 因為您無法在多個目錄林使用相同的 UPN。</span><span class="sxs-lookup"><span data-stu-id="2d80b-143">We found during testing that we needed to use a unique UPN for each user forest, as you cannot use the same UPN across multiple forests.</span></span> <span data-ttu-id="2d80b-144">因此, 我們會提供兩種可能的方式, 以同步處理 UPN 或無法同步處理。</span><span class="sxs-lookup"><span data-stu-id="2d80b-144">As a result, we were presented with two possibilities, to synchronize the UPN or to not synchronize.</span></span> 
  
- <span data-ttu-id="2d80b-145">如果每個使用者樹林中的唯一 UPN 沒有與資原始目錄林中的相關聯停用物件同步處理, 單一登入 (SSO) 至少會中斷初始登入 (假設使用者已選取儲存密碼的選項)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-145">If the unique UPN from each user forest was not synchronized to the associated disabled object in the resource forest, single sign-on (SSO) would be broken for at least the initial sign-in attempt (assuming the user selected the option to save password).</span></span> <span data-ttu-id="2d80b-146">在商務用 Skype 用戶端中, 我們假設 SIP/UPN 值相同。</span><span class="sxs-lookup"><span data-stu-id="2d80b-146">In the Skype for Business client, we assume that the SIP/UPN values are the same.</span></span> <span data-ttu-id="2d80b-147">由於這個案例中的 SIP 位址是 user@company.com, 但使用者林中已啟用物件的 UPN 事實上是 user@contoso.company.com, 所以初始登入嘗試將會失敗, 且系統會提示使用者輸入認證。</span><span class="sxs-lookup"><span data-stu-id="2d80b-147">Since the SIP address in this scenario is user@company.com, but the UPN of the enabled object in the user forest is in fact user@contoso.company.com, the initial login attempt would fail and the user would be prompted to enter credentials.</span></span> <span data-ttu-id="2d80b-148">輸入正確/實際的 UPN 後, 驗證要求會針對使用者林中的網網域控制站完成, 且登入成功。</span><span class="sxs-lookup"><span data-stu-id="2d80b-148">Upon entering their correct/actual UPN, the authentication request would be completed against the domain controllers in the user forest, and sign-in would be successful.</span></span>
    
- <span data-ttu-id="2d80b-149">如果每個使用者林中的唯一 UPN 已同步處理至資原始目錄林中的關聯停用物件, 則 AD FS 驗證將會失敗。</span><span class="sxs-lookup"><span data-stu-id="2d80b-149">If the unique UPN from each user forest was synchronized to the associated disabled object in the resource forest, AD FS authentication would fail.</span></span> <span data-ttu-id="2d80b-150">[相符規則] 會在已停用且無法用於驗證的資原始目錄林中, 找到該物件上的 UPN。</span><span class="sxs-lookup"><span data-stu-id="2d80b-150">The matching rule would find the UPN on the object in the resource forest, which was disabled and could not be used for authentication.</span></span> 
    
## <a name="create-an-office-365-tenant"></a><span data-ttu-id="2d80b-151">建立 Office 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="2d80b-151">Create an Office 365 tenant</span></span>

<span data-ttu-id="2d80b-152">您必須先將 Office 365 租使用者提供給您的部署使用。</span><span class="sxs-lookup"><span data-stu-id="2d80b-152">You will next need to provision an Office 365 tenant to use with your deployment.</span></span> <span data-ttu-id="2d80b-153">如需詳細資訊, 請參閱[Microsoft 雲端服務的訂閱、授權、帳戶和](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)租使用者。</span><span class="sxs-lookup"><span data-stu-id="2d80b-153">For more information, please see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings).</span></span> 
  
## <a name="configure-active-directory-federation-services"></a><span data-ttu-id="2d80b-154">設定 Active Directory Federation Services</span><span class="sxs-lookup"><span data-stu-id="2d80b-154">Configure Active Directory Federation Services</span></span>

<span data-ttu-id="2d80b-155">當您擁有租使用者之後, 您將需要在每個使用者目錄林中設定 Active Directory Federation Services (AD FS)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-155">Once you have a tenant, you will need to configure Active Directory Federation Services (AD FS) in each of the user forests.</span></span> <span data-ttu-id="2d80b-156">這假設您有每個目錄林都有唯一的 SIP 與 SMTP 位址及使用者主體名稱 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-156">This assumes you have a unique SIP and SMTP address and User Principal Name (UPN) for each forest.</span></span> <span data-ttu-id="2d80b-157">AD FS 是選擇性的, 在這裡使用, 以取得單一登入 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-157">AD FS is optional and is used here to get single sign-on (SSO).</span></span> <span data-ttu-id="2d80b-158">也支援使用密碼同步處理的 DirSync, 也可以用來取代 AD FS。</span><span class="sxs-lookup"><span data-stu-id="2d80b-158">DirSync with Password Sync is also supported and can also be used in place of AD FS.</span></span> 
  
<span data-ttu-id="2d80b-159">僅測試具有相符 SIP/SMTP 與 Upn 的部署。</span><span class="sxs-lookup"><span data-stu-id="2d80b-159">Only deployments with matching SIP/SMTP and UPNs were tested.</span></span> <span data-ttu-id="2d80b-160">不具備相符的 SIP/SMTP/Upn, 可能會導致功能下降, 例如 Exchange 整合與 SSO 的問題。</span><span class="sxs-lookup"><span data-stu-id="2d80b-160">Not having matching SIP/SMTP/UPNs may result in reduced functionality, such as problems with Exchange integration and SSO.</span></span> 
  
<span data-ttu-id="2d80b-161">除非您針對每個目錄林中的使用者使用唯一的 SIP/SMTP/UPN, 否則無論 AD FS 部署在哪裡, 您仍然可以執行 SSO 問題:</span><span class="sxs-lookup"><span data-stu-id="2d80b-161">Unless you use a unique SIP/SMTP/UPN for users from each forest, you can still run into SSO problems, regardless of where AD FS is deployed:</span></span> 
  
- <span data-ttu-id="2d80b-162">在每個使用者林中部署 AD FS 場之資源/使用者目錄林之間的單向或雙向信任, 所有使用者都共用公用 SIP/SMTP 網域, 但每個使用者林都有唯一的 UPN。</span><span class="sxs-lookup"><span data-stu-id="2d80b-162">One-way or two-way trusts between resource/user forests with AD FS farm deployed in each user forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
- <span data-ttu-id="2d80b-163">只有在資原始目錄林中部署了 AD FS 場的資源/使用者林之間的雙向信任, 所有使用者才會共用公用 SIP/SMTP 網域, 但每個使用者林都有唯一的 UPN。</span><span class="sxs-lookup"><span data-stu-id="2d80b-163">Two-way trusts between resource/user forests with AD FS farm deployed only in resource forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
<span data-ttu-id="2d80b-164">透過將 AD FS 伺服器陣列放在每個使用者林中, 並針對每個目錄林使用唯一的 SIP/SMTP/UPN, 我們就能解決這兩個問題。</span><span class="sxs-lookup"><span data-stu-id="2d80b-164">By placing an AD FS farm in each user forest and using a unique SIP/SMTP/UPN for each forest, we resolve both issues.</span></span> <span data-ttu-id="2d80b-165">在驗證嘗試期間, 只會搜尋特定使用者林中的帳戶並進行相符。</span><span class="sxs-lookup"><span data-stu-id="2d80b-165">Only the accounts in that specific user forest would be searched and matched during authentication attempts.</span></span> <span data-ttu-id="2d80b-166">這將協助提供更順暢的驗證程式。</span><span class="sxs-lookup"><span data-stu-id="2d80b-166">This will help provide a more seamless authentication process.</span></span> 
  
<span data-ttu-id="2d80b-167">這將是 Windows Server 2012 R2 AD FS 的標準部署, 在繼續進行之前, 必須先進行工作。</span><span class="sxs-lookup"><span data-stu-id="2d80b-167">This will be a standard deployment of the Windows Server 2012 R2 AD FS and should be working before continuing.</span></span> <span data-ttu-id="2d80b-168">如需相關指示, 請參閱[如何安裝適用于 Office 365 的 AD FS 2012 R2](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-168">For instructions, see [How To Install AD FS 2012 R2 For Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx).</span></span> 
  
<span data-ttu-id="2d80b-169">部署之後, 您必須編輯宣告規則, 以符合先前選取的來源錨點。</span><span class="sxs-lookup"><span data-stu-id="2d80b-169">Once deployed, you then have to edit the claims rule to match the Source Anchor selected earlier.</span></span> <span data-ttu-id="2d80b-170">在 AD FS MMC 中的 [信賴方信任] 底下, 以滑鼠右鍵按一下 [ **Microsoft Office 365 身分識別平臺**], 然後按一下 [**編輯聲明規則**]。</span><span class="sxs-lookup"><span data-stu-id="2d80b-170">In the AD FS MMC, under Relying Party Trusts, right-click **Microsoft Office 365 Identity Platform**, and then click **Edit Claim Rules**.</span></span> <span data-ttu-id="2d80b-171">編輯第一個規則, 然後將 ObjectSID 變更為 [ **employeeNumber**]。</span><span class="sxs-lookup"><span data-stu-id="2d80b-171">Edit the first rule, and change ObjectSID to **employeeNumber**.</span></span> 
  
![多目錄林編輯規則畫面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a><span data-ttu-id="2d80b-173">設定 AAD Connect</span><span class="sxs-lookup"><span data-stu-id="2d80b-173">Configure AAD Connect</span></span>

<span data-ttu-id="2d80b-174">在資原始目錄林拓朴中, 您必須將來自資原始目錄林和任何帳戶目錄林的使用者屬性同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="2d80b-174">In resource forest topologies, it’s required that user attributes from both the resource forest and any account forests(s) are synchronized into Azure AD.</span></span> <span data-ttu-id="2d80b-175">若要這麼做, 最簡單且建議的方式是讓 Azure AD Connect 從已啟用使用者帳戶的*所有*目錄林以及包含商務用 Skype 的林, 同步處理及合併使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="2d80b-175">The simplest and recommended way to do this is to have Azure AD Connect synchronize and merge user identities from *all* forests that have enabled user accounts and the forest that contains Skype for Business.</span></span> <span data-ttu-id="2d80b-176">如需詳細資訊, 請參閱針對[商務用 Skype 與團隊設定 AZURE AD Connect](configure-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-176">For details see, [Configure Azure AD Connect for Skype for Business and Teams](configure-azure-ad-connect.md).</span></span>

<span data-ttu-id="2d80b-177">請注意, AAD Connect 不會提供帳戶與資原始目錄林之間內部部署的同步處理。</span><span class="sxs-lookup"><span data-stu-id="2d80b-177">Note that AAD Connect does not provide synchronization on premises between the account and resource forests.</span></span> <span data-ttu-id="2d80b-178">必須使用 Microsoft 身分識別管理員或類似的產品來分別設定, 如前文所述。</span><span class="sxs-lookup"><span data-stu-id="2d80b-178">That must be separately configured using Microsoft Identity Manager or similar product, as described earlier.</span></span>
  
<span data-ttu-id="2d80b-179">完成併合並 AAD 連線後, 如果您在元節中查看物件, 就會看到類似以下的內容:</span><span class="sxs-lookup"><span data-stu-id="2d80b-179">When finished and AAD Connect is merging, if you look at an object in the metaverse, you should see something similar to this:</span></span> 
  
![多林元節物件畫面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
<span data-ttu-id="2d80b-181">綠色醒目提示的屬性已從 Office 365 合併, 黃色來自使用者林, 而藍色則來自資原始目錄林。</span><span class="sxs-lookup"><span data-stu-id="2d80b-181">The green highlighted attributes were merged from Office 365, the yellow are from the user forest, and the blue are from the resource forest.</span></span> 
  
<span data-ttu-id="2d80b-182">這是測試使用者, 您可以看到 AAD Connect 已識別來自 Office 365 的使用者和資原始目錄林物件的 sourceAnchor 和 cloudSourceAnchor, 這是1101我們先前選取的 employeeNumber。</span><span class="sxs-lookup"><span data-stu-id="2d80b-182">This is a test user, and you can see that AAD Connect has identified the sourceAnchor and the cloudSourceAnchor from the user and the resource forest objects from Office 365, in our case 1101, which is the employeeNumber selected earlier.</span></span> <span data-ttu-id="2d80b-183">然後, 就能將這個物件合併至上述內容。</span><span class="sxs-lookup"><span data-stu-id="2d80b-183">It then was able to merge this object into what you see above.</span></span> 
  
<span data-ttu-id="2d80b-184">如需詳細資訊, 請參閱[將您的內部部署目錄與 Azure Active Directory 整合](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-184">For more information, see [Integrate your on-premises directories with Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/).</span></span> 
  
<span data-ttu-id="2d80b-185">AAD Connect 應該使用預設值進行安裝, 但下列動作除外:</span><span class="sxs-lookup"><span data-stu-id="2d80b-185">AAD Connect should be installed using the defaults, except for the following:</span></span> 
  
1. <span data-ttu-id="2d80b-186">單一登入與已部署且正常運作的 AD FS: 選取 [**不要設定**]。</span><span class="sxs-lookup"><span data-stu-id="2d80b-186">Single sign-in - with AD FS already deployed and working: Select **Do not configure**.</span></span>
    
2. <span data-ttu-id="2d80b-187">連接您的目錄: 新增所有網域。</span><span class="sxs-lookup"><span data-stu-id="2d80b-187">Connect your directories: Add all of the domains.</span></span>
    
3. <span data-ttu-id="2d80b-188">在內部部署目錄中找出使用者: 選取**多個目錄**中都存在的使用者身分識別, 然後選取 [ **ObjectSID** ] 和 [ **msExchangeMasterAccountSID** ] 屬性。</span><span class="sxs-lookup"><span data-stu-id="2d80b-188">Identify users in on-premises directories: Select **User identities exist across multiple directories**, and select the **ObjectSID** and **msExchangeMasterAccountSID** attributes.</span></span>
    
4. <span data-ttu-id="2d80b-189">在 Azure AD 中識別使用者: 來源錨點: 選取您在閱讀[選取好的 sourceAnchor 屬性](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/)(使用者主體名稱- **userPrincipalName**) 後所選取的屬性。</span><span class="sxs-lookup"><span data-stu-id="2d80b-189">Identify users in Azure AD: Source Anchor: Select the attribute you've chosen after reading [Selecting a good sourceAnchor attribute](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), User Principal Name - **userPrincipalName**.</span></span>
    
5.  <span data-ttu-id="2d80b-190">選用的功能: 選取您是否已部署 Exchange 混合式。</span><span class="sxs-lookup"><span data-stu-id="2d80b-190">Optional features: Select whether you have Exchange hybrid deployed.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="2d80b-191">如果您只有 Exchange Online, 則在自動探索期間由於 CNAME 重新導向, 可能會發生 OAuth 失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="2d80b-191">If you have only Exchange Online, there could be an issue with OAuth failures during autodiscover because of CNAME redirection.</span></span> <span data-ttu-id="2d80b-192">若要修正此錯誤, 您需要從商務用 Skype Server Management Shell 執行下列 Cmdlet 來設定 Exchange 自動探索 URL:</span><span class="sxs-lookup"><span data-stu-id="2d80b-192">To correct this, you will need to set the Exchange Autodiscover URL by running the following cmdlet from the Skype for Business Server Management Shell:</span></span>
  
    <span data-ttu-id="2d80b-193">CsOAuthConfiguration-ExchangeAutoDiscoverURL HTTPs://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc</span><span class="sxs-lookup"><span data-stu-id="2d80b-193">Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc</span></span> 
    
6.  <span data-ttu-id="2d80b-194">AD FS 伺服器陣列: 選取 [**使用現有的 Windows Server 2012 R2 AD FS 伺服器**陣列], 然後輸入 AD FS 伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="2d80b-194">AD FS Farm: Select **Use an existing Windows Server 2012 R2 AD FS farm** and enter the name of the AD FS server.</span></span>
    
7.  <span data-ttu-id="2d80b-195">完成嚮導並執行必要的驗證。</span><span class="sxs-lookup"><span data-stu-id="2d80b-195">Finish the wizard and perform the necessary validations.</span></span>
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a><span data-ttu-id="2d80b-196">設定商務用 Skype Server 的混合式連線性</span><span class="sxs-lookup"><span data-stu-id="2d80b-196">Configure hybrid connectivity for Skype for Business Server</span></span>

<span data-ttu-id="2d80b-197">遵循設定商務用 Skype 混合式的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="2d80b-197">Follow the best practices for configuring Skype for Business hybrid.</span></span> <span data-ttu-id="2d80b-198">如需詳細資訊, 請參閱[規劃混合式連線性](plan-hybrid-connectivity.md)並[設定混合式連線性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-198">For more information information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a><span data-ttu-id="2d80b-199">設定 Exchange Server 的混合式連線性</span><span class="sxs-lookup"><span data-stu-id="2d80b-199">Configure hybrid connectivity for Exchange Server</span></span>

<span data-ttu-id="2d80b-200">如有需要, 請遵循設定 Exchange 混合式的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="2d80b-200">If necessary, follow the best practices for configuring Exchange hybrid.</span></span> <span data-ttu-id="2d80b-201">如需詳細資訊, 請參閱[Exchange 伺服器混合式部署](https://docs.microsoft.com/en-us/exchange/exchange-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="2d80b-201">For more information, see [Exchange Server Hybrid Deployments](https://docs.microsoft.com/en-us/exchange/exchange-hybrid).</span></span> 
  

