---
title: Lync Server 2013： 準備和安裝最佳做法分析程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303df28b307a2d23bdc468d1c53977030d0cf8df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="e5c3b-102">準備和 Lync Server 2013 中安裝最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="e5c3b-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5c3b-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="e5c3b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e5c3b-104">您必須以 Administrators 群組成員登入，來執行本主題所說明的工作。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="e5c3b-105">安裝最佳做法分析程式的系統需求</span><span class="sxs-lookup"><span data-stu-id="e5c3b-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="e5c3b-106">若要執行 Lync Server 2013，最佳做法分析程式來掃描您的環境，電腦必須執行下列其中一個下列作業系統的 64 位元版本：</span><span class="sxs-lookup"><span data-stu-id="e5c3b-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="e5c3b-107">Windows Server 2008 R2 Service Pack 1 (SP1) Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="e5c3b-108">Windows Server 2008 R2 Enterprise 作業系統 SP1</span><span class="sxs-lookup"><span data-stu-id="e5c3b-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="e5c3b-109">Windows Server 2008 R2 SP1 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="e5c3b-110">Windows Server 2012 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="e5c3b-111">Windows Server 2012 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="e5c3b-112">Windows Server 2012 Enterprise 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="e5c3b-113">Windows Server 2012 R2 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="e5c3b-114">Windows Server 2012 R2 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="e5c3b-115">Windows Server 2012 R2 Enterprise 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="e5c3b-116">Windows 8 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="e5c3b-117">Windows 7 作業系統</span><span class="sxs-lookup"><span data-stu-id="e5c3b-117">Windows 7 operating system</span></span>

<span data-ttu-id="e5c3b-118">該電腦也必須執行下列程式：</span><span class="sxs-lookup"><span data-stu-id="e5c3b-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="e5c3b-119">Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="e5c3b-120">Lync Server 2013 中，您必須手動前安裝 Lync Server 2013 伺服器上安裝 Microsoft.NET Framework 4.5 的 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="e5c3b-121">Lync Server 2013 中，核心元件。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="e5c3b-122">WMI 回溯相容性套件。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="e5c3b-123">如需詳細資訊，請參閱移轉文件中的[安裝 WMI 回溯相容性套件](install-wmi-backward-compatibility-package.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="e5c3b-124">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="e5c3b-125">如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中安裝 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md) 。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e5c3b-126">您可以支援的作業系統與 Lync Server 2013、 核心元件或 WMI 回溯相容性套件，未執行的電腦上安裝最佳做法分析程式，但您可以使用最佳做法分析程式在這些電腦上只檢視報告，不若要執行的掃描。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="e5c3b-127">選擇電腦進行安裝</span><span class="sxs-lookup"><span data-stu-id="e5c3b-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="e5c3b-128">我們建議您安裝 Lync Server 2013，專用於 Lync Server 2013 管理的電腦上的最佳做法分析程式。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="e5c3b-129">您可以在執行 Lync Server 2013 或執行 Lync Server 2013 系統管理工具的系統管理電腦的伺服器上安裝此工具。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e5c3b-130">如果您執行 Lync Server 的伺服器上安裝此工具，我們建議您使用工具來掃描唯有該伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="e5c3b-131">安裝最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="e5c3b-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="e5c3b-132">您可以下載在 Lync Server 2013 的最佳做法分析程式[https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-132">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="e5c3b-133">若要安裝最佳做法分析程式，請在您要安裝此工具的電腦上啟動 Microsoft 安裝程式檔案 RtcBPA.msi，然後依照螢幕上的指示執行。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="e5c3b-134">安裝程式檔案的預設位置是\<系統磁碟機\>\\Program Files\\Lync Server 2013\\BPA。</span><span class="sxs-lookup"><span data-stu-id="e5c3b-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

