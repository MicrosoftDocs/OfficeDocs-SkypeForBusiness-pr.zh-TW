---
title: Lync Server 2013：啟用經驗品質
description: Lync Server 2013：啟用經驗品質。
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
ms.openlocfilehash: 43746227395477596ff5e39809cf819c110287ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547869"
---
# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="51da3-103">在 Lync Server 2013 中啟用經驗品質</span><span class="sxs-lookup"><span data-stu-id="51da3-103">Enable Quality of Experience in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51da3-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="51da3-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="51da3-105">經驗品質 (QoE) 會記錄數字資料，指出有關通話與工作階段中所包含參與者、裝置名稱、驅動程式、IP 位址和端點類型的媒體品質和資訊。</span><span class="sxs-lookup"><span data-stu-id="51da3-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="51da3-106">如需詳細資訊，請參閱規劃檔中的 [規劃在 Lync Server 2013 中的監視](lync-server-2013-planning-for-monitoring.md) 。</span><span class="sxs-lookup"><span data-stu-id="51da3-106">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="51da3-107">請使用下列程式，為您的整個組織或組織中的每個網站啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="51da3-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51da3-108">若要啟用 QoE，您必須先設定監控和監控後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="51da3-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="51da3-109">如需詳細資訊，請參閱 <A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監控</A>。</span><span class="sxs-lookup"><span data-stu-id="51da3-109">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="51da3-110">使用 Lync Server 控制台啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="51da3-110">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="51da3-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="51da3-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="51da3-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="51da3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="51da3-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="51da3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="51da3-114">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="51da3-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="51da3-115">在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當集合，按一下 [ **動作**]，然後按一下 [ **啟用 QoE**]。</span><span class="sxs-lookup"><span data-stu-id="51da3-115">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="51da3-116">使用 Windows PowerShell Cmdlet 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="51da3-116">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="51da3-117">您可以使用 Windows PowerShell 及 **Set CsQoEConfiguration** Cmdlet 來啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="51da3-117">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="51da3-118">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51da3-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="51da3-119">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="51da3-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="51da3-120">針對單一位置啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="51da3-120">To enable QoE for a single location</span></span>

  - <span data-ttu-id="51da3-121">若要啟用 QoE，請將 EnableQoE 參數設定為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="51da3-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="51da3-122">停用單一位置的 QoE</span><span class="sxs-lookup"><span data-stu-id="51da3-122">To disable QoE for a single location</span></span>

  - <span data-ttu-id="51da3-123">若要停用 QoE，請將 EnableQoE 參數設定為 False ($False) 。</span><span class="sxs-lookup"><span data-stu-id="51da3-123">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="51da3-124">這不會卸載監控。</span><span class="sxs-lookup"><span data-stu-id="51da3-124">This does not uninstall monitoring.</span></span> <span data-ttu-id="51da3-125">它會暫停 QoE 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="51da3-125">It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="51da3-126">使用單一命令啟用多個位置的 QoE</span><span class="sxs-lookup"><span data-stu-id="51da3-126">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="51da3-127">此命令會為組織中目前使用的所有 QoE 設定設定啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="51da3-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="51da3-128">如需詳細資訊，請參閱 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="51da3-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51da3-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="51da3-129">See Also</span></span>


[<span data-ttu-id="51da3-130">在 Lync Server 2013 中規劃監控</span><span class="sxs-lookup"><span data-stu-id="51da3-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="51da3-131">在 Lync Server 2013 中部署監控</span><span class="sxs-lookup"><span data-stu-id="51da3-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

