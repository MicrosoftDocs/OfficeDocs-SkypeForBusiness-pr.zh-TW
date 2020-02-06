---
title: 在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 摘要：針對商務用 Skype Server 設定使用者的電話撥入式會議 PIN。
ms.openlocfilehash: eb025f069156dd54ba772dd866c09adc59d078eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818735"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="71662-103">在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN</span><span class="sxs-lookup"><span data-stu-id="71662-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="71662-104">**摘要：** 針對商務用 Skype Server 設定使用者的電話撥入式會議 PIN。</span><span class="sxs-lookup"><span data-stu-id="71662-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="71662-105">若要將電話撥入式會議加入為經過驗證的使用者，擁有 Active Directory 網域服務（AD DS）認證的商務用 Skype 伺服器使用者需要個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="71662-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="71662-106">如果使用者忘記電話撥入式會議 PIN，或尚未使用商務用 Skype Server 設定 PIN，您可以從商務用 Skype Server 的 [控制台] 設定使用者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="71662-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="71662-107">您可以自動產生 PIN 或手動建立。</span><span class="sxs-lookup"><span data-stu-id="71662-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71662-108">PIN 的特定特性（例如其最小長度）可以設定為原則。</span><span class="sxs-lookup"><span data-stu-id="71662-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="71662-109">除了全域原則之外，您還可以為個別的網站或使用者設定 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="71662-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="71662-110">若要設定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="71662-110">To set a user's PIN</span></span>

1. <span data-ttu-id="71662-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="71662-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="71662-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="71662-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="71662-113">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="71662-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="71662-114">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="71662-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="71662-115">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="71662-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="71662-116">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="71662-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="71662-117">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="71662-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="71662-118">是.</span><span class="sxs-lookup"><span data-stu-id="71662-118">a.</span></span> <span data-ttu-id="71662-119">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="71662-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="71662-120">乙.</span><span class="sxs-lookup"><span data-stu-id="71662-120">b.</span></span> <span data-ttu-id="71662-121">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="71662-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="71662-122">c-clip.</span><span class="sxs-lookup"><span data-stu-id="71662-122">c.</span></span> <span data-ttu-id="71662-123">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="71662-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="71662-124">希望.</span><span class="sxs-lookup"><span data-stu-id="71662-124">d.</span></span> <span data-ttu-id="71662-125">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="71662-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="71662-126">若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="71662-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="71662-127">e.</span><span class="sxs-lookup"><span data-stu-id="71662-127">e.</span></span> <span data-ttu-id="71662-128">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="71662-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="71662-129">如果 PIN 已鎖定，您必須先解除鎖定 PIN，才能進行設定。</span><span class="sxs-lookup"><span data-stu-id="71662-129">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="71662-130">若要解除鎖定 PIN，請按一下使用者，按一下 [**動作**]，然後按一下 [**解除鎖定 pin**]。</span><span class="sxs-lookup"><span data-stu-id="71662-130">To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="71662-131">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**設定 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="71662-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="71662-132">在 [**設定 PIN** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="71662-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="71662-133">若要允許商務用 Skype Server 產生使用者的 PIN，請選取 [**自動產生有效的 PIN** （預設值）]。</span><span class="sxs-lookup"><span data-stu-id="71662-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="71662-134">若要建立您自己的 PIN，請按一下 [**手動輸入特定 PIN**]，按一下文字方塊，然後輸入符合 pin 原則設定中所指定 pin 需求的 pin。</span><span class="sxs-lookup"><span data-stu-id="71662-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="71662-135">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71662-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="71662-136">在 [**設定 PIN**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="71662-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="71662-137">選取 [**顯示 pin** ] 核取方塊以查看 pin，然後複製 pin，並使用貴組織的慣用方法將它與使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="71662-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="71662-138">按一下 [**開啟我的電子郵件應用程式]，將新的 PIN 傳送給使用者**，即可透過電子郵件傳送 pin。</span><span class="sxs-lookup"><span data-stu-id="71662-138">Click **Open my email application to send the new PIN to the user** to send the PIN by email.</span></span> <span data-ttu-id="71662-139">如果 Microsoft Office Outlook 是您的電子郵件用戶端，則 PIN 會自動複製到新的電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="71662-139">If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message.</span></span> <span data-ttu-id="71662-140">如果您使用不同的電子郵件用戶端，請選取 [**顯示 pin** ] 核取方塊以查看 pin，然後將它複製到您的電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="71662-140">If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="71662-141">按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="71662-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71662-142">使用 Windows PowerShell Cmdlet 指派使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="71662-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="71662-143">您也可以使用 CsClientPin Cmdlet 來指派 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="71662-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="71662-144">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71662-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71662-145">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="71662-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="71662-146">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="71662-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="71662-147">自動將 PIN 號碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="71662-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="71662-148">下列命令會將 PIN 碼指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="71662-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="71662-149">因為未包含 Pin 參數，商務用 Skype 伺服器將自動產生並指派 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="71662-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="71662-150">將特定的 PIN 碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="71662-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="71662-151">這個命令會使用釘選參數，將 PIN 碼121989指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="71662-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="71662-152">如需詳細資訊，請參閱[CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="71662-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

