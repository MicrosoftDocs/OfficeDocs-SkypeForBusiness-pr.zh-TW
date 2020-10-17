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
ms.openlocfilehash: bbf4d45edce186819241ce6244e1ea1cd6677bfa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501970"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>在 Lync Server 2013 中建立裝置以測試更新功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以將測試裝置新增至 [ **測試裝置** ] 頁面，然後使用此裝置來確認新更新的功能，再將更新部署至實際執行裝置。 您可以在整個 Lync Server 環境) 或單一網站內，測試裝置全域 (。 您可以透過媒體存取控制來識別測試裝置 (MAC) 位址或序號。 當您新增裝置時，它會出現在 Lync Server 控制台的 [ **測試裝置** ] 頁面上的清單中。

<div>

## <a name="to-add-a-test-device"></a>新增測試裝置

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **測試裝置**]。

3.  按一下 [ **新增**]，然後按一下 [ **全域測試裝置** ] 或 [ **網站測試裝置**]。

4.  執行下列其中一項：
    
      - 如果您已按一下 [ **全域測試裝置**]，請跳至下一個步驟。
    
      - 如果您按一下 [ **網站測試裝置**]，請從可用網站清單中選取網站，然後按一下 **[確定]**。

5.  在 [ **新增測試裝置**] 的 [ **裝置名稱**] 中，輸入裝置的名稱。

6.  在 [ **識別碼類型**] 底下，按一下 [ **MAC 位址** 或 **序列碼**]。

7.  在 [ **唯一識別碼** ] 方塊中，輸入裝置的 MAC 位址或序號。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立測試裝置

您可以使用 Windows PowerShell 和 New-CsTestDevice Cmdlet 來建立測試裝置。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

使用此 Cmdlet 建立測試裝置時，您必須執行下列兩項作業：

  - 請以 IdentifierType 的形式指定 MACAddress 或 SerialNumber。

  - 指定裝置身分識別時包含範圍。 若要在全域範圍內建立新的裝置，請使用類似下列的語法：
    
        -Identity "global/WindowsPhone"
    
    若要在網站範圍建立測試裝置，請使用類似下列的語法：
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>使用 MAC 位址建立測試裝置

  - 這個命令會在全域範圍中建立測試裝置，並使用 MAC 位址做為 IdentifierType：
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>使用序號建立測試裝置

  - 這個命令會在 Redmond 網站) 的網站範圍 (建立新的測試裝置，並使用序數做為 IdentifierType：
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

如需詳細資訊，請參閱 [CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

