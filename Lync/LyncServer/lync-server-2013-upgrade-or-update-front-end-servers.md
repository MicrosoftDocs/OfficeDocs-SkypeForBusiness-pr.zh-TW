---
title: Lync Server 2013：升級或更新前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530320"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>在 Lync Server 2013 中升級或更新前端伺服器

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-28_

Enterprise Edition 集區中的前端伺服器會組織成 *升級網域*。 這些是集區中的前端伺服器的子集。 升級網域是透過拓撲產生器自動建立的。

當您升級伺服器時，您必須一次執行一個升級網域。 將每一部伺服器放在一個升級網域中，進行升級，然後重新開機，再移至另一個升級網域。 請務必追蹤迄今為止已升級的升級網域和伺服器。 在升級每一部伺服器時，請使用下列流程圖圖表。

![升級或更新前端伺服器](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>將升級套用至集區中的前端伺服器

1.  在集區中的前端伺服器上，執行下列 Cmdlet：
    
    **Get-CsPoolUpgradeReadinessState**
    
    如果 *PoolUpgradeState* 的值 **占線**，請等候10分鐘，然後再 **Get-CsPoolUpgradeReadinessState** 一次。 如果您在每次嘗試之間等候10分鐘之後，又至少看到三次**繁忙**，或是您看到**PoolUpgradeState** **的任何**結果，則集區發生問題。 如果此集區與嚴重損壞修復拓撲中的另一個前端集區配對，您應該將集區失敗至備份組區，然後更新此集區中的伺服器。 如需詳細資訊，請參閱 [在 Lync Server 2013 中容錯移轉集](lync-server-2013-failing-over-a-pool.md)區。
    
    如果 *PoolUpgradeState* 的值已 **準備好**，請移至步驟2。

2.  **Get-CsPoolUpgradeReadinessState** Cmdlet 也會傳回集區中每個升級網域的相關資訊，以及每個升級網域中的前端伺服器。 如果包含您要升級之伺服器或伺服器的升級網域， **ReadyforUpgrade** 值為 **True** ，您就可以立即安全升級這些伺服器。 若要這麼做，請執行下列操作：
    
    1.  使用 Cmdlet，停止與您要升級的前端伺服器的新連線 `Stop-CsWindowsService -Graceful -Verbose` 。
        
        <div>
        

        > [!NOTE]  
        > 若要在排程的伺服器停機期間執行這些伺服器升級，您可以執行此指令程式，但不含 '-<STRONG>寬容</STRONG>」參數，如下所示： <STRONG>Stop-CsWindowsService</STRONG>。 這會立即關閉服務，而不會等候所有現有的服務要求填滿。

        
        </div>
    
    2.  升級與此升級網域相關聯的伺服器。
    
    3.  重新開機伺服器，確定他們接受新的連線。

3.  針對集區中的每個其他升級網域重複步驟1和2，直到所有前端伺服器都升級為止。

</div>

</div>

<span> </span>

</div>

</div>

</div>

