---
title: Lync Server 2013：將外部使用者存取原則指派給擁有 Lync 功能的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="40e55-102">在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="40e55-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40e55-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="40e55-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="40e55-104">如果使用者已啟用 Lync Server，您可以在 Lync Server 的 [控制台] 中設定 SIP 同盟、XMPP 同盟、遠端使用者存取及公用立即訊息（IM）連線，方法是將適當的原則套用至特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="40e55-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="40e55-105">例如，如果您建立了支援遠端使用者存取的原則，您必須先將其套用至使用者，才能讓使用者從遠端位置連線到 Lync Server，並從遠端位置與內部使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="40e55-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40e55-106">若要支援外部使用者存取，您必須針對您要支援的每個外部使用者存取類型啟用支援，然後設定適當的原則和其他選項來控制其用途。</span><span class="sxs-lookup"><span data-stu-id="40e55-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="40e55-107">如需詳細資訊，請參閱在 [部署檔] 中的 [在<A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 中設定外部使用者存取支援</A>] 或 [在作業檔中<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理 lync server 2013 的同盟及外部存取</A>]。</span><span class="sxs-lookup"><span data-stu-id="40e55-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="40e55-108">使用本主題中的程式，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="40e55-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="40e55-109">將外部使用者原則套用到使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="40e55-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="40e55-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="40e55-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40e55-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="40e55-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40e55-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="40e55-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="40e55-113">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="40e55-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="40e55-114">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40e55-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="40e55-115">在 [**外部存取原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="40e55-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40e55-116">[ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用 [預設伺服器] 或 [全域原則設定]。</span><span class="sxs-lookup"><span data-stu-id="40e55-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="40e55-117">使用 Windows PowerShell Cmdlet 指派每個使用者的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="40e55-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="40e55-118">您可以使用 Windows PowerShell 和 Grant CsExternalAccessPolicy Cmdlet 來指派每個使用者的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="40e55-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="40e55-119">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="40e55-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="40e55-120">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="40e55-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="40e55-121">將每個使用者的外部存取原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="40e55-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="40e55-122">這個命令會將每個使用者的外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="40e55-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="40e55-123">將每個使用者的外部存取原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="40e55-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="40e55-124">這個命令會將每個使用者的外部存取原則 USAExternalAccessPolicy 指派給在 Active Directory 中的美國組織單位中擁有帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="40e55-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="40e55-125">如需此命令中使用的 OU 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="40e55-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="40e55-126">若要取消指派每個使用者的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="40e55-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="40e55-127">這個命令會會先前指派給 Ken Myer 的任何每使用者外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="40e55-127">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="40e55-128">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="40e55-128">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="40e55-129">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="40e55-129">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="40e55-130">如需詳細資訊，請參閱[Grant CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="40e55-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

