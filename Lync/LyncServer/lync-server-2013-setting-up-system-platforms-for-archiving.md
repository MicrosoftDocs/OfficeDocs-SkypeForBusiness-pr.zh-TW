---
title: Lync Server 2013： 在封存設定系統平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c87f8b0994cc6022cd68bd7e42bb37ae8cb84d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>針對 Lync Server 2013 中的封存設定系統平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

開始部署封裝之前，必須先在符合系統需求的硬體上安裝所需作業系統，以及所有先決條件軟體。

  - **Lync Server 2013 平台**   Lync Server 2013 部署不需要封存伺服器。 但在前端伺服器及 Standard Edition Server 上執行的整合資料收集代理程式會擷取封裝的資料，因此不需要使用另一個系統平台主控封裝。

  - **資料儲存平台**   在 Lync Server 2013 中，您可以使用下列其中之一儲存資料：
    
      - **Microsoft Exchange 整合**   您的 Exchange 部署如果您想要儲存 Lync Server 2013 封存資料，使用 Exchange 2013 部署，而不是或除了設定不同的資料庫來儲存封存資料，必須執行 Exchange 2013。 如需設定系統平台 Exchange 2013 的詳細資訊，請參閱 < Exchange 產品文件。
    
      - **SQL Server**   如果您想要使用不同的 SQL Server 資料庫來儲存封存資料，而不是或除了使用 Microsoft Exchange 整合，您必須設定系統平台] 之前部署封存資料庫。 特定系統的平台需求取決於是否封存資料庫使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。 如需設定系統平台，這些資料庫的詳細資訊，請參閱 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 產品文件。

  - **檔案伺服器平台**   Lync Server 2013 儲存 Lync Server 封存檔案存放在相同的位置您指定的檔案，當您設定您的前端伺服器或 Standard Edition 伺服器。 您無法指定另一個封裝檔案儲存的位置，所以也不需要另一個封裝檔案儲存的系統平台。 如果您使用 Microsoft Exchange 整合，封存的 Lync 通訊的檔案儲存在使用者的 Exchange 2013 伺服器的 Exchange 2013 及位於 Exchange 伺服器。

</div>

<span> </span>

</div>

</div>

</div>

