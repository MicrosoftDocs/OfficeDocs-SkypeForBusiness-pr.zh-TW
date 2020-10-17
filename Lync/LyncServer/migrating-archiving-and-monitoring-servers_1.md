---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95646d47ae7b045a193cfec49ea06ad75466853f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527400"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>移轉封存和監控伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

如果您已在 Office 通訊伺服器 2007 R2 中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，在 Lync Server 2013 環境中部署這些伺服器。 不過，如果封存和監控功能對您的組織而言很重要，您應該先在試驗集區中新增封存與監控，以在遷移程式期間使用該功能。

若希望在移轉共存階段期間繼續提供封存及監控功能，請牢記下列注意事項：

  - 封存資料和監控資料不會移至 Lync Server 2013 部署。 解除委任舊版環境之前所備份的資料，將會是 Office 通訊伺服器 2007 R2 中的活動歷史。

  - Office 通訊伺服器 2007 R2 版本的封存伺服器和監控伺服器只能與 Office 通訊伺服器 2007 R2 前端集區相關聯。 在 Lync Server 2013 中，封存與監控不再是伺服器角色，但已整合至 Lync Server 2013 前端集區的服務。

  - 在舊版和 Lync Server 2013 部署共存期間，您的 Office 通訊伺服器 2007 R2 版本的封存伺服器和監控伺服器會為位於 Office 通訊伺服器 2007 R2 pool 的使用者收集資料。 Lync Server 2013 版本的封存伺服器和監控伺服器會收集位於 Lync Server 2013 集區之使用者的資料。
    
    <div>
    

    > [!NOTE]  
    > 在遷移階段，當您仍然使用舊版 Edge server 搭配新的 Lync Server 2013 試驗集區時，Office 通訊伺服器 2007 R2 版本的封存伺服器會繼續收集位於 Office 通訊伺服器 2007 R2 集區之使用者的資料，而 Lync Server 2013 版本的封存伺服器便會收集位於 Lync Server 2013 集區之使用者的資料。

    
    </div>

  - 如果您使用協力廠商封存與監控解決方案與封存伺服器和監控伺服器搭配使用，請與您的廠商聯繫，以瞭解如何與 Lync Server 2013 整合協力廠商解決方案。

</div>

<span> </span>

</div>

</div>

</div>

