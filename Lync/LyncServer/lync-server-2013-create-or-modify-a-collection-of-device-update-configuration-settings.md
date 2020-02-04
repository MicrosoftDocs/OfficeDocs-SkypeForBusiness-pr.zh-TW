---
title: 建立或修改裝置更新設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e550f48e37ab9c225e5a4919cbc65a13fe09e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c2dd2-102">在 Lync Server 2013 中建立或修改裝置更新設定的集合</span><span class="sxs-lookup"><span data-stu-id="c2dd2-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2dd2-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c2dd2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c2dd2-104">您可以使用 Windows PowerShell 和**新的 CsDeviceUpdateConfiguration** Cmdlet 來建立裝置更新設定設定（僅限網站範圍），並使用**CsDeviceUpdateConfiguration** Cmdlet 加以修改。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="c2dd2-105">這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c2dd2-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="c2dd2-107">若要建立使用預設值的裝置更新設定設定</span><span class="sxs-lookup"><span data-stu-id="c2dd2-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="c2dd2-108">這個命令會為雷德蒙的網站建立一組新的裝置更新設定設定：</span><span class="sxs-lookup"><span data-stu-id="c2dd2-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="c2dd2-109">因為在前面的命令中沒有指定強制身分識別參數以外的任何參數，所以新的配置設定集合會針對其所有屬性使用預設值。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="c2dd2-110">若要在建立裝置更新設定時變更單一屬性值</span><span class="sxs-lookup"><span data-stu-id="c2dd2-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="c2dd2-111">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="c2dd2-112">例如，若要建立裝置更新設定的集合，根據預設，每隔21天刪除舊的記錄檔案，請使用如下的命令：</span><span class="sxs-lookup"><span data-stu-id="c2dd2-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="c2dd2-113">若要在建立裝置更新設定時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="c2dd2-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="c2dd2-114">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="c2dd2-115">例如，這個命令會將記錄清除間隔設定為21天，並將記錄的刷新間隔設為30分鐘：</span><span class="sxs-lookup"><span data-stu-id="c2dd2-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="c2dd2-116">如需有關修改現有裝置設定設定的詳細資訊，請參閱[CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="c2dd2-117">如需建立設定設定集合的詳細資料，請參閱適用于[CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="c2dd2-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

