---
title: Lync Server 2013：刪除裝置更新記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685b3e34c0f2bd5392f71899564d0738e814b616
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中刪除裝置更新記錄檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

裝置更新 Web 服務會保留大量的記錄檔集合。 此集合包含服務本身所執行的審計記錄，以及從用戶端裝置上傳的記錄檔。 若要防止伺服器填滿裝置更新 Web 服務記錄，您可能會想要清除已有特定天數的記錄檔。 根據您組織中的更新活動和用戶端裝置數目，以及使用 Lync Server 控制台或 Lync Server 管理命令介面，來設定此天數。

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台清除裝置更新記錄檔

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置記錄**檔設定]。

3.  在 [**裝置記錄**檔設定] 頁面上，按兩下您要變更的設定。

4.  在 [**編輯記錄檔設定**] 對話方塊中，將**記錄檔的保留天數 (1-365) **中，指定天數。

5.  按一下 **[認可]**。 伺服器上已超過指定天數的所有檔案都會被刪除。 此設定會套用至此設定，直到您變更。

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 清除裝置更新記錄檔

您可以使用 Windows PowerShell 和**CsDeviceUpdateLog** Cmdlet 來清除裝置更新記錄。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>在一部伺服器上清除裝置更新記錄檔

  - 下列命令會清除網頁伺服器 atl-cs-001.litwareinc.com 上的裝置更新記錄檔。 所有記錄專案超過10天的 (會從記錄中移除 DaysBack 參數) 所指定的值。
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>清除所有裝置更新記錄檔

  - 此命令會移除過期的專案 (在此範例中，會從目前在組織中使用的所有裝置更新記錄檔中，輸入超過10天的舊) 。
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

如需詳細資訊，請參閱 Help 主題 for the [CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) Cmdlet。

</div>

</div>

<span> </span>

</div>

</div>

</div>

