---
title: Lync Server 2013： Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ac976f2c05268b5cf864511b19db1fd251edbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525110"
---
# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="a3c49-102">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="a3c49-102">Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3c49-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a3c49-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a3c49-104">本主題說明 Lync Server 2013 的系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="a3c49-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="a3c49-105">預設會在每一部 Lync Server 伺服器上安裝系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="a3c49-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="a3c49-106">此外，您也可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="a3c49-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="a3c49-107">如需安裝系統管理工具的程式，請參閱 [Install Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c49-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="a3c49-108">如需開啟工具來執行管理工作的程式，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c49-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="a3c49-109">在您安裝或使用 Lync Server 系統管理工具之前，請確定您已複查基礎結構、作業系統、軟體和系統管理員權力需求。</span><span class="sxs-lookup"><span data-stu-id="a3c49-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="a3c49-110">如需基礎結構需求的詳細資訊，請參閱 [Lync Server 2013 中的系統管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c49-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="a3c49-111">如需作業系統和軟體需求的詳細資訊，以安裝 Lync Server 系統管理工具，請參閱 lync server [2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及 [Lync server 2013 中的其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c49-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="a3c49-112">安裝及使用工具時所需的使用者權限，將在 [設定和管理 Lync Server 2013 所需的系統管理員許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中說明。</span><span class="sxs-lookup"><span data-stu-id="a3c49-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="a3c49-113">系統管理工具包含下列工具：</span><span class="sxs-lookup"><span data-stu-id="a3c49-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="a3c49-114">**Lync Server 部署嚮導**    用來部署 Lync Server，並安裝所有系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="a3c49-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="a3c49-115">**Lync Server 拓撲**     產生器用於定義部署中的元件。</span><span class="sxs-lookup"><span data-stu-id="a3c49-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="a3c49-116">**Lync Server 控制台**    用於使用以 web 為基礎的介面進行部署的持續管理。</span><span class="sxs-lookup"><span data-stu-id="a3c49-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="a3c49-117">**Lync Server 管理命令**     介面使用命令列來進行部署的持續管理。</span><span class="sxs-lookup"><span data-stu-id="a3c49-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="a3c49-118">**Lync Server 記錄工具**    用來疑難排解部署中的問題。</span><span class="sxs-lookup"><span data-stu-id="a3c49-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="a3c49-119">**集中式記錄服務**    從一部電腦、集區、網站或全域檔收集記錄檔和追蹤檔案。</span><span class="sxs-lookup"><span data-stu-id="a3c49-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="a3c49-120">選取及定義包含提供者、旗標及追蹤層級的案例。</span><span class="sxs-lookup"><span data-stu-id="a3c49-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="a3c49-121">記錄會收集、匯總及顯示工具（例如任何文字型工具或 Snooper.exe）。</span><span class="sxs-lookup"><span data-stu-id="a3c49-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="a3c49-122">您可以主要使用拓撲產生器和 Lync Server 控制台來管理您的部署。</span><span class="sxs-lookup"><span data-stu-id="a3c49-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="a3c49-123">部署嚮導</span><span class="sxs-lookup"><span data-stu-id="a3c49-123">Deployment Wizard</span></span>

<span data-ttu-id="a3c49-124">您必須使用安裝媒體上所包含的 Lync Server 部署嚮導，將所有系統管理工具安裝到尚未安裝 Lync Server 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a3c49-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="a3c49-125">在 [系統管理工具] 安裝程式期間，Lync Server 部署嚮導會與其他工具一起安裝在本機上，以便您日後使用它來安裝其他元件的檔案，或移除電腦上不想要的元件的檔。</span><span class="sxs-lookup"><span data-stu-id="a3c49-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="a3c49-126">如需如何第一次從 Lync Server 安裝媒體執行 Lync Server 部署嚮導的詳細資訊，請參閱 [Install Lync server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c49-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="a3c49-127">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="a3c49-127">Topology Builder</span></span>

<span data-ttu-id="a3c49-128">如需您可以使用拓撲產生器來執行之部署工作的詳細資訊，請參閱部署檔中的每個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="a3c49-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="a3c49-129">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="a3c49-129">Lync Server Control Panel</span></span>

