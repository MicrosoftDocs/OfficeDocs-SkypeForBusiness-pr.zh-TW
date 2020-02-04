---
title: Lync Server 2013：刪除存檔設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4a0c1acf9f605fc927d7006ff50b1f4470c68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="e8651-102">在 Lync Server 2013 中刪除封存配置</span><span class="sxs-lookup"><span data-stu-id="e8651-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8651-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e8651-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e8651-104">您可以刪除網站配置或池設定。</span><span class="sxs-lookup"><span data-stu-id="e8651-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="e8651-105">無法移除全域配置。</span><span class="sxs-lookup"><span data-stu-id="e8651-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="e8651-106">如果您刪除全域設定，系統會自動將其重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="e8651-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="e8651-107">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="e8651-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="e8651-108">刪除網站或池配置以進行封存</span><span class="sxs-lookup"><span data-stu-id="e8651-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="e8651-109">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e8651-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8651-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e8651-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8651-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e8651-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8651-112">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="e8651-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="e8651-113">在封存配置清單中，按一下您要刪除的網站或池設定，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e8651-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e8651-114">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e8651-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8651-115">使用 Windows PowerShell Cmdlet 移除封存配置設定</span><span class="sxs-lookup"><span data-stu-id="e8651-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8651-116">您可以使用 Windows PowerShell 與**Remove CsArchivingConfiguration** Cmdlet 來刪除封存配置設定。</span><span class="sxs-lookup"><span data-stu-id="e8651-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="e8651-117">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="e8651-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e8651-118">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e8651-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="e8651-119">移除指定的封存配置設定集合</span><span class="sxs-lookup"><span data-stu-id="e8651-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="e8651-120">下列命令會移除套用至雷德蒙者網站的存檔設定設定：</span><span class="sxs-lookup"><span data-stu-id="e8651-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="e8651-121">若要移除所有套用至網站範圍的存檔設定</span><span class="sxs-lookup"><span data-stu-id="e8651-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="e8651-122">這個命令會移除所有套用至服務範圍的存檔設定：</span><span class="sxs-lookup"><span data-stu-id="e8651-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="e8651-123">根據指定的屬性值移除封存配置設定</span><span class="sxs-lookup"><span data-stu-id="e8651-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="e8651-124">這個命令會移除 Exchange 封存已停用的所有封存設定設定：</span><span class="sxs-lookup"><span data-stu-id="e8651-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="e8651-125">如需詳細資訊，請參閱[Remove CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="e8651-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8651-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="e8651-126">See Also</span></span>


[<span data-ttu-id="e8651-127">存檔在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="e8651-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="e8651-128">在 Lync Server 2013 中管理內部和外部通訊的存檔</span><span class="sxs-lookup"><span data-stu-id="e8651-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

