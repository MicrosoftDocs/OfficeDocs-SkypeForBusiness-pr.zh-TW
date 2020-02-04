---
title: Lync Server 2013：刪除裝置更新設定的集合
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
ms.openlocfilehash: 936a591ea46c6b599a9a72f06a9287be35e66cce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中刪除裝置更新設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您也可以使用 Windows PowerShell 與**Remove CsdeviceUpdateConfiguration** Cmdlet 來刪除裝置更新設定設定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>移除裝置更新設定的特定集合

  - 這個命令會刪除套用至雷德蒙者網站的裝置更新設定設定：
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>若要移除所有已套用至網站範圍的裝置更新設定設定

  - 這個命令會刪除所有適用于網站範圍的裝置更新設定設定：
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>根據 LogCleanUpInterval 屬性的值移除裝置更新設定設定

  - 下列命令會刪除日誌清除間隔超過10天（10.00：00：00）的所有裝置更新設定設定。
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

如需詳細資訊，請參閱[Remove CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

