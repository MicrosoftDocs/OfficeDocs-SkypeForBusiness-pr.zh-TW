---
title: 在商務用 Skype Server 中查看使用者 PIN 資訊
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
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：查看商務用 Skype Server 中的使用者 PIN 碼資訊。
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806503"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="bf680-103">在商務用 Skype Server 中查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="bf680-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="bf680-104">**摘要：** 在商務用 Skype Server 中查看使用者 PIN 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="bf680-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf680-105">若要將電話撥入式會議加入為已驗證的使用者，使用 Active Directory 網域服務的商務用 Skype 伺服器使用者 (AD DS) 認證需要 (PIN) 的個人識別碼。</span><span class="sxs-lookup"><span data-stu-id="bf680-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="bf680-106">您可以從商務用 Skype Server [控制台] 中查看使用者的 PIN 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="bf680-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf680-107">您可以檢視諸如是否已設定 PIN 或上次變更 PIN 的時間之類的 PIN 狀態資訊，但無法藉由查看 PIN 狀態來查看目前的 PIN。</span><span class="sxs-lookup"><span data-stu-id="bf680-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="bf680-108">如果使用者已遺失 PIN 碼，您可以在[設定使用者的電話撥入式會議 PIN 碼的商務用 Skype Server 中](set-a-user-s-dial-in-conferencing-pin.md)執行下列程式，以重設其 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="bf680-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="bf680-109">在商務用 Skype Server 控制台中查看使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="bf680-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bf680-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bf680-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bf680-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bf680-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bf680-112">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="bf680-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="bf680-113">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="bf680-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="bf680-114">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="bf680-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="bf680-115">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="bf680-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="bf680-116">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="bf680-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="bf680-117">a.</span><span class="sxs-lookup"><span data-stu-id="bf680-117">a.</span></span> <span data-ttu-id="bf680-118">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="bf680-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="bf680-119">b.</span><span class="sxs-lookup"><span data-stu-id="bf680-119">b.</span></span> <span data-ttu-id="bf680-120">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="bf680-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="bf680-121">c.</span><span class="sxs-lookup"><span data-stu-id="bf680-121">c.</span></span> <span data-ttu-id="bf680-122">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **等於** 或 **不等於**)。</span><span class="sxs-lookup"><span data-stu-id="bf680-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="bf680-123">d.</span><span class="sxs-lookup"><span data-stu-id="bf680-123">d.</span></span> <span data-ttu-id="bf680-124">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="bf680-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bf680-125">若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="bf680-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="bf680-126">e.</span><span class="sxs-lookup"><span data-stu-id="bf680-126">e.</span></span> <span data-ttu-id="bf680-127">按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="bf680-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bf680-p108">如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行] 和 [解除鎖定 PIN]。</span><span class="sxs-lookup"><span data-stu-id="bf680-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="bf680-130">依序按一下搜尋結果中的使用者、[執行] 和 [檢視 PIN 狀態]。</span><span class="sxs-lookup"><span data-stu-id="bf680-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bf680-131">使用 Windows PowerShell Cmdlet 來查看使用者 PIN 碼資訊</span><span class="sxs-lookup"><span data-stu-id="bf680-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="bf680-132">您可以使用 Get-CsClientPinInfo Cmdlet 來檢視使用者 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="bf680-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="bf680-133">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bf680-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bf680-134">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="bf680-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bf680-135">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="bf680-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="bf680-136">檢視使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="bf680-136">To view user PIN information</span></span>

<span data-ttu-id="bf680-137">若要查看使用者的 PIN 資訊，請在商務用 Skype Server 管理命令介面中輸入類似下列的命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="bf680-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="bf680-138">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="bf680-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="bf680-139">如需詳細資訊，請參閱 [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="bf680-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf680-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bf680-140">See also</span></span>

[<span data-ttu-id="bf680-141">在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN</span><span class="sxs-lookup"><span data-stu-id="bf680-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="bf680-142">鎖定或解除鎖定使用者 PIN 碼中的商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="bf680-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
