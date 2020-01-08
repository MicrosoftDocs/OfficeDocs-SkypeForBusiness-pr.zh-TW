---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981716"
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

如果您在 Office 通訊伺服器 2007 R2 中部署了 [封存伺服器] 和 [監視伺服器]，就可以在您遷移完前端池之後，將這些伺服器部署在 Lync Server 2013 環境中。 不過，如果封存和監控功能對您的組織而言是至關重要的，您應該先在您的試驗池新增封存和監控，才能在遷移期間使用這些功能。

如果您想要在遷移和共存階段期間進行封存與監控功能，請記住下列考慮事項：

  - 存檔資料和監視資料不會移至 Lync Server 2013 部署。 您在解除舊版環境之前備份的資料將是 Office 通訊伺服器 2007 R2 中的活動歷程記錄。

  - Office 通訊伺服器 2007 R2 版本的封存伺服器與監視伺服器只能與 Office 通訊伺服器 2007 R2 前端池相關聯。 在 Lync Server 2013 中，[封存及監視] 不再是伺服器角色，但已整合至 Lync Server 2013 前端池的服務。

  - 在舊版和 Lync Server 2013 部署共存期間，您的 Office 通訊伺服器 2007 R2 版本的封存伺服器與監視伺服器會針對駐留在 Office 通訊伺服器 2007 R2 pool 的使用者收集資料。 Lync Server 2013 版本的 [封存伺服器] 和 [監視伺服器] 可收集駐留在 Lync Server 2013 池的使用者資料。
    
    <div>
    

    > [!NOTE]  
    > 在遷移階段，當您仍將舊版 Edge 伺服器與新的 Lync Server 2013 試驗池結合使用時，Office 通訊伺服器 2007 R2 版本的封存伺服器會繼續針對駐留在 Office 通訊伺服器的使用者收集資料。2007R2 pool 和 Lync Server 2013 版本的封存伺服器會針對駐留在 Lync Server 2013 池的使用者搜集資料。

    
    </div>

  - 如果您將協力廠商的歸檔與監控解決方案與封存伺服器與監視伺服器搭配使用，請與您的廠商聯繫，以瞭解何時以及如何將協力廠商解決方案整合至 Lync Server 2013。

</div>

<span> </span>

</div>

</div>

</div>

