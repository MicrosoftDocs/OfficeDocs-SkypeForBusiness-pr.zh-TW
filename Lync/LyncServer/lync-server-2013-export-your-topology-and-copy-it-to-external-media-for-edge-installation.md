---
title: 匯出拓撲並將拓撲複製到 edge 安裝的外部媒體
description: 匯出拓撲並將拓撲複製到 edge 安裝的外部媒體。
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
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564759"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>匯出 Lync Server 2013 拓撲，並將其複製到 edge 安裝的外部媒體

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

發行拓撲之後，Lync Server 部署嚮導必須存取中央管理存放區資料，以便在伺服器上啟動部署程式。 在內部網路中，可直接從伺服器存取資料，但不在內部網域中的 Edge Server 無法存取資料。 若要讓拓撲設定資料可用於 Edge Server 部署，您必須將拓撲資料匯出至檔案，並將它複製到外部媒體 (例如，在 Edge server 上執行 Lync Server 部署嚮導之前，可從 Edge Server 取得的 USB 磁片磁碟機或網路共用) 。 使用下列程式可讓您的拓撲設定資料可用於您要部署的 Edge Server。

<div>


> [!NOTE]
> 在 Edge Server 上安裝 Lync Server 2013 之後，您可以使用內部網路中的管理工具來管理 Edge Server，這會自動將設定複寫至部署中的任何 Edge server。 唯一例外是指派及安裝憑證，以及停止和啟動服務，這兩者都必須在 Edge Server 上執行。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面使拓撲資料可用於 Edge Server

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在 Lync Server 管理命令介面中，執行下列 Cmdlet：
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  將匯出的檔案複製到外部媒體 (例如，在部署) 時，可從 Edge Server 取得的 USB 磁片磁碟機或網路共用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

