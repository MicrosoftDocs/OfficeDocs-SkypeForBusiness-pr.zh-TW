---
title: Lync Server 2013：刪除裝置更新設定的集合
description: Lync Server 2013：刪除裝置更新設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a03227869f68a52a30ea94db33bfb954b7e122
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566649"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1c365-103">在 Lync Server 2013 中刪除裝置更新設定的集合</span><span class="sxs-lookup"><span data-stu-id="1c365-103">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c365-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1c365-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1c365-105">您也可以使用 Windows PowerShell 和 **CsdeviceUpdateConfiguration** Cmdlet 來刪除裝置更新設定設定。</span><span class="sxs-lookup"><span data-stu-id="1c365-105">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="1c365-106">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1c365-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1c365-107">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="1c365-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="1c365-108">移除裝置更新設定的特定集合</span><span class="sxs-lookup"><span data-stu-id="1c365-108">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="1c365-109">此命令會刪除套用至 Redmond 網站的裝置更新設定設定：</span><span class="sxs-lookup"><span data-stu-id="1c365-109">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="1c365-110">移除所有套用至網站範圍的裝置更新設定設定</span><span class="sxs-lookup"><span data-stu-id="1c365-110">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="1c365-111">這個命令會刪除所有套用至網站範圍的裝置更新設定：</span><span class="sxs-lookup"><span data-stu-id="1c365-111">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="1c365-112">若要移除以 LogCleanUpInterval 屬性值為基礎的裝置更新配置設定</span><span class="sxs-lookup"><span data-stu-id="1c365-112">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="1c365-113">下列命令會刪除所有在10天 (10.00：00： 00) 上超過10天的裝置更新設定設定。</span><span class="sxs-lookup"><span data-stu-id="1c365-113">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="1c365-114">如需詳細資訊，請參閱 [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="1c365-114">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

