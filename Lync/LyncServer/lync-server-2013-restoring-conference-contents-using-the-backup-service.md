---
title: Lync Server 2013：使用備份服務還原會議內容
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252cdf6713db7fcb3c4658cc4adb0eb51905c1ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511446"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用備份服務還原會議內容

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果儲存在前端集區之檔案存放區中的會議資訊變成無法使用，則必須還原該資訊，讓位於集區的使用者得以保留其會議資料。如果遺失會議資料的前端集區有跟其他前端集區配對，則可以使用備份服務還原資料。

如果整個集區失敗，而必須將使用者容錯移轉至備份集區，也必須執行此工作。當這些使用者容錯移轉回原始集區時，也必須使用此程序，將會議內容複製回原始集區。

假設 Pool1 與 Pool2 配對，而 Pool1 中的會議資料遺失。 您可以使用下列 Cmdlet 來調用備份服務，以還原內容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

視會議內容的大小而定，還原會議內容可能需要一些時間。可以使用下列 Cmdlet 檢查處理狀態：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

當此 Cmdlet 傳回資料會議模組的「穩定狀態」值時，處理就已完成。

</div>

<span> </span>

</div>

</div>

</div>

