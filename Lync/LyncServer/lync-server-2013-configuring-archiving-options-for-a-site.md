---
title: Lync Server 2013：配置網站的封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="67264-102">在 Lync Server 2013 中設定網站的存檔選項</span><span class="sxs-lookup"><span data-stu-id="67264-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67264-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="67264-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="67264-104">您可以在每個網站的存檔設定中建立及設定選項，來指定要套用到特定網站的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="67264-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="67264-105">網站設定會覆寫全域配置，但僅適用于網站設定中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="67264-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="67264-106">池配置會覆寫網站配置</span><span class="sxs-lookup"><span data-stu-id="67264-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="67264-107">如需有關存檔設定的運作方式（包括全域、網站和池設定的階層），請參閱在規劃檔、部署檔或作業檔中的 [ [Lync Server 2013 存檔] 的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="67264-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67264-108">在啟用封存前，您應該先在封存配置中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="67264-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="67264-109">若要啟用封存，您必須指定封存原則，以控制全域階層的內部與外部通訊（如果適用的話）與網站和使用者層級的存檔。</span><span class="sxs-lookup"><span data-stu-id="67264-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="67264-110">如果您設定使用者層級原則，您也必須將使用者原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="67264-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="67264-111">如需建立及設定封存原則的詳細資料，請參閱在作業檔中<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 內的內部和外部通訊</A>。</span><span class="sxs-lookup"><span data-stu-id="67264-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="67264-112">在網站層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="67264-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="67264-113">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="67264-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67264-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="67264-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="67264-115">如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="67264-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67264-116">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="67264-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="67264-117">在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="67264-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="67264-118">在 [**選取網站**] 中，選取要設定為要存檔的網站。</span><span class="sxs-lookup"><span data-stu-id="67264-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="67264-119">在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="67264-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="67264-120">若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。</span><span class="sxs-lookup"><span data-stu-id="67264-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="67264-121">若要在 IM 會話與會議中啟用封存功能，請按一下 [封存**im 和網路會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="67264-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="67264-122">若要停用原則封存，請按一下 [**停**用封存]。</span><span class="sxs-lookup"><span data-stu-id="67264-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="67264-123">此外，在 [新增封存]**設定**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="67264-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="67264-124">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="67264-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="67264-125">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="67264-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="67264-126">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="67264-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="67264-127">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="67264-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="67264-128">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="67264-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="67264-129">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67264-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

