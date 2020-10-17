---
title: Lync Server 2013：開啟 Lync Server 系統管理工具
description: Lync Server 2013：開啟 Lync Server 系統管理工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01cf0dc0c17686e2b1c7bee17bdc383ab6247909
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544759"
---
# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="c5030-103">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="c5030-103">Open Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5030-104">_**主題上次修改日期：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="c5030-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="c5030-105">您可以使用本主題中的程式來開啟系統管理工具，以部署、設定或疑難排解 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="c5030-105">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="c5030-106">部署嚮導</span><span class="sxs-lookup"><span data-stu-id="c5030-106">Deployment Wizard</span></span>

  - <span data-ttu-id="c5030-107">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="c5030-107">Topology Builder</span></span>

  - <span data-ttu-id="c5030-108">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="c5030-108">Lync Server Control Panel</span></span>

  - <span data-ttu-id="c5030-109">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="c5030-109">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="c5030-110">部署嚮導</span><span class="sxs-lookup"><span data-stu-id="c5030-110">Deployment Wizard</span></span>

<span data-ttu-id="c5030-111">使用下列程式可在本機啟動部署嚮導，以新增或移除 Lync Server 2013 元件檔案。</span><span class="sxs-lookup"><span data-stu-id="c5030-111">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="c5030-112">啟動 Lync Server 2013 部署嚮導</span><span class="sxs-lookup"><span data-stu-id="c5030-112">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="c5030-113">以 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的身分，登入安裝 Lync Server 部署嚮導的電腦。</span><span class="sxs-lookup"><span data-stu-id="c5030-113">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="c5030-114">依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="c5030-114">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="c5030-115">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="c5030-115">Topology Builder</span></span>

<span data-ttu-id="c5030-116">使用下列程式開啟拓撲產生器，以定義您想要在 Lync Server 2013 拓撲中部署的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c5030-116">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="c5030-117">開啟 Lync Server 2013 拓撲產生器以設計拓撲</span><span class="sxs-lookup"><span data-stu-id="c5030-117">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="c5030-118">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="c5030-118">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5030-119">您可以使用本機 Users 群組成員的帳戶來定義拓撲，但可讀取、發佈或啟用拓撲，這是在伺服器上安裝 Lync Server 2013 所需的功能。您必須使用屬於 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，而且在要用於封存檔案存放區的檔案共用上具有「完全控制」許可權 (（即讀取、寫入及修改），讓拓撲產生器可以設定必要的自由存取控制清單 (dacl) ，或具有同等使用者權限的帳戶。) </span><span class="sxs-lookup"><span data-stu-id="c5030-119">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="c5030-120">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="c5030-120">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="c5030-121">Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="c5030-121">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="c5030-122">使用下列其中一個程式開啟 Lync Server 2013 控制台，以管理環境中的伺服器、使用者、用戶端和裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="c5030-122">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5030-123">您可以使用指派給 CsAdministrator 角色的使用者帳戶，在 Lync Server 2013 控制台中執行任何工作。</span><span class="sxs-lookup"><span data-stu-id="c5030-123">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c5030-124">您可以使用其他角色登入 Lync Server 2013 控制台，以執行特定的管理工作，取決於您需要執行的工作。</span><span class="sxs-lookup"><span data-stu-id="c5030-124">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="c5030-125">例如，您可以使用 CSArchivingAdministrator 管理 Lync Server 2013 控制台中的封存。</span><span class="sxs-lookup"><span data-stu-id="c5030-125">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c5030-126">如需角色的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="c5030-126">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="c5030-127">如需您可以用來執行特定工作的角色的詳細資訊，請參閱任務的檔。</span><span class="sxs-lookup"><span data-stu-id="c5030-127">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="c5030-128">從組織防火牆內部的任何電腦開啟 Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="c5030-128">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="c5030-129">從指派給要執行之工作的 CsAdministrator 角色或其他角色的使用者帳戶，登入內部部署中的任何電腦，最小螢幕解析度為 1024 x 768。</span><span class="sxs-lookup"><span data-stu-id="c5030-129">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5030-130">如果您已將管理簡單的統一資源定位器設定 (URL) ，您可以從組織防火牆內任何電腦上執行的網際網路瀏覽器，存取 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="c5030-130">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="c5030-131">如需設定管理簡易 URL 的詳細資訊，請參閱部署檔中的規劃檔及<A href="lync-server-2013-edit-or-configure-simple-urls.md">編輯或設定 [Lync server 2013</A> ] 中的簡易 URLs 中的「<A href="lync-server-2013-planning-for-simple-urls.md">規劃 lync server 2013 中的簡易 URLs</A> 。</span><span class="sxs-lookup"><span data-stu-id="c5030-131">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="c5030-132">開啟瀏覽器視窗，然後輸入為您的組織設定的管理 URL。</span><span class="sxs-lookup"><span data-stu-id="c5030-132">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="c5030-133">在執行 Lync Server 2013 的電腦上開啟 Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="c5030-133">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="c5030-134">從屬於 CsAdministrator 角色的成員或其他角色的使用者帳戶，其具有要執行之工作的適當使用者權限及許可權，登入已安裝 Lync Server 2013 的電腦，或至少是 Lync Server 2013 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="c5030-134">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="c5030-135">若要設定設定，電腦必須具有 1024 x 768 的最小螢幕解析度。</span><span class="sxs-lookup"><span data-stu-id="c5030-135">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="c5030-136">啟動 Lync Server 2013 控制台：按一下 [ **開始**]，按一下 [ **所有程式**]，指向 [系統 **管理工具**]，指向 [ **Microsoft Lync Server 2013**]，然後按一下 [ **Lync Server 2013 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="c5030-136">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="c5030-137">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="c5030-137">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="c5030-138">使用下列程式開啟 Lync Server 2013 管理命令介面，以使用命令列管理環境中的伺服器、使用者、用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="c5030-138">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5030-139">您可以使用指派給 CsAdministrator 角色的使用者帳戶，在 Lync Server 2013 管理命令介面中執行任何工作。</span><span class="sxs-lookup"><span data-stu-id="c5030-139">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="c5030-140">您可以使用其他角色登入，以執行特定的管理工作，取決於您需要執行的工作。</span><span class="sxs-lookup"><span data-stu-id="c5030-140">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="c5030-141">例如，您可以使用 CSArchivingAdministrator 來執行與封存管理相關的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5030-141">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="c5030-142">如需角色的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="c5030-142">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="c5030-143">如需您可以用來執行特定 Cmdlet 的角色的詳細資訊，請參閱 Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="c5030-143">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="c5030-144">您也可以使用 RTCUniversalServerAdmins、RTCUniversalUserAdmins 或 RTCUniversalReadOnlyAdmins 群組中的使用者帳戶來執行某些 Cmdlet，視 Cmdlet 而定。</span><span class="sxs-lookup"><span data-stu-id="c5030-144">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="c5030-145">開啟 Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="c5030-145">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="c5030-146">如果您開啟 Windows PowerShell 視窗，而不是 Lync Server 2013 管理命令介面，則根據預設，您無法執行 Lync Server 2013 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5030-146">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="c5030-147">若要從 Windows PowerShell 內執行 Lync Server 2013 Cmdlet，請在 Windows PowerShell 命令提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c5030-147">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="c5030-148">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c5030-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5030-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c5030-149">See Also</span></span>


[<span data-ttu-id="c5030-150">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="c5030-150">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="c5030-151">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="c5030-151">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

