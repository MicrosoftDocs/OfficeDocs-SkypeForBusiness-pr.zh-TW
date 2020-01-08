---
title: Lync Server 2013：針對災害復原部署配對前端集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c01549722fe04d0a4833a9d2c37fd5e85dc575a7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40975636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中針對災害復原部署配對前端集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

您可以使用 [拓撲建立器] 輕鬆地部署成對的前端池災害復原拓撲。

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署一對前端池

1.  如果池是新的且尚未定義，請使用拓撲產生器建立池。

2.  在拓撲建立器中，以滑鼠右鍵按一下兩個池中的一個，然後按一下 [**編輯屬性**]。

3.  按一下左窗格中的 [**復原**]，然後在右窗格中選取 [**關聯的備份池**]。

4.  在 [關聯的**備份] 池**下方的方塊中，選取您要與此 pool 配對的池。 只有尚未與另一個池配對的現有池，才可以從中選取。
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  選取 [**自動容錯移轉及語音回切**]，然後按一下 **[確定]**。
    
    當您查看此池的詳細資料時，關聯的池現在會出現在右窗格中的 [**復原**] 底下。

6.  使用拓撲產生器發佈拓撲。

7.  如果兩個池尚未部署，請立即部署它們，設定就會完成。 您可以略過此程式中的最後兩個步驟。
    
    不過，如果已在您定義成對關聯之前部署了池，您必須完成下列兩個最後一個步驟。

8.  在兩個池的每個前端伺服器上，執行下列動作：
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    這會設定備份配對所需的其他服務才能正常運作。

9.  從 Lync Server Management Shell 命令提示字元，執行下列動作：
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. 使用下列 Cmdlet 強迫兩個池的使用者與會議資料相互同步處理：
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    同步處理資料可能需要一些時間。 您可以使用下列 Cmdlet 來檢查狀態。 確定兩個方向的狀態都是穩定的狀態。
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> [語音] 的 [<STRONG>自動容錯移轉</STRONG>] 選項和 [拓撲建立器] 中的關聯時間間隔，只適用于 Lync Server 2010 中引入的語音復原功能。 選取此選項並不表示本檔中討論的 [池容錯移轉] 為 [自動]。 [池容錯移轉] 和 [回切] 總是需要系統管理員手動喚醒呼叫容錯移轉與回切 Cmdlet。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

