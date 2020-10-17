---
title: 設定 SCOM 監控
description: 設定 SCOM 監視。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c93e10c705a1a1e08972d7534e00a33c472d23a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542989"
---
# <a name="configure-scom-monitoring"></a>設定 SCOM 監控

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

在遷移至 Microsoft Lync Server 2013 之後，您必須完成一些工作以設定 Lync Server 2013，才能使用 System Center Operations Manager。

  - 對選擇的伺服器套用 Lync Server 2010 更新，以管理集中式探索邏輯。

  - 更新集中探索候選伺服器登錄機碼。

  - 設定您的主要 System Center Operations Manager 管理伺服器以覆寫候選的中央探索節點。

執行各項工作的指示提供於下。

**對選擇的伺服器套用 Lync Server 2010 更新，以管理集中式探索邏輯。**

1.  選取安裝有 System Center Operations Manager 代理程式檔案，並設定為候選探索節點的伺服器。

2.  將 Lync Server 2010 更新套用至此伺服器。 請參閱主題 [應用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)。

**更新集中探索候選伺服器登錄機碼。**

1.  在選擇用來管理集中探索邏輯的伺服器上，開啟 [Windows PowerShell] 命令視窗。

2.  在命令列輸入下列命令：
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > 編輯登錄時，如果登錄機碼已經存在，可能會顯示命令失敗的錯誤。如果您遇到這個問題，可以安心忽略錯誤。

    
    </div>

**設定您的主要 System Center Operations Manager 管理伺服器以覆寫候選的中央探索觀察程式節點。**

1.  在已安裝 System Center Operations Manager 主控台的電腦上，展開 **[管理組件物件]**，然後選取 **[物件探索]**。

2.  按一下 **[變更領域...]**。

3.  從 **[管理組件物件領域]** 頁面，選取 **[LS 探索候選]**。

4.  將 **[LS 探索候選有效值]** 覆寫為先前程序中選取的候選伺服器名稱。

最後，為了完成變更，請重新啟動 System Center Operations Manager Root Management Server 上的健全狀況服務。

</div>

<span> </span>

</div>

</div>

</div>

