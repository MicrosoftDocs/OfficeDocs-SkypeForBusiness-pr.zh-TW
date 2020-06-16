---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba86de15ea86844b677db1abb0f47f7e1995c7e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>移轉封存和監控伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

如果您已在 Lync Server 2010 環境中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，在 Lync Server 2013 環境中部署這些伺服器。 不過，如果封存和監控功能對您的組織而言很重要，您應該在遷移之前，先在 Lync Server 2013 試驗集區中新增封存和監控功能，以便在遷移程式期間使用該功能。

移轉過程中，如果您需要存封和監控功能，請記住以下注意事項：

  - 封存資料和監控資料不會移至 Lync Server 2013 部署。 您解除委任舊版環境之前所備份的資料，將會是您在 Lync Server 2010 環境中的活動歷程記錄。

  - Lync Server 2010 版本的封存伺服器和監控伺服器只能與 Lync Server 2010 前端集區相關聯。 在 Lync Server 2013 中，封存與監控不再是伺服器角色，但已整合至 Lync Server 2013 前端集區的服務。

  - 在舊版和 Lync Server 2013 部署共存期間，您的封存伺服器和監控伺服器的 Lync Server 2010 版本會為位於 Lync Server 2010 集區的使用者收集資料。 Lync Server 2013 中的封存與監控會收集位於 Lync Server 2013 集區之使用者的資料。
    
    <div>
    

    > [!NOTE]  
    > 在遷移階段，當您仍然使用舊版 Edge server 與新的 Lync Server 2013 試驗集區時，Lync server 2010 版本的封存伺服器會繼續為位於 lync server 2010 集區中的使用者收集資料，而在 Lync 2013 Server 中封存會收集位於 Lync Server 2013 集區之使用者的資料。

    
    </div>

  - 如果您使用協力廠商的封存及監控解決方案搭配 Lync Server 2013 中的封存與監控，請洽詢廠商，以瞭解如何在何時和如何將協力廠商解決方案與 Lync Server 2013 整合。

</div>

<span> </span>

</div>

</div>

</div>

