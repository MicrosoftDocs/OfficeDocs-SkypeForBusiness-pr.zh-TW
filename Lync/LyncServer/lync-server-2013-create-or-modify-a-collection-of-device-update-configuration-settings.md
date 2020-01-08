---
title: 建立或修改裝置更新設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改裝置更新設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用 Windows PowerShell 和**新的 CsDeviceUpdateConfiguration** Cmdlet 來建立裝置更新設定設定（僅限網站範圍），並使用**CsDeviceUpdateConfiguration** Cmdlet 加以修改。 這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>若要建立使用預設值的裝置更新設定設定

  - 這個命令會為雷德蒙的網站建立一組新的裝置更新設定設定：
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    因為在前面的命令中沒有指定強制身分識別參數以外的任何參數，所以新的配置設定集合會針對其所有屬性使用預設值。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>若要在建立裝置更新設定時變更單一屬性值

  - 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立裝置更新設定的集合，根據預設，每隔21天刪除舊的記錄檔案，請使用如下的命令：
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>若要在建立裝置更新設定時變更多個屬性值

  - 您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會將記錄清除間隔設定為21天，並將記錄的刷新間隔設為30分鐘：
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

如需有關修改現有裝置設定設定的詳細資訊，請參閱[CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) Cmdlet 的說明主題。 如需建立設定設定集合的詳細資料，請參閱適用于[CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

