---
title: Lync Server 2013：指定保留 CDR 資料的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="221d4-102">在 Lync Server 2013 中指定 CDR 資料的保留</span><span class="sxs-lookup"><span data-stu-id="221d4-102">Specifying retention of CDR data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="221d4-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="221d4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="221d4-104">根據預設，通話詳細資料錄製（CDR）資料會在60天之後清除。</span><span class="sxs-lookup"><span data-stu-id="221d4-104">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="221d4-105">您可以使用 [**通話詳細資料記錄**] 頁面上的設定，將資料保留較長或較短的時間週期。</span><span class="sxs-lookup"><span data-stu-id="221d4-105">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="221d4-106">如果您停用 CDR，在啟用 CDR 之前捕獲的資料，也會受到清除。</span><span class="sxs-lookup"><span data-stu-id="221d4-106">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="221d4-107">您應該設定 CDR 和體驗品質（QoE），以保留相同天數的資料。</span><span class="sxs-lookup"><span data-stu-id="221d4-107">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="221d4-108">[監視伺服器報告] 頁面提供的呼叫詳細資料包告（CDRs）中的每個通話，包括 CDR 和 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="221d4-108">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="221d4-109">如果 CDR 與 QoE 的清除持續時間不一樣，有些通話可能只會包含 CDR 資料，而其他可能只包含 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="221d4-109">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="221d4-110">使用下列程式來設定 CDR 資料的清除設定。</span><span class="sxs-lookup"><span data-stu-id="221d4-110">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="221d4-111">指定保留 CDR 資料</span><span class="sxs-lookup"><span data-stu-id="221d4-111">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="221d4-112">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="221d4-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="221d4-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="221d4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="221d4-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="221d4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="221d4-115">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。</span><span class="sxs-lookup"><span data-stu-id="221d4-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="221d4-116">在 [**通話詳細資料記錄**] 頁面上，按一下表格中的適當網站，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="221d4-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="221d4-117">若要開啟清除，請選取 [**啟用清除 CDRs**]。</span><span class="sxs-lookup"><span data-stu-id="221d4-117">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="221d4-118">在 **[保留 CDRs 的最大持續時間（天數）** ] 中：選取應保留通話詳細資料錄製的最大天數。</span><span class="sxs-lookup"><span data-stu-id="221d4-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="221d4-119">若要在**最大持續時間（天）內保留錯誤報表資料：** 請選取要保留錯誤報表的最大天數。</span><span class="sxs-lookup"><span data-stu-id="221d4-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="221d4-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="221d4-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="221d4-121">使用 Windows PowerShell Cmdlet 指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="221d4-121">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="221d4-122">您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。</span><span class="sxs-lookup"><span data-stu-id="221d4-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="221d4-123">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="221d4-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="221d4-124">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="221d4-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="221d4-125">針對特定位置指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="221d4-125">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="221d4-126">這個命令可讓您清除雷德蒙網站的 CDR 資料，並將網站設定為維持 CDR 資料，以及20天的錯誤報表資料。</span><span class="sxs-lookup"><span data-stu-id="221d4-126">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="221d4-127">若要為多個位置指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="221d4-127">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="221d4-128">這個命令會針對組織中使用的所有 CDR 配置設定，設定 CDR 保留。</span><span class="sxs-lookup"><span data-stu-id="221d4-128">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="221d4-129">如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="221d4-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="221d4-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="221d4-130">See Also</span></span>


[<span data-ttu-id="221d4-131">在 Lync Server 2013 中呼叫詳細資料錄製（CDR）</span><span class="sxs-lookup"><span data-stu-id="221d4-131">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

