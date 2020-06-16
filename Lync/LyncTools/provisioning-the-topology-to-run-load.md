---
title: 布建要執行負載的拓撲
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3e08a66397e5c6e7fb5b6111fbdcf6d11d3632a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>布建要執行負載的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>布建要執行負載的拓撲

根據您現有的 Lync Server 2013 設定和設定，您可能需要在您的環境中進行下列變更：

1.  設定 Windows PowerShell 執行原則為無限制。 若要檢查您的執行原則設定，請開啟 Lync Server 管理命令介面，並執行下列命令：

    ``` powershell
        Get-ExecutionPolicy
    ```        

    如果此命令不會傳回無限制的值，請執行下列命令：

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  若要有效地設定 Lync Server 2013，您將需要：
    
      - 熟悉 Lync Server 2013 拓撲（例如，電腦名稱稱、服務實例、網站名稱和原則）。
    
      - 將一些已建立的使用者指派給群組，例如回應群組搜尋群組（例如，SIP URIs）。

3.  若要從命令列執行腳本，您可以使用：

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  在此套件中的其中一個腳本執行完畢之後，腳本所產生的追蹤將會儲存在用來呼叫腳本的相同路徑中，名為 \<scriptname\> $h $ m $s.txt。 例如，在 12:15 P.M. 執行 ArchivingPolicy.ps1。 會產生記錄檔，例如 ArchivingPolicy121500.txt。

5.  最後，請注意，雖然我們提供了設定伺服器的範例，但您會在完成執行負載後，負責修改或刪除設定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

