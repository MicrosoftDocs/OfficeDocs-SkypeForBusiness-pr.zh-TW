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
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="deec2-102">在 Lync Server 2013 中使用備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="deec2-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deec2-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="deec2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="deec2-104">如果儲存在前端池檔案存放區中的會議資訊無法使用。</span><span class="sxs-lookup"><span data-stu-id="deec2-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="deec2-105">您必須還原此資訊，讓駐留在該池中的使用者保留其會議資料。</span><span class="sxs-lookup"><span data-stu-id="deec2-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="deec2-106">如果有遺失會議資料的前端池是與另一個前端池進行配對，您可以使用 [備份服務] 來還原資料。</span><span class="sxs-lookup"><span data-stu-id="deec2-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="deec2-107">如果整個池失敗，而且您必須將其使用者容錯移轉至備份池，也必須執行此工作。</span><span class="sxs-lookup"><span data-stu-id="deec2-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="deec2-108">當這些使用者傳回容錯移轉至原始池時，您必須使用此程式將其會議內容複寫回其原始池。</span><span class="sxs-lookup"><span data-stu-id="deec2-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="deec2-109">假設 Pool1 與 Pool2 成對，而 Pool1 中的會議資料遺失。</span><span class="sxs-lookup"><span data-stu-id="deec2-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="deec2-110">您可以使用下列 Cmdlet 來喚醒呼叫備份服務來還原內容：</span><span class="sxs-lookup"><span data-stu-id="deec2-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="deec2-111">還原會議內容可能需要一些時間，視其大小而定。</span><span class="sxs-lookup"><span data-stu-id="deec2-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="deec2-112">您可以使用下列 Cmdlet 來檢查進程狀態：</span><span class="sxs-lookup"><span data-stu-id="deec2-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="deec2-113">此程式會在此 Cmdlet 針對資料會議模組傳回穩定狀態的值時完成。</span><span class="sxs-lookup"><span data-stu-id="deec2-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

