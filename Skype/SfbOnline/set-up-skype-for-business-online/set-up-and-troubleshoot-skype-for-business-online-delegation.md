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
description: 本文將說明如何設定和疑難排解線上委派商務用 Skype疑難排解。 本文提供設定建議、最佳做法和疑難排解步驟的指引。
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239822"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="9c52a-104">商務用 Skype Online 委派的設定和疑難排解</span><span class="sxs-lookup"><span data-stu-id="9c52a-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="9c52a-105">本文將說明如何設定和疑難排解線上委派商務用 Skype疑難排解。</span><span class="sxs-lookup"><span data-stu-id="9c52a-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="9c52a-106">本文提供設定建議、最佳做法和疑難排解步驟的指引。</span><span class="sxs-lookup"><span data-stu-id="9c52a-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="9c52a-107">指導方針和需求</span><span class="sxs-lookup"><span data-stu-id="9c52a-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="9c52a-108">委派指導方針</span><span class="sxs-lookup"><span data-stu-id="9c52a-108">Guidelines for delegation</span></span>

<span data-ttu-id="9c52a-109">設定及讓委派正確工作取決於您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="9c52a-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="9c52a-110">您必須使用具有最新更新商務用 Skype 2015 完整用戶端，或使用 2016 商務用 Skype完整用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c52a-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="9c52a-111">您必須使用具有最新Outlook的 2013 用戶端，或 Outlook 2016用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c52a-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="9c52a-112">請確定委派器和代理人電腦有一Outlook為主要或預設設定檔的郵件設定檔。</span><span class="sxs-lookup"><span data-stu-id="9c52a-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="9c52a-113">該郵件設定檔應只包含一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="9c52a-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="9c52a-114">商務用 Skype代理人和代理人的代理人應為線上使用者。</span><span class="sxs-lookup"><span data-stu-id="9c52a-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="9c52a-115">此外，Exchange Server帳戶的信箱必須同時為 Online 或兩者都是內部部署。</span><span class="sxs-lookup"><span data-stu-id="9c52a-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="9c52a-116">委派者與代理人都應該使用相同的主要版本Outlook。</span><span class="sxs-lookup"><span data-stu-id="9c52a-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="9c52a-117">**在用戶端策略中，EnableExchangeDelegateSync** 屬性值應該設為 true。</span><span class="sxs-lookup"><span data-stu-id="9c52a-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="9c52a-118">您可以在線上 PowerShell 模組中商務用 Skype **Get-CSClientPolicy** Cmdlet 來驗證此設定。</span><span class="sxs-lookup"><span data-stu-id="9c52a-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="9c52a-119">委派者與代理人必須同時在不同工作站上商務用 Skype Outlook和代理人。</span><span class="sxs-lookup"><span data-stu-id="9c52a-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="9c52a-120">線上委派不支援共用商務用 Skype信箱。</span><span class="sxs-lookup"><span data-stu-id="9c52a-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="9c52a-121">這是因為共用信箱沒有傳送代理存取控制清單 (ACL ) 。</span><span class="sxs-lookup"><span data-stu-id="9c52a-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="9c52a-122">商務用 Skype用戶端版本支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-122">Skype for Business client version support</span></span>

||<span data-ttu-id="9c52a-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="9c52a-123">**Outlook 2013**</span></span>|<span data-ttu-id="9c52a-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="9c52a-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c52a-125">**Lync/商務用 Skype基本用戶端**</span><span class="sxs-lookup"><span data-stu-id="9c52a-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="9c52a-126">不支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-126">Not supported</span></span> |<span data-ttu-id="9c52a-127">不支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-127">Not supported</span></span>
|<span data-ttu-id="9c52a-128">**2015 商務用 Skype月**</span><span class="sxs-lookup"><span data-stu-id="9c52a-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="9c52a-129">支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-129">Supported</span></span>| <span data-ttu-id="9c52a-130">支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-130">Supported</span></span>|
|<span data-ttu-id="9c52a-131">**商務用 Skype 2016**</span><span class="sxs-lookup"><span data-stu-id="9c52a-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="9c52a-132">支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-132">Supported</span></span>| <span data-ttu-id="9c52a-133">支援</span><span class="sxs-lookup"><span data-stu-id="9c52a-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="9c52a-134">授權需求</span><span class="sxs-lookup"><span data-stu-id="9c52a-134">Licensing requirements</span></span>

