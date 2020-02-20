---
title: 佈建要執行負載的拓撲
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b81708cbd518b43247c4324ecc651a4089c3ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>佈建要執行負載的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>佈建要執行負載的拓撲

根據您現有的設定和 Lync Server 2013 的設定，您可能需要在您的環境中進行下列變更：

1.  Windows PowerShell 執行原則設為 Unrestricted。 若要檢查您執行的原則設定，請開啟 [Lync Server 管理命令介面，並執行下列命令：

    ``` powershell
        Get-ExecutionPolicy
    ```        

    如果此命令不會傳回值沒有限制，請執行下列命令：

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  若要有效地設定 Lync Server 2013，您將需要：
    
      - 熟悉 Lync Server 2013 拓撲 （例如，電腦名稱、 服務執行個體、 網站名稱及原則）。
    
      - 例如群組 (例如，SIP Uri) 的回應群組搜尋，請將使用者至群組，所建立的部分。

3.  若要從命令列執行指令碼，您可能會使用：

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  一般而言，其中此套件執行，從指令碼的產生追蹤中的指令碼將會儲存在從中上次叫用指令碼的相同路徑中的檔案之後，名為\<scriptname\>$h$m$s.txt。 例如，下午 12:15 執行 ArchivingPolicy.ps1 將產生的記錄檔，例如 ArchivingPolicy121500.txt。

5.  最後，請注意，雖然我們所提供的範例，設定伺服器，但您負責修改或刪除組態完成執行負載之後。

</div>

</div>

<span> </span>

</div>

</div>

</div>

