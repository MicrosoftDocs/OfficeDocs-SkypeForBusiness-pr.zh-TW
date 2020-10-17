---
title: Lync Server 2013：將封存原則套用至使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423eb8c4d96496f75f8702c5cf2ccf21a3b13b8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508920"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="838c3-102">將封存原則套用至 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="838c3-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="838c3-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="838c3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="838c3-104">如果使用者已啟用 Lync Server 2013，且已建立一或多個使用者原則來封存位於 Lync Server 2013 的使用者，您可以將適當的原則套用至那些使用者或使用者群組，以對特定使用者執行封存支援。</span><span class="sxs-lookup"><span data-stu-id="838c3-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="838c3-105">例如，如果您建立支援內部通訊封存的原則，您可以將它套用至至少一個使用者或使用者群組，以支援使用者的 Lync Server 2013 通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="838c3-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="838c3-106">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="838c3-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="838c3-107">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。</span><span class="sxs-lookup"><span data-stu-id="838c3-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="838c3-108">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="838c3-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="838c3-109">如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">管理組織、網站及集區的 Lync Server 2013 中的封存配置選項</A> 。</span><span class="sxs-lookup"><span data-stu-id="838c3-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="838c3-110">使用本主題中的程序，將先前建立的封存使用者原則套用至一或多個使用者帳戶或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="838c3-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="838c3-111">將封存使用者原則套用至使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="838c3-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="838c3-112">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="838c3-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="838c3-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="838c3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="838c3-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="838c3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="838c3-115">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="838c3-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="838c3-116">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="838c3-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="838c3-117">在 [封存**原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。</span><span class="sxs-lookup"><span data-stu-id="838c3-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="838c3-118"><STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器安裝設定。</span><span class="sxs-lookup"><span data-stu-id="838c3-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="838c3-119">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="838c3-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="838c3-120">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="838c3-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="838c3-121">使用 Windows PowerShell Cmdlet 指派 Per-User 封存原則</span><span class="sxs-lookup"><span data-stu-id="838c3-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="838c3-122">您可以使用 Windows PowerShell 和 **Grant-CsArchivingPolicy** Cmdlet 指派每個使用者的封存原則。</span><span class="sxs-lookup"><span data-stu-id="838c3-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="838c3-123">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="838c3-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="838c3-124">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="838c3-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="838c3-125">將每一使用者封存原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="838c3-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="838c3-126">下列命令將個別使用者封存原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="838c3-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="838c3-127">將每一使用者封存原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="838c3-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="838c3-128">此命令將個別使用者封存原則 RedmondArchivingPolicy 指派給帳戶位於登錄器集區 atl-cs-001.litwareinc.com 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="838c3-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="838c3-129">如需此命令中使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="838c3-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="838c3-130">指派每位使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="838c3-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="838c3-p108">下列命令解除指派任何先前指派給 Ken Myer 的個別使用者封存原則。一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="838c3-p108">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="838c3-134">如需詳細資訊，請參閱 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="838c3-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="838c3-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="838c3-135">See Also</span></span>


[<span data-ttu-id="838c3-136">在 Lync Server 2013 中管理內部和外部通訊的封存</span><span class="sxs-lookup"><span data-stu-id="838c3-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="838c3-137">在 Lync Server 2013 中指派每一使用者原則</span><span class="sxs-lookup"><span data-stu-id="838c3-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

