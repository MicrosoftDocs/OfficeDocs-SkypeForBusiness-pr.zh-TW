---
title: 準備 Active Directory skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要： 了解如何準備 Skype 安裝 Business Server 的 Active Directory 網域。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018174"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="abadd-104">準備 Active Directory skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="abadd-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="abadd-105">**摘要：** 了解如何準備 Skype 安裝 Business Server 的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="abadd-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="abadd-106">從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Business Server 下載 Skype 免費試用版。</span><span class="sxs-lookup"><span data-stu-id="abadd-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="abadd-107">Skype 商務 Server 密切與 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="abadd-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="abadd-108">您必須先準備 Active Directory 網域，才能使用 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="abadd-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="abadd-109">此程序完成部署精靈] 中，且只為網域一次完成。</span><span class="sxs-lookup"><span data-stu-id="abadd-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="abadd-110">這是因為和處理程序會建立群組，並修改的網域，您需要執行動作的唯一一次。</span><span class="sxs-lookup"><span data-stu-id="abadd-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="abadd-111">您可以執行步驟 1 到 5，以任何順序。</span><span class="sxs-lookup"><span data-stu-id="abadd-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="abadd-112">不過，您必須先執行步驟 6、 7 和 8 順序，並在步驟 1 到 5 之後，在圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="abadd-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="abadd-113">準備 Active Directory 是 8 的步驟 4。</span><span class="sxs-lookup"><span data-stu-id="abadd-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="abadd-114">如需規劃 Active Directory 的詳細資訊，請參閱[Skype for Business 伺服器環境的需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for Business Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abadd-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概觀圖表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="abadd-116">準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="abadd-116">Prepare Active Directory</span></span>

