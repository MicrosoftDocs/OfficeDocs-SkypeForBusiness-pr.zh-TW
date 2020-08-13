---
title: Lync Server 2013：設定網站的封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 818018a742a12a98b019375d9991393b1ddea37f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="bdbff-102">在 Lync Server 2013 中設定網站的封存選項</span><span class="sxs-lookup"><span data-stu-id="bdbff-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdbff-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="bdbff-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="bdbff-p101">您可以針對這其中的每一個網站，藉由在封存設定中建立和設定選項，以指定要套用至特定網站的封存選項。網站設定優先於全域設定，但僅適用於網站設定中指定的網站。集區設定優先於網站設定</span><span class="sxs-lookup"><span data-stu-id="bdbff-p101">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites. A site configuration overrides the global configuration, but only for the site specified in the site configuration. Pool configurations override site configurations</span></span>

<span data-ttu-id="bdbff-107">如需有關封存設定如何運作（包括全域、網站及集區設定的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存[在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="bdbff-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdbff-108">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="bdbff-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bdbff-109">若要啟用封存，您必須指定封存原則，以控制全域層級的內部和外部通訊的封存，以及在網站和使用者層級（如果適用）進行封存。</span><span class="sxs-lookup"><span data-stu-id="bdbff-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="bdbff-110">如果您設定使用者層級原則，您也必須將使用者原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="bdbff-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="bdbff-111">如需建立及設定封存原則的詳細資訊，請參閱 Operations 檔中的<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中的內部及外部通訊</A>的封存。</span><span class="sxs-lookup"><span data-stu-id="bdbff-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="bdbff-112">在網站層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="bdbff-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="bdbff-113">透過指派至 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="bdbff-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdbff-114">開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="bdbff-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="bdbff-115">如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱[Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bdbff-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdbff-116">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="bdbff-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="bdbff-117">在 **[封存組態]** 頁面上，按一下 **[新增]**，然後按一下 **[站台組態]**。</span><span class="sxs-lookup"><span data-stu-id="bdbff-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="bdbff-118">在 **[選取站台]** 中，選取要設定封存的網站。</span><span class="sxs-lookup"><span data-stu-id="bdbff-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="bdbff-119">在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="bdbff-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="bdbff-120">若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="bdbff-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="bdbff-121">若要同時啟用 IM 工作階段和會議的封存，請按一下 **[封存 IM 和 Web 會議工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="bdbff-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="bdbff-122">若要停用原則的封存，請按一下 **[停用封存]**。</span><span class="sxs-lookup"><span data-stu-id="bdbff-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="bdbff-123">此外，在 **[建立新的封存設定]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="bdbff-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="bdbff-124">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdbff-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="bdbff-125">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdbff-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="bdbff-126">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="bdbff-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="bdbff-127">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="bdbff-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="bdbff-128">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="bdbff-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="bdbff-129">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bdbff-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

