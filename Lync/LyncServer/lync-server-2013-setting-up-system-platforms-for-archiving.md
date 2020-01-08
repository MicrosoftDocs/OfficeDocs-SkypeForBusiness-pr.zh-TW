---
title: Lync Server 2013：設定用於存檔的系統平臺
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定存檔的系統平臺

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

開始部署封存前，您必須在符合系統需求的硬體上安裝所需的作業系統及任何其他必備軟體：

  - **Lync server 2013 platform**   lync server 2013 部署沒有存檔伺服器。 相反地，整合的資料收集代理程式會在前端伺服器和標準版伺服器上執行，以捕獲資料以進行封存，因此不需要個別的系統平臺即可託管封存。

  - **資料儲存平臺**   在 Lync Server 2013 中，您可以使用下列其中一種方法來儲存資料：
    
      - **Microsoft Exchange 整合**   如果您想要使用 Exchange 2013 部署來儲存 Lync Server 2013 存檔資料，而不是或除了針對儲存在歸檔資料的另一個資料庫之外，您的 exchange 部署必須執行 exchange 2013。 如需設定 Exchange 2013 的系統平臺的詳細資料，請參閱 Exchange 產品檔。
    
      - **SQL server**   如果您想要使用個別的 sql server 資料庫儲存歸檔資料，而不是使用 Microsoft Exchange 整合，您必須先設定資料庫的系統平臺，然後再部署歸檔。 特定的系統平臺需求取決於您是否使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 進行歸檔資料庫。 如需針對這些資料庫設定系統平臺的詳細資料，請參閱 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 產品檔。

  - **檔案伺服器平臺**   Lync server 2013 會將 Lync server 存檔檔案儲存在您設定前端伺服器或標準版伺服器時，您針對檔案儲存區所指定的相同位置。 您不能指定單獨的位置來儲存檔案儲存空間，因此不需要個別的系統平臺就能儲存檔案。 如果您使用 Microsoft Exchange 整合，Exchange 2013 將檔案儲存在 exchange 2013 伺服器上，以供駐留在這些 Exchange 伺服器上的使用者使用。

</div>

<span> </span>

</div>

</div>

</div>

