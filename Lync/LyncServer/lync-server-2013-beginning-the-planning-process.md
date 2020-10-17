---
title: Lync Server 2013：開始規劃程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513036"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a>開始 Lync Server 2013 的規劃程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

在規劃內部部署的整合通訊部署時，可能似乎 intimidating，Lync Server 提供兩個有價值的工具來協助您：

  - **規劃工具** 是一個包含有關組織相關問題的嚮導、您想要啟用的 Lync Server 功能，以及您的容量規劃需求。 然後，它會根據您的回答建立建議的部署拓撲，並產生此部署的 Microsoft Visio 圖表。

  - **拓撲** 產生器是 Lync Server 的安裝元件。 您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲。 在您開始伺服器安裝之前，它也會驗證您的拓撲。 當您在個別伺服器上安裝 Lync Server 時，伺服器會在安裝過程中讀取已發佈的拓撲，而且安裝程式會以拓撲中的導向方式來部署伺服器。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server 規劃工具

規劃工具採用工具中問題的答案，並根據 Lync Server 指導方針和最佳作法產生拓撲。 它也會根據您的回答，提供數個部署的視圖。 它會顯示所有網站的全域視圖 (，包括「中央網站」和「分支網站」) ，以及顯示每個網站上的伺服器及其他元件的詳細資訊。

執行規劃工具並不會向您認可任何特定的部署或啟動任何程式。 實際上，即使在您準備好方案之前執行規劃工具，也可能是一種非常有益的方式，可瞭解在規劃程式中需要考慮的問題種類。

您可以多次執行計畫工具，以不同方式回答問題，並比較結果。 如果您有大部分的設計，但您需要變更，您可以回到規劃工具、載入設計，然後進行變更。 完成規劃工具一次大約需要15分鐘的時間。

當您滿意後，您可以使用規劃工具來建立規劃的部署圖表。 您可以在拓撲產生器中建立部署時使用此圖表。

<div>


> [!NOTE]  
> 此版本的 Lync Server 2013 包含的計畫工具是一個預先發行版本本。 請注意，規劃工具中的容量規劃編號是初步的，且不支援最後的版本。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server 拓撲產生器

決定部署計畫之後，您可以使用拓撲產生器開始部署。 完成後，您可以使用拓撲產生器來驗證拓撲，然後在它通過後，您就可以發佈拓撲。 當您發佈拓撲時，Lync Server 會將拓撲放入中央管理存放區中（如果尚未存在），便會建立拓撲。 當您在部署中的每一部伺服器上安裝 Lync Server 時，伺服器會從中央管理存放區讀取拓撲，並自行安裝以符合其在您的部署中的角色。

或者，如果您很熟悉 Lync Server，且需要較少的規範性指導，您可以略過規劃工具並使用拓撲產生器中的嚮導，以進行部署的初始設計，以及驗證與發佈步驟。

使用拓撲產生器來規劃及發行拓撲是必要的步驟。 您無法略過拓撲產生器，並在部署中的伺服器上個別安裝 Lync Server。 每個伺服器都必須從中央管理存放區中已驗證、已發佈的拓撲讀取拓撲。

</div>

<div>

## <a name="high-level-planning-process"></a>規劃程式 High-Level

我們建議您在使用檔和規劃工具來規劃 Lync Server 部署時，使用下列一般處理常式。

1.  如果您熟悉舊版的 Lync Server，請閱讀 [Lync server 2013 中的新功能](lync-server-2013-new-features.md) ，以熟悉 lync server 2013 中的新功能和需求。

2.  請閱讀本檔本節中的其他主題： [您必須2013知道的拓撲基本知識](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)、lync [server 2013 的初始規劃決策](lync-server-2013-initial-planning-decisions.md)，以及 [lync server 2013 的用戶端](lync-server-2013-clients.md)。 請注意 [Lync Server 2013 的參考拓撲中](lync-server-2013-reference-topologies.md)所代表的規劃決策。

3.  現在，您更熟悉 Lync Server 功能和必須回答的問題種類，請執行規劃工具，然後查看產生的拓撲及其詳細資料。 請確定拓撲符合您組織的獨特需求。

4.  如果有您感興趣的特定工作負載或功能或需要深入瞭解，請參閱 [規劃 Lync Server 2013](lync-server-2013-planning.md)的適當章節。

5.  再次執行計畫工具。 您可以從您在步驟3中建立的部署開始，並修改結果，或從頭開始。
    
    如有需要，請在第三次執行計畫工具，並重複此步驟，直到您對輸出滿意為止。

6.  當您完成拓撲計畫時，請使用規劃工具來建立及列印拓撲的 Visio 圖表。 使用拓撲產生器時，您可以使用此列印輸出來輸入您的拓撲。

7.  開始部署之前，請先閱讀 [判斷您的 Lync server 2013 的系統需求](lync-server-2013-determining-your-system-requirements.md) ，並 [決定 lync server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md) ，以熟悉 lync server 的必要條件及必要基礎結構。 此外，請確定您已閱讀適用于您計畫要部署之工作負載和功能之所有 [規劃的 Lync Server 2013](lync-server-2013-planning.md) 的部分。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>從先前版本遷移

若要從先前版本遷移至 Lync Server，請參閱遷移和部署的特定指示的 [遷移](migration.md) 檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>

