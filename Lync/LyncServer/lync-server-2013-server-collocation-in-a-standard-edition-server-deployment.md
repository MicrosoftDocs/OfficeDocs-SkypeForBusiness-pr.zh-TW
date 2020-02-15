---
title: Lync Server 2013 Standard Edition server 部署中的伺服器共同配置
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
ms.openlocfilehash: 428f666ade00d2f809f25cb7eb9ef1525d7f835c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Lync Server 2013 Standard Edition server 部署中的伺服器共同配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-20 個_

本節說明伺服器角色、 資料庫及檔案共用，您可以在 Lync Server 2013 Standard Edition server 部署中組合。

<div>

## <a name="server-roles"></a>伺服器角色

在 Lync Server 2013 中，A / V 會議服務、 中繼服務、 監控和封存都組合於 Standard Edition Server，但其他設定，才能加以啟用。 您可以選擇部署中繼服務在個別伺服器上。

您可以組合信任的應用程式伺服器與 Standard Edition 伺服器。

下列伺服器角色必須分別部署到個別的電腦上：

  - Director

  - Edge Server

  - 中繼伺服器 （如果沒有與 Standard Edition server 組合）

  - Office Web Apps Server

</div>

<div>

## <a name="databases"></a>資料庫

根據預設，SQL Server Express 後端資料庫組合在 Standard Edition server 上。 您無法將其移至另一部電腦。 有一個例外狀況，您不能組合 Standard Edition server 上的其他資料庫。 如果您選擇在 Standard Edition 伺服器上部署 Persistent Chat Server，您可以組合常設聊天室資料庫及相同的 Standard Edition server 上的常設聊天室規範資料庫。

您可以組合每一個單一資料庫伺服器上的下列資料庫：

  - 監控資料庫

  - 封存資料庫

  - Enterprise Edition 前端集區後端資料庫

您可以組合任何或所有這些資料庫中的單一 SQL 執行個體，或使用個別的 SQL 執行個體各有下列限制：

  - 只有 （適用於 Enterprise Edition 前端集區中） 的單一後端資料庫、 一個監控資料庫、 一個封存資料庫、 單一常設聊天室資料庫和單一常設聊天室規範資料庫，可以包含每個 SQL 執行個體。

  - 資料庫伺服器不支援一個以上的 Enterprise Edition 前端集區、 一部伺服器執行封存，一部伺服器執行監控、 單一常設聊天室資料庫和單一常設聊天室規範資料庫，但是可支援的每個，其中一個不論資料庫是否使用相同的 SQL Server 執行個體或個別的 SQL Server 執行個體。

您可以如本節後面所述，將檔案共用與資料庫組合在一起。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，您可以選擇整合監控和封存儲存與您在部署中的部分或所有使用者的 Exchange 2013 儲存體。 您無法在部署任何為 Exchange 存放在相同伺服器上執行 Lync Server 或元件的伺服器。



</div>

<div>


> [!IMPORTANT]  
> 雖然支援資料庫的組合，但是資料庫大小可能會快速增加。 例如，當您考慮將封存資料庫與其他資料庫組合在一起時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。 基於這個理由，我們不建議組合多個資料庫，尤其是封存資料庫、 常設聊天室資料庫及與 Enterprise 集區的後端資料庫常設聊天室規範資料庫。



</div>

</div>

<div>

## <a name="file-shares"></a>檔案共用

檔案共用可以是個別的伺服器，或是在相同的伺服器上組合為下列任何一種或所有情況：

  - 資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器

  - 封存資料庫

  - 監控資料庫

  - 常設聊天室資料庫

  - 常設聊天室規範資料庫

單一檔案共用可以用於多個前端集區、Standard Edition Server (全部在同一個網站中)。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，監控和封存會使用 Lync Server 檔案共用作為 Standard Edition server。



</div>

</div>

<div>

## <a name="other-components"></a>其他元件

您無法將組合在一起的反向 proxy 伺服器，這不是 Lync Server 2013 的元件，但如果您想要支援共用與任何 Lync Server 2013 伺服器角色的同盟使用者的 web 內容所需部署中。 您，不過，可實作 Lync Server 2013 部署的反向 proxy 支援適用於其他應用程式的組織中現有的反向 proxy 伺服器上設定的支援。

您無法將任何 Exchange UM 元件或 SharePoint 元件與任何 Lync Server 2013 角色的組合。

</div>

</div>

<span> </span>

</div>

</div>

</div>

