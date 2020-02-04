---
title: Lync Server 2013：刪除未指定的數位範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a80a28cf4ee5b310790a057253ea52ca17a14aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="34322-102">在 Lync Server 2013 中刪除未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="34322-102">Delete an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34322-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="34322-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="34322-104">使用下列其中一個程式來刪除公告的未指定編號範圍。</span><span class="sxs-lookup"><span data-stu-id="34322-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="34322-105">使用 Lync Server [控制台] 刪除未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="34322-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="34322-106">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="34322-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="34322-107">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="34322-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="34322-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="34322-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34322-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="34322-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34322-110">在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**未指定的號碼**]。</span><span class="sxs-lookup"><span data-stu-id="34322-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="34322-111">在 [**未指定的號碼**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除的未指派數位範圍的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="34322-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="34322-112">在產生的數位範圍清單中，按一下名稱，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="34322-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="34322-113">按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="34322-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="34322-114">使用 Windows PowerShell 刪除未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="34322-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="34322-115">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="34322-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="34322-116">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="34322-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="34322-117">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="34322-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="34322-118">例如：</span><span class="sxs-lookup"><span data-stu-id="34322-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34322-119">如需更多選項的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">移除-CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="34322-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34322-120">請參閱</span><span class="sxs-lookup"><span data-stu-id="34322-120">See Also</span></span>


[<span data-ttu-id="34322-121">在 Lync Server 2013 中建立或修改未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="34322-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="34322-122">移除-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="34322-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="34322-123">CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="34322-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

