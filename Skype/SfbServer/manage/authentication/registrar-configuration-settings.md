---
title: 在商務用 Skype Server 中管理註冊機構配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要：管理商務用 Skype Server 的註冊機構配置設定。
ms.openlocfilehash: 0c4529fb7343cf3db1e516858987a3ba60435513
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818755"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c1cf4-103">在商務用 Skype Server 中管理註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c1cf4-104">**摘要：** 管理商務用 Skype Server 的註冊機構配置設定。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="c1cf4-105">您可以使用註冊機構來設定 proxy 伺服器驗證方法。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-105">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="c1cf4-106">您指定的驗證通訊協定決定了將池中的伺服器問題到用戶端所面臨的挑戰類型。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-106">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="c1cf4-107">可用的通訊協定包括：</span><span class="sxs-lookup"><span data-stu-id="c1cf4-107">The available protocols are:</span></span>
  
- <span data-ttu-id="c1cf4-108">**Kerberos**這是用戶端可用的最強式密碼驗證配置，但通常只有企業用戶端才能使用，因為它需要用戶端連線到金鑰發佈中心（Kerberos 網網域控制站）。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="c1cf4-109">此設定適用于伺服器只驗證企業用戶端的情況。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="c1cf4-110">**NTLM**這是在密碼上使用質詢回應雜湊配置的用戶端所能使用的密碼驗證。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="c1cf4-111">這是不需連線到金鑰發佈中心（Kerberos 網網域控制站）（例如遠端使用者）的用戶端可使用的唯一驗證形式。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="c1cf4-112">如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="c1cf4-113">**憑證驗證**當伺服器需要從 Lync Phone Edition 用戶端、常用的區域電話、商務用 Skype 和 Lync Windows Store 應用程式取得憑證時，這是新的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="c1cf4-114">在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼（PIN），然後將 SIP URI 提供給手機，並將身分識別 Joe （Ex： SN=joe@contoso.com）的使用者憑證提供給手機，即可透過該使用者登入並驗證。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="c1cf4-115">這個憑證是用來向註冊機構和 Web 服務進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c1cf4-116">我們建議您在伺服器同時支援遠端與企業用戶端的驗證時，同時啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-116">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="c1cf4-117">邊緣伺服器與內部伺服器通訊，以確保只提供 NTLM 驗證給遠端用戶端。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-117">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="c1cf4-118">如果在這些伺服器上只啟用 Kerberos，就無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-118">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="c1cf4-119">如果企業使用者也要針對伺服器進行驗證，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-119">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="c1cf4-120">如果您要使用 Lync Windows Store app 用戶端，您必須啟用憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="c1cf4-121">建立新的註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="c1cf4-122">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="c1cf4-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c1cf4-123">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c1cf4-124">在左側導覽列中，按一下 [**安全性**]，然後按一下 [**註冊機**]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="c1cf4-125">在 [**註冊機**] 頁面上，按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="c1cf4-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="c1cf4-126">在 [**選取服務**] 中，按一下要套用註冊機構的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="c1cf4-127">在 [**新的註冊機構設定**] 中，根據您的環境中用戶端和支援的功能，選取下列一或多個專案：</span><span class="sxs-lookup"><span data-stu-id="c1cf4-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="c1cf4-128">使用 Kerberos 驗證來**啟用 kerberos 驗證**，讓伺服器在池中有問題的挑戰。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="c1cf4-129">**啟用 ntlm 驗證**，以讓池中的伺服器面臨使用 NTLM 的問題。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="c1cf4-130">**啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="c1cf4-131">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="c1cf4-132">修改現有的註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="c1cf4-133">您可以使用註冊機構來設定 proxy 伺服器驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c1cf4-134">我們建議您在伺服器同時支援遠端與企業用戶端的驗證時，同時啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-134">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="c1cf4-135">邊緣伺服器與內部伺服器通訊，以確保只提供 NTLM 驗證給遠端用戶端。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-135">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="c1cf4-136">如果在這些伺服器上只啟用 Kerberos，就無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-136">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="c1cf4-137">如果企業使用者也要針對伺服器進行驗證，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-137">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="c1cf4-138">請依照這些步驟來修改現有的註冊機構。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="c1cf4-139">修改現有的註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="c1cf4-140">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="c1cf4-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c1cf4-141">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c1cf4-142">在左側導覽列中，按一下 [**安全性**]，然後按一下 [**註冊機**]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="c1cf4-143">在 [**註冊機構**] 頁面上，按一下服務，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c1cf4-144">在 [**編輯註冊機構設定**] 中，根據您的環境中用戶端和支援的功能，選取下列一或多項：</span><span class="sxs-lookup"><span data-stu-id="c1cf4-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="c1cf4-145">使用 Kerberos 驗證來**啟用 kerberos 驗證**，讓伺服器在池中有問題的挑戰。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="c1cf4-146">**啟用 ntlm 驗證**，以讓池中的伺服器面臨使用 NTLM 的問題。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="c1cf4-147">**啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="c1cf4-148">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="c1cf4-149">刪除註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="c1cf4-150">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="c1cf4-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c1cf4-151">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c1cf4-152">在左側導覽列中，按一下 [**安全性**]，然後按一下 [**註冊機**]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="c1cf4-153">在 [**註冊機**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除之註冊機構的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="c1cf4-154">在清單中，按一下您想要的註冊機構，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="c1cf4-155">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c1cf4-156">使用 Windows PowerShell Cmdlet 移除註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c1cf4-157">您可以使用 Windows PowerShell 和**CsProxyConfiguration** Cmdlet 來刪除註冊機構設定設定。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="c1cf4-158">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c1cf4-159">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c1cf4-160">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="c1cf4-161">移除一組特定的註冊機構安全設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="c1cf4-162">下列命令會移除已套用至 edge Server atl-edge-011.litwareinc.com 的註冊機構安全性設定：</span><span class="sxs-lookup"><span data-stu-id="c1cf4-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="c1cf4-163">若要移除所有套用至網站範圍的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="c1cf4-164">下列命令會移除所有已套用至註冊機構服務的註冊機構安全性設定：</span><span class="sxs-lookup"><span data-stu-id="c1cf4-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="c1cf4-165">若要移除所有允許 NTLM 驗證的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="c1cf4-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="c1cf4-166">下列命令會刪除所有註冊機構安全性設定，以允許使用 NTLM 進行用戶端驗證：</span><span class="sxs-lookup"><span data-stu-id="c1cf4-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="c1cf4-167">如需詳細資訊，請參閱[移除-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c1cf4-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

