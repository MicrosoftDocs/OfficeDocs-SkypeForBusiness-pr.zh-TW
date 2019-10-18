---
title: 在 Microsoft 團隊用戶端中實施服務品質
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 實施 Microsoft 團隊用戶端的服務品質（QoS）。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28e6664fa43819493e5b9e02d182bcec44f00905
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572560"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="7e116-103">在 Windows 用戶端上設定 QoS</span><span class="sxs-lookup"><span data-stu-id="7e116-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="7e116-104">您可以在 [群組原則] 中使用原則式 QoS，在團隊用戶端中設定預先定義 DSCP 值的來源埠範圍。</span><span class="sxs-lookup"><span data-stu-id="7e116-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="7e116-105">下表中指定的埠範圍是為每個工作負載建立原則的起點。</span><span class="sxs-lookup"><span data-stu-id="7e116-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="7e116-106">_建議的初始埠範圍_</span><span class="sxs-lookup"><span data-stu-id="7e116-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="7e116-107">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="7e116-107">Media traffic type</span></span>| <span data-ttu-id="7e116-108">用戶端來源埠範圍</span><span class="sxs-lookup"><span data-stu-id="7e116-108">Client source port range</span></span> |<span data-ttu-id="7e116-109">通訊協定</span><span class="sxs-lookup"><span data-stu-id="7e116-109">Protocol</span></span>|<span data-ttu-id="7e116-110">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="7e116-110">DSCP value</span></span>|<span data-ttu-id="7e116-111">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="7e116-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="7e116-112">音訊</span><span class="sxs-lookup"><span data-stu-id="7e116-112">Audio</span></span>| <span data-ttu-id="7e116-113">50000–50019</span><span class="sxs-lookup"><span data-stu-id="7e116-113">50,000–50,019</span></span>|<span data-ttu-id="7e116-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7e116-114">TCP/UDP</span></span>|<span data-ttu-id="7e116-115">46</span><span class="sxs-lookup"><span data-stu-id="7e116-115">46</span></span>|<span data-ttu-id="7e116-116">加急轉移（EF）</span><span class="sxs-lookup"><span data-stu-id="7e116-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="7e116-117">顯示器</span><span class="sxs-lookup"><span data-stu-id="7e116-117">Video</span></span>| <span data-ttu-id="7e116-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="7e116-118">50,020–50,039</span></span>|<span data-ttu-id="7e116-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7e116-119">TCP/UDP</span></span>|<span data-ttu-id="7e116-120">34</span><span class="sxs-lookup"><span data-stu-id="7e116-120">34</span></span>|<span data-ttu-id="7e116-121">有保證的轉寄（AF41）</span><span class="sxs-lookup"><span data-stu-id="7e116-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="7e116-122">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="7e116-122">Application/Screen Sharing</span></span>| <span data-ttu-id="7e116-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="7e116-123">50,040–50,059</span></span>|<span data-ttu-id="7e116-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7e116-124">TCP/UDP</span></span>|<span data-ttu-id="7e116-125">滿</span><span class="sxs-lookup"><span data-stu-id="7e116-125">18</span></span>|<span data-ttu-id="7e116-126">有保證的轉寄（AF21）</span><span class="sxs-lookup"><span data-stu-id="7e116-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="7e116-127">請盡可能在群群組原則物件中設定原則式 QoS 設定。</span><span class="sxs-lookup"><span data-stu-id="7e116-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="7e116-128">下列步驟與[在商務用 Skype Server 上針對您的用戶端設定埠範圍和服務品質原則](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常相似，這也有一些其他可能不必要的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7e116-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="7e116-129">若要為加入網域的 Windows 10 電腦建立 QoS 音訊原則，請先登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="7e116-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="7e116-130">開啟 [群組原則管理] （按一下 [開始]，指向 [系統管理工具]，然後按一下 [群組原則管理]），然後完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7e116-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="7e116-131">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="7e116-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="7e116-132">例如，如果所有用戶端電腦都位於一個名為「**用戶端**」的 OU 中，則應該在用戶端 OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="7e116-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="7e116-133">以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="7e116-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="7e116-134">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7e116-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="7e116-135">以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7e116-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="7e116-136">在 [群組原則管理編輯器] 中，展開 [**電腦**設定]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="7e116-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="7e116-137">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="7e116-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="7e116-138">選取 [**指定 DSCP 值**]，然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="7e116-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="7e116-139">[離開]**指定輸出限制率**未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7e116-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="7e116-140">在下一頁中，選取 [**僅限具有此可執行檔名稱的應用程式**]，然後輸入名稱 [**團隊 .exe**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7e116-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="7e116-141">此設定會指示原則只會將小組用戶端的流量相符的優先順序。</span><span class="sxs-lookup"><span data-stu-id="7e116-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="7e116-142">在第三個頁面上，確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7e116-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="7e116-143">這兩項設定可確保無論哪個電腦（IP 位址）傳送資料包，以及哪台電腦（IP 位址）會接收資料包，都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="7e116-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="7e116-144">在第四頁，從 [**選取此 QoS 原則套用至下列協定**] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="7e116-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="7e116-145">TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是兩種最常使用的網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="7e116-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="7e116-146">在 [標題] 底下，**指定來源埠號**，選取 [**從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="7e116-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="7e116-147">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="7e116-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="7e116-148">例如，如果您是透過埠50019將埠50000保留音訊流量，請輸入使用此格式的埠範圍： **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="7e116-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="7e116-149">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="7e116-149">Click **Finish**.</span></span>

11. <span data-ttu-id="7e116-150">重複步驟5-10 來建立影片和應用程式/桌面共用的原則，在步驟6和10中取代適當的值。</span><span class="sxs-lookup"><span data-stu-id="7e116-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="7e116-151">在用戶端電腦上重新整理 [群組原則] 之前，您所建立的新原則將不會生效。</span><span class="sxs-lookup"><span data-stu-id="7e116-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="7e116-152">雖然群組原則會定期自行進行重新整理，但是您可以遵循下列步驟強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="7e116-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="7e116-153">在您要重新整理群組原則的每個電腦上，開啟命令主控台。</span><span class="sxs-lookup"><span data-stu-id="7e116-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="7e116-154">確定命令主控台已設定為以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="7e116-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="7e116-155">在命令提示字元中，輸入</span><span class="sxs-lookup"><span data-stu-id="7e116-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="7e116-156">驗證群群組原則物件中的 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="7e116-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="7e116-157">若要確認已設定群組原則物件的值，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7e116-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="7e116-158">開啟命令主控台。</span><span class="sxs-lookup"><span data-stu-id="7e116-158">Open a command console.</span></span> <span data-ttu-id="7e116-159">確定命令主控台已設定為以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="7e116-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="7e116-160">在命令提示字元中，輸入：</span><span class="sxs-lookup"><span data-stu-id="7e116-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="7e116-161">這會產生報告並將它傳送到名為 gp 的文字檔。</span><span class="sxs-lookup"><span data-stu-id="7e116-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="7e116-162">或者，您也可以輸入下列命令，以在名為 gp 的 HTML 報表中產生相同的資料。</span><span class="sxs-lookup"><span data-stu-id="7e116-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="7e116-163">![運行 gpresult 命令之主控台視窗的螢幕擷取畫面。](media/Qos-in-Teams-Image3.png "運行 gpresult 命令之主控台視窗的螢幕擷取畫面。")</span><span class="sxs-lookup"><span data-stu-id="7e116-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="7e116-164">在產生的檔案中，尋找標題套用的**群組原則物件**，並確認在已套用的原則清單中，先前建立的群組原則物件名稱。</span><span class="sxs-lookup"><span data-stu-id="7e116-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="7e116-165">開啟 [登錄編輯程式]，然後移至：</span><span class="sxs-lookup"><span data-stu-id="7e116-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="7e116-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="7e116-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="7e116-167">確認資料表4中所列的登錄專案值。</span><span class="sxs-lookup"><span data-stu-id="7e116-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="7e116-168">_資料表4。QoS 的 Windows 登錄專案值_</span><span class="sxs-lookup"><span data-stu-id="7e116-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="7e116-169">名稱</span><span class="sxs-lookup"><span data-stu-id="7e116-169">Name</span></span>          |  <span data-ttu-id="7e116-170">類型</span><span class="sxs-lookup"><span data-stu-id="7e116-170">Type</span></span>  |    <span data-ttu-id="7e116-171">資料</span><span class="sxs-lookup"><span data-stu-id="7e116-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="7e116-172">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="7e116-172">Application Name</span></span>    | <span data-ttu-id="7e116-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-173">REG_SZ</span></span> |  <span data-ttu-id="7e116-174">團隊 .exe</span><span class="sxs-lookup"><span data-stu-id="7e116-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="7e116-175">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="7e116-175">DSCP Value</span></span>       | <span data-ttu-id="7e116-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-176">REG_SZ</span></span> |     <span data-ttu-id="7e116-177">46</span><span class="sxs-lookup"><span data-stu-id="7e116-177">46</span></span>      |
   |        <span data-ttu-id="7e116-178">本機 IP</span><span class="sxs-lookup"><span data-stu-id="7e116-178">Local IP</span></span>        | <span data-ttu-id="7e116-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="7e116-180">本機 IP 前置詞長度</span><span class="sxs-lookup"><span data-stu-id="7e116-180">Local IP Prefix Length</span></span> | <span data-ttu-id="7e116-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="7e116-182">本機埠</span><span class="sxs-lookup"><span data-stu-id="7e116-182">Local Port</span></span>       | <span data-ttu-id="7e116-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-183">REG_SZ</span></span> | <span data-ttu-id="7e116-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="7e116-184">50000-50019</span></span> |
   |        <span data-ttu-id="7e116-185">通訊協定</span><span class="sxs-lookup"><span data-stu-id="7e116-185">Protocol</span></span>        | <span data-ttu-id="7e116-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="7e116-187">遠端 IP</span><span class="sxs-lookup"><span data-stu-id="7e116-187">Remote IP</span></span>        | <span data-ttu-id="7e116-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="7e116-189">遠端 IP 首碼</span><span class="sxs-lookup"><span data-stu-id="7e116-189">Remote IP Prefix</span></span>    | <span data-ttu-id="7e116-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="7e116-191">遠端埠</span><span class="sxs-lookup"><span data-stu-id="7e116-191">Remote Port</span></span>       | <span data-ttu-id="7e116-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="7e116-193">節流率</span><span class="sxs-lookup"><span data-stu-id="7e116-193">Throttle Rate</span></span>      | <span data-ttu-id="7e116-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7e116-194">REG_SZ</span></span> |     <span data-ttu-id="7e116-195">-1</span><span class="sxs-lookup"><span data-stu-id="7e116-195">-1</span></span>      |

5. <span data-ttu-id="7e116-196">針對您正在使用的用戶端，確認 [應用程式名稱] 專案的值正確無誤，然後確認 [DSCP 值] 和 [本機埠] 專案都反映了 [群組原則] 物件中的設定。</span><span class="sxs-lookup"><span data-stu-id="7e116-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
