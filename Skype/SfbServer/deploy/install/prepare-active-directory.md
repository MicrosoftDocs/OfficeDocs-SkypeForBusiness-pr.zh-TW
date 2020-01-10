---
title: 為商務用 Skype Server 準備 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要：瞭解如何準備 Active Directory 網域以進行商務用 Skype Server 的安裝。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址為： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 114b2a91491dd440972f589ff45d86835c676bef
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000883"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="6ff5e-104">為商務用 Skype Server 準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ff5e-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="6ff5e-105">**摘要：** 瞭解如何為您的 Active Directory 網域進行準備，以進行商務用 Skype Server 的安裝。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="6ff5e-106">從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 的免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="6ff5e-107">商務用 Skype 伺服器與 Active Directory 密切搭配使用。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="6ff5e-108">您必須準備 Active Directory 網域，才能搭配商務用 Skype 伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="6ff5e-109">這個程式是在部署嚮導中完成，只會針對網域進行一次。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="6ff5e-110">這是因為程式會建立群組並修改網域，而您只需要執行一次。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="6ff5e-111">您可以依照任何循序執行步驟1到5。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="6ff5e-112">不過，您必須在順序中執行步驟6、7和8，並在步驟1到5之後，如圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="6ff5e-113">準備 Active Directory 是8的步驟4。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="6ff5e-114">如需規劃 Active Directory 的詳細資訊，請參閱商務用 skype [server 2019 的](../../../SfBServer2019/plan/system-requirements.md)[商務用 Skype server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或伺服器需求的環境需求。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概覽圖表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="6ff5e-116">準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ff5e-116">Prepare Active Directory</span></span>

