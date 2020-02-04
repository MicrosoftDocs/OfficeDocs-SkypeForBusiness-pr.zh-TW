---
title: Lync Server 2013：持久聊天伺服器的技術需求
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
ms.openlocfilehash: 0437f56c5eb5564eb4f85809aefd181c2cbd2eaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持續聊天伺服器的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-06_

每個主持持久聊天伺服器的電腦都必須具備使用下列元件的現有 Lync Server 2013 拓撲的存取權：

  - **Lync Server 2013，前部端伺服器。** 前端伺服器是會話初始通訊協定（SIP）路由的基礎，可讓執行持續聊天伺服器的電腦與持久的聊天功能都能正常運作。 開始部署持續聊天伺服器之前，請先確認 Lync Server 2013、標準版或 Lync Server 前端池，以及任何其他執行 Lync Server 的內部電腦（視您的組織而定）。

下列各節說明持久聊天伺服器和儲存持續聊天資料之資料庫的特定需求。

<div>

## <a name="persistent-chat-server-requirements"></a>持續聊天伺服器需求

如需有關部署 Lync Server 及最新版本持久性聊天伺服器的建議硬體的詳細資料，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

如需有關 Lync Server 與永久聊天伺服器支援的伺服器和工具作業系統的詳細資訊，請參閱支援檔中的[Lync server 2013 中的 [伺服器與工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)]。

如需部署持久聊天伺服器所需的其他軟體的詳細資訊，請參閱下表。

### <a name="persistent-chat-server-software-prerequisites"></a>持續聊天伺服器軟體必備元件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>軟體</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>訊息佇列</p></td>
<td><p>持續聊天伺服器和持續聊天相容性服務（如果已部署）使用。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>持續聊天伺服器資料庫需求

持續聊天伺服器會使用持續聊天資料庫來儲存聊天記錄、設定和使用者供給資料。 您也可以使用持續性聊天規範資料庫來儲存合規性資料。

<div>


> [!IMPORTANT]  
> 持久聊天資料庫（mgc）和規範資料庫（mgccomp）可位於相同的 SQL Server 實例或不同的 SQL 伺服器上。



</div>

若要準備資料庫伺服器平臺，請確定每個電腦都符合硬體需求，然後再安裝必備軟體。

持續聊天資料庫伺服器的伺服器平臺需要與 Lync Server 後端資料庫伺服器相同的硬體。 如需詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

在資料庫伺服器上，請確定已安裝下列其中一個軟體應用程式：

  - Microsoft SQL Server 2012。 如需有關如何安裝 Microsoft SQL Server 2012 的詳細資訊，請參閱「安裝 SQL Server [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)2012」。

  - Microsoft SQL Server 2008 R2。 如需有關如何安裝 Microsoft SQL Server 2008 R2 的詳細資料，請參閱「SQL Server 安裝（SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)）」。

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>持續聊天伺服器憑證需求

如需取得證書、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

