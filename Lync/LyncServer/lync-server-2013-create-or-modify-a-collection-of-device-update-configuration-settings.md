---
title: 建立或修改裝置更新配置設定的集合
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
ms.openlocfilehash: a1cba65da0e8c1e01c5cf5666b13b98cc2009baf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改裝置更新配置設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以在網站範圍內建立裝置更新設定設定 (，只) 使用 Windows PowerShell 和 **New-CsDeviceUpdateConfiguration** Cmdlet，然後使用 **CsDeviceUpdateConfiguration 指令程式** 加以修改。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。

<div>


> [!NOTE]
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>若要建立使用預設值的裝置更新設定

  - 這個命令會為 Redmond 網站建立一組新的裝置更新配置設定：
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    由於前述的命令中未指定強制 Identity 參數以外的任何參數，因此新的設定集合會使用其所有屬性的預設值。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>在建立裝置更新配置設定時變更單一屬性值

  - 若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。 例如，若要建立裝置更新設定的集合，根據預設，每隔21天刪除舊的記錄檔，請使用類似下列的命令：
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>在建立裝置更新設定設定時變更多個屬性值

  - 多項屬性值可透過加入多個參數加以修改。 例如，此命令會將記錄清除間隔設定為21天，記錄檔刷新間隔設定為30分鐘：
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

如需修改現有裝置設定設定的詳細資訊，請參閱 [CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) 指令程式的說明主題。 如需建立配置設定集合的詳細資訊，請參閱 [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

