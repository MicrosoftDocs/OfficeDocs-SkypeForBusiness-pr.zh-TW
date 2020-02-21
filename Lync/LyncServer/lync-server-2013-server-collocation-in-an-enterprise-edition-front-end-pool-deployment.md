---
title: Lync Server 2013 Enterprise Edition 前端集區部署中的伺服器共同配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ccfb87966008d471d879e2c25a73e098fb28f19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>在 Enterprise Edition 前端集區部署 Lync Server 2013 中的伺服器共同配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-11_

本節說明伺服器角色、 資料庫及檔案共用，您可以在 Lync Server 2013 前端集區部署中組合。

<div>

## <a name="server-roles"></a>伺服器角色

在 Lync Server 2013 中，A / V 會議服務、 中繼服務、 監控和封存都組合於前端伺服器，但其他設定，才能加以啟用。 如果您不想將中繼伺服器與前端伺服器組合在一起，您可以在另一部電腦上將其部署為獨立的中繼伺服器。

您可以將信任的應用程式伺服器與前端伺服器組合在一起。

下列伺服器角色必須分別部署到個別的電腦上：

  - Director

  - Edge Server

  - 中繼伺服器 (如果未與前端伺服器組合在一起)

  - Office Web Apps Server

您無法組合常設聊天室伺服器角色與前端伺服器。

</div>

<div>

## <a name="databases"></a>資料庫

您可以在相同的資料庫伺服器中組合下列每一個資料庫：

  - 後端資料庫

  - 監控資料庫

  - 封存資料庫

  - 常設聊天室資料庫

  - 常設聊天室規範資料庫

您可以組合任何或所有這些資料庫的 SQL Server 的單一執行個體，或使用 SQL Server 個別執行個體各有下列限制：

  - 每個 SQL Server 執行個體可以包含單一後端資料庫、 一個監控資料庫、 一個封存資料庫、 單一常設聊天室資料庫及單一常設聊天室規範資料庫。

  - 資料庫伺服器不支援一個以上的前端集區、 一個封存部署以及監控部署，但是可支援一個的每一個，不論資料庫是否使用相同的 SQL Server 執行個體或個別的 SQL Server 執行個體。

您可以如本節後面所述，將檔案共用與資料庫組合在一起。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，您必須與您在部署中的部分或所有使用者的 Exchange 2013 儲存體整合封存存放區的選項。 您無法在部署任何為 Exchange 存放在相同伺服器上執行 Lync Server 或元件的伺服器。



</div>

<div>


> [!IMPORTANT]  
> 雖然支援資料庫的組合，但是資料庫大小可能會快速增加。 例如，當您考慮將封存資料庫與其他資料庫組合在一起時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。 基於這個理由，我們不建議組合多個資料庫，尤其是封存資料庫、 常設聊天室資料庫或後端資料庫的常設聊天室規範資料庫。



</div>

</div>

<div>

## <a name="file-share"></a>檔案共用

檔案共用可以是個別的伺服器，或是在相同的伺服器上組合為下列任何一種或所有情況：

  - 資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器

  - 封存資料庫

  - 監控資料庫

  - 常設聊天室資料庫

  - 常設聊天室規範資料庫

單一檔案共用可以用於多個前端集區、Standard Edition Server (全部在同一個網站中)。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，監控和封存會使用 Lync Server 檔案共用作為前端伺服器。



</div>

</div>

<div>

## <a name="other-components"></a>其他元件

您無法將組合在一起的反向 proxy 伺服器，這不是 Lync Server 2013 的元件，但如果您想要支援共用與任何 Lync Server 2013 伺服器角色的同盟使用者的 web 內容所需部署中。 您，不過，可實作 Lync Server 2013 部署的反向 proxy 支援適用於其他應用程式的組織中現有的反向 proxy 伺服器上設定的支援。

您無法將任何 Exchange 整合通訊 (UM) 元件或 SharePoint 元件與任何 SharePoint Server 角色的組合。

</div>

</div>

<span> </span>

</div>

</div>

</div>

