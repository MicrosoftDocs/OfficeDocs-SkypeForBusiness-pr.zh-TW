---
title: 鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要：針對商務用 Skype Server 鎖定或解除鎖定使用者的電話撥入式會議 PIN。
ms.openlocfilehash: e9a5e59497a4cb771d0b20cef55b09b26817216d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818785"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="cac7e-103">鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="cac7e-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="cac7e-104">**摘要：** 針對商務用 Skype Server 鎖定或解除鎖定使用者的電話撥入式會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="cac7e-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="cac7e-105">您可以從商務用 Skype Server [控制台] 的 [**使用者**] 區段鎖定或解除鎖定使用者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="cac7e-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="cac7e-106">在商務用 Skype Server [控制台] 中鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="cac7e-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cac7e-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cac7e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cac7e-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cac7e-109">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cac7e-110">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="cac7e-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="cac7e-111">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="cac7e-112">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="cac7e-113">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="cac7e-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="cac7e-114">是.</span><span class="sxs-lookup"><span data-stu-id="cac7e-114">a.</span></span> <span data-ttu-id="cac7e-115">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="cac7e-116">乙.</span><span class="sxs-lookup"><span data-stu-id="cac7e-116">b.</span></span> <span data-ttu-id="cac7e-117">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="cac7e-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="cac7e-118">c-clip.</span><span class="sxs-lookup"><span data-stu-id="cac7e-118">c.</span></span> <span data-ttu-id="cac7e-119">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="cac7e-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="cac7e-120">希望.</span><span class="sxs-lookup"><span data-stu-id="cac7e-120">d.</span></span> <span data-ttu-id="cac7e-121">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="cac7e-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cac7e-122">若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="cac7e-123">e.</span><span class="sxs-lookup"><span data-stu-id="cac7e-123">e.</span></span> <span data-ttu-id="cac7e-124">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-124">Click **Find**.</span></span>
    
   <span data-ttu-id="cac7e-125">°.</span><span class="sxs-lookup"><span data-stu-id="cac7e-125">f.</span></span> <span data-ttu-id="cac7e-126">按一下使用者，按一下 [**動作**]，然後按一下 [**鎖定 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="cac7e-127">在商務用 Skype Server [控制台] 中解除鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="cac7e-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cac7e-128">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cac7e-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cac7e-129">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cac7e-130">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cac7e-131">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="cac7e-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="cac7e-132">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="cac7e-133">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="cac7e-134">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="cac7e-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="cac7e-135">是.</span><span class="sxs-lookup"><span data-stu-id="cac7e-135">a.</span></span> <span data-ttu-id="cac7e-136">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="cac7e-137">乙.</span><span class="sxs-lookup"><span data-stu-id="cac7e-137">b.</span></span> <span data-ttu-id="cac7e-138">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="cac7e-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="cac7e-139">c-clip.</span><span class="sxs-lookup"><span data-stu-id="cac7e-139">c.</span></span> <span data-ttu-id="cac7e-140">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="cac7e-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="cac7e-141">希望.</span><span class="sxs-lookup"><span data-stu-id="cac7e-141">d.</span></span> <span data-ttu-id="cac7e-142">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="cac7e-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cac7e-143">若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="cac7e-144">e.</span><span class="sxs-lookup"><span data-stu-id="cac7e-144">e.</span></span> <span data-ttu-id="cac7e-145">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-145">Click **Find**.</span></span>
    
   <span data-ttu-id="cac7e-146">°.</span><span class="sxs-lookup"><span data-stu-id="cac7e-146">f.</span></span> <span data-ttu-id="cac7e-147">按一下使用者，按一下 [**動作**]，然後按一下 [**解除鎖定 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="cac7e-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cac7e-148">使用 Windows PowerShell Cmdlet 鎖定及解除鎖定使用者 Pin</span><span class="sxs-lookup"><span data-stu-id="cac7e-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cac7e-149">您可以使用 Windows PowerShell 以及 Lock CsClientPin 和解除 CsClientPin Cmdlet 來鎖定和解除鎖定使用者 Pin。</span><span class="sxs-lookup"><span data-stu-id="cac7e-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="cac7e-150">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話中執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cac7e-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cac7e-151">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="cac7e-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="cac7e-152">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="cac7e-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="cac7e-153">鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="cac7e-153">To lock a user PIN</span></span>

- <span data-ttu-id="cac7e-154">若要鎖定使用者的 PIN，請使用 Lock CsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cac7e-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="cac7e-155">例如：</span><span class="sxs-lookup"><span data-stu-id="cac7e-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="cac7e-156">解除鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="cac7e-156">To unlock a user PIN</span></span>

- <span data-ttu-id="cac7e-157">若要解除鎖定使用者的 PIN，請使用 Unlock CsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cac7e-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="cac7e-158">例如：</span><span class="sxs-lookup"><span data-stu-id="cac7e-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="cac7e-159">如需詳細資訊，請參閱[Lock CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)和[解除 CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="cac7e-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
