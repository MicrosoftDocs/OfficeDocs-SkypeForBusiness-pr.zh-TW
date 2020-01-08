---
title: Lync Server 2013：監視 IIS 要求追蹤記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中監視 IIS 要求追蹤記錄檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

當您針對 Lync Server 行動服務（Mcx）啟用 Internet Information Services （IIS）要求追蹤時，產生的記錄檔案每天最多可以消耗 3 gb 的磁碟空間。 預設會啟用 IIS 追蹤記錄。 您應該監視前端伺服器，以確保它們不會耗盡磁碟空間。

根據預設，IIS 會將記錄檔儲存在% SystemDrive\\%\\inetpub\\記錄日誌檔。

若要關閉整個伺服器的 IIS 要求追蹤，請在命令列中輸入下列內容：

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

如需**HTTPLogging**命令的詳細資訊， [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)請參閱。

</div>

<span> </span>

</div>

</div>

</div>

