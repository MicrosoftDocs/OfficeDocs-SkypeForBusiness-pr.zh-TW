---
title: Lync Server 2013： 監控 IIS 要求的追蹤記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4eb6d1ec984d09f3868ad621add52fb947dd13b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>監控 IIS 要求在 Lync Server 2013 中的追蹤記錄檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

當您啟用網際網路資訊服務 (IIS) 要求的追蹤的 Lync Server Mobility Service (Mcx) 時，所產生的記錄檔可能會耗用最多三個 gb 的每日的磁碟空間。 依預設會啟用 IIS 追蹤記錄。 您應該監視前端伺服器若要確定，他們無法執行磁碟空間不足。

根據預設，IIS 會儲存在 %systemdrive%並記錄檔\\inetpub\\記錄\\記錄檔。

若要關閉 IIS 要求的追蹤整部伺服器，請在命令列中輸入下列命令：

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

如需**httpLogging**命令的詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927)。

</div>

<span> </span>

</div>

</div>

</div>

