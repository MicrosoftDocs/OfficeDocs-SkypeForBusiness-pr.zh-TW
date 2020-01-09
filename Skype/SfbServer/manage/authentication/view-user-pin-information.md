---
title: 在商務用 Skype Server 中查看使用者 PIN 資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：在商務用 Skype Server 中查看使用者 PIN 資訊。
ms.openlocfilehash: e0a74d980be4c77c5fe92f9e0d871f238a7271f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991938"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="a0b35-103">在商務用 Skype Server 中查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="a0b35-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="a0b35-104">**摘要：** 在商務用 Skype Server 中查看使用者 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="a0b35-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="a0b35-105">若要將電話撥入式會議加入為經過驗證的使用者，擁有 Active Directory 網域服務（AD DS）認證的商務用 Skype 伺服器使用者需要個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="a0b35-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="a0b35-106">您可以從商務用 Skype Server [控制台] 查看使用者的 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="a0b35-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0b35-107">您可以查看 PIN 狀態資訊，例如，PIN 是否已設定，或是 PIN 上次變更的時間，但是您看不到目前的 PIN，只需要查看 PIN 狀態即可。</span><span class="sxs-lookup"><span data-stu-id="a0b35-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="a0b35-108">如果使用者遺失其 PIN，您可以依照在[商務用 Skype Server 中設定使用者的電話撥入式會議 PIN](set-a-user-s-dial-in-conferencing-pin.md)中的程式來重設它。</span><span class="sxs-lookup"><span data-stu-id="a0b35-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a0b35-109">若要在商務用 Skype Server [控制台] 中查看使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="a0b35-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a0b35-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a0b35-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a0b35-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a0b35-112">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a0b35-113">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="a0b35-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="a0b35-114">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="a0b35-115">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="a0b35-116">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="a0b35-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="a0b35-117">是.</span><span class="sxs-lookup"><span data-stu-id="a0b35-117">a.</span></span> <span data-ttu-id="a0b35-118">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="a0b35-119">乙.</span><span class="sxs-lookup"><span data-stu-id="a0b35-119">b.</span></span> <span data-ttu-id="a0b35-120">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="a0b35-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="a0b35-121">c-clip.</span><span class="sxs-lookup"><span data-stu-id="a0b35-121">c.</span></span> <span data-ttu-id="a0b35-122">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="a0b35-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="a0b35-123">希望.</span><span class="sxs-lookup"><span data-stu-id="a0b35-123">d.</span></span> <span data-ttu-id="a0b35-124">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="a0b35-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a0b35-125">若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="a0b35-126">e.</span><span class="sxs-lookup"><span data-stu-id="a0b35-126">e.</span></span> <span data-ttu-id="a0b35-127">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a0b35-128">如果 PIN 已鎖定，您必須先解除鎖定 PIN，才能進行設定。</span><span class="sxs-lookup"><span data-stu-id="a0b35-128">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="a0b35-129">若要解除鎖定 PIN，請按一下使用者，按一下 [**動作**]，然後按一下 [**解除鎖定 pin**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-129">To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="a0b35-130">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**查看 PIN 狀態**]。</span><span class="sxs-lookup"><span data-stu-id="a0b35-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a0b35-131">使用 Windows PowerShell Cmdlet 來查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="a0b35-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a0b35-132">您可以使用 CsClientPinInfo Cmdlet 來查看使用者 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="a0b35-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="a0b35-133">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a0b35-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a0b35-134">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="a0b35-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a0b35-135">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="a0b35-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="a0b35-136">若要查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="a0b35-136">To view user PIN information</span></span>

<span data-ttu-id="a0b35-137">若要查看使用者的 PIN 資訊，請在商務用 Skype Server 管理命令介面中輸入類似以下的命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a0b35-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="a0b35-138">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="a0b35-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="a0b35-139">如需詳細資訊，請參閱[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="a0b35-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a0b35-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a0b35-140">See also</span></span>

[<span data-ttu-id="a0b35-141">在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN</span><span class="sxs-lookup"><span data-stu-id="a0b35-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="a0b35-142">鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="a0b35-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
