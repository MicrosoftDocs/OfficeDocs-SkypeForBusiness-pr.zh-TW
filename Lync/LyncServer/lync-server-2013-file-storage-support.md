---
title: Lync Server 2013 檔案儲存支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b870aa22d9dea13e84f045af8fc6fe800fb3d55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Lync Server 2013 中的檔案儲存支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10-16_

Lync Server 2013 使用相同的檔案存放區的所有檔案儲存空間。 檔案儲存支援包括下列各項：

  - 檔案共用上直接連接儲存裝置 (DAS) 或儲存區域網路 (SAN)，包括分散式檔案系統 (DFS)，且在備援獨立磁碟陣列 (RAID 的檔案存放區)。 如需儲存需求的詳細資訊，請參閱規劃文件中的[前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態的技術需求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)和[Lync Server 2013 中 director 的硬體和軟體需求](lync-server-2013-hardware-and-software-requirements-for-the-director.md)。 如需 DFS Windows Server 2008 作業系統的詳細資訊，請參閱 DFS 逐步指南的 Windows Server 2008 在[https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)。

  - 共用的檔案共用叢集。 如果您使用共用的叢集，您應該使用執行 Windows Server 2008 或 Windows Server 2008 R2 叢集伺服器。 使用叢集伺服器執行較舊版本的 Windows，可能會造成權限問題阻止部分功能不會出現。 使用 [叢集系統管理員建立檔案共用。 如需使用 [叢集系統管理員的詳細資訊，請參閱 Microsoft 知識庫文章 284838，」 方式來建立伺服器叢集檔案共用與 Cluster.exe" [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)。

</div>

<span> </span>

</div>

</div>

</div>

