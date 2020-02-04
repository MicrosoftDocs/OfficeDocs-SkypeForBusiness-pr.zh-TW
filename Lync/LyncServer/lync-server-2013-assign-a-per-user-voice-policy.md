---
title: Lync Server 2013：指派每個使用者的語音原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723403"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="179a4-102">在 Lync Server 2013 中指派每個使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="179a4-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="179a4-103">全域及網站層級語音原則會自動指派給所有啟用企業語音的 Lync Server 2013 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="179a4-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="179a4-104">您也可以使用 Lync Server 2013 的 [控制台] 或 [Lync Server 2013 管理命令介面]，將語音原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="179a4-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="179a4-105">使用本主題中的程式，將每個使用者的原則明確指派給 Lync Server 使用者。</span><span class="sxs-lookup"><span data-stu-id="179a4-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="179a4-106">使用 Lync Server [控制台] 指派使用者專用的語音原則</span><span class="sxs-lookup"><span data-stu-id="179a4-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="179a4-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="179a4-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="179a4-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="179a4-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="179a4-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="179a4-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="179a4-110">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="179a4-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="179a4-111">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="179a4-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="179a4-112">在 [**語音原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="179a4-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="179a4-113">[ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用 [預設伺服器] 或 [全域原則設定]。</span><span class="sxs-lookup"><span data-stu-id="179a4-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="179a4-114">使用 Windows PowerShell Cmdlet 指派每個使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="179a4-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="179a4-115">您可以使用 Windows PowerShell 和**Grant CsVoicePolicy** Cmdlet 指派每個使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="179a4-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="179a4-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="179a4-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="179a4-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="179a4-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="179a4-118">將每個使用者的語音原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="179a4-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="179a4-119">下列命令會將每個使用者的語音原則 RedmondVoicePolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="179a4-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="179a4-120">若要將每個使用者的語音原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="179a4-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="179a4-121">這個命令會將每個使用者的語音原則 FinanceVoicePolicy 指派給在 Active Directory 的財務 OU 中擁有帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="179a4-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="179a4-122">如需此命令中使用的 OU 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="179a4-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="179a4-123">若要取消指派每個使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="179a4-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="179a4-124">下列命令會以前指派給 Ken Myer 的任何每使用者語音原則。</span><span class="sxs-lookup"><span data-stu-id="179a4-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="179a4-125">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="179a4-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="179a4-126">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="179a4-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="179a4-127">如需詳細資訊，請參閱[Grant CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="179a4-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="179a4-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="179a4-128">See Also</span></span>


[<span data-ttu-id="179a4-129">在 Lync Server 2013 中停用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="179a4-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="179a4-130">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="179a4-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