<span data-ttu-id="abadd-117">Skype 商務 Server 緊密整合與 Active Directory 網域服務 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="abadd-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="abadd-118">Skype for Business Server 可以安裝第一次之前，必須準備 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="abadd-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="abadd-119">[] 區段中的 [部署精靈] 標題為 [**準備 Active Directory**會將使用的 Active Directory 環境與 Skype 準備 Business Server。</span><span class="sxs-lookup"><span data-stu-id="abadd-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abadd-120">Skype 商務伺服器來追蹤並彼此的所有伺服器的拓撲中使用 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="abadd-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="abadd-121">大部分的這些伺服器必須加入網域，以便 Skype for Business Server 可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="abadd-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="abadd-122">請記住，例如 Edge 和反向 Proxy 伺服器不應加入網域。</span><span class="sxs-lookup"><span data-stu-id="abadd-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="abadd-123">準備 Active Directory 程序應該執行的部署中的每個網域的僅一次。</span><span class="sxs-lookup"><span data-stu-id="abadd-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="abadd-124">觀賞影片步驟**準備 Active**directory:</span><span class="sxs-lookup"><span data-stu-id="abadd-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="abadd-125">從 [部署精靈準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="abadd-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="abadd-126">使用者身分登入 Schema Admins 與 Active Directory 網域的認證。</span><span class="sxs-lookup"><span data-stu-id="abadd-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="abadd-127">開啟 Skype for Business Server 部署精靈]。</span><span class="sxs-lookup"><span data-stu-id="abadd-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="abadd-128">如果您想要檢閱記錄檔所建立的 Skype for Business Server 部署精靈，您可以在何處部署精靈已執行，執行步驟的 AD DS 使用者的使用者目錄中的電腦上找到他們。</span><span class="sxs-lookup"><span data-stu-id="abadd-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="abadd-129">例如，如果使用者以登入網域系統管理員的網域，contoso.local，記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="abadd-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="abadd-130">按一下 [**準備 Active Directory** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="abadd-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="abadd-131">**步驟 1： 準備架構**</span><span class="sxs-lookup"><span data-stu-id="abadd-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="abadd-132">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-132">a.</span></span> <span data-ttu-id="abadd-133">檢閱步驟 1，可以在 [步驟 1 標題下方按一下下拉式清單來存取的必要條件資訊。</span><span class="sxs-lookup"><span data-stu-id="abadd-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="abadd-134">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-134">b.</span></span> <span data-ttu-id="abadd-135">按一下 [啟動 [準備架構] 精靈的步驟 1 中的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="abadd-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="abadd-136">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-136">c.</span></span> <span data-ttu-id="abadd-137">記下應該針對每個部署中，只有一次執行程序，並再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="abadd-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="abadd-138">d.</span><span class="sxs-lookup"><span data-stu-id="abadd-138">d.</span></span> <span data-ttu-id="abadd-139">一旦已備妥結構描述，您可以檢視記錄檔]，即可**檢視記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="abadd-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="abadd-140">e.</span><span class="sxs-lookup"><span data-stu-id="abadd-140">e.</span></span> <span data-ttu-id="abadd-141">按一下 [**完成**] 以關閉 [準備架構精靈] 中，並回到 [準備 Active Directory 的步驟。</span><span class="sxs-lookup"><span data-stu-id="abadd-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="abadd-142">**步驟 2： 驗證架構分割的複寫**</span><span class="sxs-lookup"><span data-stu-id="abadd-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="abadd-143">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-143">a.</span></span> <span data-ttu-id="abadd-144">登入網域的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="abadd-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="abadd-145">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-145">b.</span></span> <span data-ttu-id="abadd-146">**伺服器管理員**] 中的 [**工具**] 下拉式清單功能表中，開啟 [ **Adsi 編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="abadd-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="abadd-147">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-147">c.</span></span> <span data-ttu-id="abadd-148">在 [動作] 功能表上，按一下 [連線至]。</span><span class="sxs-lookup"><span data-stu-id="abadd-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="abadd-149">d.</span><span class="sxs-lookup"><span data-stu-id="abadd-149">d.</span></span> <span data-ttu-id="abadd-150">在 **[選取熟知的命名內容]** 的 **[連線設定]** 對話方塊中，選取 **[架構]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="abadd-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="abadd-151">e.</span><span class="sxs-lookup"><span data-stu-id="abadd-151">e.</span></span> <span data-ttu-id="abadd-152">在 [架構] 容器中下, 搜尋**CN = ms RTC-SIP SchemaVersion**。</span><span class="sxs-lookup"><span data-stu-id="abadd-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="abadd-153">如果此物件存在， **rangeUpper**屬性的值是 1150年和**rangeLower**屬性的值為 3，結構描述已成功地更新，且複寫。</span><span class="sxs-lookup"><span data-stu-id="abadd-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="abadd-154">如果此物件不存在或**rangeUpper**和**rangeLower**屬性的值不是以指定，結構描述未修改或未進行複寫。</span><span class="sxs-lookup"><span data-stu-id="abadd-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="abadd-155">**步驟 3： 準備目前樹系**</span><span class="sxs-lookup"><span data-stu-id="abadd-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="abadd-156">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-156">a.</span></span> <span data-ttu-id="abadd-157">檢閱步驟 3，也可以在 [步驟 3 標題下方按一下下拉式清單來存取的必要條件資訊。</span><span class="sxs-lookup"><span data-stu-id="abadd-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="abadd-158">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-158">b.</span></span> <span data-ttu-id="abadd-159">按一下 [啟動準備目前樹系精靈的步驟 3 中的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="abadd-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="abadd-160">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-160">c.</span></span> <span data-ttu-id="abadd-161">記下程序應該只執行一次部署中，每，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="abadd-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="abadd-162">d.</span><span class="sxs-lookup"><span data-stu-id="abadd-162">d.</span></span> <span data-ttu-id="abadd-163">指定要在其中建立萬用群組的網域。</span><span class="sxs-lookup"><span data-stu-id="abadd-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="abadd-164">如果伺服器是屬於網域，您可以選擇**本機網域**，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="abadd-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="abadd-165">e.</span><span class="sxs-lookup"><span data-stu-id="abadd-165">e.</span></span> <span data-ttu-id="abadd-166">一旦已準備樹系，您可以檢視記錄檔]，即可**檢視記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="abadd-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="abadd-167">f.</span><span class="sxs-lookup"><span data-stu-id="abadd-167">f.</span></span> <span data-ttu-id="abadd-168">按一下 [**完成**] 以關閉 [準備目前樹系] 精靈中，並回到 [準備 Active Directory 的步驟。</span><span class="sxs-lookup"><span data-stu-id="abadd-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="abadd-169">g.</span><span class="sxs-lookup"><span data-stu-id="abadd-169">g.</span></span> <span data-ttu-id="abadd-170">從 [**應用程式**] 頁面上，啟動 PowerShell，請按一下 [ **Skype for Business Server 管理命令介面**]。</span><span class="sxs-lookup"><span data-stu-id="abadd-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="abadd-171">h。</span><span class="sxs-lookup"><span data-stu-id="abadd-171">h.</span></span> <span data-ttu-id="abadd-172">輸入命令 Get-csadforest，然後按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="abadd-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="abadd-173">我。</span><span class="sxs-lookup"><span data-stu-id="abadd-173">i.</span></span> <span data-ttu-id="abadd-174">如果結果是**lc_forestsettings_state_ready 這個**，樹系成功已準備，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="abadd-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![確認樹系複寫。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="abadd-176">**步驟 4： 確認複寫的通用類別目錄**</span><span class="sxs-lookup"><span data-stu-id="abadd-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="abadd-177">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-177">a.</span></span> <span data-ttu-id="abadd-178">網域控制站上 （最好是中的遠端網站的其他網域控制站），在樹系準備先前執行的樹系中，開啟 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="abadd-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="abadd-179">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-179">b.</span></span> <span data-ttu-id="abadd-180">在 [ **Active Directory 使用者和電腦**，展開 [樹系或子網域的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="abadd-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="abadd-181">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-181">c.</span></span> <span data-ttu-id="abadd-182">按一下 [**使用者**] 容器，在左側窗格中，並尋找在右側窗格中的萬用群組**CsAdministrator** 。</span><span class="sxs-lookup"><span data-stu-id="abadd-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="abadd-183">如果出現 CsAdministrator （之間開頭 Cs 其他新萬用群組），Active Directory 複寫是否已順利完成。</span><span class="sxs-lookup"><span data-stu-id="abadd-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="abadd-184">d.</span><span class="sxs-lookup"><span data-stu-id="abadd-184">d.</span></span> <span data-ttu-id="abadd-185">如果群組還不存在，您可以強制執行複寫，或等候 15 分鐘，然後重新整理右側邊窗格。</span><span class="sxs-lookup"><span data-stu-id="abadd-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="abadd-186">群組存在時，複寫已完成。</span><span class="sxs-lookup"><span data-stu-id="abadd-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="abadd-187">**步驟 5： 準備目前的網域**</span><span class="sxs-lookup"><span data-stu-id="abadd-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="abadd-188">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-188">a.</span></span> <span data-ttu-id="abadd-189">檢閱步驟 5 的必要條件資訊。</span><span class="sxs-lookup"><span data-stu-id="abadd-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="abadd-190">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-190">b.</span></span> <span data-ttu-id="abadd-191">按一下 [步驟 5，以啟動 [準備目前的網域] 精靈中的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="abadd-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="abadd-192">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-192">c.</span></span> <span data-ttu-id="abadd-193">記下程序應該只能執行一次在部署中，每個網域，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="abadd-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="abadd-194">d.</span><span class="sxs-lookup"><span data-stu-id="abadd-194">d.</span></span> <span data-ttu-id="abadd-195">一旦準備的網域，您可以檢視記錄檔]，即可**檢視記錄檔**。</span><span class="sxs-lookup"><span data-stu-id="abadd-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="abadd-196">e.</span><span class="sxs-lookup"><span data-stu-id="abadd-196">e.</span></span> <span data-ttu-id="abadd-197">按一下 [**完成**] 以關閉 [準備目前的網域] 精靈中，並回到 [準備 Active Directory 的步驟。</span><span class="sxs-lookup"><span data-stu-id="abadd-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="abadd-198">這些步驟必須先完成其中 Skype for 找不到商務伺服器物件，否則服務可能會每個網域中不會啟動。</span><span class="sxs-lookup"><span data-stu-id="abadd-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="abadd-199">這包括任何 Active Directory 物件，例如使用者、 連絡人物件、 系統管理群組或任何其他類型的物件類型。</span><span class="sxs-lookup"><span data-stu-id="abadd-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="abadd-200">如有需要您可以使用 Set CsUserReplicatorConfiguration ADDomainNamingContextList 僅為新增網域與 Skype 商務伺服器物件。</span><span class="sxs-lookup"><span data-stu-id="abadd-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="abadd-201">**步驟 6： 確認網域中的複寫**</span><span class="sxs-lookup"><span data-stu-id="abadd-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="abadd-202">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-202">a.</span></span> <span data-ttu-id="abadd-203">按一下 [ **Skype for Business Server 管理命令介面**從 [**應用程式**] 頁面來啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="abadd-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="abadd-204">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-204">b.</span></span> <span data-ttu-id="abadd-205">若要確認網域內的複寫使用 Get-csaddomain] 命令。</span><span class="sxs-lookup"><span data-stu-id="abadd-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="abadd-206">如果您沒有指定 Domain 參數，這個值會設為本機網域。</span><span class="sxs-lookup"><span data-stu-id="abadd-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="abadd-207">執行 [contoso.local 網域] 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="abadd-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="abadd-208">藉由使用 GlobalSettingsDomainController 的參數，您可以指出儲存全域設定。</span><span class="sxs-lookup"><span data-stu-id="abadd-208">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="abadd-209">如果您的設定儲存在系統容器 （這是一般升級尚未全域設定移轉至組態容器的部署） 中，您會在您的 AD DS 樹系根中定義的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="abadd-209">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="abadd-210">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="abadd-210">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="abadd-211">如果您未指定此參數，指令程式會假設此設定會儲存在 [Configuration] 容器，且是指在 Active Directory 中的任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="abadd-211">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="abadd-212">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-212">c.</span></span> <span data-ttu-id="abadd-213">如果結果是**LC_DOMAINSETTINGS_STATE_READY**，網域已成功複寫。</span><span class="sxs-lookup"><span data-stu-id="abadd-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="abadd-214">**步驟 7： 新增使用者提供的管理存取權 skype for Business Server Control Panel**</span><span class="sxs-lookup"><span data-stu-id="abadd-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="abadd-215">a.</span><span class="sxs-lookup"><span data-stu-id="abadd-215">a.</span></span> <span data-ttu-id="abadd-216">使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="abadd-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="abadd-217">b.</span><span class="sxs-lookup"><span data-stu-id="abadd-217">b.</span></span> <span data-ttu-id="abadd-218">開啟 [ **Active Directory 使用者和電腦**，展開您的網域、 按一下 [**使用者**] 容器，以滑鼠右鍵按一下 CSAdministrator，選擇 [**屬性**。</span><span class="sxs-lookup"><span data-stu-id="abadd-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="abadd-219">c.</span><span class="sxs-lookup"><span data-stu-id="abadd-219">c.</span></span> <span data-ttu-id="abadd-220">在 **[CSAdministrator 內容]** 中，按一下 **[成員]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="abadd-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="abadd-221">d.</span><span class="sxs-lookup"><span data-stu-id="abadd-221">d.</span></span> <span data-ttu-id="abadd-222">在 [成員]\*\*\*\* 索引標籤上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="abadd-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="abadd-223">在 [選取使用者、連絡人、電腦、服務帳戶或群組]\*\*\*\* 中，找到 [輸入要選取的物件名稱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="abadd-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="abadd-224">輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。</span><span class="sxs-lookup"><span data-stu-id="abadd-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="abadd-225">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="abadd-225">Click **OK**.</span></span>
    
    <span data-ttu-id="abadd-226">e.</span><span class="sxs-lookup"><span data-stu-id="abadd-226">e.</span></span> <span data-ttu-id="abadd-227">在 [**成員**] 索引標籤，確認使用者或群組，您所選取存在。</span><span class="sxs-lookup"><span data-stu-id="abadd-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="abadd-228">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="abadd-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="abadd-229">Skype for Business Server Control Panel 是角色型存取控制的工具。</span><span class="sxs-lookup"><span data-stu-id="abadd-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="abadd-230">以 CsAdministrator 群組成員資格授與使用 Skype for Business Server 控制台中的所有可用的組態函式的完全控制權的使用者。</span><span class="sxs-lookup"><span data-stu-id="abadd-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="abadd-231">有些其他的角色是針對特定功能而設計。</span><span class="sxs-lookup"><span data-stu-id="abadd-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="abadd-232">如需可用的角色的詳細資訊，請參閱[Skype for Business 伺服器環境的需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for Business Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abadd-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="abadd-233">請注意，使用者沒有要啟用 Skype for Business Server 才能進行管理群組的成員。</span><span class="sxs-lookup"><span data-stu-id="abadd-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="abadd-234">為了協助保留安全性和角色型存取控制完整性，請將使用者新增至定義了使用者在 Skype for Business Server 部署的管理，執行何種角色群組。</span><span class="sxs-lookup"><span data-stu-id="abadd-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="abadd-235">登出，並使新的 Skype for Business Server 安全性群組，更新您的安全性權杖，然後登入 Windows，然後重新開啟 [部署精靈。</span><span class="sxs-lookup"><span data-stu-id="abadd-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="abadd-236">確認您看到**準備 Active Directory**以確認成功旁的綠色核取記號，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="abadd-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![準備 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="abadd-238">另請參閱</span><span class="sxs-lookup"><span data-stu-id="abadd-238">See also</span></span>
 
[<span data-ttu-id="abadd-239">Skype 商務 Server 2015 的 active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="abadd-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
