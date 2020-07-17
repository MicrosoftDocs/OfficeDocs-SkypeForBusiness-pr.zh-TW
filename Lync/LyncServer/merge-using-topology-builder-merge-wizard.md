---
title: 使用拓撲產生器合併嚮導進行合併
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="c9b15-102">使用拓撲產生器合併嚮導進行合併</span><span class="sxs-lookup"><span data-stu-id="c9b15-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9b15-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c9b15-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="c9b15-104">使用拓撲產生器下載現有的部署。</span><span class="sxs-lookup"><span data-stu-id="c9b15-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="c9b15-105">從 [**動作**] 功能表中，選取 [**合併 Office 通訊伺服器 2007 R2**]。</span><span class="sxs-lookup"><span data-stu-id="c9b15-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="c9b15-106">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-106">Click **Next**.</span></span>

4.  <span data-ttu-id="c9b15-107">在 [指定 Edge 安裝]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="c9b15-108">![合併拓撲嚮導的 [指定 Edge 安裝] 頁面](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "合併拓撲嚮導的 [指定 Edge 安裝] 頁面")</span><span class="sxs-lookup"><span data-stu-id="c9b15-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="c9b15-109">在 [指定 Edge 類型]\*\*\*\* 中，輸入 Edge Server 設定類型，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="c9b15-110">此範例使用 [單一 Edge Server]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="c9b15-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c9b15-111"><STRONG>擴充的 Edge 部署</STRONG>不是支援的設定。</span><span class="sxs-lookup"><span data-stu-id="c9b15-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="c9b15-112"><STRONG>擴充的 Edge server</STRONG>必須先轉換成<STRONG>單一 Edge server</STRONG>或<STRONG>負載平衡的合併 Edge</STRONG> server。</span><span class="sxs-lookup"><span data-stu-id="c9b15-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="c9b15-113">在 [**指定內部 Edge 設定**] 中，視需要輸入您 Edge 集區的內部 FQDN 與埠相關資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9b15-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="c9b15-114">![[指定內部 Edge 設定] 對話方塊](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "[指定內部 Edge 設定] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="c9b15-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="c9b15-115">在 [指定外部 Edge]\*\*\*\* 中，為您的 Edge Server 輸入 Web 會議 FQDN 資訊。</span><span class="sxs-lookup"><span data-stu-id="c9b15-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c9b15-116">在您按 [下一步]<STRONG></STRONG> 之前，請先執行本程序的下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="c9b15-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="c9b15-117">請勿錯過此步驟是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="c9b15-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="c9b15-118">如果您打算使用舊版 Office 通訊伺服器 2007 R2 Edge Server 進行同盟，請選取 [**此 Edge 集區用於同盟與公用 IM**連線] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c9b15-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="c9b15-119">如果您已部署多部 Edge Server，當中只有一部會啟用同盟功能。</span><span class="sxs-lookup"><span data-stu-id="c9b15-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="c9b15-120">如果您未勾選此方塊，且您稍後決定要啟用同盟，您必須執行拓撲產生器合併嚮導，並再次發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="c9b15-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="c9b15-121">![[Edge Server] 對話方塊中的 [指定外部 Edge] 頁面](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "[Edge Server] 對話方塊中的 [指定外部 Edge] 頁面")</span><span class="sxs-lookup"><span data-stu-id="c9b15-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="c9b15-122">在 [指定下一個躍點]\*\*\*\* 中，輸入您環境中下一個躍點位置的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c9b15-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="c9b15-123">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="c9b15-124">![Edge Server 對話方塊，指定下一個躍點頁面](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server 對話方塊，指定下一個躍點頁面")</span><span class="sxs-lookup"><span data-stu-id="c9b15-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="c9b15-125">在 [**指定 Edge 設定**] 中，如果已新增所有 Office 通訊伺服器 2007 R2 Edge server，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9b15-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="c9b15-126">若要新增更多 Office 通訊伺服器 2007 R2 Edge Server，請從步驟4開始，重複此程式。</span><span class="sxs-lookup"><span data-stu-id="c9b15-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="c9b15-127">在 [**指定內部 SIP 埠**] 中，選取預設設定（亦即，如果您未修改預設 SIP 埠）。</span><span class="sxs-lookup"><span data-stu-id="c9b15-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="c9b15-128">若您不使用預設連接埠 5061，請視需要變更，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="c9b15-129">在 [摘要]\*\*\*\* 中按 [下一步]\*\*\*\*，以開始合併拓撲。</span><span class="sxs-lookup"><span data-stu-id="c9b15-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="c9b15-130">精靈頁面會驗證拓撲的合併是否成功。</span><span class="sxs-lookup"><span data-stu-id="c9b15-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="c9b15-131">在 [狀態]\*\*\*\* 欄位中，檢查其值是否為 [成功]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="c9b15-132">在 [拓撲產生器] 的左窗格中，您現在應該會看到**BackCompatSite**，這表示您的 Office 通訊伺服器 2007 R2 環境已與 Lync Server 2013 合併。</span><span class="sxs-lookup"><span data-stu-id="c9b15-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="c9b15-133">![顯示合併拓撲的拓撲產生器](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "顯示合併拓撲的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="c9b15-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="c9b15-134">從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9b15-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="c9b15-135">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b15-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9b15-136">請務必完成下一個主題：匯<A href="import-policies-and-settings.md">入原則及設定</A>，以確保將舊版原則設定匯入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c9b15-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

