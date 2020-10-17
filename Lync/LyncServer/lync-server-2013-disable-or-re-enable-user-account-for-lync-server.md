---
title: Lync Server 2013：停用或重新啟用 Lync Server 的使用者帳戶
description: Lync Server 2013：停用或重新啟用 Lync Server 的使用者帳戶。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568169"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="11c1c-103">停用或重新啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="11c1c-103">Disable or re-enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c1c-104">_**主題上次修改日期：** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="11c1c-104">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="11c1c-105">您可以使用下列程式停用 Lync Server 2013 中先前啟用的使用者帳戶，而不會遺失您為使用者帳戶所設定的 Lync Server 設定。</span><span class="sxs-lookup"><span data-stu-id="11c1c-105">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="11c1c-106">因為您不會遺失 Lync Server 使用者帳戶設定，所以您可以重新啟用先前啟用的使用者帳戶，而不需要重新設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="11c1c-106">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="11c1c-107">只停用 Active Directory 中的使用者帳戶， <STRONG>不會</STRONG> 停止使用者登入或使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="11c1c-107">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="11c1c-108">這是因為 Lync 使用憑證驗證來簡化驗證程式，而這些用戶端憑證在180天內有效。</span><span class="sxs-lookup"><span data-stu-id="11c1c-108">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="11c1c-109">若要停止停用 Lync 伺服器存取的 Active Directory 帳戶，您必須使用 <STRONG>get-csuser 指令程式</STRONG> ，或使用 <STRONG>lync server 控制台</STRONG> （如本文所述）。</span><span class="sxs-lookup"><span data-stu-id="11c1c-109">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="11c1c-110">當使用者在 Lync 中停用，且中央管理存放區已在環境中複寫之後，使用者就無法再登入。</span><span class="sxs-lookup"><span data-stu-id="11c1c-110">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="11c1c-111">而且，已登入的使用者將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="11c1c-111">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="11c1c-112">停用或重新啟用 Lync Server 先前啟用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="11c1c-112">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="11c1c-113">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="11c1c-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11c1c-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="11c1c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11c1c-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="11c1c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11c1c-116">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="11c1c-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="11c1c-117">在 **[搜尋使用者]** 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或您想要停用或重新啟用的使用者帳戶之線路統一資源識別元 (URI)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="11c1c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="11c1c-118">按一下表中您想要停用或重新啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="11c1c-118">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="11c1c-119">在 **[動作]** 功能表上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="11c1c-119">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="11c1c-120">若要暫時停用 Lync Server 2013 的使用者帳戶，請按一下 [ **暫時停用 Lync server**]。</span><span class="sxs-lookup"><span data-stu-id="11c1c-120">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="11c1c-121">若要啟用 Lync Server 2013 的使用者帳戶，請按一下 [ **重新啟用 Lync server**]。</span><span class="sxs-lookup"><span data-stu-id="11c1c-121">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="11c1c-122">使用 Windows PowerShell 停用或重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="11c1c-122">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="11c1c-123">您可以暫時停用使用者帳戶，然後再使用 **Set-CsUser** Cmdlet 重新啟用使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="11c1c-123">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="11c1c-124">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11c1c-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="11c1c-125">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="11c1c-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="11c1c-126">停用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="11c1c-126">To disable a user account</span></span>

  - <span data-ttu-id="11c1c-127">若要暫時停用使用者帳戶，請將 Enabled 內容值設為 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="11c1c-127">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="11c1c-128">例如：</span><span class="sxs-lookup"><span data-stu-id="11c1c-128">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="11c1c-129">重新啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="11c1c-129">To re-enable a user account</span></span>

  - <span data-ttu-id="11c1c-130">若要重新啟用已停用的使用者帳戶，請將 Enabled 內容值設為 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="11c1c-130">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="11c1c-131">例如：</span><span class="sxs-lookup"><span data-stu-id="11c1c-131">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="11c1c-132">如需詳細資訊，請參閱 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="11c1c-132">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11c1c-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="11c1c-133">See Also</span></span>


[<span data-ttu-id="11c1c-134">新增及啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="11c1c-134">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="11c1c-135">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="11c1c-135">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

