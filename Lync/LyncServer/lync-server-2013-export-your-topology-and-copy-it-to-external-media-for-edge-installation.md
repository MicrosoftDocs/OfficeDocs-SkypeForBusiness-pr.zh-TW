---
title: 匯出拓撲並將拓撲複製到 Edge 安裝的外部媒體
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
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>匯出 Lync Server 2013 拓撲並將拓撲複製到 Edge 安裝的外部媒體

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

發佈拓撲之後，Lync Server 部署嚮導需要存取中央管理儲存資料，才能在伺服器上啟動部署程式。 在內部網路中，您可以直接從伺服器取得資料，但不在內部網域中的邊緣伺服器無法存取資料。 若要讓拓撲設定資料可供邊緣伺服器部署使用，您必須將拓撲資料匯出到檔案，並將其複製到外部媒體（例如，在執行 Lync Server Dep 前，可從 Edge 伺服器取得的 USB 磁片磁碟機或網路共用）Edge 伺服器上的 [loyment] 嚮導。 使用下列程式，讓您的拓撲配置資料在您要部署的邊緣伺服器上可用。

<div>


> [!NOTE]
> 在邊緣伺服器上安裝 Lync Server 2013 之後，您可以使用內部網路中的管理工具來管理 Edge 伺服器，這會自動將設定複製到部署中的任何邊緣伺服器。 唯一的例外是指派並安裝憑證和停止及啟動服務，這兩者都必須在 Edge 伺服器上完成。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面，讓您的拓撲資料可在 Edge 伺服器上使用

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在 Lync Server 管理命令介面中，執行下列 Cmdlet：
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  將匯出的檔案複製到外部媒體（例如，在部署期間從 Edge 伺服器提供的 USB 磁片磁碟機或網路共用）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

