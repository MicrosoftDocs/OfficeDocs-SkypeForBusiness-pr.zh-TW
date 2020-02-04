---
title: Lync Server 2013：修改體驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2cf4745f76fa4667d14c9da5ca2b4e5309767b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="d7664-102">在 Lync Server 2013 中修改體驗品質設定</span><span class="sxs-lookup"><span data-stu-id="d7664-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7664-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d7664-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d7664-104">根據預設，經驗品質（QoE）資料會在60天之後清除。</span><span class="sxs-lookup"><span data-stu-id="d7664-104">By default, Quality of Experience (QoE) data is purged after 60 days.</span></span> <span data-ttu-id="d7664-105">您可以使用 [**體驗資料品質**] 頁面上的設定，將資料保留較長或較短的時間週期。</span><span class="sxs-lookup"><span data-stu-id="d7664-105">You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="d7664-106">如果您停用 QoE，則在啟用 QoE 之前捕獲的資料也會受到清除。</span><span class="sxs-lookup"><span data-stu-id="d7664-106">If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d7664-107">您應該設定 [通話詳細資料錄製（CDR）] 和 [QoE]，以保留相同天數的資料。</span><span class="sxs-lookup"><span data-stu-id="d7664-107">You should configure call detail recording (CDR) and QoE to retain data for the same number of days.</span></span> <span data-ttu-id="d7664-108">[監視報告] 首頁提供的呼叫詳細資料包告（CDRs）中的每個通話都包含 CDR 和 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="d7664-108">Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information.</span></span> <span data-ttu-id="d7664-109">如果 [CDR] 和 [QoE] 的清除持續時間不一樣，有些通話可能只會包含 CDR 資料，而其他可能只包含 QoE 的資料。</span><span class="sxs-lookup"><span data-stu-id="d7664-109">If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="d7664-110">下列程式說明如何設定 QoE 資料的清除設定。</span><span class="sxs-lookup"><span data-stu-id="d7664-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="d7664-111">使用 Lync Server [控制台] 來指定 QoE 資料的保留</span><span class="sxs-lookup"><span data-stu-id="d7664-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d7664-112">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d7664-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d7664-113">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d7664-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d7664-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d7664-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d7664-115">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d7664-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d7664-116">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。</span><span class="sxs-lookup"><span data-stu-id="d7664-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="d7664-117">在 [**體驗品質資料**] 頁面上，從表格中按一下適當的網站，按一下 [**編輯**]，然後按一下 [**顯示詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="d7664-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="d7664-118">若要開啟清除，請選取 [**啟用清除 QoE**]。</span><span class="sxs-lookup"><span data-stu-id="d7664-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="d7664-119">在 **[保留 QoE 的最大持續時間（天數）** ] 中，選取 QoE 資料應保留的最大天數。</span><span class="sxs-lookup"><span data-stu-id="d7664-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="d7664-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d7664-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d7664-121">使用 Windows PowerShell Cmdlet 指定 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="d7664-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d7664-122">您可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 來建立 QoE 保留設定。</span><span class="sxs-lookup"><span data-stu-id="d7664-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="d7664-123">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d7664-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d7664-124">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d7664-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="d7664-125">若要指定特定位置的 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="d7664-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="d7664-126">這個命令可讓您清除雷德蒙網站的 QoE 資料，並將該網站設定為維護20天的 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="d7664-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="d7664-127">若要指定多個位置的 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="d7664-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="d7664-128">這個命令會針對組織中使用的所有 QoE 設定設定，設定 QoE 保留。</span><span class="sxs-lookup"><span data-stu-id="d7664-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="d7664-129">如需詳細資訊，請參閱[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d7664-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7664-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="d7664-130">See Also</span></span>


[<span data-ttu-id="d7664-131">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="d7664-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

