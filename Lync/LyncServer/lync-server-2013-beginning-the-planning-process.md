---
title: Lync Server 2013：開始規劃程序
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
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>開始 Lync Server 2013 的規劃程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

規劃內部部署的整合通訊部署可能看起來 intimidating，Lync Server 提供兩個實用的工具來協助您：

  - **規劃工具**是一個說明您組織的一系列問題、您想要啟用的 Lync Server 功能，以及您的容量規劃需求的嚮導。 然後根據您的回答建立建議的部署拓撲，並產生此部署的 Microsoft Visio 圖表。

  - [**拓撲**建立器] 是 Lync Server 的安裝元件。 您可以使用 [拓撲建立器] 來建立、調整及發佈規劃的拓撲。 它也會在您開始伺服器安裝之前驗證您的拓撲。 當您在個別伺服器上安裝 Lync Server 時，伺服器會讀取已發佈的拓撲，作為安裝程式的一部分，而安裝程式會以拓撲中的指示方式來部署伺服器。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server 規劃工具

規劃工具會針對工具中的問題提出您的答案，並根據 Lync Server 指導方針和最佳做法產生拓撲。 它也會根據您的答案，提供幾個部署的視圖。 它同時顯示所有網站的全域視圖（也就是包括中央網站和分支網站），以及每個網站上顯示伺服器與其他元件的詳細資訊。

執行規劃工具不會將您提交至任何特定部署或啟動任何進程。 事實上，即使在您有固定方案之前，仍要執行規劃工具，才能瞭解您在規劃程式中需要考慮的問題類型。

您可以多次執行規劃工具、以不同方式回答問題，以及比較結果。 如果您的設計主要是滿意的，但您需要變更，您可以返回規劃工具、載入設計，然後進行變更。 完成規劃工具需要大約15分鐘的時間。

當您滿意時，您可以使用規劃工具來建立規劃的部署圖表。 您可以使用此圖表，同時在拓撲建立器中建立部署。

<div>


> [!NOTE]  
> 此版本 Lync Server 2013 隨附的規劃工具是預發行版本本。 請注意，規劃工具中的容量規劃數位是初步的，而且最終版本不支援。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server 拓撲建立器

在您決定部署方案之後，您可以使用拓撲建立器開始部署。 完成後，您可以使用 [拓撲建立器] 來驗證拓撲，然後，如果它透過，您就可以發佈拓撲。 當您發佈拓撲時，Lync Server 會將拓朴放入中央管理儲存區中（如果目前還不存在），就會建立拓撲。 當您在部署中的每個伺服器上安裝 Lync Server 時，伺服器都會從中央管理儲存體讀取拓撲，並自行安裝，以納入其在您的部署中的角色。

或者，如果您很熟悉 Lync Server，且需要更少的規範性指示，您可以略過規劃工具，並使用拓撲建立器中的嚮導來進行部署的初始設計，以及驗證與發佈步驟。

使用 [拓撲建立器] 來規劃及發佈拓撲是必要的步驟。 您不能略過拓撲建立器，並在部署中的伺服器上個別安裝 Lync Server。 每個伺服器都必須從中央管理儲存體中已驗證且已發佈的拓撲讀取拓撲。

</div>

<div>

## <a name="high-level-planning-process"></a>高層規劃流程

我們建議您在使用檔和規劃工具來規劃 Lync Server 部署時，進行下列一般處理常式。

1.  如果您熟悉舊版 Lync Server，請閱讀[Lync server 2013 中的新功能](lync-server-2013-new-features.md)，以熟悉 lync server 2013 中的新功能和需求。

2.  閱讀本章節中的其他主題：在[規劃 Lync server 2013 之前，您必須瞭解](lync-server-2013-topology-basics-you-must-know-before-planning.md) [lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)、 [lync server 2013 的初始規劃決定](lync-server-2013-initial-planning-decisions.md)，以及[lync server 2013 的用戶端](lync-server-2013-clients.md)。 請注意在[Lync Server 2013 的參考拓朴](lync-server-2013-reference-topologies.md)中所代表的規劃決策。

3.  現在您更熟悉 Lync Server 功能及必須回答的問題種類，請執行規劃工具並查看產生的拓撲及其詳細資料。 確定拓朴符合貴組織的獨特需求。

4.  如果有您感興趣或需要瞭解的特定工作負載或功能，請閱讀[規劃 Lync Server 2013](lync-server-2013-planning.md)的適當章節。

5.  再次執行規劃工具。 您可以從您在步驟3中建立的部署開始，並修改結果，或從開頭開始。
    
    如有需要，請在第三次執行規劃工具，然後重複上述步驟，直到您對輸出滿意為止。

6.  當您完成拓撲方案後，請使用規劃工具來建立及列印您拓撲的 Visio 圖表。 您可以在使用 [拓撲建立器] 來輸入您的拓撲中使用此列印成品。

7.  開始部署之前，請先閱讀[判斷 Lync server 2013 的系統需求](lync-server-2013-determining-your-system-requirements.md)，並[判斷 lync server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)，以熟悉 lync server 的先決條件與必要基礎結構。 此外，請確定您已閱讀所有適用于您規劃部署之工作量與功能的[Lync Server 2013 規劃](lync-server-2013-planning.md)區段。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>從先前的版本遷移

如果您是從舊版遷移至 Lync Server，請參閱[遷移](migration.md)檔，以取得有關您的遷移和部署的特定指示。

</div>

</div>

<span> </span>

</div>

</div>

</div>

