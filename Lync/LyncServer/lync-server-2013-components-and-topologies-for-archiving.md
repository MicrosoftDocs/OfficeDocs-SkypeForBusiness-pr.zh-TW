---
title: Lync Server 2013： 的元件和拓撲封存
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
ms.openlocfilehash: a762219ef6cbecab47dcaeda313ff49dba51ed0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中的封存的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

如果您想要封存的 Lync Server 2013 IM 和會議內容，您可以在 Lync Server 中實作封存。

<div>

## <a name="archiving-components"></a>封存元件

封存功能包括下列元件：

  - **封存代理程式**。封存代理程式 (亦稱為整合資料收集代理程式) 會自動安裝在每個前端集區和 Standard Edition Server 上並啟動。儘管封存代理程式會自動啟動，但在啟用封存並進行適當設定之前，還是不會實際擷取任何訊息。

  - **封存資料存放區**。 Lync Server 2013 的資料儲存區可以是下列其中一項：
    
      - Exchange 2013 儲存體。 如果您啟用 [Microsoft Exchange 整合選項，使用者信箱位於 Exchange 2013 伺服器使用封存的資料，但僅限如果信箱已處於就地保留中的 Exchange 2013 儲存體。
    
      - SQL Server 儲存區。 如果您有部署中，位於 Lync Server 2013 的使用者，您可以設定封存執行支援的版本的 SQL Server，以對那些使用者啟用封存的資料庫。

封存也會要求檔案存放區，但封存會使用與前端伺服器或 Standard Edition Server 相同的檔案存放區。

如要封存的硬體和軟體需求清單，請參閱支援文件中的[支援 Lync Server 2013 的](lync-server-2013-supported-hardware.md)軟硬體[的 Server software and Lync Server 2013 中支援的基礎結構](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

您在每個使用者要求支援封存的集區中部署封存。 封存在 Enterprise Edition 集區中前端伺服器和 Standard Edition server 上執行。 封存資料存放區可以是下列項目：

  - 與 Exchange 2013 儲存體整合

  - 部署使用不同的 SQL Server 資料庫

如果您的 Exchange 2013 部署 Lync Server 部署中未包含的所有使用者，您必須為其信箱的使用者使用 Microsoft Exchange 整合首頁在 Exchange 2013 伺服器，以及您必須針對所有其他部署不同的 SQL Server 資料庫要用於封存的 Lync 使用者。

</div>

<div>

## <a name="supported-collocation"></a>支援的組合

Lync Server 2013 支援的各種組合案例中，讓您節省硬體成本 （如果您擁有小型組織） 的一部伺服器，執行多個元件，或在不同的伺服器上執行個別元件 （如果您有較大的彈性組織需要延展性和效能）。 在您決定是否組合元件之前，務必考量延展性因素。

封存部署的集區前端伺服器或 Standard Edition server 上。 如需可以那里組合的元件的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。

如果您使用個別的 SQL Server 資料庫的封存，而不是或除了整合存放裝置與 Exchange 2013 儲存體，您可以組合封存資料庫與下列其中一項：

  - 監控資料庫

  - Enterprise Edition 前端集區的後端資料庫

<div>


> [!NOTE]  
> 裝載封存資料庫的伺服器可以裝載其他資料庫。不過，當您考慮將封存資料庫與其他資料庫組合時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。基於這項因素，建議您不要將封存資料庫與後端資料庫整合。



</div>

如果您將封存資料庫與監控資料庫、後端資料庫 (或兩者) 組合在一起，即可將單一 SQL 執行個體使用於任一或所有資料庫；或者，您可以將個別 SQL 執行個體使用於每一個資料庫，但具有以下限制：

  - 每個 SQL 執行個體僅能包含單一後端資料庫、單一監控資料庫和單一封存資料庫。

如需所有伺服器角色和資料庫組合的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

