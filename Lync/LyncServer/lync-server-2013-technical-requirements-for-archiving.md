---
title: Lync Server 2013：存檔的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中的存檔技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Lync Server 2013 的技術需求包括下列各項：

  - 基礎結構需求。

  - 必須針對歸檔進行安裝的必備軟體。

  - 存檔的資料儲存需求。

  - 針對您的封存部署調整需求和考慮。

  - 歸檔資料庫的效能需求和考慮。

<div>


> [!NOTE]  
> 在此 Lync Server 2013 版本中無法使用縮放和效能資訊。



</div>

<div>

## <a name="infrastructure-requirements"></a>基礎結構需求

Lync Server 2013 的 [存檔基礎結構需求] 與「部署 Lync Server 2013」是一樣的。 如需詳細資訊，請參閱在規劃檔中[判斷 Lync Server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)。

</div>

<div>

## <a name="archiving-prerequisites"></a>歸檔必備元件

Lync Server 2013 簡化了存檔的先決條件，原因如下：

  - 封存伺服器已不再是伺服器角色。 相反地，整合的資料收集代理程式是在 pool 及標準版伺服器的前端伺服器上執行，以捕獲資料以供歸檔，因此您不需要設定個別的系統平臺來進行封存。

  - 封存使用 Lync Server 2013 檔案儲存空間來暫時儲存會議內容檔案，因此您不需要設定個別的檔案存放區來進行封存。

  - 在 Lync Server 2013 中，不需要訊息佇列。

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>存檔的資料存儲需求

此外，您還需要設定儲存空間的基礎結構。 這包括下列其中一項或兩項：

  - **Microsoft Exchange 儲存空間**。 會議內容檔案（例如 PowerPoint 簡報）會封存為附件。 如果您想要使用 Microsoft Exchange 整合，讓 Lync 封存資料與 Exchange 合規性資料儲存在一起，您必須使用 Exchange 2013 進行 Exchange 部署，並確保最大儲存空間大小支援儲存會議內容檔案。 如果您使用 Microsoft Exchange 整合選項部署歸檔，Lync 封存資料只會儲存在 Exchange 2013 伺服器上的使用者的 Exchange 2013 合規性資料。 您必須先部署 Exchange 2013，然後才能使用 Microsoft Exchange 整合選項部署並啟用封存。 如果您選擇使用 Exchange 2013 儲存空間，就不需要部署個別的 SQL Server 資料庫來進行封存，除非您有不是駐留在 Exchange 2013 伺服器上的 Lync 使用者。

  - **用於存檔的 SQL Server 資料庫儲存空間**。 若要支援不是託管于 Exchange 2013 伺服器的使用者，或者不想使用 Microsoft Exchange 整合選項，您必須使用 SQL Server 資料庫部署封存儲存空間。 Lync Server 2013 支援下列64位版本的 SQL Server：
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 標準版
    
      - Microsoft SQL Server 2012 企業版
    
      - Microsoft SQL Server 2012 標準版
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express 及 Microsoft SQL Server 2012 Express 不支援封存。 不支援32位版本的 SQL Server。 如需其他 SQL Server 需求與限制，請參閱在規劃檔或支援檔中的<A href="lync-server-2013-database-software-support.md">Lync Server 2013 資料庫軟體支援</A>。

    
    </div>
    
    您必須先設定 SQL Server 平臺，然後才能部署並啟用封存。 如果要用來發佈拓朴的帳戶具有適當的管理員權力和許可權，您可以在發佈拓撲時建立封存資料庫（LcsLog）。 您也可以日後建立資料庫，包括安裝程式的一部分。 如需 SQL Server 的詳細資料，請參閱 SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)技術中心（位於）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

