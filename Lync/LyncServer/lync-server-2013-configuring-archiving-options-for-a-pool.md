---
title: Lync Server 2013：設定集區的封存選項
description: Lync Server 2013：設定集區的封存選項。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3b28fd12fab5883e3be319bec169d13c539b1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562569"
---
# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="75575-103">在 Lync Server 2013 中設定集區的封存選項</span><span class="sxs-lookup"><span data-stu-id="75575-103">Configuring Archiving options for a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75575-104">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="75575-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="75575-105">您可以在每個集區的封存設定中建立及設定選項，以指定要套用至特定集區的封存選項。</span><span class="sxs-lookup"><span data-stu-id="75575-105">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools.</span></span> <span data-ttu-id="75575-106">集區設定會覆寫全域設定和網站設定，但僅限於集區設定中所指定的集區。</span><span class="sxs-lookup"><span data-stu-id="75575-106">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="75575-107">如需有關封存設定如何運作（包括全域、網站及集區設定的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="75575-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75575-108">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="75575-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="75575-109">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="75575-109">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="75575-110">在集區層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="75575-110">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="75575-111">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="75575-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75575-112">開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="75575-112">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="75575-113">如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="75575-113">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75575-114">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="75575-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="75575-115">**在 [封存**設定] 頁面上，按一下 [**新增**]，然後按一下 [**集**區設定]。</span><span class="sxs-lookup"><span data-stu-id="75575-115">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="75575-116">在 [ **選取服務**] 中，選取要設定封存的集區。</span><span class="sxs-lookup"><span data-stu-id="75575-116">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="75575-117">在 [ **新增封存設定**] 的 [封存 **設定** ] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="75575-117">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="75575-118">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="75575-118">**Disable archiving**</span></span>
    
      - <span data-ttu-id="75575-119">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="75575-119">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="75575-120">**封存 IM 和 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="75575-120">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="75575-121">在 [ **新增封存設定** ] 頁面中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="75575-121">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="75575-122">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75575-122">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="75575-123">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75575-123">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="75575-124">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="75575-124">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="75575-125">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="75575-125">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="75575-126">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="75575-126">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="75575-127">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="75575-127">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

