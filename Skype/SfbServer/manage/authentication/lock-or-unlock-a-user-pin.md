---
title: 鎖定或解除鎖定使用者 PIN 碼中的商務用 Skype Server
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要：鎖定或解除鎖定使用者的電話撥入式會議 PIN 碼以供商務用 Skype Server 使用。
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828363"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="b084c-103">鎖定或解除鎖定使用者 PIN 碼中的商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b084c-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="b084c-104">**摘要：** 鎖定或解除鎖定使用者的電話撥入式會議 PIN，以供商務用 Skype Server 使用。</span><span class="sxs-lookup"><span data-stu-id="b084c-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="b084c-105">您可以從商務用 Skype Server 控制台的 [ **使用者** ] 區段鎖定或解除鎖定使用者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="b084c-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b084c-106">在商務用 Skype Server 控制台中鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="b084c-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b084c-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b084c-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b084c-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b084c-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b084c-109">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b084c-110">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="b084c-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="b084c-111">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="b084c-112">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="b084c-113">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="b084c-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="b084c-114">a.</span><span class="sxs-lookup"><span data-stu-id="b084c-114">a.</span></span> <span data-ttu-id="b084c-115">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="b084c-116">b.</span><span class="sxs-lookup"><span data-stu-id="b084c-116">b.</span></span> <span data-ttu-id="b084c-117">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="b084c-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="b084c-118">c.</span><span class="sxs-lookup"><span data-stu-id="b084c-118">c.</span></span> <span data-ttu-id="b084c-119">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **等於** 或 **不等於**)。</span><span class="sxs-lookup"><span data-stu-id="b084c-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="b084c-120">d.</span><span class="sxs-lookup"><span data-stu-id="b084c-120">d.</span></span> <span data-ttu-id="b084c-121">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="b084c-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b084c-122">若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="b084c-123">e.</span><span class="sxs-lookup"><span data-stu-id="b084c-123">e.</span></span> <span data-ttu-id="b084c-124">按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="b084c-124">Click **Find**.</span></span>
    
   <span data-ttu-id="b084c-125">f.</span><span class="sxs-lookup"><span data-stu-id="b084c-125">f.</span></span> <span data-ttu-id="b084c-126">按一下使用者、**[動作]**，然後按一下 **[鎖定 PIN]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b084c-127">在商務用 Skype Server 控制台中解除鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="b084c-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b084c-128">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b084c-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b084c-129">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b084c-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b084c-130">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b084c-131">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="b084c-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="b084c-132">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="b084c-133">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="b084c-134">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="b084c-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="b084c-135">a.</span><span class="sxs-lookup"><span data-stu-id="b084c-135">a.</span></span> <span data-ttu-id="b084c-136">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="b084c-137">b.</span><span class="sxs-lookup"><span data-stu-id="b084c-137">b.</span></span> <span data-ttu-id="b084c-138">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="b084c-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="b084c-139">c.</span><span class="sxs-lookup"><span data-stu-id="b084c-139">c.</span></span> <span data-ttu-id="b084c-140">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **等於** 或 **不等於**)。</span><span class="sxs-lookup"><span data-stu-id="b084c-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="b084c-141">d.</span><span class="sxs-lookup"><span data-stu-id="b084c-141">d.</span></span> <span data-ttu-id="b084c-142">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="b084c-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b084c-143">若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="b084c-144">e.</span><span class="sxs-lookup"><span data-stu-id="b084c-144">e.</span></span> <span data-ttu-id="b084c-145">按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="b084c-145">Click **Find**.</span></span>
    
   <span data-ttu-id="b084c-146">f.</span><span class="sxs-lookup"><span data-stu-id="b084c-146">f.</span></span> <span data-ttu-id="b084c-147">按一下使用者、**[動作]**，然後按一下 **[解除鎖定 PIN]**。</span><span class="sxs-lookup"><span data-stu-id="b084c-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b084c-148">使用 Windows PowerShell Cmdlet 鎖定和解除鎖定使用者 Pin</span><span class="sxs-lookup"><span data-stu-id="b084c-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b084c-149">您可以使用 Windows PowerShell 和 Lock-CsClientPin 及 Unlock-CsClientPin Cmdlet 來鎖定和解除鎖定使用者 Pin。</span><span class="sxs-lookup"><span data-stu-id="b084c-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="b084c-150">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b084c-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b084c-151">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="b084c-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b084c-152">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="b084c-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="b084c-153">鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="b084c-153">To lock a user PIN</span></span>

- <span data-ttu-id="b084c-154">若要鎖定使用者的 PIN 碼，請使用 Lock-CsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b084c-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="b084c-155">例如：</span><span class="sxs-lookup"><span data-stu-id="b084c-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="b084c-156">解除鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="b084c-156">To unlock a user PIN</span></span>

- <span data-ttu-id="b084c-157">若要解除鎖定使用者的 PIN 碼，請使用 Unlock-CsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b084c-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="b084c-158">例如：</span><span class="sxs-lookup"><span data-stu-id="b084c-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="b084c-159">如需詳細資訊，請參閱 [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) 和 [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="b084c-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
