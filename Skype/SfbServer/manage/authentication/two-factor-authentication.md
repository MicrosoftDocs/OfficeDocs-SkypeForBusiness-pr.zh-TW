---
title: 在商務用 Skype Server 中管理雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '摘要: 在商務用 Skype Server 中管理雙因素驗證。'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193011"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="0fcef-103">在商務用 Skype Server 中管理雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="0fcef-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="0fcef-104">**摘要:** 在商務用 Skype Server 中管理雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="0fcef-105">雙因素驗證: 要求使用者提供兩種驗證或識別形式 (亦即使用者名稱/密碼組合以及權杖或憑證), 提供改良的安全性。</span><span class="sxs-lookup"><span data-stu-id="0fcef-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="0fcef-106">這也稱為「您有任何問題, 您知道」。</span><span class="sxs-lookup"><span data-stu-id="0fcef-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="0fcef-107">使用智慧卡的一個典型的雙因素驗證範例。</span><span class="sxs-lookup"><span data-stu-id="0fcef-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="0fcef-108">智慧卡包含與使用者帳戶相關聯的憑證, 而且可以對照儲存在伺服器上的使用者與憑證資訊驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="0fcef-109">您可以將使用者資訊 (使用者名稱和密碼) 與提供的憑證進行比較, 伺服器會驗證認證並驗證使用者。</span><span class="sxs-lookup"><span data-stu-id="0fcef-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="0fcef-110">將商務用 Skype Server 環境設定為支援雙因素驗證時, 請考慮下列主題。</span><span class="sxs-lookup"><span data-stu-id="0fcef-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="0fcef-111">用戶端支援</span><span class="sxs-lookup"><span data-stu-id="0fcef-111">Client Support</span></span>

<span data-ttu-id="0fcef-112">Lync Server 2013 的累計更新: 年 7 2013 月的電腦版用戶端和商務用 Skype 用戶端都是目前支援雙因素驗證的用戶端。</span><span class="sxs-lookup"><span data-stu-id="0fcef-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="0fcef-113">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="0fcef-113">Topology Requirements</span></span>

<span data-ttu-id="0fcef-114">我們強烈建議客戶使用專用的商務用 Skype 伺服器 (含邊緣、控制器和使用者池) 來部署雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="0fcef-115">若要為使用者啟用被動式驗證, 必須針對其他角色和服務停用其他驗證方法, 包括下列各項:</span><span class="sxs-lookup"><span data-stu-id="0fcef-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="0fcef-116">**配置類型**</span><span class="sxs-lookup"><span data-stu-id="0fcef-116">**Configuration Type**</span></span>|<span data-ttu-id="0fcef-117">**服務類型**</span><span class="sxs-lookup"><span data-stu-id="0fcef-117">**Service Type**</span></span>|<span data-ttu-id="0fcef-118">**伺服器角色**</span><span class="sxs-lookup"><span data-stu-id="0fcef-118">**Server Role**</span></span>|<span data-ttu-id="0fcef-119">**要停用的驗證類型**</span><span class="sxs-lookup"><span data-stu-id="0fcef-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0fcef-120">Web 服務</span><span class="sxs-lookup"><span data-stu-id="0fcef-120">Web Service</span></span>  <br/> |<span data-ttu-id="0fcef-121">System.webserver</span><span class="sxs-lookup"><span data-stu-id="0fcef-121">WebServer</span></span>  <br/> |<span data-ttu-id="0fcef-122">董事</span><span class="sxs-lookup"><span data-stu-id="0fcef-122">Director</span></span>  <br/> |<span data-ttu-id="0fcef-123">Kerberos、NTLM 和憑證</span><span class="sxs-lookup"><span data-stu-id="0fcef-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="0fcef-124">Web 服務</span><span class="sxs-lookup"><span data-stu-id="0fcef-124">Web Service</span></span>  <br/> |<span data-ttu-id="0fcef-125">System.webserver</span><span class="sxs-lookup"><span data-stu-id="0fcef-125">WebServer</span></span>  <br/> |<span data-ttu-id="0fcef-126">前端</span><span class="sxs-lookup"><span data-stu-id="0fcef-126">Front End</span></span>  <br/> |<span data-ttu-id="0fcef-127">Kerberos、NTLM 和憑證</span><span class="sxs-lookup"><span data-stu-id="0fcef-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="0fcef-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="0fcef-128">Proxy</span></span>  <br/> |<span data-ttu-id="0fcef-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="0fcef-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="0fcef-130">左邊</span><span class="sxs-lookup"><span data-stu-id="0fcef-130">Edge</span></span>  <br/> |<span data-ttu-id="0fcef-131">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="0fcef-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="0fcef-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="0fcef-132">Proxy</span></span>  <br/> |<span data-ttu-id="0fcef-133">註冊機構</span><span class="sxs-lookup"><span data-stu-id="0fcef-133">Registrar</span></span>  <br/> |<span data-ttu-id="0fcef-134">前端</span><span class="sxs-lookup"><span data-stu-id="0fcef-134">Front End</span></span>  <br/> |<span data-ttu-id="0fcef-135">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="0fcef-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="0fcef-136">除非在服務層級停用這些驗證類型, 否則在您的部署中啟用兩個要素驗證之後, 所有其他版本的用戶端將無法順利登入。</span><span class="sxs-lookup"><span data-stu-id="0fcef-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="0fcef-137">商務用 Skype 服務探索</span><span class="sxs-lookup"><span data-stu-id="0fcef-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="0fcef-138">內部和/或外部用戶端所使用的 DNS 記錄, 用來探索商務用 Skype 服務, 應該設定為解析為無法針對雙因素驗證啟用的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fcef-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="0fcef-139">在這項設定中, 沒有為雙因素驗證啟用的商務用 Skype 池中的使用者, 不需要輸入 PIN 即可進行驗證, 而商務用 Skype Pool 中啟用了雙因素驗證的使用者就會需要輸入其 PIN 才能進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="0fcef-140">Exchange 驗證</span><span class="sxs-lookup"><span data-stu-id="0fcef-140">Exchange Authentication</span></span>

