---
title: 使用拓撲產生器合併嚮導進行合併
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="4accb-102">使用拓撲產生器合併嚮導進行合併</span><span class="sxs-lookup"><span data-stu-id="4accb-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4accb-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4accb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="4accb-104">使用拓撲建立器下載現有的部署。</span><span class="sxs-lookup"><span data-stu-id="4accb-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="4accb-105">從 [**動作**] 功能表中，選取 [**合併 Office 通訊伺服器 2007 R2**]。</span><span class="sxs-lookup"><span data-stu-id="4accb-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="4accb-106">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-106">Click **Next**.</span></span>

4.  <span data-ttu-id="4accb-107">在 [**指定邊緣設定**] 中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4accb-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="4accb-108">![合併拓撲精靈，[指定 Edge 安裝] 頁面](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "合併拓撲精靈，[指定 Edge 安裝] 頁面")</span><span class="sxs-lookup"><span data-stu-id="4accb-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="4accb-109">在 [**指定邊緣類型**] 中，輸入邊緣伺服器設定的類型，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="4accb-110">這個範例使用 [**單一邊緣伺服器**] 選項。</span><span class="sxs-lookup"><span data-stu-id="4accb-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4accb-111">已<STRONG>展開的邊緣部署</STRONG>不是受支援的配置。</span><span class="sxs-lookup"><span data-stu-id="4accb-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="4accb-112"><STRONG>展開的邊緣伺服器</STRONG>必須先轉換為<STRONG>單一邊緣伺服器</STRONG>或<STRONG>負載平衡的合併邊緣</STRONG>伺服器。</span><span class="sxs-lookup"><span data-stu-id="4accb-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="4accb-113">在 [**指定內部邊緣設定**] 中，視需要輸入邊緣池的內部 FQDN 和埠相關資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="4accb-114">![[指定內部 Edge 設定] 對話方塊](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "[指定內部 Edge 設定] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="4accb-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="4accb-115">在 [**指定外部邊緣**] 中，輸入 Edge 伺服器的網路會議 FQDN 資訊。</span><span class="sxs-lookup"><span data-stu-id="4accb-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4accb-116">在您按一下<STRONG>[下一步]</STRONG>之前，請先執行此程式中的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="4accb-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="4accb-117">請務必不要錯過此步驟。</span><span class="sxs-lookup"><span data-stu-id="4accb-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="4accb-118">如果您打算將舊版 Office 通訊伺服器 2007 R2 Edge 伺服器用於同盟，請核取 [**此 Edge 池適用于同盟與公用 IM**連線] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4accb-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="4accb-119">如果您部署了多個 Edge 伺服器，則只有其中一個是針對同盟啟用。</span><span class="sxs-lookup"><span data-stu-id="4accb-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="4accb-120">如果您不選取此方塊，且稍後決定要啟用同盟，您必須執行 [拓撲建立器合併] 嚮導並再次發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="4accb-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="4accb-121">![Edge Server 對話方塊，[指定外部 Edge] 頁面](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server 對話方塊，[指定外部 Edge] 頁面")</span><span class="sxs-lookup"><span data-stu-id="4accb-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="4accb-122">在 **[指定下一個躍點]** 中，輸入您環境中下一個躍點位置的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="4accb-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="4accb-123">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="4accb-124">![Edge Server 對話方塊，[指定下一個躍點] 頁面](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server 對話方塊，[指定下一個躍點] 頁面")</span><span class="sxs-lookup"><span data-stu-id="4accb-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="4accb-125">在 [**指定邊緣設定**] 中，如果已新增所有 Office 通訊伺服器 2007 R2 Edge 伺服器，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="4accb-126">如果您要新增更多 Office 通訊伺服器 2007 R2 Edge 伺服器，請從步驟4開始重複此程式。</span><span class="sxs-lookup"><span data-stu-id="4accb-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="4accb-127">在 [**指定內部 SIP 埠**] 中，選取預設設定（也就是如果您未修改預設的 SIP 埠）。</span><span class="sxs-lookup"><span data-stu-id="4accb-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="4accb-128">如果您不是使用預設埠5061，請視需要變更，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="4accb-129">在 [**摘要**] 中，按一下 **[下一步]** 以開始合併拓撲。</span><span class="sxs-lookup"><span data-stu-id="4accb-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="4accb-130">[嚮導] 頁面會確認拓撲的合併已成功完成。</span><span class="sxs-lookup"><span data-stu-id="4accb-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="4accb-131">在 [**狀態**] 欄中，確認此值為 [**成功**]，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="4accb-132">在 [拓撲建立器] 的左窗格中，您現在應該會看到 [ **BackCompatSite**]，表示您的 Office 通訊伺服器 2007 R2 環境已與 Lync Server 2013 合併。</span><span class="sxs-lookup"><span data-stu-id="4accb-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="4accb-133">![顯示合併拓撲的拓撲產生器](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "顯示合併拓撲的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="4accb-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="4accb-134">在 [**動作**] 功能表中，按一下 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="4accb-135">**發佈嚮導**完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4accb-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4accb-136">您必須完成下一個主題、匯<A href="import-policies-and-settings.md">入原則和設定</A>，以確保將舊版原則設定匯入 Lync Server 2013，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="4accb-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

