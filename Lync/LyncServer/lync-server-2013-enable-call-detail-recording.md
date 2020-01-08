---
title: Lync Server 2013：啟用通話詳細資料錄製
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12359e331e9abd2767285a5ef8c32d56433731e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="93d12-102">啟用 Lync Server 2013 的通話詳細資料錄製</span><span class="sxs-lookup"><span data-stu-id="93d12-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93d12-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="93d12-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="93d12-104">通話詳細資料錄製（CDR）記錄對等活動的用法與診斷資訊，包括實例訊息、透過網際網路通訊協定（VoIP）通話、應用程式共用、檔案傳輸及會議。</span><span class="sxs-lookup"><span data-stu-id="93d12-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="93d12-105">使用資料可用來計算投資回報率（ROI），而診斷資料可用來針對對等活動和會議進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="93d12-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="93d12-106">使用下列程式可為您的整個組織或貴組織中的每個網站啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="93d12-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93d12-107">若要啟用 CDR，您必須設定監視及監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="93d12-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="93d12-108">如需詳細資訊，請參閱<A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監視</A>。</span><span class="sxs-lookup"><span data-stu-id="93d12-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="93d12-109">若要使用 Lync Server [控制台] 啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="93d12-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="93d12-110">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="93d12-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="93d12-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="93d12-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="93d12-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="93d12-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="93d12-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。</span><span class="sxs-lookup"><span data-stu-id="93d12-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="93d12-114">在 [**通話詳細資料記錄**] 頁面上，從表格中按一下適當的網站，按一下 [**動作**]，然後按一下 [**啟用 CDR**]。</span><span class="sxs-lookup"><span data-stu-id="93d12-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93d12-115">預設會啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="93d12-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="93d12-116">使用 Windows PowerShell Cmdlet 啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="93d12-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="93d12-117">您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="93d12-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="93d12-118">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="93d12-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="93d12-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="93d12-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="93d12-120">若要針對單一位置啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="93d12-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="93d12-121">若要停用 CDR，請將 EnableCDR 參數設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="93d12-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="93d12-122">若要針對單一位置停用 CDR</span><span class="sxs-lookup"><span data-stu-id="93d12-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="93d12-123">若要停用 CDR，請將 EnableCDR 參數設定為 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="93d12-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="93d12-124">停用 CDR 不會卸載監視。</span><span class="sxs-lookup"><span data-stu-id="93d12-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="93d12-125">它會暫停 CDR 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="93d12-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="93d12-126">若要使用單一命令在多個位置啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="93d12-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="93d12-127">這個命令會針對貴組織中目前使用的所有 CDR 配置設定啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="93d12-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="93d12-128">如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="93d12-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93d12-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="93d12-129">See Also</span></span>


[<span data-ttu-id="93d12-130">Lync Server 2013 中的規劃監控</span><span class="sxs-lookup"><span data-stu-id="93d12-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="93d12-131">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="93d12-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

