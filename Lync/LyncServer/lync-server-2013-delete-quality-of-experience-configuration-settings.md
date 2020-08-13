---
title: Lync Server 2013：刪除經驗品質設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2a3d9b8907d888f7edbd65c550315dfabe3306
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bb669-102">在 Lync Server 2013 中刪除經驗品質設定設定</span><span class="sxs-lookup"><span data-stu-id="bb669-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb669-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bb669-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bb669-p101">「經驗品質 (QoE)」計量在追蹤組織中進行之音訊和視訊通話的品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 等項目的數量。這些計量會儲存在與其他資料 (例如詳細通話記錄) 不同的資料庫中，讓您可獨立於其他資料記錄來啟用和停用 QoE。</span><span class="sxs-lookup"><span data-stu-id="bb669-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="bb669-106">當您安裝 Microsoft Lync Server 2013 時，會為您建立單一、全域的 QoE 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="bb669-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="bb669-107">系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。</span><span class="sxs-lookup"><span data-stu-id="bb669-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="bb669-108">根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="bb669-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="bb669-109">如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 QoE。</span><span class="sxs-lookup"><span data-stu-id="bb669-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="bb669-110">請注意，您也可以「刪除」全域設定。</span><span class="sxs-lookup"><span data-stu-id="bb669-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="bb669-111">不過，全域設定實際上不會被移除。</span><span class="sxs-lookup"><span data-stu-id="bb669-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="bb669-112">相反地，該集合中的所有屬性都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="bb669-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="bb669-113">例如，預設會在 QoE 設定設定的集合中啟用清除。</span><span class="sxs-lookup"><span data-stu-id="bb669-113">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="bb669-114">假設您修改全域集合以停用清除。</span><span class="sxs-lookup"><span data-stu-id="bb669-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="bb669-115">如果您稍後刪除全域設定，所有屬性都會重設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="bb669-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="bb669-116">在此情況下，這表示會再次啟用清除。</span><span class="sxs-lookup"><span data-stu-id="bb669-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="bb669-117">您可以使用 Lync Server 控制台或使用[Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) Cmdlet 來移除 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="bb669-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="bb669-118">使用 Lync Server 控制台刪除 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="bb669-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bb669-119">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="bb669-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bb669-120">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="bb669-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bb669-121">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bb669-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb669-122">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bb669-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bb669-123">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="bb669-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="bb669-124">在 [**經驗品質資料**] 頁面上，按一下您要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bb669-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="bb669-125">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb669-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bb669-126">使用 Windows PowerShell Cmdlet 移除 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="bb669-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bb669-127">您可以使用 Windows PowerShell 和**Remove-CsQoEConfiguration** Cmdlet 刪除 QoE 的設定設定。</span><span class="sxs-lookup"><span data-stu-id="bb669-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="bb669-128">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bb669-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bb669-129">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="bb669-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="bb669-130">移除指定的 QoE 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="bb669-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="bb669-131">此命令會移除套用至 Redmond 網站的 QoE 設定：</span><span class="sxs-lookup"><span data-stu-id="bb669-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="bb669-132">若要移除所有套用至網站範圍的 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="bb669-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="bb669-133">此命令會移除所有套用至網站範圍的 QoE 設定設定：</span><span class="sxs-lookup"><span data-stu-id="bb669-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="bb669-134">移除所有停用 QoE 監控的 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="bb669-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="bb669-135">這個命令會移除所有已停用 QoE 監控的 QoE 設定設定：</span><span class="sxs-lookup"><span data-stu-id="bb669-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="bb669-136">如需詳細資訊，請參閱[Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="bb669-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

