---
title: 設定監視的商務用 Skype 伺服器電腦
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：在商務用 Skype Server 2019 電腦上安裝 Operations Manager 代理程式檔案以進行監控，並將電腦設定為系統中心 proxy。
ms.openlocfilehash: 162b2dc0b50b7da5246d69d64b0bdb307212c139
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799643"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="27c3e-103">設定監視的商務用 Skype 伺服器電腦</span><span class="sxs-lookup"><span data-stu-id="27c3e-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="27c3e-104">**摘要：** 在商務用 Skype Server 2019 電腦上安裝 Operations Manager proxy 檔案以進行監控，並將電腦設定為系統中心 proxy。</span><span class="sxs-lookup"><span data-stu-id="27c3e-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="27c3e-105">您想要監視的每個商務用 Skype Server 2019 電腦，都必須能夠自行向管理伺服器提供其存在性的報告。</span><span class="sxs-lookup"><span data-stu-id="27c3e-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="27c3e-106">若要啟用此程式，您必須在每個要監視的電腦上安裝 Operations Manager 代理檔案。</span><span class="sxs-lookup"><span data-stu-id="27c3e-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="27c3e-107">安裝完代理程式檔案之後，您必須將電腦設定為系統中心 proxy。</span><span class="sxs-lookup"><span data-stu-id="27c3e-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="27c3e-108">在執行這些程式之前，請務必先在這些電腦上安裝並設定商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="27c3e-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="27c3e-109">在周邊網路以外的觀察程式節點上安裝憑證</span><span class="sxs-lookup"><span data-stu-id="27c3e-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="27c3e-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="27c3e-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="27c3e-111">在周邊網路（例如商務用 Skype Server Edge 伺服器）之外，在企業外部（例如外部綜合交易觀察程式節點）或跨 Active Directory 信任邊界的 System Center Operations Manager 代理程式可能需要系統中心作業管理員閘道伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="27c3e-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="27c3e-112">此伺服器角色可讓沒有與根管理伺服器有信任關係的代理程式，以引發通知。</span><span class="sxs-lookup"><span data-stu-id="27c3e-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="27c3e-113">如需詳細資訊，請參閱[在 Operations Manager 2012 中管理閘道伺服器](https://technet.microsoft.com/en-us/library/hh212823.aspx)。</span><span class="sxs-lookup"><span data-stu-id="27c3e-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>

<span data-ttu-id="27c3e-114">如果您在其中一個位置部署代理程式，您也必須要求並設定可讓監視者節點傳送警示給 System Center Operations Manager 的憑證。</span><span class="sxs-lookup"><span data-stu-id="27c3e-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="27c3e-115">為了簡化此程式，Operations Manager 小組已建立一組實用程式，讓您在監視者節點電腦上要求並安裝正確類型的憑證。</span><span class="sxs-lookup"><span data-stu-id="27c3e-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="27c3e-116">如需詳細資訊，以及下載這些實用程式，請參閱[使用憑證產生嚮導輕鬆取得未加入網域之代理程式的憑證](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="27c3e-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="27c3e-117">安裝 Operation Manager 代理程式檔</span><span class="sxs-lookup"><span data-stu-id="27c3e-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="27c3e-118">在系統中心設定媒體上，按兩下 **[setup.exe]。**</span><span class="sxs-lookup"><span data-stu-id="27c3e-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="27c3e-119">在 System Center Operation Manager 安裝程式嚮導中，按一下 [**安裝 Operations Manager 代理**程式]，從 [選用安裝] 底下的 [安裝代理程式]</span><span class="sxs-lookup"><span data-stu-id="27c3e-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="27c3e-120">在 System Center 設定向導中，在 [歡迎使用 System Center Operations Manager 安裝程式嚮導] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="27c3e-121">在 [目的地資料夾] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="27c3e-122">在 [管理群組設定] 頁面上，選取 [**指定管理群組資訊**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="27c3e-123">在 [管理群組設定] 頁面上，于 [**管理群組名稱**] 方塊中輸入 Operations Manager 管理群組的名稱，然後在 [**管理伺服器**] 方塊中輸入 operations manager 伺服器的主機名稱（例如 [atl-scom-001]）。</span><span class="sxs-lookup"><span data-stu-id="27c3e-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="27c3e-124">如果您變更了 Operations Manager 所使用的埠號，請在 [**管理伺服器埠**] 方塊中輸入新的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="27c3e-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="27c3e-125">否則，請將埠保留為預設值5723，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="27c3e-126">在 [代理動作帳戶] 頁面上，選取 [**本機系統**]，然後按一下 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="27c3e-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="27c3e-127">在 [Microsoft Update] 頁面上，選取 [**我不想使用 Microsoft Update** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="27c3e-128">在 [準備安裝] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="27c3e-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="27c3e-129">在 [完成 System Center Operations Manager 安裝程式嚮導] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="27c3e-130">按一下 **[** 結束]。</span><span class="sxs-lookup"><span data-stu-id="27c3e-130">Click **Exit**.</span></span>

<span data-ttu-id="27c3e-131">針對 System Center 2012，您可以按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **System Center Operations manager 2012**]，然後按一下 [ **Operations 2012 Manager 命令**介面]，確認已建立代理程式。</span><span class="sxs-lookup"><span data-stu-id="27c3e-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="27c3e-132">在 Operations Manager Shell 中，輸入下列 Windows PowerShell 命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="27c3e-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="27c3e-133">系統會顯示所有 Operations Manager 代理程式的清單。</span><span class="sxs-lookup"><span data-stu-id="27c3e-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="27c3e-134">將商務用 Skype Server 電腦設定為參與 System Center 探索</span><span class="sxs-lookup"><span data-stu-id="27c3e-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="27c3e-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="27c3e-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="27c3e-136">若要確保新的商務用 Skype 伺服器代理參與 System Center Operations Manager 的探索程式，您必須在安裝 System Center Operations Manager 主控台的每台電腦上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="27c3e-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="27c3e-137">按一下 [管理] 索引標籤上的 [**代理程式管理**]。</span><span class="sxs-lookup"><span data-stu-id="27c3e-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="27c3e-138">按一下 [**探索] 嚮導**，並完成要探索的電腦的嚮導。</span><span class="sxs-lookup"><span data-stu-id="27c3e-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="27c3e-139">重新開機健康代理程式服務。</span><span class="sxs-lookup"><span data-stu-id="27c3e-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="27c3e-140">重新開機服務將會強制發現新電腦。</span><span class="sxs-lookup"><span data-stu-id="27c3e-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="27c3e-141">如果您不重新開機服務，系統中心作業管理員可能需要4小時的時間才能探索新電腦。</span><span class="sxs-lookup"><span data-stu-id="27c3e-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="27c3e-142">確認未在 Operations Manager 事件記錄中記錄任何錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="27c3e-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="27c3e-143">成功推送代理程式的電腦將會顯示在 [代理程式管理] 清單下，而手動安裝代理程式的電腦會顯示在 [掛起的管理] 底下，按一下 [電腦名稱稱]，然後按 [核准]。</span><span class="sxs-lookup"><span data-stu-id="27c3e-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="27c3e-144">以滑鼠右鍵按一下電腦的名稱，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="27c3e-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="27c3e-145">在 [內容] 對話方塊的 [安全性] 索引標籤上，選取 [**允許此代理程式充當 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c3e-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


