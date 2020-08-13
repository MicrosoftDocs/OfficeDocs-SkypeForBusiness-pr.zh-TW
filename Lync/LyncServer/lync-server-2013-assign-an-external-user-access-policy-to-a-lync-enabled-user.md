---
title: Lync Server 2013：將外部使用者存取原則指派給啟用 Lync 功能的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612b872e0071e2ad3fa2d4d064048805a4e65953
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="c460e-102">在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="c460e-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c460e-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c460e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c460e-104">如果使用者已啟用 Lync Server，您可以將適當的原則套用至特定使用者，以在 Lync Server 控制台中設定 SIP 同盟、XMPP 同盟、遠端使用者存取和公用立即訊息 (IM) 連線。</span><span class="sxs-lookup"><span data-stu-id="c460e-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="c460e-105">例如，如果您建立原則來支援遠端使用者存取，則必須先將其套用至使用者，使用者才能從遠端位置連接至 Lync Server，並從遠端位置與內部使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="c460e-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c460e-106">若要支援外部使用者存取，您必須啟用想要支援之每種外部使用者存取類型的支援，以及設定適當原則及其他控制使用的選項。</span><span class="sxs-lookup"><span data-stu-id="c460e-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="c460e-107">如需詳細資訊，請參閱部署檔中的設定<A href="lync-server-2013-configuring-support-for-external-user-access.md">外部使用者2013存取的支援</A>，或管理 Operations 檔中的<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">lync server 2013 的同盟與外部存取</A>。</span><span class="sxs-lookup"><span data-stu-id="c460e-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="c460e-108">使用本主題中的程序，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c460e-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="c460e-109">將外部使用者原則套用至使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="c460e-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="c460e-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c460e-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c460e-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c460e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c460e-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c460e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c460e-113">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c460e-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="c460e-114">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c460e-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c460e-115">在 **[外部存取原則]** 的 **[編輯 Lync Server 使用者]** 下，選取想要套用的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="c460e-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c460e-116"><STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器或全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="c460e-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c460e-117">使用 Windows PowerShell Cmdlet 指派 Per-User 外部存取原則</span><span class="sxs-lookup"><span data-stu-id="c460e-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c460e-118">您可以使用 Windows PowerShell 和 Get-csexternalaccesspolicy 指令程式來指派每個使用者的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="c460e-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="c460e-119">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c460e-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c460e-120">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="c460e-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="c460e-121">將個別使用者外部存取原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="c460e-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="c460e-122">此命令可將個別使用者外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="c460e-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="c460e-123">將個別使用者外部存取原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="c460e-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="c460e-124">此命令可將個別使用者外部存取原則 USAExternalAccessPolicy，指派給所有具有 Active Directory 中之 UnitedStates OUto 帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="c460e-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="c460e-125">如需此命令中所使用之 OU 參數的詳細資訊，請參閱[Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="c460e-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="c460e-126">取消指派個別使用者外部存取原則</span><span class="sxs-lookup"><span data-stu-id="c460e-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="c460e-p106">此命令可將任何先前指派給 Ken Myer 的個別使用者外部存取原則予以解除指派。一旦解除指派個別使用者原則，即會自動使用全域原則或其本機網站原則 (如果存在的話) 來管理 Ken Myer。網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="c460e-p106">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="c460e-130">如需詳細資訊，請參閱[get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="c460e-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

