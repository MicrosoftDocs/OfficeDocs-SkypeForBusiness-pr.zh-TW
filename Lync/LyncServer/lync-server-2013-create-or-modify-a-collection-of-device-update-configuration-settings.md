---
title: 建立或修改裝置更新配置設定的集合
description: 建立或修改裝置更新配置設定的集合。
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
ms.openlocfilehash: 593a1a0cb0f68254748ee48440cda18c78989780
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578269"
---
# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8d221-103">在 Lync Server 2013 中建立或修改裝置更新配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="8d221-103">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d221-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8d221-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8d221-105">您可以在網站範圍內建立裝置更新設定設定 (，只) 使用 Windows PowerShell 和 **New-CsDeviceUpdateConfiguration** Cmdlet，然後使用 **CsDeviceUpdateConfiguration 指令程式** 加以修改。</span><span class="sxs-lookup"><span data-stu-id="8d221-105">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="8d221-106">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8d221-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8d221-107">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="8d221-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="8d221-108">若要建立使用預設值的裝置更新設定</span><span class="sxs-lookup"><span data-stu-id="8d221-108">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="8d221-109">這個命令會為 Redmond 網站建立一組新的裝置更新配置設定：</span><span class="sxs-lookup"><span data-stu-id="8d221-109">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="8d221-110">由於前述的命令中未指定強制 Identity 參數以外的任何參數，因此新的設定集合會使用其所有屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="8d221-110">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="8d221-111">在建立裝置更新配置設定時變更單一屬性值</span><span class="sxs-lookup"><span data-stu-id="8d221-111">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="8d221-112">若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="8d221-112">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="8d221-113">例如，若要建立裝置更新設定的集合，根據預設，每隔21天刪除舊的記錄檔，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="8d221-113">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="8d221-114">在建立裝置更新設定設定時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="8d221-114">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="8d221-115">多項屬性值可透過加入多個參數加以修改。</span><span class="sxs-lookup"><span data-stu-id="8d221-115">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="8d221-116">例如，此命令會將記錄清除間隔設定為21天，記錄檔刷新間隔設定為30分鐘：</span><span class="sxs-lookup"><span data-stu-id="8d221-116">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="8d221-117">如需修改現有裝置設定設定的詳細資訊，請參閱 [CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) 指令程式的說明主題。</span><span class="sxs-lookup"><span data-stu-id="8d221-117">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="8d221-118">如需建立配置設定集合的詳細資訊，請參閱 [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="8d221-118">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

