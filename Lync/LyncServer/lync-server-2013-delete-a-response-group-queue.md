---
title: Lync Server 2013：刪除回應群組佇列
description: Lync Server 2013：刪除回應群組佇列。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b00257a12b872615ebc124abff595268b120e1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553719"
---
# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="5cb90-103">在 Lync Server 2013 中刪除回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="5cb90-103">Delete a Response Group queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cb90-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5cb90-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5cb90-105">使用下列其中一個程序刪除佇列。</span><span class="sxs-lookup"><span data-stu-id="5cb90-105">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="5cb90-106">使用 Lync Server 控制台刪除佇列</span><span class="sxs-lookup"><span data-stu-id="5cb90-106">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="5cb90-107">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="5cb90-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="5cb90-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5cb90-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5cb90-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5cb90-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5cb90-110">在左導覽列中，按一下 **[回應群組]**，然後按一下 **[佇列]**。</span><span class="sxs-lookup"><span data-stu-id="5cb90-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="5cb90-111">在 [搜尋] 欄位中，輸入想要刪除之佇列的部分或全部名稱。</span><span class="sxs-lookup"><span data-stu-id="5cb90-111">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="5cb90-112">在佇列清單中，按一下想要的佇列，並按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="5cb90-112">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="5cb90-113">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5cb90-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="5cb90-114">使用 Windows PowerShell 刪除佇列</span><span class="sxs-lookup"><span data-stu-id="5cb90-114">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="5cb90-115">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="5cb90-115">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="5cb90-116">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="5cb90-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5cb90-117">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="5cb90-117">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="5cb90-118">例如：</span><span class="sxs-lookup"><span data-stu-id="5cb90-118">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

