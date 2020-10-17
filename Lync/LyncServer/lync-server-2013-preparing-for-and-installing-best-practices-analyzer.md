---
title: Lync Server 2013：準備及安裝最佳做法分析程式
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
ms.openlocfilehash: d6a1ddaff4813035cabc8ca6b7468f1d4d06c93e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506930"
---
# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="db4c9-102">在 Lync Server 2013 中準備及安裝最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="db4c9-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db4c9-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="db4c9-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="db4c9-104">您必須以 Administrators 群組成員登入，來執行本主題所說明的工作。</span><span class="sxs-lookup"><span data-stu-id="db4c9-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="db4c9-105">安裝最佳做法分析程式的系統需求</span><span class="sxs-lookup"><span data-stu-id="db4c9-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="db4c9-106">若要執行 Lync Server 2013，最佳做法分析程式來掃描您的環境，電腦必須執行下列其中一個作業系統的64位版本：</span><span class="sxs-lookup"><span data-stu-id="db4c9-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="db4c9-107">Windows Server 2008 R2 Service Pack 1 (SP1) Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="db4c9-108">Windows Server 2008 R2 （含 SP1 Enterprise 作業系統）</span><span class="sxs-lookup"><span data-stu-id="db4c9-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="db4c9-109">Windows Server 2008 R2 與 SP1 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="db4c9-110">Windows Server 2012 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="db4c9-111">Windows Server 2012 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="db4c9-112">Windows Server 2012 企業版作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="db4c9-113">Windows Server 2012 R2 資料中心作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="db4c9-114">Windows Server 2012 R2 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="db4c9-115">Windows Server 2012 R2 Enterprise 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="db4c9-116">Windows 8 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="db4c9-117">Windows 7 作業系統</span><span class="sxs-lookup"><span data-stu-id="db4c9-117">Windows 7 operating system</span></span>

<span data-ttu-id="db4c9-118">該電腦也必須執行下列程式：</span><span class="sxs-lookup"><span data-stu-id="db4c9-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="db4c9-119">Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="db4c9-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="db4c9-120">針對 Lync Server 2013，您必須在安裝 Lync Server 2013 之前，先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="db4c9-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="db4c9-121">Lync Server 2013，核心元件。</span><span class="sxs-lookup"><span data-stu-id="db4c9-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="db4c9-122">WMI 回溯相容性套件。</span><span class="sxs-lookup"><span data-stu-id="db4c9-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="db4c9-123">如需詳細資訊，請參閱在遷移檔中 [安裝 WMI 後退相容性套件](install-wmi-backward-compatibility-package.md) 。</span><span class="sxs-lookup"><span data-stu-id="db4c9-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="db4c9-124">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="db4c9-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="db4c9-125">如需詳細資訊，請參閱部署檔中的 [Windows PowerShell 3.0 的 Lync Server 2013 安裝](lync-server-2013-installing-windows-powershell-3-0.md) 。</span><span class="sxs-lookup"><span data-stu-id="db4c9-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="db4c9-126">您可以在支援作業系統的電腦上安裝最佳做法分析程式，但不執行 Lync Server 2013、核心元件或 WMI 回溯相容性套件，但您可以在那些電腦上使用最佳做法分析程式，只查看報告，而不是執行掃描。</span><span class="sxs-lookup"><span data-stu-id="db4c9-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="db4c9-127">選擇電腦進行安裝</span><span class="sxs-lookup"><span data-stu-id="db4c9-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="db4c9-128">建議您在專用於 Lync Server 2013 管理的電腦上，安裝 Lync Server 2013，最佳做法分析器。</span><span class="sxs-lookup"><span data-stu-id="db4c9-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="db4c9-129">您可以在執行 Lync Server 2013 的伺服器或執行 Lync Server 2013 系統管理工具的系統管理電腦上安裝工具。</span><span class="sxs-lookup"><span data-stu-id="db4c9-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="db4c9-130">[！附注] 如果您在執行 Lync Server 的伺服器上安裝工具，建議您使用工具僅掃描該伺服器。</span><span class="sxs-lookup"><span data-stu-id="db4c9-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="db4c9-131">安裝最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="db4c9-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="db4c9-132">您可以在上下載 Lync Server 2013 的最佳作法分析程式 [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539) 。</span><span class="sxs-lookup"><span data-stu-id="db4c9-132">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="db4c9-133">若要安裝最佳做法分析程式，請在您要安裝此工具的電腦上啟動 Microsoft 安裝程式檔案 RtcBPA.msi，然後依照螢幕上的指示執行。</span><span class="sxs-lookup"><span data-stu-id="db4c9-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="db4c9-134">安裝程式檔案的預設位置是「 \<system drive\> \\ program Files \\ Lync Server 2013 \\ BPA」。</span><span class="sxs-lookup"><span data-stu-id="db4c9-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

