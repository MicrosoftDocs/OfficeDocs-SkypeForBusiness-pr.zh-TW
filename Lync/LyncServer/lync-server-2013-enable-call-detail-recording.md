---
title: Lync Server 2013：啟用詳細通話記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309d96d6aacd5409aa285ddeb4b95837ca98e302
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528790"
---
# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="0ecc8-102">在 Lync Server 2013 中啟用詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="0ecc8-102">Enable call detail recording in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ecc8-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0ecc8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0ecc8-p101">詳細通話記錄 (CDR) 會記錄對等活動 (包括立即訊息、VoIP 電話、應用程式共用、檔案傳輸和會議) 的使用方式與診斷資訊。使用方式資料可以用來計算投資報酬率 (ROI)，而診斷資料則可用來排解對等活動和會議的疑難問題。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="0ecc8-106">使用下列程序來為整個組織或組織內的個別網站啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ecc8-107">如要啟用 CDR，您必須設定監控及監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="0ecc8-108">如需詳細資訊，請參閱 <A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監控</A>。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="0ecc8-109">使用 Lync Server 控制台啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="0ecc8-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0ecc8-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0ecc8-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0ecc8-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0ecc8-113">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="0ecc8-114">在 **[詳細通話記錄]** 頁面上，依序按一下表格中的適當網站、**[動作]** 和 **[啟用 CDR]**。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ecc8-115">預設會啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0ecc8-116">使用 Windows PowerShell Cmdlet 啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="0ecc8-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0ecc8-117">您可以使用 Windows PowerShell 和 **Set-CsCdrConfiguration** Cmdlet 來啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="0ecc8-118">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0ecc8-119">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="0ecc8-120">針對單一位置啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="0ecc8-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="0ecc8-121">如要停用 CDR，請將 EnableCDR 參數設為 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="0ecc8-122">針對單一位置停用 CDR</span><span class="sxs-lookup"><span data-stu-id="0ecc8-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="0ecc8-123">如要停用 CDR，請將 EnableCDR 參數設為 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="0ecc8-124">停用 CDR 不會卸載監控。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="0ecc8-125">它會暫停 CDR 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="0ecc8-126">使用單一命令啟用多個位置的 CDR</span><span class="sxs-lookup"><span data-stu-id="0ecc8-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="0ecc8-127">以下命令會啟用組織中所有目前正在使用之 CDR 組態設定的 CDR。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="0ecc8-128">如需詳細資訊，請參閱 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ecc8-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ecc8-129">See Also</span></span>


[<span data-ttu-id="0ecc8-130">在 Lync Server 2013 中規劃監控</span><span class="sxs-lookup"><span data-stu-id="0ecc8-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="0ecc8-131">在 Lync Server 2013 中部署監控</span><span class="sxs-lookup"><span data-stu-id="0ecc8-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