<span data-ttu-id="9c52a-135">**EnterpriseE3 授權案例**</span><span class="sxs-lookup"><span data-stu-id="9c52a-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="9c52a-136">**許可證**</span><span class="sxs-lookup"><span data-stu-id="9c52a-136">**License**</span></span>|<span data-ttu-id="9c52a-137">**用戶端**</span><span class="sxs-lookup"><span data-stu-id="9c52a-137">**Clients**</span></span>|<span data-ttu-id="9c52a-138">**注釋**</span><span class="sxs-lookup"><span data-stu-id="9c52a-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c52a-139">EnterpriseE3</span><span class="sxs-lookup"><span data-stu-id="9c52a-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="9c52a-140">Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="9c52a-141">商務用 Skype 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="9c52a-142">商務用 Skype基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="9c52a-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="9c52a-143">對於 Mac 用戶端，您可以委派通話，但無法委派會議。</span><span class="sxs-lookup"><span data-stu-id="9c52a-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="9c52a-144">EnterpriseE3 Office 365 電話系統 + Office 365 xCalling 方案</span><span class="sxs-lookup"><span data-stu-id="9c52a-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="9c52a-145">Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="9c52a-146">商務用 Skype 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="9c52a-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="9c52a-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="9c52a-148">商務用 Skype基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="9c52a-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="9c52a-149">對於 Mac 用戶端，您可以委派通話，但無法委派會議。</span><span class="sxs-lookup"><span data-stu-id="9c52a-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="9c52a-150">**EnterpriseE5 授權案例**</span><span class="sxs-lookup"><span data-stu-id="9c52a-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="9c52a-151">**許可證**</span><span class="sxs-lookup"><span data-stu-id="9c52a-151">**License**</span></span>|<span data-ttu-id="9c52a-152">**用戶端**</span><span class="sxs-lookup"><span data-stu-id="9c52a-152">**Clients**</span></span>|<span data-ttu-id="9c52a-153">**注釋**</span><span class="sxs-lookup"><span data-stu-id="9c52a-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c52a-154">EnterpriseE5</span><span class="sxs-lookup"><span data-stu-id="9c52a-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="9c52a-155">Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016。</span><span class="sxs-lookup"><span data-stu-id="9c52a-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="9c52a-156">商務用 Skype 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="9c52a-157">商務用 Skype基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="9c52a-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="9c52a-158">對於 Mac 用戶端，您可以委派通話，但無法委派會議。</span><span class="sxs-lookup"><span data-stu-id="9c52a-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="9c52a-159">EnterpriseE5 加 Office 365通話方案</span><span class="sxs-lookup"><span data-stu-id="9c52a-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="9c52a-160">Mac 版商務用 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="9c52a-161">Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="9c52a-162">商務用 Skype 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c52a-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="9c52a-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="9c52a-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="9c52a-164">商務用 Skype基本用戶端不支援委派。</span><span class="sxs-lookup"><span data-stu-id="9c52a-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="9c52a-165">對於 Mac 用戶端，您可以委派通話，但無法委派會議。</span><span class="sxs-lookup"><span data-stu-id="9c52a-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="9c52a-166">設定及驗證委派</span><span class="sxs-lookup"><span data-stu-id="9c52a-166">Set up and verify delegation</span></span>

<span data-ttu-id="9c52a-167">若要設定線上商務用 Skype，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9c52a-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="9c52a-168">適用于Windows用戶端</span><span class="sxs-lookup"><span data-stu-id="9c52a-168">For Windows clients</span></span>

 <span data-ttu-id="9c52a-169">**呼叫轉轉鍵**</span><span class="sxs-lookup"><span data-stu-id="9c52a-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="9c52a-170">選取 **工具**  >  **選項**  >  **呼叫轉設定。**</span><span class="sxs-lookup"><span data-stu-id="9c52a-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="9c52a-171">選取 **編輯我的代理人成員**。</span><span class="sxs-lookup"><span data-stu-id="9c52a-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="9c52a-172">選取 **新增**，選取要新增的代理人， **然後選取確定**。</span><span class="sxs-lookup"><span data-stu-id="9c52a-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="9c52a-173">**無呼叫轉轉鍵**</span><span class="sxs-lookup"><span data-stu-id="9c52a-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="9c52a-174">在 Outlook中，**選取檔案**  >  **帳戶設定**  >  **委派 Access**  >  **Add**。</span><span class="sxs-lookup"><span data-stu-id="9c52a-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="9c52a-175">找出並新增要成為代理人之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c52a-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="9c52a-176">選取的 **日曆** 功能表，然後選取編輯器 (**可讀取、建立及修改) 。**</span><span class="sxs-lookup"><span data-stu-id="9c52a-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="9c52a-177">Mac 用戶端 - Lync</span><span class="sxs-lookup"><span data-stu-id="9c52a-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="9c52a-178">**呼叫轉轉鍵**</span><span class="sxs-lookup"><span data-stu-id="9c52a-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="9c52a-179">如果用戶端沒有具有編輯我的代理人成員連結的呼叫轉轉定位點，且委派程式位於 Mac 電腦上，則委派者必須登錄 Windows 型電腦，才能設定委派。</span><span class="sxs-lookup"><span data-stu-id="9c52a-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="9c52a-180">這是因為 Mac 用戶端無法建立 MAPI 連接，而這是從 商務用 Skype 建立Outlook。</span><span class="sxs-lookup"><span data-stu-id="9c52a-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="9c52a-181">驗證成功</span><span class="sxs-lookup"><span data-stu-id="9c52a-181">Verify success</span></span>

