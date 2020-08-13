---
title: Lync Server 2013：設定使用者的電話撥入式會議 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad28eb7214cb6762e8b0941f22da8b97966e9024
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="a2a35-102">在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN</span><span class="sxs-lookup"><span data-stu-id="a2a35-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2a35-103">_**主題上次修改日期：** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="a2a35-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="a2a35-104">若要將電話撥入式會議加入為已驗證的使用者，使用 Active Directory 網域服務 (AD DS) 認證的 Lync Server 2013 使用者需要個人識別碼)  (PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="a2a35-105">如果使用者忘記電話撥入式會議 PIN，或是未使用 Lync Server 設定 PIN，您可以從 Lync Server 控制台設定使用者的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="a2a35-106">您可以自動產生 PIN 碼，也可以手動建立 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2a35-107">PIN 碼的特定特性（如其最小長度）可以設定為原則。</span><span class="sxs-lookup"><span data-stu-id="a2a35-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="a2a35-108">除了通用原則之外，您還可以為個別網站或使用者設定 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="a2a35-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="a2a35-109">如需設定 PIN 原則的詳細資訊，請參閱<A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">在 Lync Server 2013 中設定電話撥入式會議個人身分識別號碼 (PIN) 規則</A>。</span><span class="sxs-lookup"><span data-stu-id="a2a35-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="a2a35-110">設定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="a2a35-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="a2a35-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a2a35-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a2a35-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a2a35-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2a35-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a35-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2a35-114">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="a2a35-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a2a35-115">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="a2a35-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="a2a35-116">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="a2a35-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="a2a35-117">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="a2a35-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="a2a35-118">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="a2a35-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a2a35-119">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="a2a35-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a2a35-120">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="a2a35-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="a2a35-121">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **[等於]** 或 **[不等於]**)。</span><span class="sxs-lookup"><span data-stu-id="a2a35-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="a2a35-122">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="a2a35-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="a2a35-123">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a2a35-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="a2a35-124">按一下 [尋找]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2a35-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2a35-p104">如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行]<STRONG></STRONG> 和 [解除鎖定 PIN]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a2a35-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="a2a35-127">按一下搜尋結果中的使用者，按一下 [**動作**]，然後按一下 [**設定 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="a2a35-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="a2a35-128">在 [**設定 PIN** ] 對話方塊中，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="a2a35-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="a2a35-129">若要允許 Lync Server 2013 產生使用者的 PIN，請選取 [**自動產生有效的 pin** (預設) 。</span><span class="sxs-lookup"><span data-stu-id="a2a35-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="a2a35-130">若要建立您自己的 PIN，請按一下 [**手動輸入特定的 pin**]，然後按一下文字方塊，然後輸入符合 pin 原則設定中所指定之 pin 碼需求的 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="a2a35-131">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2a35-131">Click **OK**.</span></span>

9.  <span data-ttu-id="a2a35-132">在 [**設定 PIN**] 中，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="a2a35-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="a2a35-133">選取 [**顯示 pin** ] 核取方塊以查看 pin，然後複製 pin 碼，並使用組織的慣用方法將其傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="a2a35-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="a2a35-134">按一下 [**開啟我的電子郵件應用程式]，將新的 PIN 碼傳送給使用者**，以便透過電子郵件傳送 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-134">Click **Open my email application to send the new PIN to the user** to send the PIN by email.</span></span> <span data-ttu-id="a2a35-135">如果 Microsoft Office Outlook 是您的電子郵件用戶端，則 PIN 碼會自動複製到新的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="a2a35-135">If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message.</span></span> <span data-ttu-id="a2a35-136">如果您使用不同的電子郵件用戶端，請選取 [**顯示 pin** ] 核取方塊以查看 pin 碼，然後將其複製到您的電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="a2a35-136">If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="a2a35-137">按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2a35-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a2a35-138">使用 Windows PowerShell Cmdlet 指派使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="a2a35-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a2a35-139">您也可以使用 Unlock-csclientpin 指令程式指派 PIN 碼號碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="a2a35-140">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2a35-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a2a35-141">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="a2a35-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="a2a35-142">若要自動將 PIN 碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="a2a35-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="a2a35-143">下列命令會將 PIN 碼指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="a2a35-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="a2a35-144">因為未包含 Pin 參數，Lync Server 會自動產生並指派 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="a2a35-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="a2a35-145">若要將特定 PIN 碼號碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="a2a35-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="a2a35-146">這個命令會使用 Pin 參數，將 PIN 碼121989指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="a2a35-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="a2a35-147">如需詳細資訊，請參閱[unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="a2a35-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2a35-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2a35-148">See Also</span></span>


<span data-ttu-id="a2a35-149">[撥入存取號碼](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a2a35-149">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="a2a35-150">在 Lync Server 2013 中設定電話撥入式會議個人身分識別號碼 (PIN) 規則</span><span class="sxs-lookup"><span data-stu-id="a2a35-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

