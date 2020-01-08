---
title: Lync Server 2013：開啟 Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="91293-102">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="91293-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91293-103">_**主題上次修改日期：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="91293-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="91293-104">您可以使用本主題中的程式來開啟 [管理工具] 來部署、設定或疑難排解您的 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="91293-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="91293-105">部署嚮導</span><span class="sxs-lookup"><span data-stu-id="91293-105">Deployment Wizard</span></span>

  - <span data-ttu-id="91293-106">拓撲建立器</span><span class="sxs-lookup"><span data-stu-id="91293-106">Topology Builder</span></span>

  - <span data-ttu-id="91293-107">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="91293-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="91293-108">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="91293-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="91293-109">部署嚮導</span><span class="sxs-lookup"><span data-stu-id="91293-109">Deployment Wizard</span></span>

<span data-ttu-id="91293-110">使用下列程式在本機啟動部署嚮導，以新增或移除 Lync Server 2013 元件檔。</span><span class="sxs-lookup"><span data-stu-id="91293-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="91293-111">啟動 Lync Server 2013 部署嚮導</span><span class="sxs-lookup"><span data-stu-id="91293-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="91293-112">登入 Lync Server 部署嚮導以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員的身分安裝的電腦。</span><span class="sxs-lookup"><span data-stu-id="91293-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="91293-113">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="91293-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="91293-114">拓撲建立器</span><span class="sxs-lookup"><span data-stu-id="91293-114">Topology Builder</span></span>

<span data-ttu-id="91293-115">使用下列程式開啟 [拓撲建立器]，以定義您要在 Lync Server 2013 拓撲結構中部署的伺服器。</span><span class="sxs-lookup"><span data-stu-id="91293-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="91293-116">開啟 Lync Server 2013 拓撲建立器以設計拓撲</span><span class="sxs-lookup"><span data-stu-id="91293-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="91293-117">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="91293-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91293-118">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要讀取、發佈或啟用拓撲（需要在伺服器上安裝 Lync Server 2013），您必須使用網域系統管理員群組和 RTCUniv 成員的帳戶。ersalServerAdmins 群組，且在您要用於封存檔案存放區的檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲產生器可以設定必要的隨機存取控制清單（Dacl）。或具有同等使用者權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="91293-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="91293-119">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="91293-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="91293-120">Lync Server 2013 [控制台]</span><span class="sxs-lookup"><span data-stu-id="91293-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="91293-121">使用下列其中一個程式來開啟 Lync Server 2013 [控制台]，管理您環境中伺服器、使用者、用戶端和裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="91293-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91293-122">您可以使用指派給 CsAdministrator 角色的使用者帳戶來執行 Lync Server 2013 [控制台] 中的任何任務。</span><span class="sxs-lookup"><span data-stu-id="91293-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="91293-123">您可以使用其他角色登入 Lync Server 2013 [控制台] 來執行特定的系統管理工作，視需要執行的工作而定。</span><span class="sxs-lookup"><span data-stu-id="91293-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="91293-124">例如，您可以使用 CSArchivingAdministrator 來管理 Lync Server 2013 [控制台] 中的 [存檔]。</span><span class="sxs-lookup"><span data-stu-id="91293-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="91293-125">如需有關角色的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="91293-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="91293-126">如需可用於執行特定工作之角色的詳細資訊，請參閱該工作的相關檔。</span><span class="sxs-lookup"><span data-stu-id="91293-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="91293-127">從組織防火牆內的任何電腦開啟 Lync Server 2013 [控制台]</span><span class="sxs-lookup"><span data-stu-id="91293-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="91293-128">從指派給 CsAdministrator 角色的使用者帳戶，或其他具有要執行之工作之許可權的角色，請以最小的螢幕解析度 1024 x 768 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="91293-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="91293-129">如果您已設定管理簡單的統一資源定位器（URL），您可以從您組織防火牆內任何電腦上執行的網際網路瀏覽器存取 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="91293-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="91293-130">如需有關設定管理簡單 URL 的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-planning-for-simple-urls.md">簡單 2013 Url 規劃</A>，以及在部署檔中<A href="lync-server-2013-edit-or-configure-simple-urls.md">編輯或設定 lync server 2013 中的簡單 url</A> 。</span><span class="sxs-lookup"><span data-stu-id="91293-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="91293-131">開啟瀏覽器視窗，然後輸入為貴組織設定的管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="91293-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="91293-132">若要在執行 Lync Server 2013 的電腦上開啟 Lync Server 2013 [控制台]</span><span class="sxs-lookup"><span data-stu-id="91293-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="91293-133">如果使用者帳戶是 CsAdministrator 角色的成員或其他角色，且具有適當的使用者權利和許可權，且要執行該工作，請登入您已安裝 Lync Server 2013 的電腦，或者至少 Lync Server 2013 administrat[我的工具]。</span><span class="sxs-lookup"><span data-stu-id="91293-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="91293-134">若要設定設定，電腦的畫面解析度必須達到 1024 x 768 的最小值。</span><span class="sxs-lookup"><span data-stu-id="91293-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="91293-135">啟動 Lync Server 2013 [控制台]：按一下 [**開始**]，按一下 [**所有程式**]，指向 [**管理工具**]，指向 [ **Microsoft Lync Server 2013**]，然後按一下 [ **Lync Server 2013 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="91293-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="91293-136">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="91293-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="91293-137">使用下列程式來開啟 Lync Server 2013 管理命令介面，以在您的環境中使用命令列來管理伺服器、使用者、用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="91293-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91293-138">您可以使用指派給 CsAdministrator 角色的使用者帳戶來執行 Lync Server 2013 管理命令介面中的任何任務。</span><span class="sxs-lookup"><span data-stu-id="91293-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="91293-139">您可以使用其他角色登入，以執行特定的系統管理工作，視您需要執行的任務而定。</span><span class="sxs-lookup"><span data-stu-id="91293-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="91293-140">例如，您可以使用 CSArchivingAdministrator 來執行與封存管理相關的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="91293-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="91293-141">如需有關角色的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="91293-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="91293-142">如需可用於執行特定 Cmdlet 之角色的詳細資訊，請參閱 Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="91293-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="91293-143">您也可以使用 [RTCUniversalServerAdmins]、[RTCUniversalUserAdmins] 或 [RTCUniversalReadOnlyAdmins] 群組中的使用者帳戶來執行某些 Cmdlet （視 Cmdlet 而定）。</span><span class="sxs-lookup"><span data-stu-id="91293-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="91293-144">若要開啟 Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="91293-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="91293-145">如果您開啟的是 Windows PowerShell 視窗，而不是 Lync Server 2013 管理命令介面，預設就是您無法執行 Lync Server 2013 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="91293-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="91293-146">若要在 Windows PowerShell 中執行 Lync Server 2013 Cmdlet，請在 Windows PowerShell 命令提示字元輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="91293-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="91293-147">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="91293-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91293-148">請參閱</span><span class="sxs-lookup"><span data-stu-id="91293-148">See Also</span></span>


[<span data-ttu-id="91293-149">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="91293-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="91293-150">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="91293-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

