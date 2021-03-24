---
title: 在 Microsoft Teams 用戶端中 (QoS) 服務品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何使用 QoS (服務品質) Microsoft Teams 桌面用戶端優化網路流量。
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
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094781"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="9e6be-103">在 Microsoft Teams 用戶端中 (QoS) 服務品質</span><span class="sxs-lookup"><span data-stu-id="9e6be-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="9e6be-104">您可以在群組原則內使用以 (QoS) 為 Teams 用戶端中預先定義的 DSCP 值設定來源埠範圍。</span><span class="sxs-lookup"><span data-stu-id="9e6be-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="9e6be-105">下表指定的埠範圍是為每個工作負載建立策略的起點。</span><span class="sxs-lookup"><span data-stu-id="9e6be-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="9e6be-106">*表格 1.建議的初始埠範圍*</span><span class="sxs-lookup"><span data-stu-id="9e6be-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="9e6be-107">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="9e6be-107">Media traffic type</span></span>| <span data-ttu-id="9e6be-108">用戶端來源連接埠範圍 </span><span class="sxs-lookup"><span data-stu-id="9e6be-108">Client source port range</span></span> |<span data-ttu-id="9e6be-109">通訊協定</span><span class="sxs-lookup"><span data-stu-id="9e6be-109">Protocol</span></span>|<span data-ttu-id="9e6be-110">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="9e6be-110">DSCP value</span></span>|<span data-ttu-id="9e6be-111">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="9e6be-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="9e6be-112">音訊</span><span class="sxs-lookup"><span data-stu-id="9e6be-112">Audio</span></span>| <span data-ttu-id="9e6be-113">50,000-50,019</span><span class="sxs-lookup"><span data-stu-id="9e6be-113">50,000–50,019</span></span>|<span data-ttu-id="9e6be-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9e6be-114">TCP/UDP</span></span>|<span data-ttu-id="9e6be-115">46</span><span class="sxs-lookup"><span data-stu-id="9e6be-115">46</span></span>|<span data-ttu-id="9e6be-116">快速式轉送 (EF)</span><span class="sxs-lookup"><span data-stu-id="9e6be-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="9e6be-117">影片</span><span class="sxs-lookup"><span data-stu-id="9e6be-117">Video</span></span>| <span data-ttu-id="9e6be-118">50,020-50,039</span><span class="sxs-lookup"><span data-stu-id="9e6be-118">50,020–50,039</span></span>|<span data-ttu-id="9e6be-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9e6be-119">TCP/UDP</span></span>|<span data-ttu-id="9e6be-120">34</span><span class="sxs-lookup"><span data-stu-id="9e6be-120">34</span></span>|<span data-ttu-id="9e6be-121">保證式轉送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="9e6be-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="9e6be-122">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="9e6be-122">Application/Screen Sharing</span></span>| <span data-ttu-id="9e6be-123">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="9e6be-123">50,040–50,059</span></span>|<span data-ttu-id="9e6be-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9e6be-124">TCP/UDP</span></span>|<span data-ttu-id="9e6be-125">18</span><span class="sxs-lookup"><span data-stu-id="9e6be-125">18</span></span>|<span data-ttu-id="9e6be-126">保證式轉送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="9e6be-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="9e6be-127">盡可能在群組原則物件中設定以策略為基礎的 QoS 設定。</span><span class="sxs-lookup"><span data-stu-id="9e6be-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="9e6be-128">下列步驟與在商務用  [Skype Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上為用戶端的埠範圍和服務品質政策非常類似，其中可能不需要一些額外的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9e6be-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="9e6be-129">若要為加入網域的 Windows 10 電腦建立 QoS 音訊策略，首先請登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="9e6be-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="9e6be-130">開啟群組原則管理 (按一下 [開始>，指向 [管理工具，然後按一下群組原則管理) ，然後完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9e6be-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="9e6be-131">在群組原則管理中，找出應建立新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="9e6be-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="9e6be-132">例如，如果您所有的用戶端電腦都位於名為 Client 的 OU中，則新策略應在用戶端 OU 中建立。</span><span class="sxs-lookup"><span data-stu-id="9e6be-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="9e6be-133">以滑鼠右鍵按一下適當的容器，然後按一下 [在此網域中建立 **GPO，然後在這裡連結它**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="9e6be-134">在 [ **新增 GPO>** 對話方塊中，在 [名稱> 方塊中輸入新群組原則 **物件的名稱，** 然後按一下 [ **確定**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="9e6be-135">以滑鼠右鍵按一下新建立的政策，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="9e6be-136">在群組原則管理編輯器中，展開[電腦設定>、展開 **Windows 設定**、以滑鼠右鍵按一下 [以策略為基礎的 **QoS，** 然後按一下 **[建立新策略**> 。</span><span class="sxs-lookup"><span data-stu-id="9e6be-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="9e6be-137">在 [ **以策略為基礎的 QoS** 對話方塊的開啟頁面上，在 [名稱> 方塊中輸入新 **政策** 的名稱。</span><span class="sxs-lookup"><span data-stu-id="9e6be-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="9e6be-138">選取 **指定 DSCP 值** ，然後將值設為 **46**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="9e6be-139">離開 **[指定未選的外** 發節流速，然後按一下 [下 **一步**> 。</span><span class="sxs-lookup"><span data-stu-id="9e6be-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="9e6be-140">在下一頁中，選取 [只有 **具有此可執行** 檔案名稱的應用程式，然後輸入 **Teams.exe名稱，** 然後按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="9e6be-141">此設定會指示策略只排列 Teams 用戶端的符合流量的優先順序。</span><span class="sxs-lookup"><span data-stu-id="9e6be-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="9e6be-142">請確定第三頁上已選取 [任何來源 **IP 位址** 及任何目的地 **IP** 位址，然後按一下 [下 **一步**> 。</span><span class="sxs-lookup"><span data-stu-id="9e6be-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="9e6be-143">這兩個設定可確保無論哪部電腦 (IP 位址) 封包，以及哪個電腦 (IP 位址) 都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="9e6be-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="9e6be-144">第四頁，從選取此 **QoS** 原則適用于下拉式清單的通訊協定，選取 TCP 和 **UDP。**</span><span class="sxs-lookup"><span data-stu-id="9e6be-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="9e6be-145">TCP (傳輸控制通訊) 和 UDP (使用者資料包通訊) 是最常用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="9e6be-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="9e6be-146">在標題下 **指定來源埠號碼**，選取 **從此來源埠或範圍**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="9e6be-147">在隨附的文字方塊中，輸入音訊廣播所保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="9e6be-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="9e6be-148">例如，如果您透過埠 50019 為音訊流量保留埠 50000，請使用此格式輸入埠範圍 **：50000：50019**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="9e6be-149">按一下 **[完成>**。</span><span class="sxs-lookup"><span data-stu-id="9e6be-149">Click **Finish**.</span></span>

1. <span data-ttu-id="9e6be-150">重複步驟 5-10，為影片和應用程式/桌面共用建立策略，在步驟 6 和 10 中以適當的值來表示。</span><span class="sxs-lookup"><span data-stu-id="9e6be-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="9e6be-151">在用戶端電腦上重新更新群組原則之前，您建立的新政策不會生效。</span><span class="sxs-lookup"><span data-stu-id="9e6be-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="9e6be-152">雖然群群組原則會自行定期重新更新，但您可以遵循下列步驟來強制立即重新建立：</span><span class="sxs-lookup"><span data-stu-id="9e6be-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="9e6be-153">在您想要重新更新群組原則的每部電腦上，開啟以系統管理員 (*以系統管理員*) 。</span><span class="sxs-lookup"><span data-stu-id="9e6be-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="9e6be-154">在命令提示符中，輸入</span><span class="sxs-lookup"><span data-stu-id="9e6be-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="9e6be-155">驗證群組原則物件中的 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="9e6be-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="9e6be-156">若要確認已設定群組原則物件的值，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9e6be-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="9e6be-157">開啟以系統管理員 (*命令提示*) 。</span><span class="sxs-lookup"><span data-stu-id="9e6be-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="9e6be-158">在命令提示符中，輸入</span><span class="sxs-lookup"><span data-stu-id="9e6be-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="9e6be-159">這會產生已申請的 GPO 報告，並將其傳送至名為gp.txt的 *文字檔*。</span><span class="sxs-lookup"><span data-stu-id="9e6be-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="9e6be-160">針對名為gp.html 的可讀 *HTML* 報表，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9e6be-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="9e6be-161">在產生的檔案中，尋找 **標題為已** 應用群組原則物件，並確認先前建立之群組原則物件的名稱在已應用原則清單中。</span><span class="sxs-lookup"><span data-stu-id="9e6be-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="9e6be-162">開啟登錄編輯程式，然後前往</span><span class="sxs-lookup"><span data-stu-id="9e6be-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="9e6be-163">HKEY \_ LOCAL \_ MACHINE \\ 軟體策略 Microsoft Windows \\ \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="9e6be-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="9e6be-164">確認資料表 2 中列出的登錄機碼目值。</span><span class="sxs-lookup"><span data-stu-id="9e6be-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="9e6be-165">*表格 2.QoS 的 Windows 登錄機碼目值*</span><span class="sxs-lookup"><span data-stu-id="9e6be-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="9e6be-166">名稱</span><span class="sxs-lookup"><span data-stu-id="9e6be-166">Name</span></span>          |  <span data-ttu-id="9e6be-167">類型</span><span class="sxs-lookup"><span data-stu-id="9e6be-167">Type</span></span>  |    <span data-ttu-id="9e6be-168">資料</span><span class="sxs-lookup"><span data-stu-id="9e6be-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="9e6be-169">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="9e6be-169">Application Name</span></span>    | <span data-ttu-id="9e6be-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-170">REG_SZ</span></span> |  <span data-ttu-id="9e6be-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="9e6be-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="9e6be-172">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="9e6be-172">DSCP Value</span></span>       | <span data-ttu-id="9e6be-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-173">REG_SZ</span></span> |     <span data-ttu-id="9e6be-174">46</span><span class="sxs-lookup"><span data-stu-id="9e6be-174">46</span></span>      |
   |        <span data-ttu-id="9e6be-175">本地 IP</span><span class="sxs-lookup"><span data-stu-id="9e6be-175">Local IP</span></span>        | <span data-ttu-id="9e6be-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="9e6be-177">本地 IP 前置長度</span><span class="sxs-lookup"><span data-stu-id="9e6be-177">Local IP Prefix Length</span></span> | <span data-ttu-id="9e6be-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="9e6be-179">本地埠</span><span class="sxs-lookup"><span data-stu-id="9e6be-179">Local Port</span></span>       | <span data-ttu-id="9e6be-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-180">REG_SZ</span></span> | <span data-ttu-id="9e6be-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="9e6be-181">50000-50019</span></span> |
   |        <span data-ttu-id="9e6be-182">通訊協定</span><span class="sxs-lookup"><span data-stu-id="9e6be-182">Protocol</span></span>        | <span data-ttu-id="9e6be-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="9e6be-184">遠端 IP</span><span class="sxs-lookup"><span data-stu-id="9e6be-184">Remote IP</span></span>        | <span data-ttu-id="9e6be-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="9e6be-186">遠端 IP 首碼</span><span class="sxs-lookup"><span data-stu-id="9e6be-186">Remote IP Prefix</span></span>    | <span data-ttu-id="9e6be-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="9e6be-188">遠端埠</span><span class="sxs-lookup"><span data-stu-id="9e6be-188">Remote Port</span></span>       | <span data-ttu-id="9e6be-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="9e6be-190">節流速率</span><span class="sxs-lookup"><span data-stu-id="9e6be-190">Throttle Rate</span></span>      | <span data-ttu-id="9e6be-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9e6be-191">REG_SZ</span></span> |     <span data-ttu-id="9e6be-192">-1</span><span class="sxs-lookup"><span data-stu-id="9e6be-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="9e6be-193">確認您使用之用戶端的應用程式名稱專案值正確無誤，並確認 DSCP 值和本地埠專案都反映群組原則物件中的設定。</span><span class="sxs-lookup"><span data-stu-id="9e6be-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9e6be-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="9e6be-194">Related topics</span></span>

[<span data-ttu-id="9e6be-195">在 Teams 中 (QoS) 服務品質</span><span class="sxs-lookup"><span data-stu-id="9e6be-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)