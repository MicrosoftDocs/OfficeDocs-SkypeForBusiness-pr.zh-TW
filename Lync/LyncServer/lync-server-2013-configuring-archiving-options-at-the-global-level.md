---
title: Lync Server 2013：設定全域層級的封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3798d64ba8a2252058756b04b51481e90bdf95c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="e5bf5-102">在 Lync Server 2013 中設定全域層級的封存選項</span><span class="sxs-lookup"><span data-stu-id="e5bf5-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5bf5-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e5bf5-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e5bf5-104">當您將封存新增至拓撲併發行拓撲時，Lync Server 會建立通用設定進行封存。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="e5bf5-105">根據預設，全域設定中不會啟用任何封存選項。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="e5bf5-106">全域設定會控制針對整個部署啟用哪些選項，除非您設定的網站或集區設定會覆寫全域設定。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="e5bf5-107">如需有關封存設定如何運作（包括全域、網站及集區設定的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5bf5-108">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="e5bf5-109">在全域層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="e5bf5-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="e5bf5-110">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5bf5-111">開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="e5bf5-112">如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5bf5-113">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="e5bf5-114">**在 [封存**設定] 頁面上，依序按一下 [**全域**]、[**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e5bf5-115">在 [ **編輯封存設定-全域**] 的 [封存 **設定** ] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="e5bf5-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="e5bf5-116">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="e5bf5-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="e5bf5-117">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="e5bf5-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="e5bf5-118">**封存 IM 和 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="e5bf5-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="e5bf5-119">此外，在 [ **編輯封存設定–通用** ] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e5bf5-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="e5bf5-120">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="e5bf5-121">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="e5bf5-122">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="e5bf5-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="e5bf5-123">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="e5bf5-124">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="e5bf5-125">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e5bf5-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

