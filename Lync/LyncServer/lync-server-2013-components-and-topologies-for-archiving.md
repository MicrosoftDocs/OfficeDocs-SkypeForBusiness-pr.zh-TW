---
title: Lync Server 2013：封存的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中封存的元件與拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

如果您想要封存 Lync Server 2013 IM 和會議內容，您可以在 Lync Server 中執行封存。

<div>

## <a name="archiving-components"></a>封存元件

[存檔] 功能包括下列元件：

  - 封存**代理**程式。 封存代理程式（也稱為 [整合資料收集代理程式]）會自動安裝並在每個前端池和標準版伺服器上啟用。 雖然封存代理程式會自動啟用，但在啟用封存並適當設定前，不會實際捕獲任何訊息。

  - **歸檔資料儲存空間**。 Lync Server 2013 的資料儲存空間可能是下列其中一項：
    
      - Exchange 2013 儲存空間。 如果您啟用 Microsoft Exchange 整合選項，則駐留在 Exchange 2013 伺服器的使用者信箱會將 Exchange 2013 儲存空間用於已歸檔的資料，但只有在已將信箱放在就地保留中的情況下。
    
      - SQL Server 儲存空間。 如果您的部署中有駐留在 Lync Server 2013 的使用者，您可以設定封存資料庫來執行受支援版本的 SQL Server，以便為這些使用者啟用封存。

封存也需要檔案儲存空間，但封存會使用與前端伺服器或標準版伺服器相同的檔案儲存空間。

如需封存的硬體和軟體需求清單，請參閱可支援性檔中的[Lync server 2013 支援的硬體](lync-server-2013-supported-hardware.md)和[lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

您在擁有需要封存支援之使用者的每個池中部署封存。 在企業版池和標準版伺服器上，封存是在前端伺服器上執行。 歸檔資料儲存空間可能如下：

  - 與 Exchange 2013 存儲整合

  - 使用個別的 SQL Server 資料庫部署

如果您的 Exchange 2013 部署不包括 Lync Server 部署中的所有使用者，您必須針對其信箱是 Exchange 2013 伺服器上的主使用者，使用 Microsoft Exchange 整合，而且您必須部署個別的 SQL Server 資料庫，以供所有其他專案使用要用來進行封存的 Lync 使用者。

</div>

<div>

## <a name="supported-collocation"></a>支援的 Collocation

Lync Server 2013 支援各種不同的 collocation 案例，可讓您靈活地在一部伺服器（如果您有小型組織）上執行多個元件來儲存硬體成本，或在不同的伺服器上執行個別元件（如果您有較大需要可伸縮性和效能的組織）。 在您決定是否要 collocate 元件之前，請務必先考慮伸縮性因素。

存檔是在 pool 或 Standard Edition 伺服器的前端伺服器上部署。 如需可在該處 collocated 之元件的詳細資訊，請參閱支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。

如果您使用個別的 SQL Server 資料庫進行歸檔，而不是或除了整合 Exchange 2013 儲存空間之外，您可以使用下列任何一種方式來 collocate 封存資料庫：

  - 監控資料庫

  - 企業版頂層端池的後端資料庫

<div>


> [!NOTE]  
> 裝載存檔資料庫的伺服器可以裝載其他資料庫。 不過，當您考慮將封存資料庫與其他資料庫 collocating 時，請注意，如果您要封存的郵件超過幾個使用者，存檔資料庫所需的磁碟空間就會變得很大。 基於這個原因，我們不建議您 collocating 封存資料庫與後端資料庫。



</div>

如果您使用監視資料庫、後端資料庫或這兩個資料庫 collocate 封存資料庫，您可以針對任何或所有資料庫使用單一 SQL 實例，或者，您也可以針對每個資料庫使用個別的 SQL 實例，包括下列各項：責任

  - 每個 SQL 實例只能包含一個後端資料庫、單一監視資料庫及單一存檔資料庫。

如需 collocation 所有伺服器角色和資料庫的詳細資料，請參閱可支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

