---
title: '在 Microsoft 團隊用戶端中實現服務品質 (QoS) '
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何使用服務品質 (QoS) 來優化 Microsoft 團隊桌面用戶端的網路流量。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526400"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="09ce2-103">在 Microsoft 團隊用戶端中實現服務品質 (QoS) </span><span class="sxs-lookup"><span data-stu-id="09ce2-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="09ce2-104">您可以在群組原則中使用原則式服務品質 (QoS) ，以在團隊用戶端中設定預先定義之 DSCP 值的來源埠範圍。</span><span class="sxs-lookup"><span data-stu-id="09ce2-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="09ce2-105">下表中指定的埠範圍是為每個工作負載建立原則的起點。</span><span class="sxs-lookup"><span data-stu-id="09ce2-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="09ce2-106">*資料表1。建議的初始埠範圍*</span><span class="sxs-lookup"><span data-stu-id="09ce2-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="09ce2-107">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="09ce2-107">Media traffic type</span></span>| <span data-ttu-id="09ce2-108">用戶端來源連接埠範圍 </span><span class="sxs-lookup"><span data-stu-id="09ce2-108">Client source port range</span></span> |<span data-ttu-id="09ce2-109">通訊協定</span><span class="sxs-lookup"><span data-stu-id="09ce2-109">Protocol</span></span>|<span data-ttu-id="09ce2-110">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="09ce2-110">DSCP value</span></span>|<span data-ttu-id="09ce2-111">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="09ce2-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="09ce2-112">音訊</span><span class="sxs-lookup"><span data-stu-id="09ce2-112">Audio</span></span>| <span data-ttu-id="09ce2-113">50,000-50,019</span><span class="sxs-lookup"><span data-stu-id="09ce2-113">50,000–50,019</span></span>|<span data-ttu-id="09ce2-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="09ce2-114">TCP/UDP</span></span>|<span data-ttu-id="09ce2-115">46</span><span class="sxs-lookup"><span data-stu-id="09ce2-115">46</span></span>|<span data-ttu-id="09ce2-116">快速式轉送 (EF)</span><span class="sxs-lookup"><span data-stu-id="09ce2-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="09ce2-117">影片</span><span class="sxs-lookup"><span data-stu-id="09ce2-117">Video</span></span>| <span data-ttu-id="09ce2-118">50,020-50,039</span><span class="sxs-lookup"><span data-stu-id="09ce2-118">50,020–50,039</span></span>|<span data-ttu-id="09ce2-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="09ce2-119">TCP/UDP</span></span>|<span data-ttu-id="09ce2-120">34</span><span class="sxs-lookup"><span data-stu-id="09ce2-120">34</span></span>|<span data-ttu-id="09ce2-121">保證式轉送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="09ce2-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="09ce2-122">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="09ce2-122">Application/Screen Sharing</span></span>| <span data-ttu-id="09ce2-123">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="09ce2-123">50,040–50,059</span></span>|<span data-ttu-id="09ce2-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="09ce2-124">TCP/UDP</span></span>|<span data-ttu-id="09ce2-125">滿</span><span class="sxs-lookup"><span data-stu-id="09ce2-125">18</span></span>|<span data-ttu-id="09ce2-126">保證式轉送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="09ce2-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="09ce2-127">請盡可能在群群組原則物件中設定原則式 QoS 設定。</span><span class="sxs-lookup"><span data-stu-id="09ce2-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="09ce2-128">下列步驟與  [在商務用 Skype Server 上針對您的用戶端設定埠範圍和服務品質原則](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常相似，這也有一些其他可能不必要的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="09ce2-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="09ce2-129">若要為加入網域的 Windows 10 電腦建立 QoS 音訊原則，請先登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="09ce2-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="09ce2-130">開啟 [群組原則管理] (按一下 [開始]，指向 [系統管理工具]，然後按一下 [群組原則管理]) ，然後完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="09ce2-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="09ce2-131">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="09ce2-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="09ce2-132">例如，如果所有用戶端電腦都位於一個名為「 **用戶端**」的 OU 中，則應該在用戶端 OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="09ce2-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="09ce2-133">以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="09ce2-134">在 [ **新增 GPO** ] 對話方塊的 [ **名稱** ] 方塊中，輸入新群組原則物件的名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="09ce2-135">以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="09ce2-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="09ce2-136">在 [群組原則管理編輯器] 中，展開 [ **電腦**設定]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [ **原則式 QoS**]，然後按一下 [ **建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="09ce2-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="09ce2-137">在 [ **原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [ **名稱** ] 方塊中輸入新原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="09ce2-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="09ce2-138">選取 [ **指定 DSCP 值** ]，然後將值設定為 **46**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="09ce2-139">[離開] **指定輸出限制率** 未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="09ce2-140">在下一頁中，選取 [ **僅限具有此可執行檔名稱的應用程式** ]，然後輸入 **Teams.exe**的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="09ce2-141">此設定會指示原則只會將小組用戶端的流量相符的優先順序。</span><span class="sxs-lookup"><span data-stu-id="09ce2-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="09ce2-142">在第三個頁面上，確認已選取 [ **所有來源 ip 位址** ] 和 [ **任何目的地 ip 位址** ]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="09ce2-143">這兩項設定可確保資料包會受到管理，不論哪台電腦 (IP 位址) 傳送資料包，以及哪些電腦 (IP 位址) 會接收資料包。</span><span class="sxs-lookup"><span data-stu-id="09ce2-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="09ce2-144">在第四頁，從 [**選取此 QoS 原則套用至下列協定**] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="09ce2-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="09ce2-145">TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是兩種最常使用的網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="09ce2-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="09ce2-146">在 [標題] 底下， **指定來源埠號**，選取 [ **從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="09ce2-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="09ce2-147">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="09ce2-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="09ce2-148">例如，如果您是透過埠50019將埠50000保留音訊流量，請輸入使用此格式的埠範圍： **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="09ce2-149">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="09ce2-149">Click **Finish**.</span></span>

1. <span data-ttu-id="09ce2-150">重複步驟5-10 來建立影片和應用程式/桌面共用的原則，在步驟6和10中取代適當的值。</span><span class="sxs-lookup"><span data-stu-id="09ce2-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="09ce2-151">在用戶端電腦上重新整理 [群組原則] 之前，您所建立的新原則將不會生效。</span><span class="sxs-lookup"><span data-stu-id="09ce2-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="09ce2-152">雖然群組原則會定期自行進行重新整理，但是您可以遵循下列步驟強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="09ce2-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="09ce2-153">在您要重新整理群組原則的每一台電腦上，以系統管理員身分開啟命令提示字元， (*以系統管理員身分執行*) 。</span><span class="sxs-lookup"><span data-stu-id="09ce2-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="09ce2-154">在命令提示字元中，輸入</span><span class="sxs-lookup"><span data-stu-id="09ce2-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="09ce2-155">驗證群群組原則物件中的 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="09ce2-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="09ce2-156">若要確認已設定群組原則物件的值，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="09ce2-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="09ce2-157">以系統管理員身分開啟命令提示字元， (*以系統管理員身分執行*) 。</span><span class="sxs-lookup"><span data-stu-id="09ce2-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="09ce2-158">在命令提示字元中，輸入</span><span class="sxs-lookup"><span data-stu-id="09ce2-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="09ce2-159">這會產生已套用 Gpo 的報告，並將它傳送到名為 *gp.txt*的文字檔。</span><span class="sxs-lookup"><span data-stu-id="09ce2-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="09ce2-160">如需名為 *gp.html*的可讀性較強的 HTML 報表，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="09ce2-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="09ce2-161">在產生的檔案中，尋找標題套用的 **群組原則物件** ，並確認在已套用的原則清單中，先前建立的群組原則物件名稱。</span><span class="sxs-lookup"><span data-stu-id="09ce2-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="09ce2-162">開啟 [登錄編輯程式]，然後移至</span><span class="sxs-lookup"><span data-stu-id="09ce2-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="09ce2-163">HKEY \_ 本機 \_ 電腦 \\ 軟體 \\ 原則 \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="09ce2-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="09ce2-164">確認資料表2中所列的登錄專案值。</span><span class="sxs-lookup"><span data-stu-id="09ce2-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="09ce2-165">*表格2。QoS 的 Windows 登錄專案值*</span><span class="sxs-lookup"><span data-stu-id="09ce2-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="09ce2-166">名稱</span><span class="sxs-lookup"><span data-stu-id="09ce2-166">Name</span></span>          |  <span data-ttu-id="09ce2-167">類型</span><span class="sxs-lookup"><span data-stu-id="09ce2-167">Type</span></span>  |    <span data-ttu-id="09ce2-168">資料</span><span class="sxs-lookup"><span data-stu-id="09ce2-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="09ce2-169">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="09ce2-169">Application Name</span></span>    | <span data-ttu-id="09ce2-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-170">REG_SZ</span></span> |  <span data-ttu-id="09ce2-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="09ce2-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="09ce2-172">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="09ce2-172">DSCP Value</span></span>       | <span data-ttu-id="09ce2-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-173">REG_SZ</span></span> |     <span data-ttu-id="09ce2-174">46</span><span class="sxs-lookup"><span data-stu-id="09ce2-174">46</span></span>      |
   |        <span data-ttu-id="09ce2-175">本機 IP</span><span class="sxs-lookup"><span data-stu-id="09ce2-175">Local IP</span></span>        | <span data-ttu-id="09ce2-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="09ce2-177">本機 IP 前置詞長度</span><span class="sxs-lookup"><span data-stu-id="09ce2-177">Local IP Prefix Length</span></span> | <span data-ttu-id="09ce2-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="09ce2-179">本機埠</span><span class="sxs-lookup"><span data-stu-id="09ce2-179">Local Port</span></span>       | <span data-ttu-id="09ce2-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-180">REG_SZ</span></span> | <span data-ttu-id="09ce2-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="09ce2-181">50000-50019</span></span> |
   |        <span data-ttu-id="09ce2-182">通訊協定</span><span class="sxs-lookup"><span data-stu-id="09ce2-182">Protocol</span></span>        | <span data-ttu-id="09ce2-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="09ce2-184">遠端 IP</span><span class="sxs-lookup"><span data-stu-id="09ce2-184">Remote IP</span></span>        | <span data-ttu-id="09ce2-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="09ce2-186">遠端 IP 首碼</span><span class="sxs-lookup"><span data-stu-id="09ce2-186">Remote IP Prefix</span></span>    | <span data-ttu-id="09ce2-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="09ce2-188">遠端埠</span><span class="sxs-lookup"><span data-stu-id="09ce2-188">Remote Port</span></span>       | <span data-ttu-id="09ce2-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="09ce2-190">節流率</span><span class="sxs-lookup"><span data-stu-id="09ce2-190">Throttle Rate</span></span>      | <span data-ttu-id="09ce2-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="09ce2-191">REG_SZ</span></span> |     <span data-ttu-id="09ce2-192">-1</span><span class="sxs-lookup"><span data-stu-id="09ce2-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="09ce2-193">針對您正在使用的用戶端，確認 [應用程式名稱] 專案的值正確無誤，然後確認 [DSCP 值] 和 [本機埠] 專案都反映了 [群組原則] 物件中的設定。</span><span class="sxs-lookup"><span data-stu-id="09ce2-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="09ce2-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="09ce2-194">Related topics</span></span>

[<span data-ttu-id="09ce2-195">在團隊中實現服務品質 (QoS) </span><span class="sxs-lookup"><span data-stu-id="09ce2-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)