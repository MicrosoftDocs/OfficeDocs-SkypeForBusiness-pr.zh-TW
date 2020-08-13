---
title: Lync Server 2013：指派每個使用者的撥號對應表原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134439"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="8589b-102">在 Lync Server 2013 中指派每個使用者的撥號對應表原則</span><span class="sxs-lookup"><span data-stu-id="8589b-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8589b-103">若要為企業語音使用者或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指定撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8589b-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="8589b-104">當您未明確指派現有的每一使用者撥號對應表時，使用者帳戶會自動使用全域撥號對應表或網站層級撥號對應表（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="8589b-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="8589b-105">如果您想要針對所有已啟用 Enterprise Voice 的使用者使用全域或網站撥號對應表，您可以略過本節。</span><span class="sxs-lookup"><span data-stu-id="8589b-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="8589b-106">使用 Lync Server 2013 控制台指派撥號對應表</span><span class="sxs-lookup"><span data-stu-id="8589b-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="8589b-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8589b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8589b-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="8589b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8589b-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8589b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8589b-110">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="8589b-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8589b-111">在 [**搜尋使用者**] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="8589b-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="8589b-112">在表格中，按一下您要指派撥號對應表的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8589b-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="8589b-113">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="8589b-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="8589b-114">在 [**編輯 Lync Server 使用者**] 頁面的 [**電話**語音] 下，按一下 [**企業語音**]。</span><span class="sxs-lookup"><span data-stu-id="8589b-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="8589b-115">按一下 [撥號對應表**原則**]，然後選擇想要的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8589b-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="8589b-116">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="8589b-116">Click **Commit**.</span></span>

<span data-ttu-id="8589b-117">如需設定撥號對應表的詳細資訊，請參閱在[Lync Server 2013 中設定撥號](lync-server-2013-configuring-dial-plans.md)對應表主題。</span><span class="sxs-lookup"><span data-stu-id="8589b-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8589b-118">使用 Windows PowerShell Cmdlet 指派 Per-User 撥號對應表</span><span class="sxs-lookup"><span data-stu-id="8589b-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8589b-119">您可以將每一使用者撥號對應表指派給 Windows PowerShell 和**get-csdialplan** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8589b-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="8589b-120">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8589b-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8589b-121">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="8589b-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="8589b-122">將每一使用者撥號對應表指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="8589b-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="8589b-123">下列命令會指派每個使用者的撥號對應表 RedmondDialPlan 給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="8589b-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="8589b-124">將每一使用者撥號對應表指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="8589b-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="8589b-125">這個命令會將個別使用者撥號對應表 RedmondDialPlan 指派給 Redmond 的城市中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="8589b-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="8589b-126">如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="8589b-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="8589b-127">取消指派個別使用者撥號對應表</span><span class="sxs-lookup"><span data-stu-id="8589b-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="8589b-128">下列命令 unassigns 先前指派給 Ken Myer 的任何每一使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8589b-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="8589b-129">未指派每個使用者的撥號對應表後，Ken Myer 會透過全域撥號對應表自動管理，他的本機網站撥號對應表 (若存在) 或指派給其註冊機構或 PSTN 閘道的服務範圍撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8589b-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="8589b-130">服務範圍撥號對應表優先于任何網站撥號對應表，而網站撥號對應表的優先順序會高於全域撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8589b-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="8589b-131">如需詳細資訊，請參閱[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="8589b-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="8589b-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8589b-132">See Also</span></span>


[<span data-ttu-id="8589b-133">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="8589b-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="8589b-134">啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8589b-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

