---
title: Lync Server 2013：Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="862b9-102">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="862b9-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="862b9-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="862b9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="862b9-104">本主題說明 Lync Server 2013 的管理工具。</span><span class="sxs-lookup"><span data-stu-id="862b9-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="862b9-105">預設會在每個 Lync Server 伺服器上安裝系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="862b9-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="862b9-106">此外，您還可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="862b9-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="862b9-107">如需安裝管理工具的程式，請參閱[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="862b9-108">如需開啟 [工具] 以執行管理工作的程式，請參閱[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="862b9-109">在安裝或使用 Lync Server 管理工具之前，請務必先檢查基礎結構、作業系統、軟體及系統管理員許可權需求。</span><span class="sxs-lookup"><span data-stu-id="862b9-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="862b9-110">如需基礎結構需求的詳細資料，請參閱[Lync Server 2013 中的管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="862b9-111">如需安裝 Lync Server 系統管理工具之作業系統和軟體需求的詳細資料，請參閱 lync [server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="862b9-112">安裝及使用工具所需的使用者權利和許可權，會在[設定和管理 Lync Server 2013 所需的管理員權利和許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中加以說明。</span><span class="sxs-lookup"><span data-stu-id="862b9-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="862b9-113">管理工具組括下列各項：</span><span class="sxs-lookup"><span data-stu-id="862b9-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="862b9-114">**[Lync server 部署嚮導]**   可用於部署 Lync Server 及安裝所有系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="862b9-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="862b9-115">**Lync Server 拓撲**   建立器可用來定義您部署中的元件。</span><span class="sxs-lookup"><span data-stu-id="862b9-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="862b9-116">**Lync Server [控制台**   ] 可讓您使用 web 型介面進行部署的日常管理。</span><span class="sxs-lookup"><span data-stu-id="862b9-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="862b9-117">**Lync Server Management Shell**   使用命令列來進行部署的日常管理。</span><span class="sxs-lookup"><span data-stu-id="862b9-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="862b9-118">**Lync Server 記錄工具**   用來針對您的部署問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="862b9-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="862b9-119">**集中式記錄服務**   從一部電腦、池、網站或全域檔收集記錄和追蹤檔案。</span><span class="sxs-lookup"><span data-stu-id="862b9-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="862b9-120">選取並定義包含提供者、標誌和追蹤層級的案例。</span><span class="sxs-lookup"><span data-stu-id="862b9-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="862b9-121">記錄會收集、匯總並與工具（例如任何以文字為基礎的工具或 Snooper）一起顯示。</span><span class="sxs-lookup"><span data-stu-id="862b9-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="862b9-122">您可以使用 [拓撲建立器] 和 [Lync Server 控制台] 來管理您的部署。</span><span class="sxs-lookup"><span data-stu-id="862b9-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="862b9-123">部署嚮導</span><span class="sxs-lookup"><span data-stu-id="862b9-123">Deployment Wizard</span></span>

<span data-ttu-id="862b9-124">您必須使用安裝媒體上隨附的 Lync Server 部署嚮導，將所有系統管理工具安裝到尚未安裝 Lync Server 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="862b9-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="862b9-125">在 [管理工具] 安裝程式中，Lync Server 部署嚮導會與其他工具一起安裝在本機，以便您日後可以使用它來為其他元件安裝檔案，或移除您不想要的元件的檔案電腦.</span><span class="sxs-lookup"><span data-stu-id="862b9-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="862b9-126">如需有關如何第一次從 Lync Server 安裝媒體執行 Lync Server 部署嚮導的詳細資訊，請參閱[安裝 Lync server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="862b9-127">拓撲建立器</span><span class="sxs-lookup"><span data-stu-id="862b9-127">Topology Builder</span></span>

<span data-ttu-id="862b9-128">如需使用拓撲結構建立器所能執行之部署工作的詳細資訊，請參閱每個伺服器角色的部署檔。</span><span class="sxs-lookup"><span data-stu-id="862b9-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="862b9-129">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="862b9-129">Lync Server Control Panel</span></span>

<span data-ttu-id="862b9-130">您可以使用 Lync Server 2013 [控制台] 執行管理和維護 Lync Server 2013 所需的大部分系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="862b9-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="862b9-131">Lync Server [控制台] 可讓您使用圖形使用者介面（GUI）來管理執行 Lync Server 的伺服器設定，以及組織中的使用者、用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="862b9-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="862b9-132">Lync Server 管理命令介面使用 Lync Server [控制台] 做為執行 Lync Server 配置的基礎機制。</span><span class="sxs-lookup"><span data-stu-id="862b9-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="862b9-133">Lync Server 的 [控制台] 會自動安裝在每個 Lync Server 前端伺服器或標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="862b9-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="862b9-134">在這個版本中，您會遠端系統管理邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="862b9-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="862b9-135">您也可以在另一部電腦（例如，您想要集中管理 Lync Server 的管理主控台）上安裝 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="862b9-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="862b9-136">如需詳細資訊，請參閱[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="862b9-137">若要使用 Lync Server [控制台] 來設定設定，您必須使用指派給 CsAdministrator 角色的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="862b9-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="862b9-138">如需有關 Lync Server 2013 中預先定義的管理角色的詳細資訊，請參閱<A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中規劃角色式存取控制</A>。</span><span class="sxs-lookup"><span data-stu-id="862b9-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="862b9-139">若要使用 Lync Server [控制台] 設定設定，您也必須使用最小螢幕解析度為 1024 x 768 的電腦。</span><span class="sxs-lookup"><span data-stu-id="862b9-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="862b9-140">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="862b9-140">Lync Server Management Shell</span></span>

<span data-ttu-id="862b9-141">在 Lync Server 中，Lync Server 管理命令介面會提供一種管理和管理的新方法。</span><span class="sxs-lookup"><span data-stu-id="862b9-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="862b9-142">Lync Server 管理命令介面是在 Windows PowerShell 命令列介面上建立的強大管理介面，其中包含一組完整的 Lync Server 專用的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="862b9-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="862b9-143">使用 Lync Server 管理命令介面時，您會看到一組豐富的設定和自動化控制。</span><span class="sxs-lookup"><span data-stu-id="862b9-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="862b9-144">[拓撲建立器] 和 [Lync Server 控制台] 都會將這些 Cmdlet 的子集都實現，以支援 Lync Server 的管理。</span><span class="sxs-lookup"><span data-stu-id="862b9-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="862b9-145">Lync Server 管理命令介面包含所有 Lync Server 管理工作的 Cmdlet，您可以單獨使用這些 Cmdlet 來管理您的部署。</span><span class="sxs-lookup"><span data-stu-id="862b9-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="862b9-146">如需詳細資訊，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔或每個 Cmdlet 的命令列說明。</span><span class="sxs-lookup"><span data-stu-id="862b9-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="862b9-147">記錄工具</span><span class="sxs-lookup"><span data-stu-id="862b9-147">Logging Tool</span></span>

<span data-ttu-id="862b9-148">Lync Server 記錄工具可在產品執行時捕獲產品的記錄及追蹤資訊，協助進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="862b9-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="862b9-149">您可以使用此工具在任何 Lync Server 伺服器角色上執行調試會話。</span><span class="sxs-lookup"><span data-stu-id="862b9-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="862b9-150">如需記錄工具的詳細資訊，請參閱 TechNet Library 上的 Lync Server 2010 記錄工具檔[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)。</span><span class="sxs-lookup"><span data-stu-id="862b9-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="862b9-151">在任何情況下，建議針對 Lync Server 記錄工具的所有記錄收集收集集中式記錄服務。</span><span class="sxs-lookup"><span data-stu-id="862b9-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="862b9-152">Lync Server 記錄工具仍可正常運作，但如果集中式記錄服務已在執行，則會干擾或無法呈現。</span><span class="sxs-lookup"><span data-stu-id="862b9-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="862b9-153">您應該只使用集中式記錄服務或 Lync Server 記錄工具，但不要同時使用這兩個工具。</span><span class="sxs-lookup"><span data-stu-id="862b9-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="862b9-154">如需集中式記錄服務的詳細資訊，以及為何應以獨佔方式使用它，請參閱<A href="lync-server-2013-using-the-centralized-logging-service.md">在 Lync Server 2013 中使用集中式記錄服務</A>。</span><span class="sxs-lookup"><span data-stu-id="862b9-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="862b9-155">本節內容</span><span class="sxs-lookup"><span data-stu-id="862b9-155">In This Section</span></span>

  - [<span data-ttu-id="862b9-156">Lync Server 2013 中的管理工具基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="862b9-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="862b9-157">Lync Server 2013 中的伺服器及工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="862b9-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="862b9-158">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="862b9-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="862b9-159">設定和管理 Lync Server 2013 所需的系統管理員權限</span><span class="sxs-lookup"><span data-stu-id="862b9-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="862b9-160">在 Lync Server 2013 中發行拓撲的需求</span><span class="sxs-lookup"><span data-stu-id="862b9-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="862b9-161">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="862b9-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="862b9-162">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="862b9-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - <span data-ttu-id="862b9-163">[Lync Server 2013 [控制台] 的疑難排解](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)</span><span class="sxs-lookup"><span data-stu-id="862b9-163">[Troubleshooting Lync Server 2013 Control Panel](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)</span></span>

  - [<span data-ttu-id="862b9-164">在 Lync Server 2013 中使用集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="862b9-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="862b9-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="862b9-165">See Also</span></span>


[<span data-ttu-id="862b9-166">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="862b9-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

