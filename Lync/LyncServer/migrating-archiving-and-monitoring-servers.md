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
ms.openlocfilehash: 6f201b1f7520b365654635c61e4fcebae3c46a0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>移轉封存和監控伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

如果您在 Lync Server 2010 環境中部署封存伺服器及監控伺服器，您可以在移轉您的前端集區後部署 [Lync Server 2013 環境上的這些伺服器。 如果貴組織的關鍵封存和監控功能，不過，您應該新增封存和監控至 Lync Server 2013 試驗集區，以便在遷移過程中功能可供使用移轉之前。

移轉過程中，如果您需要存封和監控功能，請記住以下注意事項：

  - 封存資料和監控資料不會移至 Lync Server 2013 部署中。 您解除委任舊版環境之前所備份的資料，將會是您在 Lync Server 2010 環境中的活動歷程記錄。

  - 封存伺服器及監控伺服器的 Lync Server 2010 版本可以只與 Lync Server 2010 前端集區相關聯。 在 Lync Server 2013 中，封存和監控不再伺服器角色，但服務整合到 Lync Server 2013 前端集區。

  - 在您的舊版和 Lync Server 2013 部署共存期間，封存伺服器及監控伺服器的 Lync Server 2010 版本會收集使用者的資料位於 Lync Server 2010 集區。 封存和監控 Lync Server 2013 中的收集使用者的資料位於 Lync Server 2013 集區。
    
    <div>
    

    > [!NOTE]  
    > 移轉時仍使用舊版 Edge server 與試驗集區，Lync Server 2010 版本的封存伺服器將持續收集使用者的資料位於 Lync Server 2010 集區新 Lync Server 2013 和 Lync Server 2013 中的封存的階段蒐集使用者的資料位於 Lync Server 2013 集區。

    
    </div>

  - 如果您使用第三方封存與監控解決方案搭配封存和監控 Lync Server 2013 中的，請洽詢您的廠商需何時和如何需要與 Lync Server 2013 整合的協力廠商解決方案。

</div>

<span> </span>

</div>

</div>

</div>

