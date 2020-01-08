---
title: Lync Server 2013：使用備份服務還原會議內容
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用備份服務還原會議內容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果儲存在前端池檔案存放區中的會議資訊無法使用。 您必須還原此資訊，讓駐留在該池中的使用者保留其會議資料。 如果有遺失會議資料的前端池是與另一個前端池進行配對，您可以使用 [備份服務] 來還原資料。

如果整個池失敗，而且您必須將其使用者容錯移轉至備份池，也必須執行此工作。 當這些使用者傳回容錯移轉至原始池時，您必須使用此程式將其會議內容複寫回其原始池。

假設 Pool1 與 Pool2 成對，而 Pool1 中的會議資料遺失。 您可以使用下列 Cmdlet 來喚醒呼叫備份服務來還原內容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

還原會議內容可能需要一些時間，視其大小而定。 您可以使用下列 Cmdlet 來檢查進程狀態：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

此程式會在此 Cmdlet 針對資料會議模組傳回穩定狀態的值時完成。

</div>

<span> </span>

</div>

</div>

</div>

