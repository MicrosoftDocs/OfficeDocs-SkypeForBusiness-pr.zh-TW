---
title: 在商務用 Skype Server 中管理 Web 服務設定
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 摘要：管理商務用 Skype Server 中的 Web 服務設定。
ms.openlocfilehash: 6d79e0567790f10dd86c68f64d7bde54d3540b44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099169"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b16dc-103">在商務用 Skype Server 中管理 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b16dc-104">**摘要：** 在商務用 Skype Server 中管理 Web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="b16dc-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b16dc-105">您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取用來存取商務用 Skype Server 相關的網頁伺服器和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="b16dc-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="b16dc-106">請遵循下列步驟建立新的 Web 服務原則。</span><span class="sxs-lookup"><span data-stu-id="b16dc-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="b16dc-107">若要建立新的 web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="b16dc-108">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b16dc-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b16dc-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b16dc-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b16dc-110">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b16dc-111">在 [ **Web 服務** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="b16dc-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="b16dc-112">若要設定網站的 Web 服務，請按一下 [ **網站** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="b16dc-113">在 [ **選取網站**] 中，按一下要套用 Web 服務原則的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b16dc-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="b16dc-114">若要設定集區的 Web 服務，請按一下 [ **集** 區設定]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="b16dc-115">在 [ **選取服務**] 中，按一下將套用 Web 服務原則的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b16dc-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="b16dc-116">在 **[新的 Web 服務設定**] 的 **整合式 windows 驗證** 中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="b16dc-117">根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="b16dc-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b16dc-118">**啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。</span><span class="sxs-lookup"><span data-stu-id="b16dc-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="b16dc-119">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="b16dc-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="b16dc-120">[**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="b16dc-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="b16dc-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b16dc-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b16dc-122">修改現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="b16dc-123">您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取用來存取商務用 Skype Server 相關的網頁伺服器和 web 服務。</span><span class="sxs-lookup"><span data-stu-id="b16dc-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="b16dc-124">請遵循下列步驟來修改現有的 Web 服務原則。</span><span class="sxs-lookup"><span data-stu-id="b16dc-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b16dc-125">修改現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="b16dc-126">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b16dc-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b16dc-127">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b16dc-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b16dc-128">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b16dc-129">在 [ **Web 服務** ] 頁面上，按一下設定，然後按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b16dc-130">在 [ **編輯 Web 服務] 設定** 的 **整合式 windows 驗證** 中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="b16dc-131">根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="b16dc-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b16dc-132">**啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。</span><span class="sxs-lookup"><span data-stu-id="b16dc-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="b16dc-133">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="b16dc-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="b16dc-134">[**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="b16dc-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="b16dc-135">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b16dc-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="b16dc-136">刪除現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="b16dc-137">請遵循下列步驟刪除 web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="b16dc-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="b16dc-138">若要刪除 web 服務設定設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="b16dc-139">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b16dc-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b16dc-140">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b16dc-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b16dc-141">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="b16dc-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b16dc-142">在 [ **Web 服務** ] 頁面上的搜尋欄位中，輸入您要刪除之原則的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="b16dc-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="b16dc-143">在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="b16dc-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="b16dc-144">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b16dc-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b16dc-145">使用 Windows PowerShell Cmdlet 刪除 Web 服務設定設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b16dc-146">您可以使用 Windows PowerShell 和 **Remove-CsWebServiceConfiguration** Cmdlet 刪除 web 服務設定設定。</span><span class="sxs-lookup"><span data-stu-id="b16dc-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="b16dc-147">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b16dc-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b16dc-148">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="b16dc-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b16dc-149">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="b16dc-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="b16dc-150">刪除特定的 web 服務設定集合集合</span><span class="sxs-lookup"><span data-stu-id="b16dc-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="b16dc-151">下列命令會移除套用至 Redmond 網站的 Web 服務安全性設定：</span><span class="sxs-lookup"><span data-stu-id="b16dc-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b16dc-152">若要刪除所有套用至網站範圍的 web 服務設定設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="b16dc-153">下列命令會移除套用至服務範圍的所有 Web 服務安全性設定：</span><span class="sxs-lookup"><span data-stu-id="b16dc-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="b16dc-154">若要刪除所有允許憑證驗證的 web 服務設定</span><span class="sxs-lookup"><span data-stu-id="b16dc-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="b16dc-155">下列命令會移除所有允許使用憑證驗證的 Web 服務安全性設定：</span><span class="sxs-lookup"><span data-stu-id="b16dc-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="b16dc-156">如需詳細資訊，請參閱 [Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b16dc-156">For details, see [Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
