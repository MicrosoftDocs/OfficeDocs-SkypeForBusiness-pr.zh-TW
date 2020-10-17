---
title: Lync Server 2013：啟用或停用與 Exchange storage 的整合
description: Lync Server 2013：啟用或停用與 Exchange storage 的整合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42d140bd99bdc4aa86bea2f6ad310c4e06f06faf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546539"
---
# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="3b2d8-103">啟用或停用與 Exchange storage 的 Lync Server 2013 整合</span><span class="sxs-lookup"><span data-stu-id="3b2d8-103">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b2d8-104">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="3b2d8-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="3b2d8-105">在 [Lync Server 2013 控制台] 中，您可以使用封存設定來啟用及停用與 Exchange 儲存的整合。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-105">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="3b2d8-106">這包含下列封存組態：</span><span class="sxs-lookup"><span data-stu-id="3b2d8-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="3b2d8-107">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="3b2d8-108">選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="3b2d8-109">如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="3b2d8-110">啟用或停用 Microsoft Exchange storage 的整合</span><span class="sxs-lookup"><span data-stu-id="3b2d8-110">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="3b2d8-111">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b2d8-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b2d8-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b2d8-114">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="3b2d8-115">按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯]\*\*\*\* 和 [顯示詳細資料]\*\*\*\*，然後執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3b2d8-115">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="3b2d8-116">若要啟用與 Exchange 2013 儲存的整合，請選取 [ **Microsoft Exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-116">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="3b2d8-117">若要停用 Exchange 2013 儲存的整合，請清除 [ **Microsoft Exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-117">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="3b2d8-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="3b2d8-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b2d8-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3b2d8-119">See Also</span></span>


[<span data-ttu-id="3b2d8-120">Lync Server 2013 中的封存運作方式</span><span class="sxs-lookup"><span data-stu-id="3b2d8-120">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="3b2d8-121">為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="3b2d8-121">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

