---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>移轉封存和監控伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

如果您在 Lync Server 2010 環境中部署了 [封存伺服器] 和 [監視伺服器]，您可以在您遷移前端池之後，將這些伺服器部署在 Lync Server 2013 環境中。 不過，如果封存和監控功能對您的組織而言是至關重要的，您應該先在您的 Lync Server 2013 試驗區中新增封存和監控，以便在遷移過程中使用這些功能。

如果您想要在遷移期間進行封存與監控，請記住下列考慮事項：

  - 存檔資料和監視資料不會移至 Lync Server 2013 部署。 您在解除舊版環境之前備份的資料將是 Lync Server 2010 環境中的活動歷程記錄。

  - Lync Server 2010 版本的封存伺服器和監視伺服器只能與 Lync Server 2010 前端池相關聯。 在 Lync Server 2013 中，[封存及監視] 不再是伺服器角色，但已整合至 Lync Server 2013 前端池的服務。

  - 在舊版和 Lync Server 2013 部署期間共存期間，Lync Server 2010 版本的封存伺服器與監視伺服器會針對駐留在 Lync Server 2010 池的使用者收集資料。 Lync Server 2013 中的 [封存與監控] 可收集駐留在 Lync Server 2013 池的使用者資料。
    
    <div>
    

    > [!NOTE]  
    > 在遷移階段，當您仍將舊版 Edge 伺服器與新的 Lync Server 2013 試驗池結合使用時，Lync Server 2010 版本的封存伺服器會繼續針對駐留在 lync server 2010 中的使用者收集資料，並在 Lync Server 2013 中歸檔收集駐留在 Lync Server 2013 池的使用者資料。

    
    </div>

  - 如果您在 Lync Server 2013 與 [封存與監控] 結合使用協力廠商的 [封存與監控] 解決方案，請諮詢您的供應商，瞭解您需要何時以及如何將協力廠商解決方案整合到 Lync Server 2013。

</div>

<span> </span>

</div>

</div>

</div>

