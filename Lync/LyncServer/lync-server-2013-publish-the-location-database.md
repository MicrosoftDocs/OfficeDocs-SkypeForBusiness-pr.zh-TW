---
title: Lync Server 2013： 發佈位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b773e5332ba05d20da9ece0b7ecb521d664e3b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="edce7-102">發佈位置資料庫從 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edce7-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edce7-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="edce7-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="edce7-104">您加入至位置資料庫的新位置將不會成為提供給用戶端之前已發佈。</span><span class="sxs-lookup"><span data-stu-id="edce7-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="edce7-105">如需詳細資訊，請參閱 < Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="edce7-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="edce7-106">**發佈 CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="edce7-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="edce7-107">如果您使用緊急位置識別號碼 (ELIN) 閘道，您也需要將 Elin 上傳至您的公用交換的電話網路 (PSTN) 電信業者的自動位置識別 (ALI) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="edce7-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="edce7-108">您 PSTN 電信業者可能需要您使用 ELIN 記錄的特定格式。</span><span class="sxs-lookup"><span data-stu-id="edce7-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="edce7-109">如需詳細資訊，請連絡您 PSTN 電信業者。</span><span class="sxs-lookup"><span data-stu-id="edce7-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="edce7-110">您可以從位置資訊服務資料庫匯出記錄及它們格式化為必要。</span><span class="sxs-lookup"><span data-stu-id="edce7-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="edce7-111">若要發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="edce7-111">To publish the location database</span></span>

  - <span data-ttu-id="edce7-112">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="edce7-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="edce7-113">執行下列 cmdlet 以發佈位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="edce7-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

