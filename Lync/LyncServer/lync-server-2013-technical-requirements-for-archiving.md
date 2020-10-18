---
title: Lync Server 2013：封存的技術需求
description: Lync Server 2013：封存的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6100753ad2c62424eb68c8c258094ba51848170e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577169"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中封存的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Lync Server 2013 技術需求包括下列各項：

  - 基礎結構需求。

  - 必須針對封存安裝的必要軟體。

  - 封存的資料儲存需求。

  - 封存部署的擴充需求和考慮。

  - 封存資料庫的效能需求和考慮。

<div>


> [!NOTE]  
> 在此 Lync Server 2013 版本中，無法使用調整和效能資訊。



</div>

<div>

## <a name="infrastructure-requirements"></a>基礎結構需求

Lync Server 2013 封存基礎結構需求與部署 Lync Server 2013 相同。 如需詳細資訊，請參閱規劃檔中的 [判斷您的 Lync Server 2013 基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md) 。

</div>

<div>

## <a name="archiving-prerequisites"></a>封存必要條件

Lync Server 2013 簡化封存的必要條件，原因如下：

  - 封存伺服器不再是伺服器角色。 相反地，整合的資料收集代理程式會在集區和 Standard Edition server 的前端伺服器上執行，以捕獲要封存的資料，因此您不會設定個別的系統平臺進行封存。

  - 封存使用 Lync Server 2013 檔案存放區來暫時儲存會議內容檔案，所以您不會設定個別的檔案存放區進行封存。

  - 在 Lync Server 2013 中，不需要訊息佇列。

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>封存的資料儲存需求

此外，您還需要設定封存儲存的基礎結構。 這包括下列其中一項或兩項：

  - **Microsoft Exchange storage**。 會議內容檔案（例如 PowerPoint 簡報）會封存為附件。 如果您想要使用 Microsoft Exchange 整合，讓 Lync 封存資料儲存在 Exchange 合規性資料中，您必須使用 Exchange 2013 進行 Exchange 部署，並確保儲存大小上限支援會議內容檔案的儲存。 如果您使用 Microsoft Exchange 整合選項部署封存，則只有位於 Exchange 2013 伺服器上的使用者才會儲存 Lync 封存資料與 Exchange 2013 相容性資料。 您必須先部署 Exchange 2013，再使用 Microsoft Exchange 整合選項部署及啟用封存。 如果您選擇使用 Exchange 2013 儲存區，除非您有未位於 Exchange 2013 伺服器的 Lync 使用者，否則不需要部署個別的 SQL Server 資料庫進行封存。

  - **用於封存的 SQL Server 資料庫儲存區**。 若要支援非位於 Exchange 2013 伺服器的使用者，或是不想要使用 Microsoft Exchange 整合選項，您必須使用 SQL Server 資料庫部署封存儲存區。 Lync Server 2013 支援下列64位版本的 SQL Server：
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支援封存。 不支援32位版本的 SQL Server。 如需其他 SQL Server 需求和限制，請參閱規劃檔或支援檔中的 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 中的資料庫軟體支援</A> 。

    
    </div>
    
    在部署及啟用封存之前，您必須先設定 SQL Server 平臺。 若要用來發行拓撲的帳戶具有適當的系統管理員許可權，您可以在發行拓撲時，建立封存資料庫 (LcsLog) 。 您也可以之後再建立資料庫，包括在安裝程序中。 如需 SQL Server 的詳細資訊，請參閱 SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

