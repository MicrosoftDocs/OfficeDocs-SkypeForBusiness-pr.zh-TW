---
title: 在共存案例中使用 Lync Server 2010 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529920"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="63d97-102">在共存案例中使用 Lync Server 2010 管理套件</span><span class="sxs-lookup"><span data-stu-id="63d97-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63d97-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="63d97-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="63d97-104">許多客戶在其企業中採用推廣計畫，讓使用者從 Microsoft Lync Server 2010 逐步遷移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="63d97-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="63d97-105">這些公司的系統管理員會關心監控這兩種版本的 Lync Server，以協助確保他們的所有使用者都能取得最佳的通訊體驗。</span><span class="sxs-lookup"><span data-stu-id="63d97-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="63d97-106">在此案例中，Lync Server 2013 管理元件支援使用 Lync Server 2010 管理元件的並列遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="63d97-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="63d97-107">在 Lync Server 2010 中，透過隨中央管理存放區儲存的拓撲檔來探索 Lync Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="63d97-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="63d97-108">在此設定中，一部電腦會報告所有其他 Lync Server 電腦是否存在。</span><span class="sxs-lookup"><span data-stu-id="63d97-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="63d97-109">Lync Server 2013 的管理元件現在使用電腦層級探索，而不是 Lync Server 2010 中所用的中央探索機制。</span><span class="sxs-lookup"><span data-stu-id="63d97-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="63d97-110">這表示每個 System Center agent 實質上會自行探索，並向 System Center Operations Manager 報告其存在性。</span><span class="sxs-lookup"><span data-stu-id="63d97-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="63d97-111">使用電腦層級探索可簡化系統中心基礎結構的管理，也會啟用不同版本的 Lync Server 管理套件 (例如，lync Server 2010 的管理套件和 Lync Server 2013 的管理元件) ，都能更輕鬆地相互共存。</span><span class="sxs-lookup"><span data-stu-id="63d97-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="63d97-112">若要支援此遷移，您必須先升級現有的 Lync Server 2010 監控，以避免覆蓋範圍的缺口。</span><span class="sxs-lookup"><span data-stu-id="63d97-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="63d97-113">若要這麼做，請選擇現有的 Lync Server 2010 電腦，以在將中央管理存放區升級至 Lync Server 2013 之前，先為 Lync Server 2010 服務中央探索腳本。</span><span class="sxs-lookup"><span data-stu-id="63d97-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="63d97-114">這是四個步驟的處理常式：</span><span class="sxs-lookup"><span data-stu-id="63d97-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="63d97-115">將 Lync Server 2010 管理元件升級為累計更新7。</span><span class="sxs-lookup"><span data-stu-id="63d97-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="63d97-116">指示 Lync Server 2010 電腦執行中央探索腳本。</span><span class="sxs-lookup"><span data-stu-id="63d97-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="63d97-117">覆寫 Microsoft Lync Server 2010 管理元件中的「集中探索候選人」。</span><span class="sxs-lookup"><span data-stu-id="63d97-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="63d97-118">確認已探索到新的集中探索候選項目。</span><span class="sxs-lookup"><span data-stu-id="63d97-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="63d97-119">指示 Lync Server 2010 電腦執行中央探索腳本</span><span class="sxs-lookup"><span data-stu-id="63d97-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="63d97-120">若要提名非中央管理存放區電腦 (例如，Lync Server 前端) 伺服器處理中央探索，您必須在非中央管理存放區伺服器上建立下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="63d97-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="63d97-121">HKLM \\ 軟體 \\ Microsoft \\ 即時通訊 \\ 健康情況 \\ CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="63d97-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="63d97-122">您可以完成下列程式來建立此登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="63d97-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="63d97-123">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63d97-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="63d97-124">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="63d97-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="63d97-125">在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **軟體**]，展開 [ **Microsoft**]，然後展開 [ **即時通訊**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="63d97-126">以滑鼠右鍵按一下 [ **健全**]，按一下 [ **新增**]，然後按一下 [機 **碼**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="63d97-127">如果 **狀況** 機碼不存在，請以滑鼠右鍵按一下 [ **即時通訊**]，指向 [ **新增**]，然後按一下 [機 **碼**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="63d97-128">建立新金鑰時，輸入 Health，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="63d97-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="63d97-129">建立新機碼之後，輸入 **CentralDiscoveryCandidate** ，然後按 enter 重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="63d97-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="63d97-130">這可能需要數小時的時間來挑選此項變更。</span><span class="sxs-lookup"><span data-stu-id="63d97-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="63d97-131">若要讓變更立即生效，請停止狀況代理程式服務，然後再重新開機。</span><span class="sxs-lookup"><span data-stu-id="63d97-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="63d97-132">若要重新開機狀況代理程式服務，請在 Lync Server 2010 電腦上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="63d97-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="63d97-133">依序按一下 [ **開始**]、[ **所有程式**]、[ **附屬設施**]、[ **命令提示**字元] 及 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="63d97-134">在主控台視窗中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="63d97-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="63d97-135">您會看到一則訊息，指出「System Center Management service 即將停止」，接著還有第二封訊息，告知您已停止服務。</span><span class="sxs-lookup"><span data-stu-id="63d97-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="63d97-136">服務停止後，您可以輸入下列命令，然後按 ENTER，以重新開機它：</span><span class="sxs-lookup"><span data-stu-id="63d97-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="63d97-137">覆寫 Lync Server 2010 管理元件中的集中探索候選人</span><span class="sxs-lookup"><span data-stu-id="63d97-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="63d97-138">在指示 Lync Server 2010 電腦在 Lync Server 2010 電腦上報告之後，您也需要通知 Lync Server 2010 管理元件有關此變更的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="63d97-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="63d97-139">若要這麼做，您將需要在管理元件中建立覆寫。</span><span class="sxs-lookup"><span data-stu-id="63d97-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="63d97-140">若要完成，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="63d97-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="63d97-141">在 Operations Manager 主控台中，按一下 [ **製作**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="63d97-142">在 [製作] 索引標籤上，展開 [ **管理元件物件**]，按一下 [ **物件發現**]，然後按一下 [ **範圍**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="63d97-143">在 [ **範圍管理元件物件** ] 對話方塊中，選取具有目標 **LS 探索候選** 專案的專案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="63d97-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="63d97-144">請注意，只有在您已安裝 Lync Server 2010 管理元件時，才會顯示 LS 探索候選人。</span><span class="sxs-lookup"><span data-stu-id="63d97-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="63d97-145">在 Operations Manager 主控台中，以滑鼠右鍵按一下 [ **LS 探索候選人**]，指向 [ **覆寫**]，指向 **[覆寫物件探索**]，然後按一下 [ **類別的所有物件： LS 探索候選**專案]。</span><span class="sxs-lookup"><span data-stu-id="63d97-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="63d97-146">在 [覆**寫屬性**] 對話方塊中，選取 [參數**中央探索 WatcherNode Fqdn**] 旁邊的 [覆**寫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="63d97-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="63d97-147">在 [覆 **寫值** ] 和 [ **有效值** ] 方塊中，輸入 Lync Server 2010 電腦的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="63d97-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="63d97-148">選取 [ **強制執行** ] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="63d97-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="63d97-149">建立覆寫後，您必須重新開機根管理伺服器上的健康情況服務。</span><span class="sxs-lookup"><span data-stu-id="63d97-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="63d97-150">若要重新開機狀況服務，請在根管理伺服器上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="63d97-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="63d97-151">依序按一下 [ **開始**]、[ **所有程式**]、[ **附屬設施**]、[ **命令提示**字元] 及 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="63d97-152">在主控台視窗中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="63d97-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="63d97-153">您會看到一則訊息，說明「System Center Management service 即將停止」，接著還有第二封訊息，告知您已停止服務。</span><span class="sxs-lookup"><span data-stu-id="63d97-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="63d97-154">服務停止後，您可以輸入下列命令並按 ENTER 鍵，以重新開機它：</span><span class="sxs-lookup"><span data-stu-id="63d97-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="63d97-155">確認已發現新的集中探索候選項目</span><span class="sxs-lookup"><span data-stu-id="63d97-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="63d97-156">升級中央管理存放區的最後一個步驟是，確定 Lync Server 2010 管理元件已探索到新的集中探索候選項目。</span><span class="sxs-lookup"><span data-stu-id="63d97-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="63d97-157">若要這麼做，請開啟 Operations Manager 主控台，然後按一下 [監視]。</span><span class="sxs-lookup"><span data-stu-id="63d97-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="63d97-158">在 [監視] 索引標籤上，展開 [ **Microsoft Lync Server 2010 Health**]，展開 [ **拓撲探索**]，然後按一下 [ **探索狀態視圖**]。</span><span class="sxs-lookup"><span data-stu-id="63d97-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="63d97-159">驗證顯示中的列是否有列出集中式探索候選人之完整功能變數名稱的 **路徑** 。</span><span class="sxs-lookup"><span data-stu-id="63d97-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="63d97-160">您也應該確認電腦狀態已報告為 **狀況良好**。</span><span class="sxs-lookup"><span data-stu-id="63d97-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

