---
title: Lync Server 2013：刪除通話駐留軌道範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 888c66150ffd371925f911d23d0d2b9171d0bf30
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="93010-102">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="93010-102">Delete a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93010-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="93010-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="93010-104">使用下列其中一個程式來刪除通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="93010-104">Use one of the following procedures to delete a Call Park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="93010-105">使用 Lync Server 控制台刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="93010-105">To use Lync Server Control Panel to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="93010-106">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="93010-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="93010-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="93010-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="93010-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="93010-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="93010-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="93010-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="93010-110">在左側導覽列中，依序按一下 **[語音功能]**、**[通話駐留]**。</span><span class="sxs-lookup"><span data-stu-id="93010-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="93010-111">在 [ **通話駐留** ] 頁面上的搜尋欄位中，輸入您要刪除之軌道範圍的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="93010-111">On the **Call Park** page, in the search field, type all or part of the name of the orbit range that you want to delete.</span></span>

5.  <span data-ttu-id="93010-112">在軌道的產生清單中，按一下軌道，然後按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="93010-112">In the resulting list of orbits, click the orbit, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="93010-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="93010-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="93010-114">使用 Windows PowerShell 刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="93010-114">To use Windows PowerShell to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="93010-115">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="93010-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="93010-116">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="93010-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="93010-117">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="93010-117">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    <span data-ttu-id="93010-118">例如：</span><span class="sxs-lookup"><span data-stu-id="93010-118">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93010-119">如需更多選項的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>。</span><span class="sxs-lookup"><span data-stu-id="93010-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93010-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93010-120">See Also</span></span>


[<span data-ttu-id="93010-121">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="93010-121">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="93010-122">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="93010-122">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="93010-123">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="93010-123">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

