---
title: 管理受信任的應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 受信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK (受商務用 Skype Server 信任) 為基礎的應用程式。
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187072"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="d5120-103">在商務用 Skype Server 中管理受信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="d5120-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="d5120-104">*受信任的應用程式*是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK (受商務用 Skype Server 信任) 為基礎的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5120-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="d5120-105">如需有關 UCMA 應用程式的詳細資訊, 請參閱「統一通訊管理的http://go.microsoft.com/fwlink/p/?linkId=210320API 3.0 核心 SDK 檔」。</span><span class="sxs-lookup"><span data-stu-id="d5120-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="d5120-106">若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲, 您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="d5120-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="d5120-107">您可以在本文中瞭解如何設定新的受信任應用程式伺服器、查看信任的應用程式清單, 以及查看受信任的應用程式資訊。</span><span class="sxs-lookup"><span data-stu-id="d5120-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="d5120-108">設定新的信任應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="d5120-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="d5120-109">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="d5120-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d5120-110">啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server**], 然後按一下 [**商務用 skype server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="d5120-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="d5120-111">選取 [**從現有部署下載拓朴**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5120-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="d5120-112">在 [**另存拓朴為**] 對話方塊中, 按一下您要使用的拓撲產生器檔案, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d5120-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="d5120-113">在左窗格中, 以滑鼠右鍵按一下 [**信任的應用程式伺服器**], 然後按一下 [**新增信任的應用程式池**]。</span><span class="sxs-lookup"><span data-stu-id="d5120-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="d5120-114">輸入受信任的應用程式池的 [**池 FQDN** ], 選取它是否為單一伺服器或多重伺服器, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5120-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="d5120-115">在 [**選取下一個躍點]** 頁面上的清單中, 選取 [商務用 Skype Server 前端] 池。</span><span class="sxs-lookup"><span data-stu-id="d5120-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="d5120-116">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d5120-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="d5120-117">選取最上層**的商務用 Skype Server**, 然後在 [**動作**] 功能表中, 按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="d5120-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="d5120-118">**受信任的應用程式池**應該已成功建立, 且與正確的 [前端] 池相關聯。</span><span class="sxs-lookup"><span data-stu-id="d5120-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="d5120-119">查看信任的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="d5120-119">View a list of trusted applications</span></span>

<span data-ttu-id="d5120-120">您可以使用商務用 Skype Server 的 [控制台] 來查看您在商務用 Skype Server 環境中部署之受信任的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="d5120-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="d5120-121">受信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK (受商務用 Skype Server 信任) 為基礎的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5120-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="d5120-122">下列清單將摘要列出這項信任關係:</span><span class="sxs-lookup"><span data-stu-id="d5120-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="d5120-123">商務用 Skype Server 不會對受信任的應用程式進行驗證。</span><span class="sxs-lookup"><span data-stu-id="d5120-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="d5120-124">受信任的應用程式不會受到 SIP 交易、連線或網際網路通訊協定 (VoIP) 通話的商務用 Skype 伺服器的限制。</span><span class="sxs-lookup"><span data-stu-id="d5120-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="d5120-125">受信任的應用程式可以模仿任何使用者, 而且無需出現在 rosters 中, 即可加入會議。</span><span class="sxs-lookup"><span data-stu-id="d5120-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="d5120-126">受信任的應用程式高度可用且具有彈性。</span><span class="sxs-lookup"><span data-stu-id="d5120-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="d5120-127">在商務用 Skype Server 的 [控制台] 中, 您可以看到應用程式名稱、其執行所在的池中, 以及它們所使用的埠。</span><span class="sxs-lookup"><span data-stu-id="d5120-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="d5120-128">若要查看受信任的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="d5120-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="d5120-129">從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d5120-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="d5120-130">如需有關商務用 Skype Server 中可用的預先定義管理角色的詳細資訊, 請參閱以[角色為基礎的存取控制 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="d5120-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="d5120-131">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d5120-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="d5120-132">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**信任的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d5120-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="d5120-133">如有需要, 請在 [**受信任的應用程式**] 頁面上, 按一下欄標題來排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5120-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="d5120-134">查看受信任的應用程式資訊</span><span class="sxs-lookup"><span data-stu-id="d5120-134">View trusted application information</span></span>

<span data-ttu-id="d5120-135">您可以使用 Windows PowerShell 和**CsTrustedApplication** Cmdlet 來查看您信任之應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d5120-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="d5120-136">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d5120-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="d5120-137">若要查看受信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="d5120-137">To view trusted applications</span></span>

<span data-ttu-id="d5120-138">若要查看所有受信任的應用程式, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="d5120-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="d5120-139">這個命令會針對每個受信任的應用程式傳回類似下列的資訊:</span><span class="sxs-lookup"><span data-stu-id="d5120-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="d5120-140">如需詳細資訊, 請參閱[CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。</span><span class="sxs-lookup"><span data-stu-id="d5120-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
