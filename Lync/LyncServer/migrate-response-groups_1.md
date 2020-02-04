---
title: 移轉回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="b8f7b-102">移轉回應群組</span><span class="sxs-lookup"><span data-stu-id="b8f7b-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8f7b-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b8f7b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b8f7b-104">將使用者移至 Lync Server 2013 池之後，您就可以遷移回應群組。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="b8f7b-105">遷移回應群組包括複製代理群組、佇列、工作流程和音訊檔案，以及將回應群組連絡人物件從舊版部署移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="b8f7b-106">在您遷移舊版回應群組之後，就會透過 Lync Server 2013 池中的回應群組應用程式來處理回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="b8f7b-107">舊版池已不再處理回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8f7b-108">雖然您可以在將所有使用者移至 Lync Server 2013 池之前先遷移回應群組，但我們建議您先移動所有使用者。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="b8f7b-109">特別是，回應群組代理的使用者在移至 Lync Server 2013 池之前，將不會有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="b8f7b-110">在您遷移回應群組之前，您必須先部署包含回應群組應用程式的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="b8f7b-111">當您部署企業語音時，系統會預設安裝並啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b8f7b-112">您可以執行**CsService – ApplicationServer** Cmdlet，以確保已安裝回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8f7b-113">在您遷移舊版回應群組之前，您可以在 Lync Server 2013 池中建立新的 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="b8f7b-114">若要將回應群組從舊版池遷移至 Lync Server 2013，請執行**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="b8f7b-115">您必須先安裝 Windows 管理工具（WMI）回溯相容性介面封裝，才能執行**移動 CsRgsConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="b8f7b-116">若要安裝此應用程式，請執行 OCSWMIBC。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="b8f7b-117">您可以在安裝媒體的 [設定] 資料夾中找到 OCSWMIBC。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8f7b-118">回應群組遷移 Cmdlet 會移動整個池的回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="b8f7b-119">您無法選取要遷移的特定群組、佇列或工作流程。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="b8f7b-120">在您遷移回應群組之後，您需要更新正式代理程式用來登入和登出其回應群組的 URL，並使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面] Cmdlet 來確認所有的代理群組、佇列和工作流程已移動成功.</span><span class="sxs-lookup"><span data-stu-id="b8f7b-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b8f7b-121">當您遷移回應群組時，系統不會移除 Office 通訊伺服器 2007 R2 回應群組。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="b8f7b-122">請勿移除 Office 通訊伺服器 2007 R2 回應群組。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="b8f7b-123">如果您移除 Office 通訊伺服器 2007 R2 回應群組，Lync Server 2013 中的回應群組就會停止運作。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8f7b-124">我們建議您不要從先前的部署移除任何資料，除非您解除該池。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="b8f7b-125">此外，我們強烈建議您在遷移後立即匯出回應群組。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="b8f7b-126">如果 Office 通訊伺服器 2007 R2 回應群組已移除，您可以從備份中還原回應群組，以取得 Lync Server 2013 回應群組再次執行。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="b8f7b-127">當您執行**CsRgsConfiguration** Cmdlet 時，系統會在舊版池中保留代理群組、佇列、工作流程和音訊檔案，以供回滾之用。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="b8f7b-128">不過，如果您需要回滾到舊版池，您必須執行**CsApplicationEndpoint** Cmdlet，以將連絡人物件移回舊版資源區。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8f7b-129">我們建議您不要從舊版池中刪除任何回應群組資料，直到您解除該池為止。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="b8f7b-130">針對遷移回應群組設定所遵循的程式，假設您的舊版池與 Lync Server 2013 池之間有一對一關聯性。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="b8f7b-131">如果您打算在您的遷移和部署期間合併或分割池，您需要規劃哪些舊版池會對應到哪個 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="b8f7b-132">若要遷移回應群組設定</span><span class="sxs-lookup"><span data-stu-id="b8f7b-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="b8f7b-133">在安裝媒體的 Setup 資料夾中找到 OCSWMIBC，然後進行安裝。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="b8f7b-134">以 RTCUniversalServerAdmins 群組成員的帳戶登入電腦，或擁有同等的系統管理員許可權和許可權。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="b8f7b-135">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="b8f7b-136">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="b8f7b-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="b8f7b-137">例如：</span><span class="sxs-lookup"><span data-stu-id="b8f7b-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="b8f7b-138">如果您在 Office 通訊伺服器 2007 R2 環境中部署 Microsoft Office Communicator 2007 R2 的 [回應群組] 索引標籤，請從 Office Communicator 2007 R2 索引標籤 .xml 檔案中移除索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8f7b-139">正式代理程式使用 [回應群組] 索引標籤登入其回應群組，然後才能接聽來電。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="b8f7b-140">如果您已部署 [回應群組] 索引標籤，就表示您在部署 Office Communicator 2007 R2 索引標籤 .xml 檔案時，選擇該位置。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="b8f7b-141">為使用者提供由代理程式登入和登出其回應群組所需的更新 URL。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8f7b-142">URL 通常https://webpoolFQDN/RgsClients/Tab.aspx是，其中 webpoolFQDN 是與您剛剛遷移至 Lync Server 2013 之池相關聯之網頁池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8f7b-143">在使用者升級至 Lync 2013 之後，不需要此步驟，因為 URL 可從 Lync 中的 [<STRONG>工具</STRONG>] 功能表取得。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="b8f7b-144">使用 Lync Server [控制台] 驗證回應群組的遷移</span><span class="sxs-lookup"><span data-stu-id="b8f7b-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b8f7b-145">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="b8f7b-146">在左側功能窗格中，按一下 [**回應群組**]。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="b8f7b-147">在 [**工作流程**] 索引標籤上，確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="b8f7b-148">按一下 [**佇列**] 索引標籤，並確認您的 Office 通訊伺服器 2007 R2 環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="b8f7b-149">按一下 [**群組**] 索引標籤，並確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="b8f7b-150">使用 Cmdlet 驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="b8f7b-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="b8f7b-151">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="b8f7b-152">如需有關下列 Cmdlet 的詳細資訊，請執行：</span><span class="sxs-lookup"><span data-stu-id="b8f7b-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="b8f7b-153">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="b8f7b-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="b8f7b-154">確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="b8f7b-155">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="b8f7b-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="b8f7b-156">確認您的 Office 通訊伺服器 2007 R2 環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="b8f7b-157">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="b8f7b-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="b8f7b-158">確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b8f7b-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

