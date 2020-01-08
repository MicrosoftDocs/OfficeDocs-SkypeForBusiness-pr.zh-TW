---
title: Lync Server 2013：從 Lync Server 移除使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="45e6f-102">從 Lync Server 2013 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45e6f-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45e6f-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="45e6f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="45e6f-104">您可以使用下列程式在 Lync Server 2013 中移除先前新增的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="45e6f-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45e6f-105">移除使用者將會導致您遺失任何您為使用者帳戶所設定的設定。</span><span class="sxs-lookup"><span data-stu-id="45e6f-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="45e6f-106">如果您想改為暫時停用使用者帳戶，請參閱停用<A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">或重新啟用 Lync Server 2013 的使用者帳戶</A>主題。</span><span class="sxs-lookup"><span data-stu-id="45e6f-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="45e6f-107">使用 Lync Server 管理命令介面移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45e6f-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="45e6f-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="45e6f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="45e6f-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="45e6f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="45e6f-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="45e6f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="45e6f-111">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="45e6f-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="45e6f-112">在 [**搜尋使用者**] 方塊中，輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="45e6f-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="45e6f-113">在表格中，按一下您要移除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="45e6f-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="45e6f-114">在 [**動作**] 功能表上，選取 [**從 Lync Server 移除**]，隨後便會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="45e6f-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="45e6f-115">從對話方塊中，選取 **[確定]** 以移除使用者。</span><span class="sxs-lookup"><span data-stu-id="45e6f-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="45e6f-116">使用 Windows PowerShell Cmdlet 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45e6f-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="45e6f-117">您可以使用 Disable Move-csuser Cmdlet 來移除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="45e6f-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="45e6f-118">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="45e6f-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="45e6f-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="45e6f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="45e6f-120">移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45e6f-120">To remove a user account</span></span>

  - <span data-ttu-id="45e6f-121">若要移除使用者帳戶，請使用 Disable-Move-csuser Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="45e6f-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="45e6f-122">例如：</span><span class="sxs-lookup"><span data-stu-id="45e6f-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="45e6f-123">執行此命令之後，就無法重新啟用帳戶及其先前的設定。</span><span class="sxs-lookup"><span data-stu-id="45e6f-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="45e6f-124">相反地，您必須使用 Enable-Move-csuser Cmdlet 來為 Ken Myer 建立全新的帳戶。</span><span class="sxs-lookup"><span data-stu-id="45e6f-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="45e6f-125">如需詳細資訊，請參閱[Disable move-csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="45e6f-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45e6f-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="45e6f-126">See Also</span></span>


[<span data-ttu-id="45e6f-127">停用或重新啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45e6f-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="45e6f-128">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="45e6f-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

