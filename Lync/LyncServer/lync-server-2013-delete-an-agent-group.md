---
title: Lync Server 2013：刪除代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcdc0245f6fdd835492084fcae91389409f52c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="7c4cf-102">刪除 Lync Server 2013 中的代理群組</span><span class="sxs-lookup"><span data-stu-id="7c4cf-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c4cf-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7c4cf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7c4cf-104">使用下列其中一個程式來刪除 [代理程式] 群組。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="7c4cf-105">若要使用 Lync Server [控制台] 刪除代理群組</span><span class="sxs-lookup"><span data-stu-id="7c4cf-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="7c4cf-106">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="7c4cf-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7c4cf-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7c4cf-109">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="7c4cf-110">在 [**回應群組**] 頁面上，在 [搜尋] 欄位中輸入您要刪除之 agent 群組的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="7c4cf-111">在產生的清單中，按一下您要刪除的群組，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="7c4cf-112">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="7c4cf-113">使用 Windows PowerShell 刪除代理群組</span><span class="sxs-lookup"><span data-stu-id="7c4cf-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="7c4cf-114">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="7c4cf-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="7c4cf-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7c4cf-116">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="7c4cf-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="7c4cf-117">例如：</span><span class="sxs-lookup"><span data-stu-id="7c4cf-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c4cf-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="7c4cf-118">See Also</span></span>


[<span data-ttu-id="7c4cf-119">在 Lync Server 2013 中建立或修改代理群組</span><span class="sxs-lookup"><span data-stu-id="7c4cf-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="7c4cf-120">移除-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7c4cf-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="7c4cf-121">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="7c4cf-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

