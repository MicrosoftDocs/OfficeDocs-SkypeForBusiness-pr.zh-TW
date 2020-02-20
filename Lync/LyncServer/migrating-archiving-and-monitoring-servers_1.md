---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 799f2258344d94f4dcfc0e477bd3e77316c3a060
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>移轉封存和監控伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

如果您在 Office Communications Server 2007 R2 中部署封存伺服器及監控伺服器，您可以在移轉您的前端集區後部署 [Lync Server 2013 環境上的這些伺服器。 如果貴組織的關鍵封存和監控功能，不過，您應該新增封存和監控至試驗集區，以便在遷移過程中功能可供使用移轉之前。

若希望在移轉共存階段期間繼續提供封存及監控功能，請牢記下列注意事項：

  - 封存資料和監控資料不會移至 Lync Server 2013 部署中。 您在解除委任舊版環境之前備份資料都將您的 Office Communications Server 2007 R2 中的活動的記錄。

  - 封存伺服器及監控伺服器的 Office Communications Server 2007 R2 版本可以只與 Office Communications Server 2007 R2 前端集區相關聯。 在 Lync Server 2013 中，封存和監控不再伺服器角色，但服務整合到 Lync Server 2013 前端集區。

  - 在您的舊版和 Lync Server 2013 部署共存期間，封存伺服器及監控伺服器的 Office Communications Server 2007 R2 版本會收集使用者的資料位於 Office Communications Server 2007 R2 集區。 封存伺服器及監控伺服器的 Lync Server 2013 版本收集使用者的資料位於 Lync Server 2013 集區。
    
    <div>
    

    > [!NOTE]  
    > 移轉階段時您仍在使用舊版 Edge server 與新的 Lync Server 2013 試驗集區、 封存伺服器的 Office Communications Server 2007 R2 版本將持續收集使用者的資料位於 Office Communications Server 2007R2 集區與 Lync Server 2013 版本的封存伺服器蒐集使用者的資料位於 Lync Server 2013 集區。

    
    </div>

  - 如果您使用第三方封存與監控解決方案封存伺服器及監控伺服器搭配使用，談到您的廠商何時和如何需要與 Lync Server 2013 整合的協力廠商解決方案。

</div>

<span> </span>

</div>

</div>

</div>

