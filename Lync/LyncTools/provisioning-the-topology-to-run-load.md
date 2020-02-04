---
title: 提供要執行負載的拓撲
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
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>提供要執行負載的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>提供要執行負載的拓撲

視 Lync Server 2013 的現有設定和配置而定，您可能需要在您的環境中進行下列變更：

1.  將 [Windows PowerShell 執行原則] 設定為 [無限制]。 若要檢查執行原則設定，請開啟 Lync Server 管理命令介面，然後執行下列命令：

    ``` powershell
        Get-ExecutionPolicy
    ```        

    如果這個命令沒有傳回無限制值，請執行此命令：

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  若要有效地設定 Lync Server 2013，您將需要：
    
      - 熟悉 Lync Server 2013 拓撲（例如，電腦名稱稱、服務實例、網站名稱及原則）。
    
      - 指派一些已建立至群組的使用者，例如回應群組查尋群組（例如 SIP Uri）。

3.  若要從命令列執行腳本，您可以使用：

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  通常，在此套件中的其中一個腳本執行之後，來自腳本的產生追蹤將會儲存在檔案中的相同路徑中，名為\<scriptname\>$h $ m $ s。 例如，在 12:15 P.M. 執行 ArchivingPolicy. ps1。 會產生一個記錄檔，例如 ArchivingPolicy121500。

5.  最後請注意，雖然我們提供了設定伺服器的範例，但您負責在執行完載入之後修改或刪除設定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

