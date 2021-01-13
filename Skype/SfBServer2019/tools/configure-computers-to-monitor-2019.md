---
title: 設定要監控的商務用 Skype 伺服器電腦
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：在商務用 Skype Server 2019 電腦上安裝 Operations Manager 代理程式檔案，並將該電腦設定為系統中心 proxy。
ms.openlocfilehash: 08328e430acd4fa651fccd89b827d5c103066dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806073"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="7cc1e-103">設定要監控的商務用 Skype 伺服器電腦</span><span class="sxs-lookup"><span data-stu-id="7cc1e-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="7cc1e-104">**摘要：** 在商務用 Skype Server 2019 電腦上安裝 Operations Manager 代理程式檔案，並將該電腦設定為系統中心 proxy。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="7cc1e-105">您要監視的每一部商務用 Skype Server 2019 電腦都必須能夠自我報告其存在於管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="7cc1e-106">若要啟用此程式，您必須在要監視的每一部電腦上安裝 Operations Manager 代理程式檔案。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="7cc1e-107">安裝代理程式檔案之後，您必須將電腦設定為系統中心 proxy。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="7cc1e-108">在執行這些程式之前，請務必先在這些電腦上安裝及設定商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="7cc1e-109">將憑證安裝在位於周邊網路外的監看員節點上</span><span class="sxs-lookup"><span data-stu-id="7cc1e-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="7cc1e-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="7cc1e-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="7cc1e-111">在周邊網路中執行的 System Center Operations Manager 代理 (例如商務用 Skype Server Edge Server)  (，例如外部綜合交易觀察器節點) 或透過 Active Directory 信任界限內，可能需要設定 System Center Operations Manager 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="7cc1e-112">此伺服器角色可讓代理程式與根管理伺服器之間不具有信任關係，以引發警示。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="7cc1e-113">如需詳細資訊，請參閱 [管理 Operations Manager 中的閘道伺服器 2012](https://technet.microsoft.com/library/hh212823.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span></span>

<span data-ttu-id="7cc1e-114">如果您在這些位置中的其中一個位置部署代理程式，您也需要要求及設定憑證，以啟用監看員節點，將提醒傳送至 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="7cc1e-115">為了簡化這個程序，Operations Manager 團隊已建立一套公用程式，讓您要求正確類型的憑證，並安裝於監控程式節點電腦上。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="7cc1e-116">如需詳細資訊，以及若要下載這些公用程式，請參閱 [使用憑證產生嚮導輕鬆取得未加入網域之代理程式的憑證](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="7cc1e-117">安裝 Operation Manager 代理程式檔案</span><span class="sxs-lookup"><span data-stu-id="7cc1e-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="7cc1e-118">在 System Center 安裝媒體上，按兩下 [ **Setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="7cc1e-119">在 System Center operations Manager 安裝程式嚮導中，按一下 [ **安裝 Operations Manager Agent**]，從 [選用安裝] 底下的 [安裝代理程式]。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="7cc1e-120">在 [System Center 安裝精靈] 的 [歡迎使用 System Center Operations Manager 安裝精靈] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="7cc1e-121">在 [目的地資料夾] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="7cc1e-122">在 [管理群組設定] 頁面上，選取 [ **指定管理群組資訊** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="7cc1e-123">在 [管理群組設定] 頁面上的 [ **管理組名** ] 方塊中，輸入 Operations Manager 管理群組的名稱，然後在 [ **管理伺服器** ] 方塊中輸入 operations manager 伺服器的主機名稱 (例如，atl-ws-01-scom-001) 。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="7cc1e-124">如果您變更了 Operations Manager 所使用的埠號碼，請在 [ **管理伺服器埠** ] 方塊中輸入新的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="7cc1e-125">否則，保留預設值5723的埠，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="7cc1e-126">在 [代理程式動作帳戶] 頁面上選取 [**本機系統**]，然後按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="7cc1e-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="7cc1e-127">在 [Microsoft Update] 頁面上，選取 [ **我不想使用 Microsoft 更新** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="7cc1e-128">在 [準備安裝] 頁面上，按一下 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="7cc1e-129">在 [完成 System Center Operations Manager 安裝精靈] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="7cc1e-130">按一下 **[結束]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-130">Click **Exit**.</span></span>

<span data-ttu-id="7cc1e-131">針對 System Center 2012，您可以先依序按一下 [ **開始**]、[ **所有程式**]、[ **System Center Operations Manager 2012**]，然後按一下 [ **Operations 2012 管理員命令** 介面] 來驗證代理程式是否已建立。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="7cc1e-132">在 Operations Manager 命令介面中，輸入下列 Windows PowerShell 命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="7cc1e-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="7cc1e-133">將會顯示所有 Operations Manager 代理程式的清單。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="7cc1e-134">設定商務用 Skype Server 電腦參與 System Center 探索</span><span class="sxs-lookup"><span data-stu-id="7cc1e-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="7cc1e-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="7cc1e-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="7cc1e-136">若要確定新的商務用 Skype 伺服器代理程式參與 System Center Operations Manager 的探索程式，您必須在已安裝 System Center Operations Manager 主控台的每一部電腦上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="7cc1e-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="7cc1e-137">在 [管理] 索引標籤上，按一下 [ **代理程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="7cc1e-138">按一下 [ **探索] [探索]** ，並完成要探索之電腦的嚮導。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="7cc1e-139">重新開機 Health Agent 服務。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="7cc1e-140">重新開機服務將會強制探索新的電腦。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="7cc1e-141">如果您不重新開機服務，可能需要長達4小時，由 System Center Operations Manager 探索新電腦。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="7cc1e-142">確認 Operations Manager 事件記錄中未記錄任何錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="7cc1e-143">成功推入代理程式的電腦會顯示在「代理程式管理」清單下，並以手動方式安裝代理人的電腦顯示在 [擱置的管理] 下，按一下 [電腦名稱稱] 並按 [核准]。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="7cc1e-144">在電腦名稱上按一下滑鼠右鍵，然後按一下 [內容]。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="7cc1e-145">在 [內容] 對話方塊的 [安全性] 索引標籤上，選取 [ **允許此代理程式成為 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7cc1e-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


