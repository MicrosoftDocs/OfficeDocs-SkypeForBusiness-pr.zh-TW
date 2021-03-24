---
title: 管理信任的應用程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由商務用 Skype Server 所信任。
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103159"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="d9042-103">在商務用 Skype Server 中管理信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="d9042-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="d9042-104">*信任的應用程式* 是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由商務用 Skype Server 所信任。</span><span class="sxs-lookup"><span data-stu-id="d9042-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="d9042-105">如需 UCMA 應用程式的詳細資訊，請參閱中的「整合通訊 Managed API 3.0 核心 SDK 檔」 https://go.microsoft.com/fwlink/p/?linkId=210320 。</span><span class="sxs-lookup"><span data-stu-id="d9042-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="d9042-106">您應以 RTCUniversalServerAdmins 及 Domain Admins 群組成員的身分登入，才能在加入或移除伺服器角色時，成功地發行、啟用或停用拓撲。</span><span class="sxs-lookup"><span data-stu-id="d9042-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="d9042-107">您可以使用本文來瞭解如何設定新的信任應用程式伺服器、查看信任的應用程式清單，以及查看信任的應用程式資訊。</span><span class="sxs-lookup"><span data-stu-id="d9042-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="d9042-108">設定新的信任應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="d9042-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="d9042-109">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="d9042-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d9042-110">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 伺服器**]，然後按一下 [ **商務用 skype server 拓撲** 產生器]。</span><span class="sxs-lookup"><span data-stu-id="d9042-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="d9042-111">選取 **[從現有部署下載拓撲]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d9042-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="d9042-112">在 [ **另存拓撲** ] 對話方塊中，按一下您要使用的拓撲產生器檔案，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d9042-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="d9042-113">在左窗格中，以滑鼠右鍵按一下 [ **信任的應用程式伺服器**]，然後按一下 [ **新增信任的應用程式集** 區]。</span><span class="sxs-lookup"><span data-stu-id="d9042-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="d9042-114">輸入信任的應用程式集區的 [集區 FQDN]，選擇要讓它成為單一伺服器或多部伺服器，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d9042-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="d9042-115">在 [ **選取下一個躍點]** 頁面上，從清單中選取商務用 Skype 伺服器前端集區。</span><span class="sxs-lookup"><span data-stu-id="d9042-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="d9042-116">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d9042-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="d9042-117">選取上方節點 **商務用 Skype Server**，然後從 [ **動作** ] 功能表中，按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="d9042-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="d9042-118">**信任的應用程式集** 區應已成功建立，並與正確的前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="d9042-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="d9042-119">查看信任的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="d9042-119">View a list of trusted applications</span></span>

<span data-ttu-id="d9042-120">您可以使用商務用 Skype Server 控制台，以查看已部署在商務用 Skype 伺服器環境中之信任的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="d9042-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="d9042-121">信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由商務用 Skype Server 所信任。</span><span class="sxs-lookup"><span data-stu-id="d9042-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="d9042-122">此信任關係摘要如下清單所示：</span><span class="sxs-lookup"><span data-stu-id="d9042-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="d9042-123">受信任的應用程式不會受到商務用 Skype 伺服器的驗證的挑戰。</span><span class="sxs-lookup"><span data-stu-id="d9042-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="d9042-124">受信任的應用程式不會受到 SIP 交易的商務用 Skype 伺服器（透過網際網路通訊協定的連線或呼出語音 (VoIP) 通話的限制）。</span><span class="sxs-lookup"><span data-stu-id="d9042-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="d9042-125">信任的應用程式可以模仿任何使用者，並且可以加入會議，而不會出現在名冊中。</span><span class="sxs-lookup"><span data-stu-id="d9042-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="d9042-126">信任的應用程式具有高可用性和彈性。</span><span class="sxs-lookup"><span data-stu-id="d9042-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="d9042-127">在商務用 Skype Server 控制台中，您可以看到應用程式的名稱、執行所在的集區，以及其使用的埠。</span><span class="sxs-lookup"><span data-stu-id="d9042-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="d9042-128">若要查看信任的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="d9042-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="d9042-129">從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d9042-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="d9042-130">如需商務用 Skype Server 中可用的預先定義管理角色的詳細資訊，請參閱以 [角色為基礎的存取控制 (RBAC) ](../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="d9042-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="d9042-131">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d9042-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="d9042-132">在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **信任的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d9042-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="d9042-133">在 [ **信任的應用程式** ] 頁面上，按一下欄標題以排序應用程式（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="d9042-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="d9042-134">查看信任的應用程式資訊</span><span class="sxs-lookup"><span data-stu-id="d9042-134">View trusted application information</span></span>

<span data-ttu-id="d9042-135">您可以使用 Windows PowerShell 和 **Get-CsTrustedApplication** 指令程式，查看您信任之應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9042-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="d9042-136">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9042-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="d9042-137">檢視信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="d9042-137">To view trusted applications</span></span>

<span data-ttu-id="d9042-138">若要查看您的所有信任的應用程式，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="d9042-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="d9042-139">對於各個信任的應用程式，這個命令將傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="d9042-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="d9042-140">如需詳細資訊，請參閱＜[Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)＞。</span><span class="sxs-lookup"><span data-stu-id="d9042-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span></span>