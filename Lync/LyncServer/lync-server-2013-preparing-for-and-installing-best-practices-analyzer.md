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
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="05afb-102">在 Lync Server 2013 中準備及安裝最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="05afb-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05afb-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="05afb-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="05afb-104">您必須以系統管理員群組成員的身分登入，才能執行本主題中所述的工作。</span><span class="sxs-lookup"><span data-stu-id="05afb-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="05afb-105">最佳做法分析程式安裝的系統需求</span><span class="sxs-lookup"><span data-stu-id="05afb-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="05afb-106">若要執行 Lync Server 2013、最佳做法分析程式來掃描您的環境，電腦必須執行下列其中一個作業系統的64位版本：</span><span class="sxs-lookup"><span data-stu-id="05afb-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="05afb-107">Windows Server 2008 R2 Service Pack 1 （SP1）標準作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="05afb-108">Windows Server 2008 R2 （含 SP1 Enterprise 作業系統）</span><span class="sxs-lookup"><span data-stu-id="05afb-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="05afb-109">Windows Server 2008 R2 （含 SP1 資料中心作業系統）</span><span class="sxs-lookup"><span data-stu-id="05afb-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="05afb-110">Windows Server 2012 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="05afb-111">Windows Server 2012 標準作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="05afb-112">Windows Server 2012 企業版作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="05afb-113">Windows Server 2012 R2 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="05afb-114">Windows Server 2012 R2 標準作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="05afb-115">Windows Server 2012 R2 Enterprise 作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="05afb-116">Windows 8 作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="05afb-117">Windows 7 作業系統</span><span class="sxs-lookup"><span data-stu-id="05afb-117">Windows 7 operating system</span></span>

<span data-ttu-id="05afb-118">電腦也必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="05afb-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="05afb-119">Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="05afb-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="05afb-120">針對 Lync Server 2013，您必須先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5，才能安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="05afb-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="05afb-121">Lync Server 2013、核心元件。</span><span class="sxs-lookup"><span data-stu-id="05afb-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="05afb-122">WMI 向後相容性套件。</span><span class="sxs-lookup"><span data-stu-id="05afb-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="05afb-123">如需詳細資訊，請參閱在遷移檔中[安裝 WMI 向後相容性套件](install-wmi-backward-compatibility-package.md)。</span><span class="sxs-lookup"><span data-stu-id="05afb-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="05afb-124">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="05afb-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="05afb-125">如需詳細資訊，請參閱在部署檔中[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md) 。</span><span class="sxs-lookup"><span data-stu-id="05afb-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="05afb-126">您可以在有未執行 Lync Server 2013、核心元件或 WMI 向後相容性套件之支援作業系統的電腦上安裝最佳做法分析程式，但您只能在這些電腦上使用最佳做法分析程式來查看報表，而不是以執行掃描。</span><span class="sxs-lookup"><span data-stu-id="05afb-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="05afb-127">選擇要安裝的電腦</span><span class="sxs-lookup"><span data-stu-id="05afb-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="05afb-128">我們建議您在專用於 Lync Server 2013 管理的電腦上安裝 Lync Server 2013、最佳做法分析程式。</span><span class="sxs-lookup"><span data-stu-id="05afb-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="05afb-129">您可以在執行 Lync Server 2013 的伺服器或執行 Lync Server 2013 系統管理工具的系統管理電腦上安裝該工具。</span><span class="sxs-lookup"><span data-stu-id="05afb-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="05afb-130">如果您在執行 Lync Server 的伺服器上安裝該工具，建議您使用該工具只掃描該伺服器。</span><span class="sxs-lookup"><span data-stu-id="05afb-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="05afb-131">安裝最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="05afb-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="05afb-132">您可以下載適用于 Lync Server 2013 的最佳做法分析[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)程式。</span><span class="sxs-lookup"><span data-stu-id="05afb-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="05afb-133">若要安裝最佳做法分析程式，請在您要安裝此工具的電腦上啟動 Microsoft Installer 檔案 RtcBPA，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="05afb-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="05afb-134">安裝程式檔案的預設\<位置是系統磁碟機\>\\程式檔\\Lync Server 2013\\BPA。</span><span class="sxs-lookup"><span data-stu-id="05afb-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