<span data-ttu-id="9c52a-182">如果設定成功，代理人應該會看到您已新增為 < 名稱>郵件的代理人，以及已建立 "我 **管理** 通話的人 **"** 群組。</span><span class="sxs-lookup"><span data-stu-id="9c52a-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="9c52a-183">委派程式應該會看到已建立 **代理人** 群組。</span><span class="sxs-lookup"><span data-stu-id="9c52a-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c52a-184">委派許可權通常會在設定程式 30 分鐘內顯示。</span><span class="sxs-lookup"><span data-stu-id="9c52a-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="9c52a-185">不過，此程式最多可能需要 24 小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="9c52a-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="9c52a-186">疑難排解</span><span class="sxs-lookup"><span data-stu-id="9c52a-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="9c52a-187">常見問題</span><span class="sxs-lookup"><span data-stu-id="9c52a-187">Common issues</span></span>

- > <span data-ttu-id="9c52a-188">**問題 1** 委派程式從用戶端移除代理人之後，代理人專案會繼續出現在我管理通話Outlook群組中。</span><span class="sxs-lookup"><span data-stu-id="9c52a-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="9c52a-189">**解析度 1** 在 商務用 Skype用戶端上，以滑鼠右鍵按一下 [代理人群組中的代理人，然後選取 **[從群組移除**> 。</span><span class="sxs-lookup"><span data-stu-id="9c52a-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="9c52a-190">**問題 2** 透過用戶端授予代理人存取權Outlook，代理人不會顯示確認訊息或我 **管理** 通話的人群組。</span><span class="sxs-lookup"><span data-stu-id="9c52a-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="9c52a-191">**解析度 2** 從用戶端移除Outlook，等待約 15 分鐘進行複製，然後再次新增代理人。</span><span class="sxs-lookup"><span data-stu-id="9c52a-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="9c52a-192">其他常見問題</span><span class="sxs-lookup"><span data-stu-id="9c52a-192">Other common issues</span></span>

- <span data-ttu-id="9c52a-193">如果超過 25 個委派者與 25 個代理人的臨界值，則委派無法工作。</span><span class="sxs-lookup"><span data-stu-id="9c52a-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="9c52a-194">不支援 商務用 Skype基本用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c52a-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9c52a-195">如果您安裝基本商務用 Skype，它會移除並中斷委派。</span><span class="sxs-lookup"><span data-stu-id="9c52a-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="9c52a-196">如果 **MAPI 狀態** 值無法 **確定，** 請確認 SIP 和 **SMTP** 值相符。 </span><span class="sxs-lookup"><span data-stu-id="9c52a-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9c52a-197">當您第一次啟動 MAPI 狀態後，可能需要數分鐘的時間，才能顯示為確定商務用 Skype Outlook。</span><span class="sxs-lookup"><span data-stu-id="9c52a-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="9c52a-198">不支援為安全性群組建立安全性群組並新增委派許可權。</span><span class="sxs-lookup"><span data-stu-id="9c52a-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="9c52a-199">MAPI 無法使用。</span><span class="sxs-lookup"><span data-stu-id="9c52a-199">MAPI is unavailable.</span></span> <span data-ttu-id="9c52a-200">請參閱[2016 用戶端商務用 Skype MAPI 無法使用」錯誤](https://support.microsoft.com/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="9c52a-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="9c52a-201">無法Exchange Online用戶端來商務用 Skype信箱。</span><span class="sxs-lookup"><span data-stu-id="9c52a-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="9c52a-202">如果發生這種情況，請執行 Outlook[連接測試](https://testconnectivity.microsoft.com/)，以確保通過。</span><span class="sxs-lookup"><span data-stu-id="9c52a-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9c52a-203">相關主題</span><span class="sxs-lookup"><span data-stu-id="9c52a-203">Related topics</span></span>
[<span data-ttu-id="9c52a-204">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="9c52a-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9c52a-205">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="9c52a-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
