---
title: Lync Server 2013：還原回應群組設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d2b257fe2a77faacca588f2df5632d6476c673b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511400"
---
# <a name="restoring-response-group-settings-in-lync-server-2013"></a>在 Lync Server 2013 中還原回應群組設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

如果您已部署回應群組應用程式，而且您需要還原後端伺服器或 Standard Edition Server，您也需要還原回應群組設定。

<div>

## <a name="to-restore-response-group-configuration-settings"></a>還原回應群組組態設定

1.  在命令列中輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

