---
title: Lync Server 2013：啟用體驗品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="c4e76-102">啟用 Lync Server 2013 的體驗品質</span><span class="sxs-lookup"><span data-stu-id="c4e76-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4e76-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c4e76-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c4e76-104">經驗品質（QoE）會記錄數位資料，指出媒體質量與參與者的相關資訊、裝置名稱、驅動程式、IP 位址，以及通話和會話中所涉及的端點類型。</span><span class="sxs-lookup"><span data-stu-id="c4e76-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="c4e76-105">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃監視](lync-server-2013-planning-for-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e76-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="c4e76-106">使用下列程式為您的整個組織或貴組織中的每個網站啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="c4e76-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4e76-107">若要啟用 QoE，您必須先設定監視及監視後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c4e76-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="c4e76-108">如需詳細資訊，請參閱<A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監視</A>。</span><span class="sxs-lookup"><span data-stu-id="c4e76-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="c4e76-109">使用 Lync Server [控制台] 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c4e76-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c4e76-110">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c4e76-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="c4e76-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c4e76-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c4e76-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c4e76-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c4e76-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。</span><span class="sxs-lookup"><span data-stu-id="c4e76-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="c4e76-114">在 [**體驗品質資料**] 頁面上，按一下表格中的適當集合，按一下 [**動作**]，然後按一下 [**啟用 QoE**]。</span><span class="sxs-lookup"><span data-stu-id="c4e76-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c4e76-115">使用 Windows PowerShell Cmdlet 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c4e76-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c4e76-116">您可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 來啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="c4e76-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="c4e76-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c4e76-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c4e76-118">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="c4e76-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="c4e76-119">若要針對單一位置啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c4e76-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="c4e76-120">若要啟用 QoE，請將 EnableQoE 參數設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="c4e76-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="c4e76-121">針對單一位置停用 QoE</span><span class="sxs-lookup"><span data-stu-id="c4e76-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="c4e76-122">若要停用 QoE，請將 EnableQoE 參數設定為 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="c4e76-122">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="c4e76-123">這不會卸載監視。</span><span class="sxs-lookup"><span data-stu-id="c4e76-123">This does not uninstall monitoring.</span></span> <span data-ttu-id="c4e76-124">它會暫停 QoE 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="c4e76-124">It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="c4e76-125">若要在多個位置使用單一命令來啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c4e76-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="c4e76-126">這個命令會針對貴組織中目前使用的所有 QoE 設定設定啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="c4e76-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="c4e76-127">如需詳細資訊，請參閱[設定 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="c4e76-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4e76-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="c4e76-128">See Also</span></span>


[<span data-ttu-id="c4e76-129">Lync Server 2013 中的規劃監控</span><span class="sxs-lookup"><span data-stu-id="c4e76-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="c4e76-130">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="c4e76-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

