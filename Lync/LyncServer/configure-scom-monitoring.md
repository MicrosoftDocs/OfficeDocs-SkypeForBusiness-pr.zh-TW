---
title: 設定 SCOM 監控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>設定 SCOM 監控

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

遷移至 Microsoft Lync Server 2013 之後，您必須完成幾項工作，才能將 Lync Server 2013 設定為與 System Center Operations Manager 搭配使用。

  - 將 Lync Server 2010 更新套用至選擇的伺服器，以管理集中式發現邏輯。

  - 更新中央探索候選伺服器登錄機碼。

  - 設定您的主要系統中心作業管理員管理伺服器來覆寫候選的中央探索節點。

以下提供執行其中每個任務的指示。

**將 Lync Server 2010 更新套用至選擇的伺服器，以管理集中式發現邏輯。**

1.  選擇安裝系統中心作業管理員代理檔案的伺服器，並將其設定為候選搜尋節點。

2.  將 Lync Server 2010 更新套用至此伺服器。 請參閱[應用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)主題。

**更新中央探索候選伺服器登錄機碼。**

1.  在伺服器上選擇要管理中央探索邏輯，請開啟 Windows PowerShell 命令視窗。

2.  在命令列中，輸入下列內容：
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > 每當您編輯註冊表時，如果登錄機碼已存在，您可能會遇到「命令失敗」的錯誤。 如果您遇到這種情況，您可以放心地忽略錯誤。

    
    </div>

**設定您的主要系統中心作業管理員管理伺服器，以覆寫候選的中央探索觀察程式節點。**

1.  在已安裝 System Center Operations Manager 主控台的電腦上，展開 [**管理套件物件**]，然後選取 [**物件發現**]。

2.  按一下 [**變更範圍]。**

3.  從 [**範圍管理套件物件**] 頁面上，選取 [ **LS 探索候選**]。

4.  在先前的程式中，將**LS 搜尋候選生效值**覆寫為所選擇的候選伺服器名稱。

最後，若要完成您的變更，請重新開機 System Center Operations Manager 根管理伺服器上的健康情況服務。

</div>

<span> </span>

</div>

</div>

</div>