<span data-ttu-id="6ff5e-117">商務用 Skype Server 與 Active Directory 網域服務（AD DS）緊密整合。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6ff5e-118">在商務用 Skype Server 第一次安裝之前，必須準備作用中的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="6ff5e-119">標題為 [**準備 Active Directory** ] 的部署嚮導區段會準備作用中的 active directory 環境，以便與商務用 Skype 伺服器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ff5e-120">商務用 Skype Server 使用（AD DS）來追蹤並與拓撲中的所有伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="6ff5e-121">每個伺服器都必須加入網域，才能讓商務用 Skype 伺服器正常運作。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-121">Every server must be joined to the domain so that Skype for Business Server can work properly.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6ff5e-122">針對部署中的每個網域，只能執行一次準備 Active Directory 程式。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-122">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="6ff5e-123">觀看**準備 Active Directory**的影片步驟：</span><span class="sxs-lookup"><span data-stu-id="6ff5e-123">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="6ff5e-124">從 [部署] 嚮導準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ff5e-124">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="6ff5e-125">以擁有 Active Directory 網域之架構管理員認證的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-125">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="6ff5e-126">開啟商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-126">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6ff5e-127">如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行步驟之 AD DS 使用者的使用者目錄中，找到執行 [部署嚮導] 的電腦上的日誌檔。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-127">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="6ff5e-128">例如，如果使用者是以網域（contoso）的網域管理員身分登入，則記錄檔案位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-128">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="6ff5e-129">按一下 [**準備 Active Directory** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-129">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="6ff5e-130">**步驟1：準備架構**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-130">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="6ff5e-131">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-131">a.</span></span> <span data-ttu-id="6ff5e-132">若要查看步驟1的先決條件資訊，請按一下步驟1標題下方的下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-132">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="6ff5e-133">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-133">b.</span></span> <span data-ttu-id="6ff5e-134">按一下步驟1中的 [**執行**]，啟動 [準備架構] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-134">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="6ff5e-135">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-135">c.</span></span> <span data-ttu-id="6ff5e-136">請注意，此程式對於每個部署只能執行一次，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-136">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="6ff5e-137">希望.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-137">d.</span></span> <span data-ttu-id="6ff5e-138">準備好架構之後，您可以按一下 [**查看記錄**] 來查看記錄。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-138">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="6ff5e-139">e.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-139">e.</span></span> <span data-ttu-id="6ff5e-140">按一下 **[完成]** 以關閉 [準備架構] 嚮導，然後返回 [準備 Active Directory] 步驟。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-140">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="6ff5e-141">**步驟2：驗證架構分區的複製**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-141">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="6ff5e-142">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-142">a.</span></span> <span data-ttu-id="6ff5e-143">登入網域的網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-143">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="6ff5e-144">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-144">b.</span></span> <span data-ttu-id="6ff5e-145">從**伺服器管理員**中的 [**工具**] 下拉式功能表開啟 [ **ADSI 編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-145">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="6ff5e-146">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-146">c.</span></span> <span data-ttu-id="6ff5e-147">在 [**動作**] 功能表上，按一下 **[連線至]**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-147">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="6ff5e-148">希望.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-148">d.</span></span> <span data-ttu-id="6ff5e-149">在 [連線**設定**] 對話方塊中的 [**選取已知命名內容**] 底下，選取 [**架構**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-149">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="6ff5e-150">e.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-150">e.</span></span> <span data-ttu-id="6ff5e-151">在架構容器底下，搜尋**CN = ms-SIP-SchemaVersion**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-151">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="6ff5e-152">如果這個物件存在，且**rangeUpper**屬性的值為1150，且**rangeLower**屬性的值是3，則架構已成功更新並複製。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-152">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="6ff5e-153">如果此物件不存在，或**rangeUpper**和**rangeLower**屬性的值不是指定的，則架構並未被修改或未複製。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-153">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="6ff5e-154">**步驟3：準備目前的林**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-154">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="6ff5e-155">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-155">a.</span></span> <span data-ttu-id="6ff5e-156">若要查看步驟3的先決條件資訊，請按一下步驟3標題下方的下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-156">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="6ff5e-157">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-157">b.</span></span> <span data-ttu-id="6ff5e-158">按一下步驟3中的 [**執行**]，啟動 [準備目前的林] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-158">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="6ff5e-159">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-159">c.</span></span> <span data-ttu-id="6ff5e-160">請注意，每個部署的程式只應執行一次，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-160">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="6ff5e-161">希望.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-161">d.</span></span> <span data-ttu-id="6ff5e-162">指定將建立通用群組的網域。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-162">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="6ff5e-163">如果伺服器是網域的一部分，您可以選擇 [**本地域**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-163">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="6ff5e-164">e.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-164">e.</span></span> <span data-ttu-id="6ff5e-165">在林準備好之後，您可以按一下 [**查看記錄**] 來查看記錄。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-165">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="6ff5e-166">°.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-166">f.</span></span> <span data-ttu-id="6ff5e-167">按一下 **[完成]** ，關閉 [準備目前的林] 嚮導，然後返回 [準備 Active Directory] 步驟。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-167">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="6ff5e-168">7.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-168">g.</span></span> <span data-ttu-id="6ff5e-169">按一下 [**應用程式**] 頁面上的 [**商務用 Skype Server Management Shell** ] 以啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-169">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="6ff5e-170">h.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-170">h.</span></span> <span data-ttu-id="6ff5e-171">輸入命令 CsAdForest，然後按**enter**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-171">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="6ff5e-172">是否.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-172">i.</span></span> <span data-ttu-id="6ff5e-173">如果結果是**LC_FORESTSETTINGS_STATE_READY**，則目錄林已順利進行準備，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-173">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![驗證林複製。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="6ff5e-175">**步驟4：驗證全域編目的複製**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-175">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="6ff5e-176">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-176">a.</span></span> <span data-ttu-id="6ff5e-177">在網網域控制站（最好是位於其他網網域控制站的遠端網站中），在執行目錄林準備的林中，開啟**Active Directory 使用者和電腦**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-177">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="6ff5e-178">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-178">b.</span></span> <span data-ttu-id="6ff5e-179">在**Active Directory 使用者和電腦**中，展開您的林或子域的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-179">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="6ff5e-180">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-180">c.</span></span> <span data-ttu-id="6ff5e-181">按一下左側窗格中的 [**使用者**] 容器，然後在右側窗格中尋找 [通用群組] **CsAdministrator** 。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-181">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="6ff5e-182">如果 CsAdministrator （在以 Cs 開頭的其他新通用群組）存在，則表示已成功進行 Active Directory 複製。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-182">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="6ff5e-183">希望.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-183">d.</span></span> <span data-ttu-id="6ff5e-184">如果群組尚不存在，您可以強制進行複製，或等候15分鐘並重新整理右側窗格。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-184">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="6ff5e-185">當群組存在時，複製就完成了。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-185">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="6ff5e-186">**步驟5：準備目前的網域**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-186">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="6ff5e-187">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-187">a.</span></span> <span data-ttu-id="6ff5e-188">查看步驟5的先決條件資訊。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-188">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="6ff5e-189">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-189">b.</span></span> <span data-ttu-id="6ff5e-190">按一下步驟5中的 [**執行**]，啟動 [準備目前的網域] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-190">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="6ff5e-191">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-191">c.</span></span> <span data-ttu-id="6ff5e-192">請注意，這個程式只能針對部署中的每個網域執行一次，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-192">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="6ff5e-193">希望.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-193">d.</span></span> <span data-ttu-id="6ff5e-194">準備好網域之後，您可以按一下 [**查看記錄**] 來查看記錄。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-194">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="6ff5e-195">e.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-195">e.</span></span> <span data-ttu-id="6ff5e-196">按一下 **[完成]** ，關閉 [準備目前的網域] 嚮導，然後返回 [準備 Active Directory] 步驟。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-196">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="6ff5e-197">在已找到商務用 Skype Server 物件的每個網域中，都必須完成這些步驟，否則服務可能無法啟動。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-197">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="6ff5e-198">這包括任何類型的 Active Directory 物件，例如使用者、連絡人物件、系統管理群組或任何其他類型的物件。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-198">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="6ff5e-199">如有需要，您可以使用 CsUserReplicatorConfiguration-ADDomainNamingCoNtextList 來新增只有商務用 Skype Server 物件的網域。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-199">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="6ff5e-200">**步驟6：驗證網域中的複製**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-200">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="6ff5e-201">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-201">a.</span></span> <span data-ttu-id="6ff5e-202">按一下 [**應用程式**] 頁面上的 [**商務用 Skype Server Management Shell** ] 以啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-202">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="6ff5e-203">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-203">b.</span></span> <span data-ttu-id="6ff5e-204">使用命令 CsAdDomain 驗證網域中的複製。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-204">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="6ff5e-205">如果您沒有指定 Domain 參數，則會將此值設定至本機網域。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-205">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="6ff5e-206">針對 contoso. 本地域執行命令的範例：</span><span class="sxs-lookup"><span data-stu-id="6ff5e-206">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="6ff5e-207">使用參數 GlobalSettingsDomainController，您可以指出儲存全域設定的位置。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-207">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="6ff5e-208">如果您的設定是儲存在系統容器中（這通常是將未將全域設定遷移至配置容器的升級部署），您可以在 AD DS 目錄林的根目錄中定義網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-208">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="6ff5e-209">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-209">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6ff5e-210">如果您沒有指定此參數，Cmdlet 會假設設定會儲存在配置容器中，並參照 Active Directory 中的任何網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-210">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="6ff5e-211">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-211">c.</span></span> <span data-ttu-id="6ff5e-212">如果結果是**LC_DOMAINSETTINGS_STATE_READY**，則網域已順利複製。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-212">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="6ff5e-213">**步驟7：新增使用者以提供對商務用 Skype Server 控制台的系統管理存取權**</span><span class="sxs-lookup"><span data-stu-id="6ff5e-213">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="6ff5e-214">是.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-214">a.</span></span> <span data-ttu-id="6ff5e-215">使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-215">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="6ff5e-216">乙.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-216">b.</span></span> <span data-ttu-id="6ff5e-217">開啟 [ **Active Directory 使用者和電腦**]，展開您的網域，按一下 [**使用者**] 容器，以滑鼠右鍵按一下 [CSAdministrator]，然後選擇 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-217">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="6ff5e-218">c-clip.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-218">c.</span></span> <span data-ttu-id="6ff5e-219">在 [CSAdministrator 內容] \*\*\*\* 中，按一下 [成員] \*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-219">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="6ff5e-220">希望.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-220">d.</span></span> <span data-ttu-id="6ff5e-221">按一下 [**成員**] 索引標籤上的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-221">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="6ff5e-222">在 [選取使用者、連絡人、電腦、服務帳戶或群組] \*\*\*\* 中，找到 [輸入要選取的物件名稱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-222">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="6ff5e-223">輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-223">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="6ff5e-224">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-224">Click **OK**.</span></span>
    
    <span data-ttu-id="6ff5e-225">e.</span><span class="sxs-lookup"><span data-stu-id="6ff5e-225">e.</span></span> <span data-ttu-id="6ff5e-226">在 [**成員**] 索引標籤上，確認您所選取的使用者或群組存在。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-226">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="6ff5e-227">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-227">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="6ff5e-228">商務用 Skype Server 的 [控制台] 是一個以角色為基礎的存取控制工具。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-228">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="6ff5e-229">[CsAdministrator] 群組中的成員資格提供使用商務用 Skype Server 控制台的使用者，以取得所有可用的配置功能。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-229">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="6ff5e-230">有些其他的角色是針對特定功能而設計。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-230">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="6ff5e-231">如需可用角色的詳細資訊，請參閱商務用 skype [server 2019 的](../../../SfBServer2019/plan/system-requirements.md)[商務用 Skype server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或伺服器需求的環境需求。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-231">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="6ff5e-232">請注意，您不需要針對商務用 Skype Server 啟用使用者，就能成為管理群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-232">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="6ff5e-233">若要協助保留安全性與角色式的存取控制完整性，請將使用者新增至群組，以定義使用者在管理商務用 Skype Server 部署時所執行的角色。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-233">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="6ff5e-234">登出，然後重新登入 Windows，以便使用新的商務用 Skype Server 安全群組來更新您的安全權杖，然後重新開啟 [部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-234">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="6ff5e-235">確認您在 [**準備 Active Directory** ] 旁看到綠色的核取記號，以確認成功，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-235">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![準備 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="6ff5e-237">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ff5e-237">See also</span></span>
 
[<span data-ttu-id="6ff5e-238">商務用 Skype Server 2015 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="6ff5e-238">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
