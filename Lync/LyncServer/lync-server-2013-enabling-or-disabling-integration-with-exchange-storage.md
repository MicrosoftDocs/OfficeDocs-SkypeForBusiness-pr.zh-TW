---
title: Lync Server 2013：啟用或停用 Exchange 儲存體整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d2ded7e4cf586faf1f15ea6205aa23802413dc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="0c069-102">啟用或停用 Lync Server 2013 與 Exchange 儲存空間的整合</span><span class="sxs-lookup"><span data-stu-id="0c069-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c069-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0c069-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0c069-104">在 Lync Server 2013 [控制台] 中，您可以使用封存配置來啟用和停用 Exchange 儲存。</span><span class="sxs-lookup"><span data-stu-id="0c069-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="0c069-105">這包括下列歸檔設定：</span><span class="sxs-lookup"><span data-stu-id="0c069-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="0c069-106">當您部署 Lync Server 2013 時預設會建立的全域配置。</span><span class="sxs-lookup"><span data-stu-id="0c069-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0c069-107">您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。</span><span class="sxs-lookup"><span data-stu-id="0c069-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="0c069-108">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="0c069-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="0c069-109">啟用或停用 Microsoft Exchange 儲存空間的整合</span><span class="sxs-lookup"><span data-stu-id="0c069-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="0c069-110">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0c069-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0c069-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="0c069-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0c069-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0c069-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0c069-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="0c069-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="0c069-114">在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0c069-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="0c069-115">若要啟用與 Exchange 2013 儲存空間的整合，請選取 [ **Microsoft Exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0c069-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="0c069-116">若要停用 Exchange 2013 儲存區的整合，請清除 [ **Microsoft Exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0c069-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="0c069-117">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c069-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c069-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="0c069-118">See Also</span></span>


[<span data-ttu-id="0c069-119">存檔在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="0c069-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="0c069-120">管理您組織、網站和池的 Lync Server 2013 中的封存配置選項</span><span class="sxs-lookup"><span data-stu-id="0c069-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

