---
title: Lync Server 2013：刪除工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f3265591b1beb7180864b8e3a613989dfca397
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="a80e6-102">在 Lync Server 2013 中刪除工作流程</span><span class="sxs-lookup"><span data-stu-id="a80e6-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a80e6-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a80e6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a80e6-104">請使用下列其中一個程序來刪除工作流程：</span><span class="sxs-lookup"><span data-stu-id="a80e6-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="a80e6-105">使用 Lync Server 控制台刪除工作流程</span><span class="sxs-lookup"><span data-stu-id="a80e6-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="a80e6-106">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="a80e6-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a80e6-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a80e6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a80e6-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a80e6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a80e6-109">在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。</span><span class="sxs-lookup"><span data-stu-id="a80e6-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="a80e6-110">在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。</span><span class="sxs-lookup"><span data-stu-id="a80e6-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="a80e6-111">在 **[選取服務]** 搜尋欄位中，輸入裝載您要刪除之工作流程的 **ApplicationServer** 服務的部分或完整名稱。</span><span class="sxs-lookup"><span data-stu-id="a80e6-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="a80e6-112">在服務清單中，按一下所需的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a80e6-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a80e6-113">[回應群組設定工具] 網頁隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="a80e6-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="a80e6-114">您也可以連線到<STRONG>Https:// &lt; webPoolFqdn &gt; /RgsConfig</STRONG>，直接從網頁瀏覽器開啟回應群組設定工具網頁。</span><span class="sxs-lookup"><span data-stu-id="a80e6-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="a80e6-115">在 **[管理現有的工作流程]** 下，找出您要刪除的工作流程，然後按一下 **[執行]** 下的 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="a80e6-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="a80e6-116">按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="a80e6-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="a80e6-117">使用 Windows PowerShell 刪除工作流程</span><span class="sxs-lookup"><span data-stu-id="a80e6-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="a80e6-118">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="a80e6-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a80e6-119">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a80e6-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a80e6-120">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="a80e6-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="a80e6-121">例如：</span><span class="sxs-lookup"><span data-stu-id="a80e6-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

