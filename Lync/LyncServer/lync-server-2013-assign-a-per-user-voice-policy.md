---
title: Lync Server 2013：指派每位使用者的語音原則
description: Lync Server 2013：指派每位使用者的語音原則。
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
ms.openlocfilehash: e7ea0b171e10302b4c466187c54324cc2548e821
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563559"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="b1394-103">在 Lync Server 2013 中指派每位使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="b1394-103">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b1394-104">全域與網站層級語音原則會自動指派給所有啟用 Enterprise Voice 的 Lync Server 2013 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1394-104">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="b1394-105">您也可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將語音原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="b1394-105">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b1394-106">使用本主題中的程式，將每一使用者原則明確指派給 Lync Server 使用者。</span><span class="sxs-lookup"><span data-stu-id="b1394-106">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="b1394-107">使用 Lync Server 控制台指派使用者特有的語音原則</span><span class="sxs-lookup"><span data-stu-id="b1394-107">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b1394-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b1394-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1394-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b1394-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1394-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b1394-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1394-111">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b1394-111">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b1394-112">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="b1394-112">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b1394-113">在 [**語音原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="b1394-113">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b1394-114"><STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器或全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="b1394-114">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="b1394-115">指派每位使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="b1394-115">Assign per-user voice policies</span></span>

<span data-ttu-id="b1394-116">您可以使用 Windows PowerShell 和 **Grant-CsVoicePolicy** Cmdlet 指派每位使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="b1394-116">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="b1394-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b1394-117">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b1394-118">若要瞭解如何使用遠端 Windows PowerShell 連接至 Lync Server，請閱讀此 Lync Server Windows PowerShell 博客文章： [快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="b1394-118">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="b1394-119">將每一使用者語音原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="b1394-119">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="b1394-120">下列命令會將每位使用者的語音原則 RedmondVoicePolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="b1394-120">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="b1394-121">將每一使用者語音原則指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="b1394-121">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="b1394-122">這個命令會將個別使用者的語音原則 FinanceVoicePolicy 指派給在 Active Directory 之財務 OU 中具有帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="b1394-122">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="b1394-123">如需此命令中所使用之 OU 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="b1394-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="b1394-124">取消指派個別使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="b1394-124">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="b1394-125">下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者語音原則。</span><span class="sxs-lookup"><span data-stu-id="b1394-125">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b1394-126">一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="b1394-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b1394-127">網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="b1394-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b1394-128">如需詳細資訊，請參閱 [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="b1394-128">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1394-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b1394-129">See Also</span></span>


[<span data-ttu-id="b1394-130">停用 Lync Server 2013 的 Enterprise Voice 使用者</span><span class="sxs-lookup"><span data-stu-id="b1394-130">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="b1394-131">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="b1394-131">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

