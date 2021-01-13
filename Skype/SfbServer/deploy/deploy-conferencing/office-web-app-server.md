---
title: 設定商務用 Skype Server 中的 Office Web Apps Server 整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要：閱讀此主題以瞭解如何設定 Office Web Apps Server 與商務用 Skype Server 之間的整合，以啟用 Web 會議的 PowerPoint 簡報。
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820463"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="7f994-103">設定商務用 Skype Server 中的 Office Web Apps Server 整合</span><span class="sxs-lookup"><span data-stu-id="7f994-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="7f994-104">**摘要：** 閱讀此主題以瞭解如何設定 Office Web Apps Server 與商務用 Skype Server 之間的整合，以啟用 Web 會議的 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="7f994-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="7f994-105">商務用 Skype 伺服器採用 Office Web Apps Server 來處理 Web 會議 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="7f994-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="7f994-106">如需此方法之優點的詳細資訊，請參閱 [在商務用 Skype Server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="7f994-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="7f994-107">您必須先確定已部署並設定 Office Web Apps server，才能設定商務用 Skype 伺服器以使用 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="7f994-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="7f994-108">如需 Office Web Apps Server 的資訊，請參閱 [部署基礎結構： Office Online 伺服器](https://go.microsoft.com/fwlink/p/?linkid=257525)一文。</span><span class="sxs-lookup"><span data-stu-id="7f994-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="7f994-109">成功安裝 Office Web Apps Server 並正確設定網頁伺服器陣列後，您必須先將 Office Web Apps Server 探索 URL 新增至商務用 Skype 伺服器拓撲，才能設定商務用 Skype Server 與新伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="7f994-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7f994-110">Office Web Apps Server 的最新小小小，稱為 Office Online Server，它是由商務用 Skype Server 所支援。</span><span class="sxs-lookup"><span data-stu-id="7f994-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="7f994-111">如需詳細資訊，請參閱 [Office Online Server 檔](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7f994-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="7f994-112">設定商務用 Skype Server 與 Office Web Apps Server 通訊</span><span class="sxs-lookup"><span data-stu-id="7f994-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="7f994-113">若要將 Office Web Apps Server 新增至拓撲，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7f994-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="7f994-114">開啟商務用 Skype Server 拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="7f994-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="7f994-115">在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7f994-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="7f994-p104">在 **[另存拓撲]** 對話方塊的 **[檔案名稱]** 方塊中，鍵入拓撲文件的名稱 (例如 **PreWebAppsServerTopology**)，然後按一下 **[儲存]**。如果新拓撲之後發生問題，就可以擷取並重新發行此拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f994-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="7f994-118">在 [拓撲產生器] 中，展開 [ **商務用 Skype 伺服器**]，展開您網站的名稱，展開 [ **Enterprise Edition 前端** 集區]，以滑鼠右鍵按一下其中一個集區的名稱，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="7f994-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="7f994-119">在 **[編輯內容]** 對話方塊的 **[一般]** 索引標籤上，尋找標題 **[關聯 Office Web Apps Server]**，然後按一下 **[新增]** (或從下拉式清單中選取現有的 Office Web Apps Server)。</span><span class="sxs-lookup"><span data-stu-id="7f994-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="7f994-120">在 **[定義新的 Office Web Apps Server]** 對話方塊的 **[Office Web Apps Server FQDN]** 方塊中，鍵入 Office Web Apps Server 電腦的完整網域名稱 (FQDN)；執行此動作時，您的 Office Web Apps Server 探索 URL 應自動輸入至 **[Office Web Apps Server 探索 URL]** 方塊。</span><span class="sxs-lookup"><span data-stu-id="7f994-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="7f994-121">如果 Office Web Apps Server 安裝于內部部署和商務用 Skype Server 所在的網路區域中，則選項 **Office Web Apps server 部署在外部網路中 (也就是說，不應該選取周邊/網際網路)** 。</span><span class="sxs-lookup"><span data-stu-id="7f994-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="7f994-122">如果 Office Web Apps Server 部署在內部防火牆外，則選取 **[Office Web Apps Server 部署在外部網路 (亦即周邊/網際網路]** 選項。</span><span class="sxs-lookup"><span data-stu-id="7f994-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="7f994-123">在 **[定義新的 Office Web Apps Server]** 對話方塊中，按一下 **[確定]**，然後按一下 **[編輯內容]** 對話方塊中的 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7f994-123">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="7f994-124">然後會將探索 URL 列為集區的關聯之一。</span><span class="sxs-lookup"><span data-stu-id="7f994-124">The discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="7f994-125">您必須對每個需要與 Office Web Apps Server 建立關聯的集區重複此程序。</span><span class="sxs-lookup"><span data-stu-id="7f994-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="7f994-126">將探索 URL 新增至拓撲之後，您必須發佈更新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f994-126">After you have added the discovery URL to the topology, you must then publish the updated topology.</span></span> <span data-ttu-id="7f994-127">在拓撲產生器中執行此作業的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="7f994-127">To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="7f994-128">按一下 **[動作]**，然後按一下 **[發行拓撲]**。</span><span class="sxs-lookup"><span data-stu-id="7f994-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="7f994-129">在發行拓撲精靈的 **[發行拓撲]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f994-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="7f994-130">在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="7f994-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="7f994-131">關閉拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="7f994-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="7f994-132">設定外部使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="7f994-132">Configure access for external users</span></span>

<span data-ttu-id="7f994-133">如果您想要讓外部使用者 (也就是說，使用者從組織的防火牆外登入) 若要存取 Office Web Apps Server PowerPoint 簡報，則您必須使用 Office Web Apps Server 和反向 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f994-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="7f994-134">您也必須建立及設定網站發行規則，這會協助確保使用者能夠連接到伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f994-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="7f994-135">驗證設定</span><span class="sxs-lookup"><span data-stu-id="7f994-135">Validate the configuration</span></span>

<span data-ttu-id="7f994-136">將 Office Web Apps Server 新增至拓撲之後，在發行拓撲之後，您應該會在商務用 Skype Server 事件記錄檔中看到兩個新的事件記錄事件。</span><span class="sxs-lookup"><span data-stu-id="7f994-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="7f994-137">首先，應新增 LS 資料 MCU 事件 (事件識別碼 41034) 。此事件會報告已探索到 Office Web Apps Server：</span><span class="sxs-lookup"><span data-stu-id="7f994-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="7f994-138">**已探索 Web 會議伺服器 Office Web Apps Server，PowerPoint 內容已啟用。**</span><span class="sxs-lookup"><span data-stu-id="7f994-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="7f994-139">除了該之外，您還應該看到另一個 LS 資料 MCU 事件， (事件識別碼 41032) ，以報告回 URLs 的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="7f994-139">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="7f994-140">例如，您應該會看到類似下列的內容：</span><span class="sxs-lookup"><span data-stu-id="7f994-140">For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="7f994-141">**Web 會議伺服器 Office Web Apps Server discovery 已成功。**</span><span class="sxs-lookup"><span data-stu-id="7f994-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="7f994-142">**Office Web Apps Server 內部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ; 嵌入 =**</span><span class="sxs-lookup"><span data-stu-id="7f994-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="7f994-143">**Office Web Apps Server 內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ; 嵌入 = true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="7f994-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="7f994-144">如果您已設定外部使用者的存取權，您也會看到類似下列專案的內容：</span><span class="sxs-lookup"><span data-stu-id="7f994-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="7f994-145">**Office Web Apps Server 外部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ; 嵌入**</span><span class="sxs-lookup"><span data-stu-id="7f994-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="7f994-146">**Office Web Apps Server 內部出席者頁面： <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**</span><span class="sxs-lookup"><span data-stu-id="7f994-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="7f994-147">如果您看到 LS 資料 MCU 事件，但事件識別碼為41033，表示 Office Web Apps Server discovery 失敗。</span><span class="sxs-lookup"><span data-stu-id="7f994-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="7f994-148">在此情況下，商務用 Skype 伺服器將嘗試多次，以探索新設定的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="7f994-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="7f994-149">如果探索過程重複失敗，您應該移除拓撲檔中的 Office Web Apps Server、發佈更新的拓撲，然後在解決連接問題後，嘗試將 Office Web Apps Server 重新新增至拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f994-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="7f994-150">如果 Office Web Apps Server 似乎已正確設定，且已被探索程式識別，您可以在一對商務用 Skype 用戶端之間共用 PowerPoint 簡報，以確認 Office Web Apps Server 的運作方式如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="7f994-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="7f994-151">如果使用者 A 可以載入及顯示 PowerPoint 簡報，而且使用者 B 可以加入會議，並查看該簡報之後，Office Web Apps Server 會正常運作。</span><span class="sxs-lookup"><span data-stu-id="7f994-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="7f994-152">即使已正確設定 Office Web Apps Server，當您嘗試共用 PowerPoint 簡報時，可能會收到錯誤訊息「某些共用功能因伺服器連線問題而無法使用」。</span><span class="sxs-lookup"><span data-stu-id="7f994-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="7f994-153">如果您收到該錯誤訊息，您應該重新開機前端伺服器 (或與新 Office Web Apps Server 關聯的伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="7f994-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

