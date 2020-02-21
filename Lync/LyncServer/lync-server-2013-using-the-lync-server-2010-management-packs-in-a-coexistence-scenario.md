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
ms.openlocfilehash: ffc2aed62b9ad26fd1498787ecd3d58144a005b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="70701-102">在共存案例中使用 Lync Server 2010 管理套件</span><span class="sxs-lookup"><span data-stu-id="70701-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70701-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="70701-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="70701-104">許多客戶採用導入程式順序會逐漸遷移使用者從 Microsoft Lync Server 2010 to Lync Server 2013 企業內的內容。</span><span class="sxs-lookup"><span data-stu-id="70701-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="70701-105">在這些公司系統管理員將在意監視兩個版本的 Lync Server，以協助確保所有使用者可獲得最可能的通訊體驗。</span><span class="sxs-lookup"><span data-stu-id="70701-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="70701-106">此案例中，為 Lync Server 2013 管理組件支援與 Lync Server 2010 管理組件的並排顯示移轉路徑。</span><span class="sxs-lookup"><span data-stu-id="70701-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="70701-107">在 [Lync Server 2010，Lync Server 電腦發現整個拓撲文件儲存與中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="70701-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="70701-108">在此組態中，在單一電腦會報告其他所有 Lync Server 電腦的存在。</span><span class="sxs-lookup"><span data-stu-id="70701-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="70701-109">針對 Lync Server 2013 管理組件現在會使用機器層級探索而不是使用 Lync Server 2010 中的集中探索機制。</span><span class="sxs-lookup"><span data-stu-id="70701-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="70701-110">這表示每個 System Center 代理程式基本上探索本身，並報告至 System Center Operations Manager 其存在。</span><span class="sxs-lookup"><span data-stu-id="70701-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="70701-111">使用電腦層級探索簡化管理 System Center 基礎結構和也可讓不同版本的 Lync Server 管理組件 （例如，管理組件的 Lync Server 2010） 和 Lync Server 2013 管理組件若要更輕鬆地共存。</span><span class="sxs-lookup"><span data-stu-id="70701-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="70701-112">若要支援此移轉，您必須升級監視以避免涵蓋範圍間斷的傷害您現有 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="70701-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="70701-113">若要這麼做，請選擇現有的 Lync Server 2010 電腦來升級您的中央管理存放區至 Lync Server 2013 之前服務 [Lync Server 2010 的集中探索指令碼。</span><span class="sxs-lookup"><span data-stu-id="70701-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="70701-114">這是四個步驟的程序：</span><span class="sxs-lookup"><span data-stu-id="70701-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="70701-115">將 Lync Server 2010 管理組件升級至累計更新 7。</span><span class="sxs-lookup"><span data-stu-id="70701-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="70701-116">指示 Lync Server 2010 的電腦執行集中探索指令碼。</span><span class="sxs-lookup"><span data-stu-id="70701-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="70701-117">覆寫的 Microsoft Lync Server 2010 管理組件中的集中探索候選項目。</span><span class="sxs-lookup"><span data-stu-id="70701-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="70701-118">請確認已探索到新的集中探索候選。</span><span class="sxs-lookup"><span data-stu-id="70701-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="70701-119">指示 Lync Server 2010 電腦執行集中探索指令碼</span><span class="sxs-lookup"><span data-stu-id="70701-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="70701-120">若要指定非中央管理存放區電腦 （例如，Lync Server 前端） 伺服器來處理集中探索，您必須在非中央管理存放區伺服器上建立下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="70701-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="70701-121">HKLM\\軟體\\Microsoft\\即時通訊\\狀況\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="70701-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="70701-122">您可以建立此登錄機碼，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="70701-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="70701-123">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70701-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="70701-124">在 [執行]\*\*\*\* 對話方塊中，輸入 **regedit**，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="70701-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="70701-125">在 「 登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開**軟體**，依序展開 [ **Microsoft**，，然後展開 [**即時通訊**。</span><span class="sxs-lookup"><span data-stu-id="70701-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="70701-126">以滑鼠右鍵按一下 [**健康情況**，按一下 [**新增**]，然後按一下 [**機碼**。</span><span class="sxs-lookup"><span data-stu-id="70701-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="70701-127">如果**健康情況**機碼不存在，然後在**即時通訊**上按一下滑鼠右鍵，指向 [**新增**]，，然後按一下 [**機碼**。</span><span class="sxs-lookup"><span data-stu-id="70701-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="70701-128">建立新的索引鍵時，輸入健康情況，並按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="70701-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="70701-129">在建立新的金鑰之後，輸入**CentralDiscoveryCandidate** ，然後按 ENTER 以重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="70701-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="70701-130">它可能需要的電腦數小時，要揀選這項變更。</span><span class="sxs-lookup"><span data-stu-id="70701-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="70701-131">若要變更立即生效，停止，並再重新啟動 Health 代理程式服務。</span><span class="sxs-lookup"><span data-stu-id="70701-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="70701-132">若要重新啟動 Health 代理程式服務，請完成下列程序在 Lync Server 2010 的電腦上：</span><span class="sxs-lookup"><span data-stu-id="70701-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="70701-133">按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**，以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="70701-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="70701-134">在主控台視窗中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="70701-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="70701-135">您會看到訊息指出 「 System Center Management] 服務會停止 」 後面接著第二個的訊息，告知您的服務已停止。</span><span class="sxs-lookup"><span data-stu-id="70701-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="70701-136">服務停止之後，您可以重新啟動它中輸入下列命令並按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="70701-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="70701-137">覆寫 Lync Server 2010 管理組件中的集中探索候選項目</span><span class="sxs-lookup"><span data-stu-id="70701-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="70701-138">之後指示 Lync Server 2010 的電腦回報 Lync Server 2010 的電腦上，您必須通知這項變更以及 Lync Server 2010 管理組件。</span><span class="sxs-lookup"><span data-stu-id="70701-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="70701-139">若要這麼做，您必須在管理組件中建立覆寫。</span><span class="sxs-lookup"><span data-stu-id="70701-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="70701-140">可以藉由完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="70701-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="70701-141">在 Operations Manager 主控台中，按一下 [**撰寫**]。</span><span class="sxs-lookup"><span data-stu-id="70701-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="70701-142">製作索引標籤上，依序展開 [**管理組件物件**，請按一下 [**物件探索**]，和 [**範圍**。</span><span class="sxs-lookup"><span data-stu-id="70701-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="70701-143">在 [**範圍管理組件物件**] 對話方塊中，選取的項目與目標**LS 探索候選項目**，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="70701-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="70701-144">請注意，只有當您已安裝 Lync Server 2010 管理組件，會出現 LS 探索候選項目。</span><span class="sxs-lookup"><span data-stu-id="70701-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="70701-145">在 Operations Manager 主控台中，以滑鼠右鍵按一下**LS 探索候選項目**，指向 [**覆寫**，並指向 [**覆寫物件探索**，然後按一下 [**類別的所有物件： LS 探索候選項目**。</span><span class="sxs-lookup"><span data-stu-id="70701-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="70701-146">在 [**覆寫內容**] 對話方塊中，選取參數**集中探索 WatcherNode Fqdn**旁的 [**覆寫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="70701-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="70701-147">在 [**覆寫值**和**有效的值**] 方塊中輸入的 Lync Server 2010 電腦的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="70701-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="70701-148">選取 [**強制**] 核取方塊，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="70701-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="70701-149">您已建立覆寫之後，您需要重新啟動 Root Management Server 上的健全狀況服務。</span><span class="sxs-lookup"><span data-stu-id="70701-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="70701-150">若要重新啟動的健全狀況服務，請完成下列程序 Root Management Server 上：</span><span class="sxs-lookup"><span data-stu-id="70701-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="70701-151">按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**，以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="70701-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="70701-152">在主控台視窗中，輸入下列命令，並按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="70701-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="70701-153">您會看到訊息，表示，「 System Center Management] 服務已停止 」，後面加上第二個的訊息，告知您的服務已停止。</span><span class="sxs-lookup"><span data-stu-id="70701-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="70701-154">服務停止之後，您可以再重新啟動它中輸入下列命令並按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="70701-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="70701-155">確認已探索到新的集中探索候選項目</span><span class="sxs-lookup"><span data-stu-id="70701-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="70701-156">再升級中央管理存放區的最後一個步驟是確認 Lync Server 2010 管理組件已探索到新的集中探索候選項目。</span><span class="sxs-lookup"><span data-stu-id="70701-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="70701-157">若要這麼做，開啟 Operations Manager 主控台中，然後按一下 [監視]。</span><span class="sxs-lookup"><span data-stu-id="70701-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="70701-158">在 [監視] 索引標籤上依序展開 [ **Microsoft Lync Server 2010 狀況**、 展開**拓撲搜索**，，然後按一下**探索狀態檢視**。</span><span class="sxs-lookup"><span data-stu-id="70701-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="70701-159">確認中顯示的資料列有列出集中探索候選項目的完整的網域名稱的**路徑**。</span><span class="sxs-lookup"><span data-stu-id="70701-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="70701-160">您也應確認電腦狀態被回報為**狀況良好**。</span><span class="sxs-lookup"><span data-stu-id="70701-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

