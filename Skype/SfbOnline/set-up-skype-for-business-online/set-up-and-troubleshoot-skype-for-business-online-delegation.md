---
title: 商務用 Skype Online 委派的設定和疑難排解
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 本文說明如何設定和疑難排解商務用 Skype Online 委派。 本文提供設定建議、最佳做法及疑難排解步驟的指導方針。
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706478"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="bf848-104">商務用 Skype Online 委派的設定和疑難排解</span><span class="sxs-lookup"><span data-stu-id="bf848-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="bf848-105">本文說明如何設定和疑難排解商務用 Skype Online 委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="bf848-106">本文提供設定建議、最佳做法及疑難排解步驟的指導方針。</span><span class="sxs-lookup"><span data-stu-id="bf848-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="bf848-107">原則與需求</span><span class="sxs-lookup"><span data-stu-id="bf848-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="bf848-108">委派指導方針</span><span class="sxs-lookup"><span data-stu-id="bf848-108">Guidelines for delegation</span></span>

<span data-ttu-id="bf848-109">設定和取得委派正常運作的方式，取決於您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="bf848-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="bf848-110">您必須使用商務用 Skype 2015 完整版用戶端（含最新的更新或商務用 Skype 2016 完整用戶端）。</span><span class="sxs-lookup"><span data-stu-id="bf848-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="bf848-111">您必須使用 Outlook 2013 用戶端，並安裝最新的更新或 Outlook 2016 用戶端。</span><span class="sxs-lookup"><span data-stu-id="bf848-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="bf848-112">確定 delegator 和委派電腦有一個作為主要或預設設定檔的 Outlook 郵件設定檔。</span><span class="sxs-lookup"><span data-stu-id="bf848-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="bf848-113">該郵件設定檔應該只包含一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="bf848-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="bf848-114">Delegator 和代理人的商務用 Skype 應該是線上使用者。</span><span class="sxs-lookup"><span data-stu-id="bf848-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="bf848-115">此外，每個帳戶的 Exchange 伺服器信箱都必須是線上或都在內部部署。</span><span class="sxs-lookup"><span data-stu-id="bf848-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="bf848-116">Delegator 和代理人都應該使用相同的主要版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bf848-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="bf848-117">在用戶端原則中， **EnableExchangeDelegateSync**屬性值應該設定為**true** 。</span><span class="sxs-lookup"><span data-stu-id="bf848-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="bf848-118">您可以在商務用 Skype Online PowerShell 模組中執行**CSClientPolicy** Cmdlet，以驗證此設定。</span><span class="sxs-lookup"><span data-stu-id="bf848-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="bf848-119">在不同的工作站上，delegator 和代理人都必須登入商務用 Skype 和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bf848-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="bf848-120">商務用 Skype Online 委派不支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="bf848-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="bf848-121">這是因為共用信箱沒有**sendonbehalf**存取控制清單（ACL）。</span><span class="sxs-lookup"><span data-stu-id="bf848-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="bf848-122">商務用 Skype 用戶端版本支援</span><span class="sxs-lookup"><span data-stu-id="bf848-122">Skype for Business client version support</span></span>

||<span data-ttu-id="bf848-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="bf848-123">**Outlook 2013**</span></span>|<span data-ttu-id="bf848-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="bf848-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf848-125">**Lync/商務用 Skype 基本用戶端**</span><span class="sxs-lookup"><span data-stu-id="bf848-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="bf848-126">不支援</span><span class="sxs-lookup"><span data-stu-id="bf848-126">Not supported</span></span> |<span data-ttu-id="bf848-127">不支援</span><span class="sxs-lookup"><span data-stu-id="bf848-127">Not supported</span></span>
|<span data-ttu-id="bf848-128">**商務用 Skype 2015**</span><span class="sxs-lookup"><span data-stu-id="bf848-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="bf848-129">受</span><span class="sxs-lookup"><span data-stu-id="bf848-129">Supported</span></span>| <span data-ttu-id="bf848-130">受</span><span class="sxs-lookup"><span data-stu-id="bf848-130">Supported</span></span>|
|<span data-ttu-id="bf848-131">**商務用 Skype 2016**</span><span class="sxs-lookup"><span data-stu-id="bf848-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="bf848-132">受</span><span class="sxs-lookup"><span data-stu-id="bf848-132">Supported</span></span>| <span data-ttu-id="bf848-133">受</span><span class="sxs-lookup"><span data-stu-id="bf848-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="bf848-134">授權需求</span><span class="sxs-lookup"><span data-stu-id="bf848-134">Licensing requirements</span></span>

