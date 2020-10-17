---
title: Lync Server 2013：指定保留 CDR 資料
description: Lync Server 2013：指定保留 CDR 資料。
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
ms.openlocfilehash: d9367721a2390ad701702818590ac14e69da0df9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563399"
---
# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="94618-103">在 Lync Server 2013 中指定保留 CDR 資料</span><span class="sxs-lookup"><span data-stu-id="94618-103">Specifying retention of CDR data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94618-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="94618-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="94618-105">根據預設，[詳細通話記錄] (CDR) 資料會在60天之後清除。</span><span class="sxs-lookup"><span data-stu-id="94618-105">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="94618-106">您可以使用 [ **詳細通話記錄** ] 頁面上的設定，將資料保留較長或更短的時間週期。</span><span class="sxs-lookup"><span data-stu-id="94618-106">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="94618-107">如果您停用 CDR，啟用 CDR 之前所捕獲的資料也會受到清除。</span><span class="sxs-lookup"><span data-stu-id="94618-107">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94618-108">您應設定 CDR 和經驗品質 (QoE) 保留相同天數的資料。</span><span class="sxs-lookup"><span data-stu-id="94618-108">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="94618-109">「監控伺服器報告」頁面提供的 [通話詳細資料包告] 中的每個通話 (Cdr) ，包含 CDR 和 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="94618-109">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="94618-110">如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="94618-110">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="94618-111">使用下列程式可設定 CDR 資料的清除設定。</span><span class="sxs-lookup"><span data-stu-id="94618-111">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="94618-112">指定保留 CDR 資料</span><span class="sxs-lookup"><span data-stu-id="94618-112">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="94618-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="94618-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="94618-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="94618-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94618-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="94618-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="94618-116">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。</span><span class="sxs-lookup"><span data-stu-id="94618-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="94618-117">在 [ **詳細通話記錄** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="94618-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="94618-118">若要開啟清除，請選取 [ **啟用清除 cdr**]。</span><span class="sxs-lookup"><span data-stu-id="94618-118">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="94618-119">在 [ **保持 cdr 的最大持續期間 (天數) ：** 選取應該保留詳細通話記錄的最大天數。</span><span class="sxs-lookup"><span data-stu-id="94618-119">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="94618-120">在 [ **將錯誤報表的最大持續時間 (天數]) 中：** 選取應該保留錯誤報表的最大天數。</span><span class="sxs-lookup"><span data-stu-id="94618-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="94618-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="94618-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="94618-122">使用 Windows PowerShell Cmdlet 指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="94618-122">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="94618-123">您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。</span><span class="sxs-lookup"><span data-stu-id="94618-123">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="94618-124">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="94618-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="94618-125">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="94618-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="94618-126">指定特定位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="94618-126">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="94618-127">此命令可讓您清除 Redmond 網站的 CDR 資料，並將網站設定為維護 CDR 資料和錯誤報表資料的20天。</span><span class="sxs-lookup"><span data-stu-id="94618-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="94618-128">指定多個位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="94618-128">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="94618-129">此命令會針對組織中使用的所有 CDR 設定設定，設定 CDR 保留。</span><span class="sxs-lookup"><span data-stu-id="94618-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="94618-130">如需詳細資訊，請參閱 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="94618-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94618-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="94618-131">See Also</span></span>


[<span data-ttu-id="94618-132">Lync Server 2013 中的詳細通話記錄 (CDR) </span><span class="sxs-lookup"><span data-stu-id="94618-132">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

