---
title: Lync Server 2013：建立或修改新的用戶端版本原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e95abe52883bff2c99ad02b01ea4cc1473f4626f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="10ae6-102">在 Lync Server 2013 中建立或修改新的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="10ae6-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10ae6-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="10ae6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="10ae6-104">您可以使用用戶端版本原則，指定環境中支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="10ae6-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="10ae6-105">使用用戶端版本設定可協助減少支援多個用戶端版本相關的成本。</span><span class="sxs-lookup"><span data-stu-id="10ae6-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="10ae6-106">它也可以改善整體使用者經驗，因為當舊版用戶端與更新版本互動時，舊版的用戶端就可以限制可用的功能。</span><span class="sxs-lookup"><span data-stu-id="10ae6-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="10ae6-107">您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，建立或修改用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="10ae6-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="10ae6-108">使用 Lync Server 控制台建立或修改用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="10ae6-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="10ae6-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="10ae6-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10ae6-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="10ae6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10ae6-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="10ae6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10ae6-112">在左導覽列中，按一下 [**用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="10ae6-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10ae6-113">預設會選取 [<STRONG>用戶端版本原則</STRONG>] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="10ae6-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="10ae6-114">在 [**用戶端版本原則**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="10ae6-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="10ae6-115">若要建立用戶端版本原則，請按一下 [**新增**]，選取 [**網站原則**]、[**集區原則**] 或 [**使用者原則**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="10ae6-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="10ae6-116">若要修改全域原則或其他現有的用戶端版本原則，請選取原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="10ae6-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="10ae6-117">在 [**編輯用戶端版本原則**] 頁面上，如在[Lync Server 2013 中建立或修改新的用戶端版本原則規則](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)中所述，建立或修改規則。</span><span class="sxs-lookup"><span data-stu-id="10ae6-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="10ae6-118">使用 Windows PowerShell Cmdlet 建立或修改用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="10ae6-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="10ae6-119">您可以使用**New-CsClientVersionPolicy** Cmdlet 來建立用戶端版本原則，並使用**Set-CsClientVersionPolicy** Cmdlet 加以修改。</span><span class="sxs-lookup"><span data-stu-id="10ae6-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="10ae6-120">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="10ae6-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="10ae6-121">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="10ae6-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="10ae6-122">若要建立新的網站範圍用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="10ae6-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="10ae6-123">下列命令會建立套用至 Redmond 網站的新用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="10ae6-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="10ae6-124">由於未指定其他參數，因此新原則會使用預設的用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="10ae6-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="10ae6-125">若要建立新的每一使用者用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="10ae6-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="10ae6-126">若要建立每一使用者原則，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="10ae6-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="10ae6-127">如需詳細資訊，請參閱[New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 及[Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="10ae6-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

