---
title: Lync Server 2013： 部署配對的前端集區用於災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f33e72c6f7d02787f53d16de3a42a0b3227d67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 的災害復原部署配對的前端集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

您可以輕易地部署成對使用拓撲產生器的前端集區的災害復原拓撲。

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署一對前端集區

1.  如果的新集區尚未定義，使用拓撲產生器來建立集區。

2.  在拓撲產生器，以滑鼠右鍵按一下其中一個兩個集區]，，，然後按一下 [**編輯內容]**。

3.  按一下左窗格中的 [恢復]****，然後選取右窗格中的 [關聯的備份集區]****。

4.  在下方 [關聯的備份集區]**** 中，選取您要與此集區配對的集區。您僅能選取尚未與其他集區配對的現有集區。
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  選取 [語音自動容錯移轉和容錯回復]****，然後按一下 [確定]****。
    
    現在當您檢視此集區的詳細資料時，會在右窗格的 [恢復]**** 中顯示關聯的集區。

6.  使用拓撲產生器來發行拓撲。

7.  若尚未部署這兩個集區，請立即部署，以完成組態。您可在此程序中略過最後這兩個步驟。
    
    然而，若在您定義成對關聯之前，就已部署了集區，您就必須完成下列兩個最後步驟。

8.  在兩個集區中的每部前端伺服器上，執行下列項目：
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    這會設定使備份配對順利運作所需的其他服務。

9.  從 Lync Server 管理命令介面命令提示字元處，執行下列命令：
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. 使用下列 Cmdlet，強制兩個集區的使用者及會議資料互相進行同步處理：
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    同步處理資料可能需要花費一些時間。 您可以使用下列 Cmdlet 檢查狀態。 請確定兩個方向狀態不穩定的狀態。
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <STRONG>自動容錯移轉和容錯回復] 語音</STRONG>選項，並在拓撲產生器的相關聯的時間間隔僅適用於 Lync Server 2010 中引進的語音恢復功能。 選取此選項不表示會自動使用本文件中討論的集區容錯移轉。 集區容錯移轉和容錯回復一律需要管理員以手動方式分別呼叫容錯移轉和容錯回復 Cmdlet。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