<span data-ttu-id="bf848-135">**企業版 E3 授權案例**</span><span class="sxs-lookup"><span data-stu-id="bf848-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="bf848-136">**授權**</span><span class="sxs-lookup"><span data-stu-id="bf848-136">**License**</span></span>|<span data-ttu-id="bf848-137">**台**</span><span class="sxs-lookup"><span data-stu-id="bf848-137">**Clients**</span></span>|<span data-ttu-id="bf848-138">**筆記**</span><span class="sxs-lookup"><span data-stu-id="bf848-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf848-139">企業版 E3</span><span class="sxs-lookup"><span data-stu-id="bf848-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="bf848-140">Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用</span><span class="sxs-lookup"><span data-stu-id="bf848-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bf848-141">與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="bf848-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="bf848-142">商務用 Skype 基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bf848-143">對於 Mac 用戶端，您可以委派通話，但不能委派會議。</span><span class="sxs-lookup"><span data-stu-id="bf848-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="bf848-144">企業版 E3 （含 Office 365 電話系統 + Office 365 xCalling 方案）</span><span class="sxs-lookup"><span data-stu-id="bf848-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="bf848-145">Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用</span><span class="sxs-lookup"><span data-stu-id="bf848-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bf848-146">與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="bf848-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bf848-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bf848-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="bf848-148">商務用 Skype 基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bf848-149">對於 Mac 用戶端，您可以委派通話，但不能委派會議。</span><span class="sxs-lookup"><span data-stu-id="bf848-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="bf848-150">**企業版 E5 授權案例**</span><span class="sxs-lookup"><span data-stu-id="bf848-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="bf848-151">**授權**</span><span class="sxs-lookup"><span data-stu-id="bf848-151">**License**</span></span>|<span data-ttu-id="bf848-152">**台**</span><span class="sxs-lookup"><span data-stu-id="bf848-152">**Clients**</span></span>|<span data-ttu-id="bf848-153">**筆記**</span><span class="sxs-lookup"><span data-stu-id="bf848-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf848-154">企業版 E5</span><span class="sxs-lookup"><span data-stu-id="bf848-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="bf848-155">Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="bf848-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="bf848-156">與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="bf848-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="bf848-157">商務用 Skype 基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bf848-158">對於 Mac 用戶端，您可以委派通話，但不能委派會議。</span><span class="sxs-lookup"><span data-stu-id="bf848-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="bf848-159">企業版 E5 加上 Office 365 通話方案</span><span class="sxs-lookup"><span data-stu-id="bf848-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="bf848-160">Mac 版商務用 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="bf848-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="bf848-161">Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用</span><span class="sxs-lookup"><span data-stu-id="bf848-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bf848-162">與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="bf848-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bf848-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bf848-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="bf848-164">商務用 Skype 基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bf848-165">對於 Mac 用戶端，您可以委派通話，但不能委派會議。</span><span class="sxs-lookup"><span data-stu-id="bf848-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="bf848-166">設定並驗證委派</span><span class="sxs-lookup"><span data-stu-id="bf848-166">Set up and verify delegation</span></span>

