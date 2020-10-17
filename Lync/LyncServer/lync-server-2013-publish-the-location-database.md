---
title: Lync Server 2013：發佈位置資料庫
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
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512370"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="bd51f-102">從 Lync Server 2013 發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="bd51f-102">Publish the location database from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd51f-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="bd51f-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="bd51f-104">在發佈之前，您新增至位置資料庫的新位置將不會供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="bd51f-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="bd51f-105">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bd51f-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="bd51f-106">**Export-cslisconfiguration 發佈**</span><span class="sxs-lookup"><span data-stu-id="bd51f-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="bd51f-107">如果您使用緊急位置識別號碼 (ELIN) 閘道，您也必須將 Elin 上傳至您公用交換電話網路 (PSTN) 電信公司的自動位置識別， (阿裡) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="bd51f-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="bd51f-108">您的 PSTN 電信公司可能需要使用特定的 ELIN 記錄格式。</span><span class="sxs-lookup"><span data-stu-id="bd51f-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="bd51f-109">如需詳細資訊，請與您的 PSTN 電信公司聯繫。</span><span class="sxs-lookup"><span data-stu-id="bd51f-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="bd51f-110">您可以匯出位置資訊服務資料庫中的記錄，並視需要進行格式化。</span><span class="sxs-lookup"><span data-stu-id="bd51f-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="bd51f-111">發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="bd51f-111">To publish the location database</span></span>

  - <span data-ttu-id="bd51f-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bd51f-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="bd51f-113">執行下列 Cmdlet 來發佈位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="bd51f-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

