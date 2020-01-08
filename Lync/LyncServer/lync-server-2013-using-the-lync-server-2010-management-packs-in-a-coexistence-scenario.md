---
title: 在共存案例中使用 Lync Server 2010 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="e7e36-102">在共存案例中使用 Lync Server 2010 管理套件</span><span class="sxs-lookup"><span data-stu-id="e7e36-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7e36-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e7e36-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e7e36-104">許多客戶在其企業中採用推出方案，這些使用者會從 Microsoft Lync Server 2010 逐步遷移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e7e36-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="e7e36-105">這些公司的系統管理員會關心監視兩個版本的 Lync Server，以協助確保他們的所有使用者都能獲得最佳的通訊體驗。</span><span class="sxs-lookup"><span data-stu-id="e7e36-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="e7e36-106">在這種情況下，Lync Server 2013 管理套件支援與 Lync Server 2010 管理套件進行並排遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="e7e36-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="e7e36-107">在 Lync Server 2010 中，Lync Server 電腦是透過中央管理存放區所儲存的拓撲檔來探索。</span><span class="sxs-lookup"><span data-stu-id="e7e36-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="e7e36-108">在這個設定中，單一電腦會報告所有其他 Lync Server 電腦是否存在。</span><span class="sxs-lookup"><span data-stu-id="e7e36-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="e7e36-109">Lync Server 2013 的管理套件現在使用電腦層級探索，而不是在 Lync Server 2010 中使用的中央探索機制。</span><span class="sxs-lookup"><span data-stu-id="e7e36-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="e7e36-110">這表示每個系統中心代理程式都本質上探索自己，並將它的存在性報告給 System Center 運營系統管理員。</span><span class="sxs-lookup"><span data-stu-id="e7e36-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="e7e36-111">使用電腦層級探索可簡化系統中心基礎結構的管理，同時也會啟用不同版本的 Lync Server 管理套件（例如，Lync Server 2010 的管理套件和 Lync Server 2013 的管理套件）更容易地共存。</span><span class="sxs-lookup"><span data-stu-id="e7e36-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="e7e36-112">若要支援這項遷移，您必須先升級現有的 Lync Server 2010 監視，以避免覆蓋範圍中的差距。</span><span class="sxs-lookup"><span data-stu-id="e7e36-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="e7e36-113">若要這樣做，請選擇現有的 Lync Server 2010 電腦，在將您的中央管理儲存在 Lync Server 2013 升級前，為 Lync Server 2010 提供中央探索腳本服務。</span><span class="sxs-lookup"><span data-stu-id="e7e36-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="e7e36-114">這是四個步驟的程式：</span><span class="sxs-lookup"><span data-stu-id="e7e36-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="e7e36-115">將 Lync Server 2010 管理套件升級為累積更新7。</span><span class="sxs-lookup"><span data-stu-id="e7e36-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="e7e36-116">指示 Lync Server 2010 電腦執行中央探索腳本。</span><span class="sxs-lookup"><span data-stu-id="e7e36-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="e7e36-117">覆寫 Microsoft Lync Server 2010 管理套件中的 [集中搜尋候選]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="e7e36-118">確認已探索新的中央探索候選方案。</span><span class="sxs-lookup"><span data-stu-id="e7e36-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="e7e36-119">指示 Lync Server 2010 電腦執行中央探索腳本</span><span class="sxs-lookup"><span data-stu-id="e7e36-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="e7e36-120">若要提名非集中式管理商店電腦（例如，Lync Server 前端伺服器）來處理中央探索，您必須在非中央管理儲存伺服器上建立下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="e7e36-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="e7e36-121">HKLM\\\軟體\\Microsoft\\即時通訊\\健康情況\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="e7e36-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="e7e36-122">您可以透過完成下列程式來建立此登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="e7e36-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="e7e36-123">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="e7e36-124">在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="e7e36-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="e7e36-125">在 [登錄編輯程式] 中，展開 [ \*\* \_HKEY 本機\_電腦**]、展開 [**軟體**]、[ **Microsoft**]，然後展開 [**即時通訊\*\*]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="e7e36-126">以滑鼠右鍵按一下 [**健康情況**]，按一下 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="e7e36-127">如果**健康**時間金鑰不存在，請以滑鼠右鍵按一下 [**即時通訊**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="e7e36-128">建立新的金鑰後，請輸入 Health，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="e7e36-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="e7e36-129">建立新的金鑰之後，請輸入**CentralDiscoveryCandidate** ，然後按 enter 鍵來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="e7e36-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="e7e36-130">可能需要幾個小時的時間，才能取得這項變更。</span><span class="sxs-lookup"><span data-stu-id="e7e36-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="e7e36-131">若要讓變更立即生效，請停止並重新啟動 Health 代理服務。</span><span class="sxs-lookup"><span data-stu-id="e7e36-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="e7e36-132">若要重新開機 Health 代理程式服務，請在 Lync Server 2010 電腦上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="e7e36-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="e7e36-133">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="e7e36-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e7e36-134">在主控台視窗中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e7e36-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="e7e36-135">您會看到一則訊息，指出「System Center 管理服務即將停止」，後面接著第二個訊息，告訴您該服務已停止。</span><span class="sxs-lookup"><span data-stu-id="e7e36-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="e7e36-136">停止服務之後，您可以輸入下列命令，然後按 ENTER 來重新開機它：</span><span class="sxs-lookup"><span data-stu-id="e7e36-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="e7e36-137">覆寫 Lync Server 2010 管理套件中的中央探索候選人</span><span class="sxs-lookup"><span data-stu-id="e7e36-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="e7e36-138">指示 Lync Server 2010 電腦在 Lync Server 2010 電腦上報告之後，您必須通知 Lync Server 2010 管理套件與此變更。</span><span class="sxs-lookup"><span data-stu-id="e7e36-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="e7e36-139">若要這樣做，您將需要在管理套件中建立覆寫。</span><span class="sxs-lookup"><span data-stu-id="e7e36-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="e7e36-140">完成下列程式，即可完成作業：</span><span class="sxs-lookup"><span data-stu-id="e7e36-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="e7e36-141">在 Operations Manager 主控台中，按一下 [**撰寫**]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="e7e36-142">在 [撰寫] 索引標籤上，展開 [**管理套件物件**]，按一下 [**物件發現**]，然後按一下 [**範圍**]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="e7e36-143">在 [**範圍管理套件物件**] 對話方塊中，選取具有目標 LS [**探索候選**] 的專案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7e36-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="e7e36-144">請注意，只有當您已安裝 Lync Server 2010 管理套件時，才會出現 LS 搜尋候選版本。</span><span class="sxs-lookup"><span data-stu-id="e7e36-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="e7e36-145">在 Operations Manager 主控台中，以滑鼠右鍵按一下**LS [探索候選人**]，指向 [**覆寫**]，指向 [覆**寫物件探索**]，然後按一下 [**所有類別的物件： LS 探索候選**專案]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="e7e36-146">在 [ **Override 屬性**] 對話方塊中，選取參數 [**中央探索 WatcherNode Fqdn**] 旁的 [**覆蓋**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7e36-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="e7e36-147">在 [**取代值**] 和 [**生效值**] 方塊中，輸入 Lync Server 2010 電腦的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e7e36-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="e7e36-148">選取 [**強制**] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7e36-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="e7e36-149">在您建立覆蓋之後，您必須重新開機根管理伺服器上的健康情況服務。</span><span class="sxs-lookup"><span data-stu-id="e7e36-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="e7e36-150">若要重新開機健康情況服務，請在根管理伺服器上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="e7e36-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="e7e36-151">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="e7e36-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e7e36-152">在主控台視窗中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e7e36-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="e7e36-153">您會看到一則訊息，指出「系統中心管理服務即將停止」，後面接著第二個訊息，告訴您該服務已停止。</span><span class="sxs-lookup"><span data-stu-id="e7e36-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="e7e36-154">停止服務之後，您可以輸入下列命令，然後按 ENTER 來重新開機它：</span><span class="sxs-lookup"><span data-stu-id="e7e36-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="e7e36-155">確認已發現新的中央探索候選人</span><span class="sxs-lookup"><span data-stu-id="e7e36-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="e7e36-156">升級「中央管理儲存區」前的最後一個步驟是，確定 Lync Server 2010 管理套件發現了新的中央探索候選版本。</span><span class="sxs-lookup"><span data-stu-id="e7e36-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="e7e36-157">若要這樣做，請開啟 Operations Manager 主控台，然後按一下 [監視]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="e7e36-158">在 [監視] 索引標籤上，展開 [ **Microsoft Lync Server 2010 健康情況**]，展開 [**拓撲探索**]，然後按一下 [**探索狀態視圖**]。</span><span class="sxs-lookup"><span data-stu-id="e7e36-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="e7e36-159">確認顯示中的列有一個**路徑**，其中列出「集中搜尋候選字」的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e7e36-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="e7e36-160">您也應該確認電腦狀態報表為**健康情況**。</span><span class="sxs-lookup"><span data-stu-id="e7e36-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

