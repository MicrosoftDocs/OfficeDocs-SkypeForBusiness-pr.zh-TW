---
title: Lync Server 2013：在全域層級設定封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21653d38c7b56fa93395422a2e20906afd0cc3e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="aafc0-102">在 Lync Server 2013 的全域層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="aafc0-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aafc0-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="aafc0-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="aafc0-104">當您在拓撲中新增封存併發布拓撲時，Lync Server 會建立一個全域配置來進行封存。</span><span class="sxs-lookup"><span data-stu-id="aafc0-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="aafc0-105">根據預設，全域配置中不會啟用任何存檔選項。</span><span class="sxs-lookup"><span data-stu-id="aafc0-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="aafc0-106">全域設定會控制為整個部署啟用哪些選項，除非您設定網站或池設定，而這會覆寫全域配置。</span><span class="sxs-lookup"><span data-stu-id="aafc0-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="aafc0-107">如需有關存檔設定的運作方式（包括全域、網站和池設定的階層），請參閱在規劃檔、部署檔或作業檔中的 [ [Lync Server 2013 存檔] 的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="aafc0-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aafc0-108">在啟用封存前，您應該先在封存配置中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="aafc0-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="aafc0-109">在全域層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="aafc0-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="aafc0-110">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="aafc0-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aafc0-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="aafc0-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="aafc0-112">如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aafc0-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aafc0-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="aafc0-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="aafc0-114">在 [**存檔**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="aafc0-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="aafc0-115">在 [**編輯封存設定-全域**] 中的 [**存檔設定**] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="aafc0-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="aafc0-116">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="aafc0-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="aafc0-117">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="aafc0-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="aafc0-118">**封存 IM 與 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="aafc0-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="aafc0-119">此外，在 [**編輯存檔設定–全域**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="aafc0-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="aafc0-120">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="aafc0-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="aafc0-121">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="aafc0-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="aafc0-122">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="aafc0-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="aafc0-123">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="aafc0-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="aafc0-124">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="aafc0-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="aafc0-125">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aafc0-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

