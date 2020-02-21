---
title: Lync Server 2013： 從開始規劃程序
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
ms.openlocfilehash: 04bc27b965da5d4761e3283ea3106a8a3b90ebf8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>開始 Lync Server 2013 的規劃程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-24_

規劃內部部署時整合的通訊部署可能有些聲勢浩大，Lync Server 提供兩種非常有用的工具，可協助您：

  - **規劃工具**是提供一系列的組織，您想要啟用 Lync Server 功能和容量規劃需求的相關問題的精靈。 然後會建立根據您的答案，建議的部署拓撲，並產生此部署的 Microsoft Visio 圖表。

  - **拓撲產生器**是 Lync Server 安裝元件。 您可以使用拓撲產生器來建立、 調整，及發佈您計劃的拓撲。 若要安裝伺服器之前，它也會驗證您的拓撲。 當您在個別伺服器上安裝 Lync Server 時，伺服器安裝過程中，讀取已發行的拓撲，並依照拓撲中的指示，安裝程式會部署伺服器。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server 規劃工具

規劃工具接受您對問題的回答工具中，並產生根據 Lync Server 指導方針和最佳作法的拓撲。 它也會提供數個檢視的部署，根據您的答案。 它會顯示所有網站 （也就，包括中央站台和分公司站台），這兩個全域檢視和顯示伺服器和其他元件，每個站台的詳細檢視。

執行規劃工具不會認可您向任何特定的部署或啟動任何程序。 事實上，即使之前必須記住的公司的計劃執行規劃工具可以是非常更有意義的方式了解您需要考慮在您規劃程序中的問題類型。

您可以執行規劃工具多次，以不同的回答問題並比較結果。 如果您有您滿意大部分，但是您需要進行的變更設計，您可以回到 [規劃工具、 載入設計]，並進行變更。 所需約 15 分鐘一次完成規劃工具。

您滿意之後，您可以使用規劃工具建立計劃部署的圖表。 在拓撲產生器建立部署時，您可以使用此圖表中。

<div>


> [!NOTE]  
> 隨附於此版本的 Lync Server 2013 規劃工具是搶鮮版。 附註中規劃工具的容量規劃數字屬初始版本，並不支援的最終版本。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server 拓撲產生器

一旦您已決定在您的部署計劃，您使用拓撲產生器開始部署。 完成後，您使用拓撲產生器來驗證拓撲，並接著，如果它通過，您可以發佈拓撲。 當您發行拓撲時，Lync Server 會將拓撲放至中央管理存放區，如果不存在，會建立這一次。 當您部署中，每部伺服器上安裝 Lync Server 時，伺服器會讀取從中央管理存放區的拓撲，並安裝以符合您在部署中其角色本身擷取。

或者，如果您是非常熟悉 Lync Server，而且不需要規定，您可以略過規劃工具，並在拓撲產生器中使用精靈，您的部署的初始設計也用來驗證和發佈的步驟。

若要規劃並發行拓撲使用拓撲產生器是必要的步驟。 您無法略過拓撲產生器和 Lync Server 個別伺服器上安裝在您的部署中。 每部伺服器必須從中央管理存放區中的驗證、 發行拓撲讀取拓樸。

</div>

<div>

## <a name="high-level-planning-process"></a>高階規劃程序

我們建議使用文件和規劃工具規劃 Lync Server 部署的下列一般程序。

1.  如果您已熟悉舊版的 Lync Server，請閱讀[Lync Server 2013 中的新功能](lync-server-2013-new-features.md)，以熟悉的新功能和 Lync Server 2013 中的需求。

2.  閱讀本章節屬於文件中的其他主題：[規劃針對 Lync Server 2013 前必須知道的拓撲基本知識](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)、[初始規劃決策以便 Lync Server 2013](lync-server-2013-initial-planning-decisions.md)，和[Lync Server 2013 的用戶端](lync-server-2013-clients.md)。 請注意在[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)中表示的規劃決策。

3.  既然您已較熟悉 Lync Server 功能與幾種類型的必須回答的問題，執行規劃工具，並檢視產生的拓撲和其詳細資料。 請確定拓撲適合貴組織的獨特需求。

4.  如果有特定的工作量或功能您感興趣，或需要若要了解，請閱讀[Planning for Lync Server 2013](lync-server-2013-planning.md)的適當區段。

5.  再次執行規劃工具。 您可以開始部署您在步驟 3 中建立及修改結果，或從頭開始。
    
    如有需要執行規劃工具第三個階段，並重複，直到您滿意輸出。

6.  當您已完成的拓樸計劃時，使用規劃工具來建立及列印您的拓樸的 Visio 圖表。 您可以使用此 printout 時使用拓撲產生器中，輸入您的拓撲。

7.  在您開始部署之前讀取[決定 Lync Server 2013 系統需求](lync-server-2013-determining-your-system-requirements.md)，以及[決定 Lync Server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)以熟悉的先決條件和必要基礎結構的 Lync Server。 此外，請確定您已閱讀所有章節的[Planning for Lync Server 2013](lync-server-2013-planning.md)適用於工作負載和您計劃部署的功能。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>從舊版移轉

如果您從舊版移轉至 Lync Server，請參閱[移轉](migration.md)文件的移轉和部署的特定指示。

</div>

</div>

<span> </span>

</div>

</div>

</div>

