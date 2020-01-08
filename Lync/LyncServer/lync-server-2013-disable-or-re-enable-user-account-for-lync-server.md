---
title: Lync Server 2013：停用或重新啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="e4c80-102">停用或重新啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e4c80-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4c80-103">_**主題上次修改日期：** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="e4c80-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="e4c80-104">您可以使用下列程式在 Lync Server 2013 中停用先前啟用的使用者帳戶，而不會遺失您為使用者帳戶所設定的 Lync 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="e4c80-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="e4c80-105">因為您不會遺失 Lync Server 使用者帳戶設定，所以您可以重新啟用先前已啟用的使用者帳戶，而不需重新設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e4c80-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e4c80-106">只要停用 Active Directory 中的使用者帳戶，<STRONG>就不會</STRONG>阻止使用者登入或使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e4c80-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="e4c80-107">這是因為 Lync 使用憑證驗證來優化驗證程式，而這些用戶端憑證在180天內有效。</span><span class="sxs-lookup"><span data-stu-id="e4c80-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="e4c80-108">如果您想要停止停用 Lync 伺服器存取權的 Active Directory 帳戶，您必須使用<STRONG>Disable move-csuser</STRONG> Cmdlet，或使用<STRONG>Lync server [控制台</STRONG>] 做為本文中所述。</span><span class="sxs-lookup"><span data-stu-id="e4c80-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="e4c80-109">使用者在 Lync 中停用，且中央管理儲存體已在使用者將無法再登入的環境中複製。</span><span class="sxs-lookup"><span data-stu-id="e4c80-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="e4c80-110">此外，已登入的使用者也會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="e4c80-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="e4c80-111">針對 Lync Server 停用或重新啟用先前啟用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e4c80-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="e4c80-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e4c80-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4c80-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e4c80-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4c80-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e4c80-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4c80-115">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="e4c80-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e4c80-116">在 [**搜尋使用者**] 方塊中，輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="e4c80-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="e4c80-117">在表格中，按一下您要停用或重新啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e4c80-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="e4c80-118">在 [**動作**] 功能表上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e4c80-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="e4c80-119">若要暫時停用 Lync Server 2013 的使用者帳戶，請按一下 [**針對 Lync Server 暫時停**用]。</span><span class="sxs-lookup"><span data-stu-id="e4c80-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="e4c80-120">若要啟用 Lync Server 2013 的使用者帳戶，請按一下 [**針對 Lync Server 重新啟用**]。</span><span class="sxs-lookup"><span data-stu-id="e4c80-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="e4c80-121">使用 Windows PowerShell 來停用或重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e4c80-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="e4c80-122">使用者帳戶可以暫時停用，稍後再使用**move-csuser** Cmdlet 重新啟用。</span><span class="sxs-lookup"><span data-stu-id="e4c80-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="e4c80-123">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e4c80-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e4c80-124">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e4c80-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="e4c80-125">停用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e4c80-125">To disable a user account</span></span>

  - <span data-ttu-id="e4c80-126">若要暫時停用使用者帳戶，請將 Enabled 屬性的值設為 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="e4c80-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="e4c80-127">例如：</span><span class="sxs-lookup"><span data-stu-id="e4c80-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="e4c80-128">若要重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e4c80-128">To re-enable a user account</span></span>

  - <span data-ttu-id="e4c80-129">若要重新啟用已停用的使用者帳戶，請將 Enabled 屬性的值設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="e4c80-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="e4c80-130">例如：</span><span class="sxs-lookup"><span data-stu-id="e4c80-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="e4c80-131">如需詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="e4c80-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4c80-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="e4c80-132">See Also</span></span>


[<span data-ttu-id="e4c80-133">新增及啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e4c80-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="e4c80-134">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="e4c80-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

