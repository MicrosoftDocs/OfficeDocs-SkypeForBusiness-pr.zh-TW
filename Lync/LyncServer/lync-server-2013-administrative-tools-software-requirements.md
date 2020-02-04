---
title: Lync Server 2013：系統管理工具軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="16a08-102">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="16a08-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16a08-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="16a08-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="16a08-104">本主題描述除了作業系統需求之外，安裝和使用 Lync Server 2013 系統管理工具所需的軟體。</span><span class="sxs-lookup"><span data-stu-id="16a08-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="16a08-105">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="16a08-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="16a08-106">Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="16a08-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="16a08-107">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="16a08-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="16a08-108">Windows PowerShell 3.0 是執行 Microsoft Lync Server 2013 的任何元件所必需的。</span><span class="sxs-lookup"><span data-stu-id="16a08-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="16a08-109">如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="16a08-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="16a08-110">Windows Installer 版本4。5</span><span class="sxs-lookup"><span data-stu-id="16a08-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="16a08-111">Lync Server 2013 使用 Windows 安裝程式技術來安裝、卸載及維護各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="16a08-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="16a08-112">Windows Installer 版本4.5 提供給 Windows Server 作業系統的可發佈元件。</span><span class="sxs-lookup"><span data-stu-id="16a08-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="16a08-113">Windows Installer 4.5 隨附 Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2，這表示您不需要下載任何執行 Lync Server 2013 之電腦的實用程式。</span><span class="sxs-lookup"><span data-stu-id="16a08-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="16a08-114">（Lync Server 2013 只能安裝在運行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的電腦上。）</span><span class="sxs-lookup"><span data-stu-id="16a08-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="16a08-115">不過，如果您想要在管理員工作站上安裝 Lync Server 管理命令介面或 Lync Server 拓撲建立器，您可能需要下載 Windows Installer 4.5。</span><span class="sxs-lookup"><span data-stu-id="16a08-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="16a08-116">該實用程式隨附于 Windows 7 和 Windows 2008 R2，但不適用於任何舊版的 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="16a08-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="16a08-117">您可以從 Microsoft 下載中心下載 Windows Installer 4.5 <http://go.microsoft.com/fwlink/p/?linkid=197395>。</span><span class="sxs-lookup"><span data-stu-id="16a08-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="16a08-118">Microsoft Silverlight 5 瀏覽器外掛程式</span><span class="sxs-lookup"><span data-stu-id="16a08-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="16a08-119">Lync Server 2013 [控制台] 是一個以 web 為基礎的工具，需要您安裝最新版的 Microsoft Silverlight 5 瀏覽器外掛程式。</span><span class="sxs-lookup"><span data-stu-id="16a08-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="16a08-120">當您啟動 Lync Server 2013 [控制台] 時，如果未安裝這個軟體，或安裝的是舊版，Lync Server 2013 [控制台] 會提示您安裝所需的版本。</span><span class="sxs-lookup"><span data-stu-id="16a08-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16a08-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="16a08-121">See Also</span></span>


[<span data-ttu-id="16a08-122">Lync Server 2013 中的伺服器及工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="16a08-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="16a08-123">Lync Server 2013 中的管理工具基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="16a08-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="16a08-124">設定和管理 Lync Server 2013 所需的系統管理員權限</span><span class="sxs-lookup"><span data-stu-id="16a08-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

