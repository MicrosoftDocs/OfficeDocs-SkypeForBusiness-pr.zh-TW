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
ms.openlocfilehash: 14a4c5f81b88db33ba86c4410109a0943b81cb87
ms.sourcegitcommit: eb2182617d8f72f8a7ea95f7af101d10c6f4e9a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2020
ms.locfileid: "41852003"
---
<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>在 Lync Server 2013 中升級或更新前端伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-28_

企業版池中的前端伺服器會組織成*升級網域*。 這些是池中的前端伺服器子集。 升級網域是由拓撲產生器自動建立。

當您升級伺服器時，您必須一次升級一個網域。 將每個伺服器放在一個升級網域中，將其升級後再重新開機，然後再移至另一個升級網域。 請務必追蹤目前已升級的升級網域和伺服器。 升級每個伺服器時，請使用下列流程圖圖表。

![升級或更新前端伺服器](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>在池中將升級套用到前端伺服器

1.  在池中的前端伺服器上，執行下列 Cmdlet：
    
    **Get-CsPoolUpgradeReadinessState**
    
    如果*PoolUpgradeState*的值為 [**忙碌**]，請等候10分鐘，然後再次嘗試**CsPoolUpgradeReadinessState** 。 如果您至少在每次嘗試之間有10分鐘後再看到 [**忙碌**]，或者如果您看到**PoolUpgradeState**的任何**InsufficientActiveFrontEnds**結果，則該池有問題。 如果這個池與災害復原拓朴中的另一個前端池成對，您應該將該池失敗轉移至 [備份] 池，然後更新此池中的伺服器。 如需詳細資訊，請參閱[在 Lync Server 2013 中轉移池失敗](lync-server-2013-failing-over-a-pool.md)。
    
    如果*PoolUpgradeState*的值已**準備好**，請移至步驟2。

2.  **CsPoolUpgradeReadinessState** Cmdlet 也會傳回有關池中每個升級網域的相關資訊，以及每個升級網域中的最上層端伺服器。 如果包含您要升級之伺服器或伺服器的升級網域的**ReadyforUpgrade**值為**True** ，您就可以立即安全地升級這些伺服器。 若要這樣做，請執行下列動作：
    
    1.  停止使用`Stop-CsWindowsService -Graceful -Verbose` Cmdlet 來升級到前端伺服器的新連線。
        
        <div>
        

        > [!NOTE]  
        > 如果您在排程的伺服器停機期間執行這些伺服器升級，您可以執行此不含 '-<STRONG>寬容</STRONG>」參數的 Cmdlet，如下所示：<STRONG>停止 CsWindowsService</STRONG>。 這會立即關閉服務，而不需要填寫所有現有的服務要求。

        
        </div>
    
    2.  升級與此升級網域相關聯的伺服器。
    
    3.  重新開機伺服器，並確認他們接受新的連線。

3.  針對池中的其他每個升級網域重複步驟1和2，直到所有前端伺服器都已升級為止。

</div>

</div>

<span> </span>

</div>

</div>

</div>