<span data-ttu-id="bf848-167">若要設定商務用 Skype Online 委派，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bf848-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="bf848-168">針對 Windows 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf848-168">For Windows clients</span></span>

 <span data-ttu-id="bf848-169">**[來電轉接] 索引標籤**</span><span class="sxs-lookup"><span data-stu-id="bf848-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="bf848-170">選取 [**來電轉接設定**] 的 [**工具** > **選項** > ]。</span><span class="sxs-lookup"><span data-stu-id="bf848-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="bf848-171">選取 [**編輯我的代理人成員**]。</span><span class="sxs-lookup"><span data-stu-id="bf848-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="bf848-172">選取 [**新增**]，選取您要新增的代理人，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bf848-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="bf848-173">**[無來電轉接] 索引標籤**</span><span class="sxs-lookup"><span data-stu-id="bf848-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="bf848-174">在 Outlook 中，**選取** > [檔案**帳戶設定** > **] 委派 Access** > [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bf848-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="bf848-175">找出並新增要成為代理人的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="bf848-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="bf848-176">選取 [行事**曆**] 功能表，然後選取 **[編輯者（可讀取、建立及修改專案）**]。</span><span class="sxs-lookup"><span data-stu-id="bf848-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="bf848-177">針對 Mac 用戶端-Lync</span><span class="sxs-lookup"><span data-stu-id="bf848-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="bf848-178">**[來電轉接] 索引標籤**</span><span class="sxs-lookup"><span data-stu-id="bf848-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="bf848-179">如果用戶端沒有 [**編輯我的代理人成員**] 連結的 [**來電轉接**] 索引標籤，且 delegator 位於 Mac 電腦上，Delegator 必須登入 Windows 電腦，才能設定委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="bf848-180">這是因為 Mac 用戶端無法進行 MAPI 連線，而這是從 Outlook 建立商務用 Skype 委派所需要的。</span><span class="sxs-lookup"><span data-stu-id="bf848-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="bf848-181">驗證成功</span><span class="sxs-lookup"><span data-stu-id="bf848-181">Verify success</span></span>

<span data-ttu-id="bf848-182">如果設定成功，代理人會看到**您已新增為 < 名稱>** 訊息的代理人，也會建立 [**我管理的人員**] 群組通話。</span><span class="sxs-lookup"><span data-stu-id="bf848-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="bf848-183">Delegator 應該會看到 [**代理人**] 群組已建立。</span><span class="sxs-lookup"><span data-stu-id="bf848-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf848-184">委派許可權通常會出現在安裝程式的30分鐘內。</span><span class="sxs-lookup"><span data-stu-id="bf848-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="bf848-185">不過，這個處理常式可能需要長達24小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="bf848-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="bf848-186">疑難排解</span><span class="sxs-lookup"><span data-stu-id="bf848-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="bf848-187">常見問題</span><span class="sxs-lookup"><span data-stu-id="bf848-187">Common issues</span></span>

- > <span data-ttu-id="bf848-188">**問題 1**在 delegator 已移除 Outlook 用戶端的代理人之後，該代理人專案會繼續出現在 [**我管理呼叫**] 群組的 [人員]。</span><span class="sxs-lookup"><span data-stu-id="bf848-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="bf848-189">**解析度 1**在商務用 Skype 用戶端上，以滑鼠右鍵按一下 [**代理人**] 群組中的代理人，然後選取 [**從群組移除**]。</span><span class="sxs-lookup"><span data-stu-id="bf848-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="bf848-190">**問題 2**透過 Outlook 用戶端授與委派存取權之後，就不會再顯示確認訊息，也不會顯示 [**我管理的使用者**] 群組通話的人員。</span><span class="sxs-lookup"><span data-stu-id="bf848-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="bf848-191">**解析度 2**移除 Outlook 用戶端的委派，等待大約15分鐘進行複製，然後再新增該代理程式。</span><span class="sxs-lookup"><span data-stu-id="bf848-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="bf848-192">其他常見問題</span><span class="sxs-lookup"><span data-stu-id="bf848-192">Other common issues</span></span>

- <span data-ttu-id="bf848-193">如果超過25個 delegators 及25個代理人的閾值，委派就無法運作。</span><span class="sxs-lookup"><span data-stu-id="bf848-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="bf848-194">商務用 Skype 基本用戶端不受支援。</span><span class="sxs-lookup"><span data-stu-id="bf848-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bf848-195">如果您安裝商務用 Skype 基本用戶端，則會移除並中斷委派。</span><span class="sxs-lookup"><span data-stu-id="bf848-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="bf848-196">如果**MAPI 狀態值**不是 **[確定]**，請確定**SIP**與**SMTP**值相符。</span><span class="sxs-lookup"><span data-stu-id="bf848-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bf848-197">在您第一次啟動商務用 Skype 和 Outlook 之後，可能需要幾分鐘的時間，才能讓 MAPI 狀態顯示為 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="bf848-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="bf848-198">不支援建立安全性群組及新增該安全性群組的委派許可權。</span><span class="sxs-lookup"><span data-stu-id="bf848-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="bf848-199">MAPI 無法使用。</span><span class="sxs-lookup"><span data-stu-id="bf848-199">MAPI is unavailable.</span></span> <span data-ttu-id="bf848-200">請參閱[商務用 Skype 2016 用戶端的「MAPI 無法使用」錯誤](https://support.microsoft.com/en-us/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="bf848-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="bf848-201">無法透過商務用 Skype 用戶端存取 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="bf848-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="bf848-202">如果發生這種情況，請執行[Outlook 連線測試](https://testconnectivity.microsoft.com/)，以確定它已通過。</span><span class="sxs-lookup"><span data-stu-id="bf848-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bf848-203">相關主題</span><span class="sxs-lookup"><span data-stu-id="bf848-203">Related topics</span></span>
[<span data-ttu-id="bf848-204">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="bf848-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="bf848-205">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="bf848-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
