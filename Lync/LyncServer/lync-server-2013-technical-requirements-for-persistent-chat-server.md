---
title: Lync Server 2013： Persistent Chat Server 的技術需求
description: Lync Server 2013： Persistent Chat Server 的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905563f31de36d41a48aea5fb8db3cfde9cb2434
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550329"
---
# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中 Persistent Chat Server 的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-06_

主控 Persistent Chat Server 的每一部電腦都必須能夠存取現有的 Lync Server 2013 拓撲，其元件如下：

  - **Lync server 2013，前端伺服器。**  前端伺服器是會話初始通訊協定 (SIP) 路由的基礎，它使得執行持續聊天伺服器的電腦與可能的持久聊天功能之間進行通訊。 在您開始部署 Persistent Chat Server 之前，請根據組織的需要，確認 Lync Server 2013、Standard Edition 或 Lync Server 前端集區和任何其他執行 Lync Server 之內部電腦的部署。

下列各節說明 Persistent Chat Server 和儲存 Persistent Chat 資料之資料庫的特定需求。

<div>

## <a name="persistent-chat-server-requirements"></a>Persistent Chat Server 需求

如需部署 Lync Server 的建議硬體及最新版本的 Persistent Chat Server 的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。

如需有關 Lync Server 和 Persistent Chat Server 之伺服器和工具作業系統支援的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

如需部署 Persistent Chat Server 所需之其他軟體的詳細資訊，請參閱下表。

### <a name="persistent-chat-server-software-prerequisites"></a>Persistent Chat Server 軟體必要條件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>軟體</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>訊息佇列</p></td>
<td><p>由 Persistent Chat Server 和 Persistent Chat 規章服務（若已部署）使用。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Persistent Chat Server 資料庫需求

Persistent Chat Server 會使用 Persistent Chat 資料庫來儲存聊天記錄、設定和使用者布建資料。 另外，它會使用 Persistent 聊天室規範資料庫來儲存規範資料。

<div>


> [!IMPORTANT]  
> Persistent Chat database (mgc) 與規範資料庫 (mgccomp) 可以位於相同的 SQL Server 實例或不同的 SQL Server 上。



</div>

若要準備資料庫伺服器平臺，請確定每一部電腦都符合硬體需求，然後安裝必要軟體。

Persistent Chat 資料庫伺服器的伺服器平臺需要與 Lync Server 後端資料庫伺服器相同的硬體。 如需詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。

在資料庫伺服器上，確定已安裝下列其中一個軟體應用程式：

  - Microsoft SQL Server 2012。 如需如何安裝 Microsoft SQL Server 2012 的詳細資訊，請參閱《安裝 SQL Server 2012 》 [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559) 。

  - Microsoft SQL Server 2008 R2。 如需如何安裝 Microsoft SQL Server 2008 R2 的詳細資訊，請參閱《 SQL server 安裝 (SQL Server 2008 R2) 》 [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702) 。

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Persistent Chat Server 憑證需求

如需取得憑證、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

