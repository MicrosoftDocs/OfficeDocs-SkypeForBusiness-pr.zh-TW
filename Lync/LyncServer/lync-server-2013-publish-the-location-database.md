---
title: Lync Server 2013：發佈位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afc13a67ccdad3d27328107e095f1bffa66fdcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="cf4ea-102">從 Lync Server 2013 發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="cf4ea-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf4ea-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="cf4ea-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="cf4ea-104">您新增至位置資料庫的新位置將不會提供給用戶端，直到它們發佈為止。</span><span class="sxs-lookup"><span data-stu-id="cf4ea-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="cf4ea-105">如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="cf4ea-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="cf4ea-106">**發佈-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cf4ea-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="cf4ea-107">如果您使用緊急位置身分識別號碼（ELIN）閘道，您也需要將 ELINs 上傳到您的公用交換電話網絡</span><span class="sxs-lookup"><span data-stu-id="cf4ea-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="cf4ea-108">您的 PSTN 載波可能會要求您針對 ELIN 記錄使用特定的格式。</span><span class="sxs-lookup"><span data-stu-id="cf4ea-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="cf4ea-109">如需詳細資訊，請與您的 PSTN 運營商聯繫。</span><span class="sxs-lookup"><span data-stu-id="cf4ea-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="cf4ea-110">您可以從位置資訊服務資料庫匯出記錄，並根據需要設定其格式。</span><span class="sxs-lookup"><span data-stu-id="cf4ea-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="cf4ea-111">發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="cf4ea-111">To publish the location database</span></span>

  - <span data-ttu-id="cf4ea-112">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="cf4ea-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="cf4ea-113">執行下列 Cmdlet 來發佈位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="cf4ea-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

