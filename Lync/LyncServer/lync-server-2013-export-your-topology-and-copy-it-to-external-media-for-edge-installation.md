---
title: 匯出拓撲並將它複製到邊緣安裝的外部媒體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1637b711d2743d5a2e1fb8a5138949fc3a21ec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>匯出您的 Lync Server 2013 拓撲，並將它複製到邊緣安裝的外部媒體

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

發行拓撲之後，[Lync Server 部署精靈會需要存取中央管理存放區資料才能在伺服器上啟動部署程序。 在內部網路中，資料無法直接從伺服器，但不在內部網域中的 Edge Server 無法存取的資料。 您必須要使用 Edge Server 部署的拓撲組態資料，請將拓撲資料匯出至檔案，並將它複製到外部媒體 （例如 USB 磁碟機或可從 Edge Server 的網路共用） 在執行 Lync Server Dep 之前loyment Edge Server 上的精靈。 使用下列程序以在您要部署 Edge Server 上提供您的拓撲組態資料。

<div>


> [!NOTE]
> Edge Server 上安裝 Lync Server 2013 之後，您會管理 Edge Server 使用的系統管理工具在內部網路中，這會自動將設定複寫到您在部署中任何 Edge Server。 唯一的例外是指派安裝憑證並停止及啟動服務，這兩種都必須完成 Edge Server 上。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>若要使用您的拓撲資料 Edge Server 上使用 Lync Server 管理命令介面

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在 Lync Server 管理命令介面中，執行下列 cmdlet:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  將匯出的檔案複製到外部媒體 （例如 USB 磁碟機或在部署期間可從 Edge Server 的網路共用）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

