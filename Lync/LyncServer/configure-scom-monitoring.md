---
title: 設定 SCOM 監控
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
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>設定 SCOM 監控

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

2.  將 Lync Server 2010 更新套用至此伺服器。 請參閱主題[應用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)。

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
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.

    
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

