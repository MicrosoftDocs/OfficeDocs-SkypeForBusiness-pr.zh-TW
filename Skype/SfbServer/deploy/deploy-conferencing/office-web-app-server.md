---
title: 在商務用 Skype Server 中設定與 Office Web Apps Server 的整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '摘要: 請閱讀本主題, 以瞭解如何設定 Office Web Apps 伺服器與商務用 Skype 伺服器之間的整合, 以啟用適用于 Web 會議的 PowerPoint 簡報。'
ms.openlocfilehash: 7be69b24b2ae64763b1f9b0d324b812b60f69434
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "36194111"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="44e2d-103">在商務用 Skype Server 中設定與 Office Web Apps Server 的整合</span><span class="sxs-lookup"><span data-stu-id="44e2d-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="44e2d-104">**摘要:** 請閱讀本主題, 瞭解如何設定 Office Web Apps 伺服器與商務用 Skype 伺服器之間的整合, 以啟用適用于 Web 會議的 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="44e2d-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="44e2d-105">商務用 Skype 伺服器使用 Office Web Apps 伺服器來處理適用于 Web 會議的 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="44e2d-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="44e2d-106">如需此方法的優點資訊, 請參閱[在商務用 Skype 伺服器中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="44e2d-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="44e2d-107">在您可以將商務用 Skype Server 設定為使用 Office Web Apps Server 之前, 您必須先確認已部署並設定 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="44e2d-108">如需 Office Web Apps 伺服器的詳細資訊, 請參閱[部署基礎結構: Office Online 伺服器](https://go.microsoft.com/fwlink/p/?linkid=257525)一文。</span><span class="sxs-lookup"><span data-stu-id="44e2d-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="44e2d-109">成功安裝 Office Web Apps 伺服器並正確設定您的網站伺服器之後, 您必須先將 Office Web Apps Server 探索 URL 新增至您的商務用 Skype 中, 以設定商務用 Skype 伺服器與新伺服器通訊伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="44e2d-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="44e2d-110">Office Web Apps Server 的最新小版本命名為「Office Online Server」, 而商務用 Skype Server 支援此伺服器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="44e2d-111">如需詳細資訊, 請參閱[Office Online Server 檔](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="44e2d-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="44e2d-112">設定商務用 Skype 伺服器與 Office Web Apps 伺服器進行通訊</span><span class="sxs-lookup"><span data-stu-id="44e2d-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="44e2d-113">若要將 Office Web Apps 伺服器新增到拓撲中, 請完成下列步驟:</span><span class="sxs-lookup"><span data-stu-id="44e2d-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="44e2d-114">開啟商務用 Skype Server 拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="44e2d-115">在 [**拓撲**建立器] 對話方塊中, 選取 [**從現有的部署下載拓撲結構**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="44e2d-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="44e2d-116">在 [**將拓朴儲存為**] 對話方塊中, 于 [檔案名] 方塊中輸入拓撲檔的名稱 ( \*\*\*\* 例如, **PreWebAppsServerTopology**), 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="44e2d-116">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**.</span></span> <span data-ttu-id="44e2d-117">如果您在新的拓撲中遇到問題, 可在稍後檢索並重新發佈此拓撲。</span><span class="sxs-lookup"><span data-stu-id="44e2d-117">This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="44e2d-118">在 [拓撲建立器] 中, 展開 [**商務用 Skype 伺服器**], 展開您網站的名稱, 展開 [**企業版前端池**], 以滑鼠右鍵按一下其中一個池的名稱, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="44e2d-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="44e2d-119">在 [**編輯屬性**] 對話方塊的 [**一般**] 索引標籤上, 找到 [**關聯 Office Web Apps 伺服器**] 的 [標題], 然後按一下下拉式清單中的 [**新增**] (或選取現有的 Office Web Apps 伺服器)。</span><span class="sxs-lookup"><span data-stu-id="44e2d-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="44e2d-120">在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中, 輸入您 office web apps server 電腦的完整功能變數名稱 (FQDN);當您這樣做時, 您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="44e2d-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="44e2d-121">如果 Office Web Apps 伺服器已安裝于內部部署, 且位於與商務用 Skype Server 相同的網路區域中, 則不應選取 [ **Office Web apps] 伺服器 (也就是 [週邊/網際網路])** 。</span><span class="sxs-lookup"><span data-stu-id="44e2d-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="44e2d-122">如果 Office Web Apps 伺服器是在您的內部防火牆外部署, 請選取 [ **Office Web Apps 伺服器] 部署在外部網路 (也就是 [週邊/網際網路])**。</span><span class="sxs-lookup"><span data-stu-id="44e2d-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="44e2d-123">在 [**定義新的 Office Web Apps Server** ] 對話方塊中, 按一下 **[確定]**, 然後按一下 [**編輯屬性**] 對話方塊中的 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="44e2d-123">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="44e2d-124">然後, 發現 URL 就會列為其中一個池的關聯。</span><span class="sxs-lookup"><span data-stu-id="44e2d-124">The discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="44e2d-125">您必須針對需要與您的 Office Web Apps 伺服器相關聯的每個池重複此程式。</span><span class="sxs-lookup"><span data-stu-id="44e2d-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="44e2d-126">將探索 URL 新增到拓撲之後, 您必須接著發佈更新後的拓撲。</span><span class="sxs-lookup"><span data-stu-id="44e2d-126">After you have added the discovery URL to the topology, you must then publish the updated topology.</span></span> <span data-ttu-id="44e2d-127">若要在拓撲建立器中執行此動作:</span><span class="sxs-lookup"><span data-stu-id="44e2d-127">To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="44e2d-128">按一下 [**動作**], 然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="44e2d-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="44e2d-129">在 [發佈拓撲嚮導] 的 [**發佈拓撲**] 頁面上, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="44e2d-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="44e2d-130">在 [**發佈嚮導完成]** 頁面上, 按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="44e2d-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="44e2d-131">關閉拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="44e2d-132">設定外部使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="44e2d-132">Configure access for external users</span></span>

<span data-ttu-id="44e2d-133">如果您想要將外部使用者 (也就是從組織外的防火牆以外的使用者登入), 若要存取 Office Web Apps Server PowerPoint 簡報, 就必須使用 Office Web Apps Server 和反向 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="44e2d-134">您也需要建立並設定網站發佈規則, 這將有助於確保使用者能夠連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="44e2d-135">驗證配置</span><span class="sxs-lookup"><span data-stu-id="44e2d-135">Validate the configuration</span></span>

<span data-ttu-id="44e2d-136">在已將 Office Web Apps 伺服器新增到拓撲之後, 且在該拓撲發佈之後, 您應該會在商務用 Skype Server 事件記錄檔中看到兩個新的事件記錄事件。</span><span class="sxs-lookup"><span data-stu-id="44e2d-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="44e2d-137">首先, 應該新增 LS 資料 MCU 事件 (事件 ID 41034);這個事件會報告已發現 Office Web Apps 伺服器:</span><span class="sxs-lookup"><span data-stu-id="44e2d-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="44e2d-138">**已發現 Web 會議 Server Office Web Apps Server, 已啟用 PowerPoint 內容。**</span><span class="sxs-lookup"><span data-stu-id="44e2d-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="44e2d-139">此外, 您還會看到另一個 [LS 資料 MCU] 事件 (事件 ID 41032), 該事件會傳回 Office Web Apps Server Url。</span><span class="sxs-lookup"><span data-stu-id="44e2d-139">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="44e2d-140">例如, 您應該會看到類似以下的內容:</span><span class="sxs-lookup"><span data-stu-id="44e2d-140">For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="44e2d-141">**網路會議服務器 Office Web Apps 伺服器探索已成功完成。**</span><span class="sxs-lookup"><span data-stu-id="44e2d-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="44e2d-142">**Office Web Apps Server 內部簡報者頁面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; embed =**</span><span class="sxs-lookup"><span data-stu-id="44e2d-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="44e2d-143">**Office Web Apps 伺服器內部出席者頁面: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="44e2d-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="44e2d-144">如果您已設定外部使用者的存取權, 您也會看到類似以下的內容:</span><span class="sxs-lookup"><span data-stu-id="44e2d-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="44e2d-145">**Office Web Apps Server 外部簡報者頁面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; 內嵌**</span><span class="sxs-lookup"><span data-stu-id="44e2d-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="44e2d-146">**Office Web Apps 伺服器內部出席者頁面: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span><span class="sxs-lookup"><span data-stu-id="44e2d-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="44e2d-147">如果您看到 LS 資料 MCU 事件, 且事件 ID 為 41033, 表示 Office Web Apps Server 發現失敗。</span><span class="sxs-lookup"><span data-stu-id="44e2d-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="44e2d-148">在這種情況下, 商務用 Skype 伺服器會根據需要嘗試許多次數, 以探索新設定的 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44e2d-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="44e2d-149">如果探索程式重複失敗, 您應該從拓撲檔中移除 Office Web Apps 伺服器、發佈更新的拓撲, 然後在連線問題解決之後, 嘗試將 Office Web Apps 伺服器新增到拓撲結構。</span><span class="sxs-lookup"><span data-stu-id="44e2d-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="44e2d-150">如果 Office Web Apps 伺服器出現正確設定, 且已被探索程式辨識, 您可以在一對商務用 Skype 用戶端之間共用 PowerPoint 簡報, 以驗證 Office Web Apps 伺服器是否如期運作。</span><span class="sxs-lookup"><span data-stu-id="44e2d-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="44e2d-151">如果使用者 A 可以載入並顯示 PowerPoint 簡報, 而使用者 B 可以接著加入會議, 然後查看該簡報, 則 Office Web Apps Server 就能正常運作。</span><span class="sxs-lookup"><span data-stu-id="44e2d-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="44e2d-152">即使 Office Web Apps 伺服器的設定正確, 您也可能會在嘗試共用 PowerPoint 簡報時, 收到「由於伺服器連線問題, 有些共用功能無法使用」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="44e2d-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="44e2d-153">如果您收到該錯誤訊息, 您應該重新開機與新的 Office Web Apps 伺服器相關聯的前端伺服器 (或伺服器)。</span><span class="sxs-lookup"><span data-stu-id="44e2d-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

