---
title: Lync Server 2013 server 組合 in Standard Edition Server 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e50aa9339d992e73cf4e5b32b1e49fc2a144e67
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510310"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Lync Server 2013 的 Standard Edition server 部署中的伺服器組合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-20_

本節說明您可以在 Lync Server 2013 Standard Edition server 部署中組合的伺服器角色、資料庫及檔案共用。

<div>

## <a name="server-roles"></a>伺服器角色

在 Lync Server 2013 中，A/V 會議服務、中繼服務、監控和封存都是在 Standard Edition Server 上組合，但需要進行其他設定才能加以啟用。 您可以選擇在不同的伺服器上部署中繼服務。

您可以使用 Standard Edition server 組合信任的應用程式伺服器。

下列伺服器角色必須分別部署到個別的電腦上：

  - Director

  - Edge Server

  - 若未使用 Standard Edition server 組合，則為轉送伺服器 () 

  - Office Web Apps Server

</div>

<div>

## <a name="databases"></a>資料庫

根據預設，SQL Server Express 後端資料庫是組合在 Standard Edition Server 上。 您無法將它移動到不同的電腦。 有一個例外狀況，您無法組合 Standard Edition server 上的其他資料庫。 如果您選擇在 Standard Edition server 上部署 Persistent Chat Server，您可以在相同的 Standard Edition 伺服器上組合 Persistent chat 資料庫和 Persistent Chat 規範資料庫。

您可以在單一資料庫伺服器上組合下列每一個資料庫：

  - 監控資料庫

  - 封存資料庫

  - Enterprise Edition 前端集區的後端資料庫

您可以在單一 SQL 實例中組合任何或任何或所有這些資料庫，或針對每個資料庫使用個別的 SQL 實例，但有下列限制：

  - 每個 SQL 實例僅能包含一個適用于 Enterprise Edition 前端集區的後端資料庫 () 、單一監控資料庫、單一封存資料庫、單一持久聊天資料庫及單一持久聊天規範資料庫。

  - 資料庫伺服器不支援一個以上的 Enterprise Edition 前端集區、一部執行封存的伺服器、單一持久聊天資料庫及單一持久聊天規範資料庫，但不論資料庫使用的是相同的 SQL Server 實例還是不同的 SQL Server 實例，它都可以支援其中一個。

您可以如本節後面所述，將檔案共用與資料庫組合在一起。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，您可以選擇將監控和封存儲存整合至部署中的部分或所有使用者的 Exchange 2013 儲存體。 您無法在 Exchange 儲存體所在的伺服器上部署任何執行 Lync Server 或元件的伺服器。



</div>

<div>


> [!IMPORTANT]  
> 雖然支援資料庫的組合，但是資料庫大小可能會快速增加。 例如，當您考慮將封存資料庫與其他資料庫組合在一起時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。 基於這個理由，我們不建議使用企業版集區的後端資料庫，組合多個資料庫，尤其是封存資料庫、Persistent Chat 資料庫及 Persistent Chat 合規性資料庫。



</div>

</div>

<div>

## <a name="file-shares"></a>檔案共用

檔案共用可以是個別的伺服器，或是在相同的伺服器上組合為下列任何一種或所有情況：

  - 資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器

  - 封存資料庫

  - 監控資料庫

  - Persistent Chat 資料庫

  - Persistent Chat 規範資料庫

單一檔案共用可以用於多個前端集區、Standard Edition Server (全部在同一個網站中)。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，監控和封存使用 Lync Server 檔案共用做為 Standard Edition server。



</div>

</div>

<div>

## <a name="other-components"></a>其他元件

您無法組合反向 proxy 伺服器（不是 Lync Server 2013 元件），但是如果您想要支援使用任何 Lync Server 2013 伺服器角色的同盟使用者共用網頁內容，則您的部署中也是必要的。 不過，您可以在組織中對其他應用程式使用的現有反向 proxy 伺服器上設定支援，以執行 Lync Server 2013 部署的反向 proxy 支援。

您無法組合任何含任何 Lync Server 2013 角色的 Exchange UM 元件或 SharePoint 元件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

