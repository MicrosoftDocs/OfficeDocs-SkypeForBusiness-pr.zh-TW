---
title: Lync Server 2013：建立裝置以測試更新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b197c4b42542310746568fe351f98c7d991509cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>在 Lync Server 2013 中建立裝置以測試更新功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以將測試裝置新增至「測試裝置」**** 頁面，然後先使用此裝置來確認新更新的功能，再將更新部署至生產裝置。 您可以在整個 Lync Server 環境中，或在單一網站內，對裝置進行全域測試。 您是以裝置的媒體存取控制 (MAC) 位址或序號來識別測試裝置。 當您新增裝置時，它會出現在 Lync Server [控制台] 的 [**測試裝置**] 頁面上的清單中。

<div>

## <a name="to-add-a-test-device"></a>新增測試裝置

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**測試裝置**]。

3.  按一下 [**新增**]，然後按一下 [**全域測試裝置**] 或 [**網站測試裝置**]。

4.  請執行下列其中一項操作：
    
      - 如果您按一下 [**全域測試裝置**]，請跳到下一個步驟。
    
      - 如果您按一下 [**網站測試裝置**]，請從可用網站清單中選取網站，然後按一下 **[確定]**。

5.  在 [**新測試裝置**] 的 [**裝置名稱**] 中，輸入裝置的名稱。

6.  在 [**識別碼類型**] 下，按一下 [ **MAC 位址**] 或 [**序列值**]。

7.  在 [**唯一識別碼**] 方塊中，輸入裝置的 MAC 位址或序列值。

8.  按一下 [認可]****。

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立測試裝置

您可以使用 Windows PowerShell 和 CsTestDevice Cmdlet 來建立測試裝置。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

使用此 Cmdlet 建立測試裝置時，您必須執行兩個動作：

  - 將 MACAddress 或 SerialNumber 指定為 IdentifierType。

  - 指定裝置身分識別時包含範圍。 若要在全域範圍中建立新的裝置，請使用類似以下的語法：
    
        -Identity "global/WindowsPhone"
    
    若要在網站範圍建立測試裝置，請使用類似以下的語法：
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>使用 MAC 位址建立測試裝置

  - 這個命令會在全域作用中建立測試裝置，並使用 MAC 位址做為 IdentifierType：
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>使用序列值建立測試裝置

  - 這個命令會在網站範圍（針對雷德蒙的網站）建立新的測試裝置，並使用序列值做為 IdentifierType：
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

如需詳細資訊，請參閱[新版-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

