---
title: 管理商務用 Skype Server 中的註冊器設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要：管理商務用 Skype Server 的註冊機設定設定。
ms.openlocfilehash: a1cd1048ea37a249126ec892560312a482459d44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119572"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1b30d-103">管理商務用 Skype Server 中的註冊器設定設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1b30d-104">**摘要：** 管理商務用 Skype Server 的註冊機設定設定。</span><span class="sxs-lookup"><span data-stu-id="1b30d-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="1b30d-105">您可以使用註冊機構來設定 proxy 伺服器驗證方法。</span><span class="sxs-lookup"><span data-stu-id="1b30d-105">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="1b30d-106">您指定的驗證通訊協定會決定集區中的伺服器在用戶端上面臨的挑戰類型。</span><span class="sxs-lookup"><span data-stu-id="1b30d-106">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="1b30d-107">可用的通訊協定包括：</span><span class="sxs-lookup"><span data-stu-id="1b30d-107">The available protocols are:</span></span>
  
- <span data-ttu-id="1b30d-108">**Kerberos** 這是可供用戶端使用的最強式密碼型驗證配置，但通常只適用于企業用戶端，因為它需要用戶端連線至金鑰發佈中心 (Kerberos 網域控制站) 。</span><span class="sxs-lookup"><span data-stu-id="1b30d-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="1b30d-109">此設定適用于伺服器只驗證企業用戶端的情況。</span><span class="sxs-lookup"><span data-stu-id="1b30d-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="1b30d-110">**NTLM** 這是以密碼為基礎的驗證，可供在密碼上使用挑戰回應雜湊配置的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="1b30d-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="1b30d-111">這是唯一可供用戶端使用的驗證表單，但不連接到金鑰發佈中心 (Kerberos 網域控制站) （例如遠端使用者）。</span><span class="sxs-lookup"><span data-stu-id="1b30d-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="1b30d-112">如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。</span><span class="sxs-lookup"><span data-stu-id="1b30d-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="1b30d-113">**憑證驗證** 當伺服器需要從 Lync Phone Edition 用戶端、公共區域電話、商務用 Skype 和 Lync Windows Store 應用程式取得憑證時，這是一種新的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="1b30d-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="1b30d-114">在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼 (PIN) 來成功驗證之後，商務用 Skype 伺服器便會將 SIP URI 布建到電話，並布建商務用 Skype Server 簽署憑證，或是識別 Joe (Ex： SN=joe@contoso.com ) 至電話的使用者憑證。</span><span class="sxs-lookup"><span data-stu-id="1b30d-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="1b30d-115">此憑證用來驗證註冊機構和 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="1b30d-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1b30d-116">當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="1b30d-116">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="1b30d-117">Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。</span><span class="sxs-lookup"><span data-stu-id="1b30d-117">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="1b30d-118">如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="1b30d-118">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="1b30d-119">如果企業使用者也會驗證服務器，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="1b30d-119">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="1b30d-120">如果您要使用 Lync Windows Store 應用程式用戶端，則必須啟用憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="1b30d-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="1b30d-121">若要建立新的註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="1b30d-122">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1b30d-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="1b30d-123">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1b30d-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="1b30d-124">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="1b30d-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="1b30d-125">在 [**註冊機**] 頁面上，按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="1b30d-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="1b30d-126">在 [ **選取服務**] 中，按一下要套用註冊器的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b30d-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="1b30d-127">在 [ **新註冊機] 設定** 中，根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="1b30d-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="1b30d-128">**啟用 kerberos 驗證** 讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。</span><span class="sxs-lookup"><span data-stu-id="1b30d-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="1b30d-129">**啟用 ntlm 驗證** 讓集區中的伺服器使用 NTLM 時面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="1b30d-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="1b30d-130">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="1b30d-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="1b30d-131">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="1b30d-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="1b30d-132">修改現有的註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="1b30d-133">您可以使用註冊機構來設定 proxy 伺服器驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="1b30d-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1b30d-134">當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="1b30d-134">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="1b30d-135">Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。</span><span class="sxs-lookup"><span data-stu-id="1b30d-135">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="1b30d-136">如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="1b30d-136">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="1b30d-137">如果企業使用者也會驗證服務器，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="1b30d-137">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="1b30d-138">請遵循下列步驟來修改現有的註冊機。</span><span class="sxs-lookup"><span data-stu-id="1b30d-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="1b30d-139">若要修改現有的註冊器配置設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="1b30d-140">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1b30d-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="1b30d-141">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1b30d-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="1b30d-142">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="1b30d-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="1b30d-143">在 [ **註冊機構** ] 頁面上，按一下服務，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1b30d-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1b30d-144">在 [ **編輯註冊機設定**] 中，依據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="1b30d-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="1b30d-145">**啟用 kerberos 驗證** 讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。</span><span class="sxs-lookup"><span data-stu-id="1b30d-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="1b30d-146">**啟用 ntlm 驗證** 讓集區中的伺服器使用 NTLM 時面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="1b30d-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="1b30d-147">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="1b30d-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="1b30d-148">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="1b30d-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="1b30d-149">若要刪除註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="1b30d-150">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1b30d-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="1b30d-151">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1b30d-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1b30d-152">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="1b30d-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="1b30d-153">在 [ **註冊機** ] 頁面上的搜尋欄位中，輸入您要刪除之註冊機構的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="1b30d-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="1b30d-154">在清單中，按一下您想要的註冊機構，按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="1b30d-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="1b30d-155">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b30d-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1b30d-156">使用 Windows PowerShell Cmdlet 移除註冊機設定設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1b30d-157">您可以使用 Windows PowerShell 和 **set-csproxyconfiguration** Cmdlet 來刪除註冊機設定設定。</span><span class="sxs-lookup"><span data-stu-id="1b30d-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="1b30d-158">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b30d-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1b30d-159">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="1b30d-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1b30d-160">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="1b30d-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="1b30d-161">移除一組特定的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="1b30d-162">下列命令會移除已套用至 edge Server atl-edge-011.litwareinc.com 的註冊機安全性設定：</span><span class="sxs-lookup"><span data-stu-id="1b30d-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="1b30d-163">若要移除所有套用至網站範圍的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="1b30d-164">下列命令會移除所有已套用至註冊機構服務的註冊機安全性設定：</span><span class="sxs-lookup"><span data-stu-id="1b30d-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="1b30d-165">移除所有允許 NTLM 驗證的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="1b30d-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="1b30d-166">下列命令會刪除所有的註冊器安全性設定，這些設定允許使用 NTLM 進行用戶端驗證：</span><span class="sxs-lookup"><span data-stu-id="1b30d-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="1b30d-167">如需詳細資訊，請參閱 [Remove-set-csproxyconfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1b30d-167">For details, see [Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
