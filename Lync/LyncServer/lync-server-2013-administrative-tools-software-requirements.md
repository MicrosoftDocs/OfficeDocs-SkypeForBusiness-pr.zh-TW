---
title: Lync Server 2013：系統管理工具軟體需求
description: Lync Server 2013：系統管理工具軟體需求。
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
ms.openlocfilehash: 0c723d56cbda0c171fab206e3bcd3b2da0cc5b4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552959"
---
# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="7a0c9-103">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="7a0c9-103">Administrative tools software requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a0c9-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7a0c9-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7a0c9-105">本主題說明除了作業系統需求以外，安裝及使用 Lync Server 2013 系統管理工具所需的軟體。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-105">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="7a0c9-106">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="7a0c9-106">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="7a0c9-107">Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-107">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="7a0c9-108">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="7a0c9-108">Windows PowerShell 3.0</span></span>

<span data-ttu-id="7a0c9-109">若要執行 Microsoft Lync Server 2013 的任何元件，都需要有 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-109">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7a0c9-110">如需詳細資訊，請參閱 [安裝適用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-110">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="7a0c9-111">Windows Installer 4.5 版</span><span class="sxs-lookup"><span data-stu-id="7a0c9-111">Windows Installer Version 4.5</span></span>

<span data-ttu-id="7a0c9-112">Lync Server 2013 使用 Windows Installer 技術來安裝、卸載及維護各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-112">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="7a0c9-113">Windows Installer 4.5 版是以 Windows Server 作業系統適用的可轉散發元件形式提供。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-113">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="7a0c9-114">Windows Installer 4.5 隨附 Windows Server 2012 R2、Windows Server 2012 及 Windows Server 2008 R2，這表示您不需要為任何執行 Lync Server 2013 的電腦下載公用程式。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-114">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="7a0c9-115"> (Lync Server 2013 僅可安裝在執行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的電腦上。 ) </span><span class="sxs-lookup"><span data-stu-id="7a0c9-115">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="7a0c9-116">不過，如果您想要在系統管理員工作站上安裝 Lync Server 管理命令介面或 Lync Server 拓撲產生器，您可能需要下載 Windows Installer 4.5。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-116">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="7a0c9-117">該公用程式隨附 Windows 7 和 Windows 2008 R2，但不是任何舊版 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-117">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="7a0c9-118">您可以從 Microsoft 下載中心下載 Windows Installer 4.5，網址為 <https://go.microsoft.com/fwlink/p/?linkid=197395> 。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-118">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="7a0c9-119">Microsoft Silverlight 5 瀏覽器外掛程式</span><span class="sxs-lookup"><span data-stu-id="7a0c9-119">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="7a0c9-120">Lync Server 2013 控制台是以網路為基礎的工具，並要求您安裝最新版的 Microsoft Silverlight 5 瀏覽器外掛程式。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-120">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="7a0c9-121">當您啟動 Lync Server 2013 控制台時，若未安裝此軟體或已安裝舊版，Lync Server 2013 控制台會提示您安裝必要的版本。</span><span class="sxs-lookup"><span data-stu-id="7a0c9-121">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a0c9-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7a0c9-122">See Also</span></span>


[<span data-ttu-id="7a0c9-123">Lync Server 2013 中的伺服器和工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="7a0c9-123">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="7a0c9-124">Lync Server 2013 中的系統管理工具基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="7a0c9-124">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="7a0c9-125">安裝和管理 Lync Server 2013 時所需的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="7a0c9-125">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

