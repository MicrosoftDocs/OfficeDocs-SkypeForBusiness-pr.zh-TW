---
title: 移轉回應群組
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e06b7cec1b02a194b1bb892af0e60771a15ebd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527450"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="d1786-102">移轉回應群組</span><span class="sxs-lookup"><span data-stu-id="d1786-102">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1786-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d1786-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d1786-104">將使用者移至 Lync Server 2013 集區之後，您可以遷移回應群組。</span><span class="sxs-lookup"><span data-stu-id="d1786-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="d1786-105">遷移回應群組包括複製代理程式群組、佇列、工作流程和音訊檔，以及將舊版部署的回應群組連絡人物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="d1786-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d1786-106">遷移舊版回應群組之後，對回應群組的呼叫會由 Lync Server 2013 集區中的回應群組應用程式來處理。</span><span class="sxs-lookup"><span data-stu-id="d1786-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="d1786-107">舊版集區不會再處理對回應群組的通話。</span><span class="sxs-lookup"><span data-stu-id="d1786-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1786-108">雖然您可以在將所有使用者移至 Lync Server 2013 集區之前遷移回應群組，我們建議您先移動所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d1786-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="d1786-109">特別是，回應群組代理的使用者在將新功能移至 Lync Server 2013 集區之前，將不會有其完整功能。</span><span class="sxs-lookup"><span data-stu-id="d1786-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="d1786-110">在遷移回應群組之前，您必須已部署包含回應群組應用程式的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="d1786-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="d1786-111">當您部署企業語音時，預設會安裝及啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1786-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d1786-112">您可以執行 **Get-CsService – ApplicationServer** Cmdlet 來確定是否已安裝回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1786-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1786-113">您可以在遷移舊版回應群組之前，先在 Lync Server 2013 集區中建立新的 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="d1786-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="d1786-114">若要將回應群組從舊版集區遷移至 Lync Server 2013，您需要執行 **Move-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1786-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="d1786-115">在執行 **Move-CsRgsConfiguration** 之前，必須先安裝 Windows Management Instrumentation (WMI) 回溯相容性介面套件。</span><span class="sxs-lookup"><span data-stu-id="d1786-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="d1786-116">執行 OCSWMIBC.msi 即可安裝此應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1786-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="d1786-117">您可在安裝媒體的安裝資料夾中找到 OCSWMIBC.msi。</span><span class="sxs-lookup"><span data-stu-id="d1786-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1786-118">回應群組遷移 Cmdlet 會移動整個集區的回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="d1786-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="d1786-119">您無法選取要移轉的特定群組、佇列或工作流程。</span><span class="sxs-lookup"><span data-stu-id="d1786-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="d1786-120">遷移回應群組之後，您必須更新正式代理程式用來登入和登出其回應群組的 URL，並使用 Lync Server 控制台或 Lync Server 管理命令介面 Cmdlet，確認所有代理人群組、佇列和工作流程都已順利移動。</span><span class="sxs-lookup"><span data-stu-id="d1786-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d1786-121">當您遷移回應群組時，不會移除 Office 通訊伺服器 2007 R2 回應群組。</span><span class="sxs-lookup"><span data-stu-id="d1786-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="d1786-122">請勿移除 Office 通訊伺服器 2007 R2 回應群組。</span><span class="sxs-lookup"><span data-stu-id="d1786-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="d1786-123">如果您移除 Office 通訊伺服器 2007 R2 回應群組，Lync Server 2013 中的回應群組便會停止運作。</span><span class="sxs-lookup"><span data-stu-id="d1786-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1786-124">建議集區解除委任之後，再移除先前部署的各項資料。</span><span class="sxs-lookup"><span data-stu-id="d1786-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="d1786-125">此外，強烈建議移轉後立即匯出回應群組。</span><span class="sxs-lookup"><span data-stu-id="d1786-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="d1786-126">如果 Office 通訊伺服器 2007 R2 回應群組已移除，您可以從備份還原回應群組，使 Lync Server 2013 回應群組再次執行。</span><span class="sxs-lookup"><span data-stu-id="d1786-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="d1786-127">執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。</span><span class="sxs-lookup"><span data-stu-id="d1786-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="d1786-128">不過如果需要回復舊版集區，則需要執行 **Move-CsApplicationEndpoint** Cmdlet，將連絡人物件移回舊版集區。</span><span class="sxs-lookup"><span data-stu-id="d1786-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1786-129">建議您在解除委任集區之後，才從舊版集區刪除任何回應群組資料。</span><span class="sxs-lookup"><span data-stu-id="d1786-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="d1786-130">針對遷移回應群組設定所遵循的程式，假設您在舊版集區和 Lync Server 2013 集區之間具有一對一的關聯性。</span><span class="sxs-lookup"><span data-stu-id="d1786-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="d1786-131">如果您想要在遷移和部署期間整合或分割集區，您需要規劃哪些舊版集區對應到哪些 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="d1786-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="d1786-132">遷移回應群組設定</span><span class="sxs-lookup"><span data-stu-id="d1786-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="d1786-133">在安裝媒體的安裝資料夾中找到 OCSWMIBC.msi，然後執行安裝。</span><span class="sxs-lookup"><span data-stu-id="d1786-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="d1786-134">使用 RTCUniversalServerAdmins 群組的成員帳戶 (或具有對等系統管理員權限的帳戶) 登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d1786-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="d1786-135">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d1786-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="d1786-136">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d1786-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="d1786-137">例如：</span><span class="sxs-lookup"><span data-stu-id="d1786-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="d1786-138">如果您已在 Office 通訊伺服器 2007 R2 環境中部署 Microsoft Office Communicator 2007 R2 的 [回應群組] 索引標籤，請從 Office Communicator 2007 R2 tabs.xml 檔案中移除索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d1786-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1786-139">正式代理程式會先使用 [回應群組] 索引標籤來登入回應群組，之後才能接收通話。</span><span class="sxs-lookup"><span data-stu-id="d1786-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="d1786-140">如果您已部署 [回應群組] 索引標籤，您會在部署 Office Communicator 2007 R2 tabs.xml 檔案時選擇其位置。</span><span class="sxs-lookup"><span data-stu-id="d1786-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="d1786-141">提供使用者更新過的 URL，以讓代理程式用來登入與登出回應群組。</span><span class="sxs-lookup"><span data-stu-id="d1786-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1786-142">URL 通常是指 https://webpoolFQDN/RgsClients/Tab.aspx 與您剛才遷移至 Lync Server 2013 之集區相關聯之網頁集區的完整功能變數名稱 (FQDN) 的 webpoolFQDN。</span><span class="sxs-lookup"><span data-stu-id="d1786-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1786-143">在使用者升級至 Lync 2013 之後，不需要此步驟，因為您可以從 Lync 的 [ <STRONG>工具</STRONG> ] 功能表中取得 URL。</span><span class="sxs-lookup"><span data-stu-id="d1786-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="d1786-144">使用 Lync Server 控制台驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="d1786-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d1786-145">開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d1786-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d1786-146">在左導覽列中，按一下 **[回應群組]**。</span><span class="sxs-lookup"><span data-stu-id="d1786-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="d1786-147">在 [ **工作流程** ] 索引標籤上，確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="d1786-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="d1786-148">按一下 [ **佇列** ] 索引標籤，確認清單中包含 Office 通訊伺服器 2007 R2 環境中的所有佇列。</span><span class="sxs-lookup"><span data-stu-id="d1786-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="d1786-149">按一下 [ **群組** ] 索引標籤，並確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理程式群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="d1786-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="d1786-150">使用 Cmdlet 驗證回應群組移轉</span><span class="sxs-lookup"><span data-stu-id="d1786-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="d1786-151">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d1786-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="d1786-152">如需有關下列 Cmdlet 的詳細資訊，請執行：</span><span class="sxs-lookup"><span data-stu-id="d1786-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="d1786-153">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d1786-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="d1786-154">確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理程式群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="d1786-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="d1786-155">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d1786-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="d1786-156">確認您的 Office 通訊伺服器 2007 R2 環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="d1786-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="d1786-157">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d1786-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="d1786-158">確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="d1786-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