<span data-ttu-id="0fcef-141">已針對 Microsoft Exchange 部署雙因素驗證的客戶, 可能會發現用戶端中的某些功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="0fcef-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="0fcef-142">這是目前的設計, 因為商務用 Skype 用戶端不支援依賴 Exchange 整合之功能的雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="0fcef-143">聯絡</span><span class="sxs-lookup"><span data-stu-id="0fcef-143">Contacts</span></span>

<span data-ttu-id="0fcef-144">已設定為利用整合連絡人存放區功能的商務用 Skype 使用者, 會在使用雙因素驗證登入後, 發現他們的連絡人已不再提供使用。</span><span class="sxs-lookup"><span data-stu-id="0fcef-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="0fcef-145">您應該使用**CsUcsRollback** Cmdlet 來移除整合連絡人存放區中的現有使用者連絡人, 並將其儲存在商務用 Skype 伺服器中, 然後再啟用雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="0fcef-146">技能搜尋</span><span class="sxs-lookup"><span data-stu-id="0fcef-146">Skill Search</span></span>

<span data-ttu-id="0fcef-147">在商務用 Skype 環境中設定技能搜尋功能的客戶, 會發現當商務用 Skype 啟用雙因素驗證時, 這項功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="0fcef-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="0fcef-148">這是因為 Microsoft SharePoint 目前不支援雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="0fcef-149">憑證</span><span class="sxs-lookup"><span data-stu-id="0fcef-149">Credentials</span></span>

<span data-ttu-id="0fcef-150">有幾個有關儲存 Skype for Business 認證的部署考慮, 可能會影響設定為使用雙因素驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="0fcef-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="0fcef-151">刪除儲存的認證</span><span class="sxs-lookup"><span data-stu-id="0fcef-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="0fcef-152">使用者應該使用商務用 Skype 用戶端中的 [**刪除我的登入資訊**] 選項, 然後在嘗試使用雙因素進行第一次登入時, 在商務用%localappdata%\Microsoft\Office\15.0\Skype 中刪除其 SIP 個人資料資料夾authentication.</span><span class="sxs-lookup"><span data-stu-id="0fcef-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="0fcef-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="0fcef-153">DisableNTCredentials</span></span>

<span data-ttu-id="0fcef-154">使用 Kerberos 或 NTLM 驗證方法時, 系統會自動使用使用者的 Windows 認證來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="0fcef-155">在支援 Kerberos 和/或 NTLM 的一般商務用 Skype Server 部署中, 使用者在每次登入時都不應輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="0fcef-156">如果在提示使用者輸入 PIN 前, 系統不小心提示認證, 可能是透過群組原則, 在用戶端電腦上無意間設定**DisableNTCredentials**登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="0fcef-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="0fcef-157">若要防止額外的認證提示, 請在本機工作站上建立下列登錄專案, 或使用 [商務用 Skype] 管理範本, 以使用群組原則將指定之群組的所有使用者套用到其中:</span><span class="sxs-lookup"><span data-stu-id="0fcef-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="0fcef-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="0fcef-158">SavePassword</span></span>

<span data-ttu-id="0fcef-159">當使用者第一次登入商務用 Skype 時, 系統會提示使用者儲存其密碼。</span><span class="sxs-lookup"><span data-stu-id="0fcef-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="0fcef-160">如果選取此選項, 此選項可讓使用者的用戶端憑證儲存在個人憑證存放區, 並將使用者的 Windows 認證儲存在本機電腦的認證管理員中。</span><span class="sxs-lookup"><span data-stu-id="0fcef-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="0fcef-161">當商務用 Skype 設定為支援雙因素驗證時, 必須停用**SavePassword**登錄設定。</span><span class="sxs-lookup"><span data-stu-id="0fcef-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="0fcef-162">若要防止使用者儲存其密碼, 請在本機工作站上變更下列登錄專案, 或使用 [商務用 Skype] 管理範本, 以使用群組原則將指定之群組的所有使用者套用到其中:</span><span class="sxs-lookup"><span data-stu-id="0fcef-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="0fcef-163">AD FS 2.0 權杖重播</span><span class="sxs-lookup"><span data-stu-id="0fcef-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="0fcef-164">AD FS 2.0 提供稱為權杖重播偵測的功能, 可讓您檢測到使用相同權杖的多個權杖要求, 然後再將它丟棄。</span><span class="sxs-lookup"><span data-stu-id="0fcef-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="0fcef-165">啟用此功能時, 權杖重放偵測會在 WS 同盟備用設定檔和 SAML WebSSO 設定檔中保護驗證要求的完整性, 只要確認沒有多次使用相同的權杖。</span><span class="sxs-lookup"><span data-stu-id="0fcef-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="0fcef-166">在安全性非常重要的情況下 (例如使用網亭時), 應啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="0fcef-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="0fcef-167">如需有關權杖重播偵測的詳細資訊, 請參閱[安全規劃和部署 AD FS 2.0 的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。</span><span class="sxs-lookup"><span data-stu-id="0fcef-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="0fcef-168">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="0fcef-168">External User Access</span></span>

<span data-ttu-id="0fcef-169">在這些主題中, 將 ADFS Proxy 或反向 Proxy 設定為支援商務用 Skype 的雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="0fcef-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0fcef-170">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0fcef-170">See also</span></span>

[<span data-ttu-id="0fcef-171">在商務用 Skype Server 中設定雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="0fcef-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
