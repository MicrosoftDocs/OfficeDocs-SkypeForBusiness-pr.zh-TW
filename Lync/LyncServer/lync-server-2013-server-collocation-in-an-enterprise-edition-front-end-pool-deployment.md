---
title: Enterprise Edition 前端集區部署中的 Lync Server 2013 伺服器組合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Enterprise Edition 前端集區部署中 Lync Server 2013 的伺服器組合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-11_

本節說明您可以在 Lync Server 2013 前端池部署中 collocate 的伺服器角色、資料庫及檔案共用。

<div>

## <a name="server-roles"></a>伺服器角色

在 Lync Server 2013 中，A/V 會議服務、轉送服務、監控及封存都是在前端伺服器上 collocated，但需要進行額外的設定才能啟用它們。 如果您不想要 collocate 前端伺服器的中繼伺服器，您可以將它作為獨立的中繼伺服器部署在另一部電腦上。

您可以使用前端伺服器 collocate 受信任的應用程式伺服器。

下列伺服器角色必須分別部署在不同的電腦上：

  - Director

  - Edge 伺服器

  - 中繼伺服器（如果沒有與前端伺服器 collocated）

  - Office Web Apps 伺服器

您無法 collocate 持久聊天伺服器角色與前端伺服器。

</div>

<div>

## <a name="databases"></a>資料庫

您可以在同一個資料庫伺服器上 collocate 下列每一個資料庫：

  - 後端資料庫

  - 監控資料庫

  - 封存資料庫

  - 持續聊天資料庫

  - 持續聊天合規性資料庫

您可以在單一 SQL Server 實例中 collocate 任何或任何或所有這些資料庫，或針對每個實例使用個別的 SQL Server 實例，但有下列限制：

  - 每個 SQL Server 實例都只能包含一個後端資料庫、單一監視資料庫、單一封存資料庫、單一持續式聊天資料庫，以及單一持續聊天合規性資料庫。

  - 資料庫伺服器不支援一個以上的前端池、一個封存部署，以及一個監視部署，但不論資料庫是使用相同的 SQL Server 實例，還是不同的 SQL Server 實例，都可以支援其中一個。

您可以 collocate 與資料庫共用檔案，如本節稍後所述。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，您可以選擇將存檔儲存與 Exchange 2013 儲存空間整合在您的部署中的部分或所有使用者。 您無法在與 Exchange 儲存空間相同的伺服器上，部署任何執行 Lync Server 或元件的伺服器。



</div>

<div>


> [!IMPORTANT]  
> 雖然支援 collocation 資料庫，但資料庫大小可以快速增加。 例如，當您考慮將封存資料庫與其他資料庫 collocating 時，請注意，如果您要封存的郵件超過幾個使用者，存檔資料庫所需的磁碟空間就會變得很大。 基於這個原因，我們不建議您 collocating 多個資料庫，特別是封存資料庫、持久聊天資料庫，或與後端資料庫的持續聊天合規性資料庫。



</div>

</div>

<div>

## <a name="file-share"></a>檔案共用

檔案共用可以是個別的伺服器，也可以與下列任一或所有專案在同一台伺服器上 collocated：

  - 資料庫伺服器，包括企業版頂層端池的後端伺服器

  - 封存資料庫

  - 監控資料庫

  - 持續聊天資料庫

  - 持續聊天合規性資料庫

單一檔案共用可用於多個前端池，標準版伺服器（全部位於同一個網站中）。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，監視及封存使用 Lync Server 檔案共用作為前端伺服器。



</div>

</div>

<div>

## <a name="other-components"></a>其他元件

如果您想要支援使用任何 Lync Server 2013 伺服器角色的同盟使用者共用網頁內容，則您無法 collocate 並非 Lync Server 2013 元件的反向 proxy 伺服器，但在部署中則是必要的。 不過，您可以針對 Lync Server 2013 部署執行反向 proxy 支援，方法是在組織中針對其他應用程式所使用的現有反向 proxy 伺服器上設定支援。

您無法使用任何 SharePoint Server 角色 collocate 任何 Exchange 整合訊息（UM）元件或 SharePoint 元件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

