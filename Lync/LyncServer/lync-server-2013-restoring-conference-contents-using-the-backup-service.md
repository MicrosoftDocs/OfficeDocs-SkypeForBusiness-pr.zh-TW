---
title: Lync Server 2013： 還原會議內容使用備份服務
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
ms.openlocfilehash: c3aab42110bf1bf8eaafcebeddcd3acd168a80e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="c56fc-102">使用 Lync Server 2013 中備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="c56fc-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c56fc-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="c56fc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c56fc-p101">如果儲存在前端集區之檔案存放區中的會議資訊變成無法使用，則必須還原該資訊，讓位於集區的使用者得以保留其會議資料。如果遺失會議資料的前端集區有跟其他前端集區配對，則可以使用備份服務還原資料。</span><span class="sxs-lookup"><span data-stu-id="c56fc-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="c56fc-p102">如果整個集區失敗，而必須將使用者容錯移轉至備份集區，也必須執行此工作。當這些使用者容錯移轉回原始集區時，也必須使用此程序，將會議內容複製回原始集區。</span><span class="sxs-lookup"><span data-stu-id="c56fc-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="c56fc-109">假設 Pool1 與 Pool2 配對，而 Pool1 中的會議資料遺失。</span><span class="sxs-lookup"><span data-stu-id="c56fc-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="c56fc-110">您可以使用下列 cmdlet 來叫用的內容還原備份服務：</span><span class="sxs-lookup"><span data-stu-id="c56fc-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="c56fc-p104">視會議內容的大小而定，還原會議內容可能需要一些時間。可以使用下列 Cmdlet 檢查處理狀態：</span><span class="sxs-lookup"><span data-stu-id="c56fc-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="c56fc-113">當此 Cmdlet 傳回資料會議模組的「穩定狀態」值時，處理就已完成。</span><span class="sxs-lookup"><span data-stu-id="c56fc-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