<span data-ttu-id="a3c49-130">您可以使用 Lync Server 2013 控制台執行管理及維護 Lync Server 2013 所需的大部分管理工作。</span><span class="sxs-lookup"><span data-stu-id="a3c49-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="a3c49-131">Lync Server 控制台可讓您使用圖形使用者介面 (GUI) 管理執行 Lync Server 之伺服器的設定，以及組織中的使用者、用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="a3c49-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="a3c49-132">Lync Server 管理命令介面會使用 Lync Server 控制台做為進行 Lync 伺服器設定的基礎機制。</span><span class="sxs-lookup"><span data-stu-id="a3c49-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="a3c49-133">Lync Server 控制台會自動安裝在每一部 Lync Server 前端伺服器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="a3c49-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="a3c49-134">在這一版中，您可以遠端方式管理 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="a3c49-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="a3c49-135">您也可以在另一部電腦上安裝 Lync Server 控制台，例如您想要從中集中管理 Lync Server 的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="a3c49-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="a3c49-136">如需詳細資訊，請參閱 [Install Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c49-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="a3c49-137">若要使用 Lync Server 控制台設定設定，您必須使用指派給 CsAdministrator 角色的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="a3c49-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="a3c49-138">如需 Lync Server 2013 中可用的預先定義管理角色的詳細資訊，請參閱 <A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中規劃以角色為基礎的存取控制</A>。</span><span class="sxs-lookup"><span data-stu-id="a3c49-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="a3c49-139">若要使用 Lync Server 控制台設定設定，您也必須使用最小螢幕解析度為 1024 x 768 的電腦。</span><span class="sxs-lookup"><span data-stu-id="a3c49-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="a3c49-140">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="a3c49-140">Lync Server Management Shell</span></span>

<span data-ttu-id="a3c49-141">在 Lync Server 中，Lync Server 管理命令介面提供一種管理和管理的新方法。</span><span class="sxs-lookup"><span data-stu-id="a3c49-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="a3c49-142">Lync Server 管理命令介面是一種強大的管理介面，可在 Windows PowerShell 命令列介面上建立，其中包含一組完整的 Lync Server 專用 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3c49-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="a3c49-143">透過 Lync Server 管理命令介面，您可以取得一組豐富的設定和自動化控制。</span><span class="sxs-lookup"><span data-stu-id="a3c49-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="a3c49-144">拓撲產生器和 Lync Server 控制台都會執行這些 Cmdlet 的子集，以支援 Lync Server 的管理。</span><span class="sxs-lookup"><span data-stu-id="a3c49-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="a3c49-145">Lync Server 管理命令介面包含所有 Lync Server 管理工作的 Cmdlet，您可以個別使用 Cmdlet 來管理您的部署。</span><span class="sxs-lookup"><span data-stu-id="a3c49-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="a3c49-146">如需詳細資訊，請參閱 [Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面檔或每個 Cmdlet 的命令列說明。</span><span class="sxs-lookup"><span data-stu-id="a3c49-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="a3c49-147">記錄工具</span><span class="sxs-lookup"><span data-stu-id="a3c49-147">Logging Tool</span></span>

<span data-ttu-id="a3c49-148">Lync Server 記錄工具可在產品執行時，透過產品取得記錄和追蹤資訊，協助進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="a3c49-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="a3c49-149">您可以使用工具在任何 Lync Server 伺服器角色上執行調試會話。</span><span class="sxs-lookup"><span data-stu-id="a3c49-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="a3c49-150">如需有關記錄工具的詳細資訊，請參閱 TechNet 文件庫上的 Lync Server 2010 記錄工具檔 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。</span><span class="sxs-lookup"><span data-stu-id="a3c49-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3c49-151">在所有情況下，針對 Lync Server 記錄工具的所有記錄收集建議使用集中式記錄服務。</span><span class="sxs-lookup"><span data-stu-id="a3c49-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="a3c49-152">Lync Server 記錄工具仍可運作，但如果集中式記錄服務已經在執行中，它會干擾或呈現。</span><span class="sxs-lookup"><span data-stu-id="a3c49-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="a3c49-153">您應該只使用集中式記錄服務或 Lync Server 記錄工具，但決不會同時使用。</span><span class="sxs-lookup"><span data-stu-id="a3c49-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="a3c49-154">如需集中式記錄服務的詳細資訊，以及您應以獨佔方式使用的詳細資訊，請參閱 <A href="lync-server-2013-using-the-centralized-logging-service.md">在 Lync Server 2013 中使用集中式記錄服務</A>。</span><span class="sxs-lookup"><span data-stu-id="a3c49-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a3c49-155">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a3c49-155">In This Section</span></span>

  - [<span data-ttu-id="a3c49-156">Lync Server 2013 中的系統管理工具基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="a3c49-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="a3c49-157">Lync Server 2013 中的伺服器和工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="a3c49-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="a3c49-158">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="a3c49-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="a3c49-159">安裝和管理 Lync Server 2013 時所需的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="a3c49-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="a3c49-160">在 Lync Server 2013 中發行拓撲的需求</span><span class="sxs-lookup"><span data-stu-id="a3c49-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="a3c49-161">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="a3c49-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="a3c49-162">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="a3c49-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="a3c49-163">疑難排解 Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="a3c49-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="a3c49-164">在 Lync Server 2013 中使用集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="a3c49-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3c49-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a3c49-165">See Also</span></span>


[<span data-ttu-id="a3c49-166">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="a3c49-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

