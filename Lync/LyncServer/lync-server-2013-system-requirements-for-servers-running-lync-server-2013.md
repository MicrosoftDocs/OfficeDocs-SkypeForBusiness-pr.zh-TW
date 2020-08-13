---
title: Lync Server 2013：執行 Lync Server 2013 之伺服器的系統需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0affd2d951d437a930bc7f210e0878e2978f8731
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417578"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="6cfa4-102">執行 Lync Server 2013 之伺服器的系統需求</span><span class="sxs-lookup"><span data-stu-id="6cfa4-102">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cfa4-103">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="6cfa4-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6cfa4-104">如需硬體需求的詳細資訊，請參閱<A href="lync-server-2013-server-hardware-platforms.md">伺服器硬體平臺的 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6cfa4-105">Standard Edition 和 Enterprise Edition 伺服器共用相同的軟體需求。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="6cfa4-106">執行 Lync Server 2013 Enterprise Edition 的伺服器專為大型組織做為主要組織部署。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="6cfa4-107">Enterprise Edition Server 依設計最多可讓每個集區容納約 80,000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="6cfa4-108">執行 Lync Server 2013 的伺服器，Standard Edition 是針對小型組織和主要組織部署的遠端位置而設計。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="6cfa4-109">一對的 Standard Edition 伺服器最多可支援5000使用者。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="6cfa4-110">如需有關 Standard Edition server 和 Enterprise Edition server 之間差異的詳細資訊，請參閱[Lync Server 2013 的部署概況](lync-server-2013-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="6cfa4-111">作業系統安裝</span><span class="sxs-lookup"><span data-stu-id="6cfa4-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6cfa4-112">Lync Server 2013 只適用于64位的版本，需要有64位的硬體和64版本的 Windows Server 作業系統。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="6cfa4-113">此版本不提供 Lync Server 2013 的32位版本。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="6cfa4-114">Standard Edition 和 Enterprise Edition server 可以使用下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="6cfa4-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="6cfa4-115">Windows Server 2008 R2 SP1 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="6cfa4-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="6cfa4-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6cfa4-116">Windows Server 2012</span></span>

  - <span data-ttu-id="6cfa4-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6cfa4-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="6cfa4-118">在 Standard Edition Server 或 Enterprise Edition 前端伺服器上安裝作業系統軟體。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="6cfa4-119">套用所有更新，讓作業系統具有與組織的標準相符的最新更新和必要更新層級。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="6cfa4-120">如需有關運作需求的詳細資訊，請參閱支援檔中的[伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="6cfa4-121">Lync Server 2013 不支援就地升級作業系統。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-121">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="6cfa4-122">您必須部署個別的集區，並將使用者遷移至具有不同作業系統的新集區。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-122">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6cfa4-123">若要讓 Lync Server 2013 在 Windows Server 2012 R2 上運作，您可能需要在 Windows Server 中變更登錄機碼的值。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-123">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="6cfa4-124">若要讓憑證正確運作，且要讓用戶端向 Survivable 分支裝置註冊，可能需要這種變更。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-124">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="6cfa4-125">如需詳細資訊，請參閱 <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> 。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-125">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="6cfa4-126">Lync Server 2013 的其他軟體</span><span class="sxs-lookup"><span data-stu-id="6cfa4-126">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="6cfa4-127">除了作業系統所需的更新之外，Lync Server 2013 還需要作業系統角色、功能和軟體才能運作。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-127">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="6cfa4-128">如需在發行拓撲及安裝 Lync Server 2013 之前必須安裝之其他軟體的詳細資訊，請參閱規劃檔中的[其他軟體需求（Lync Server 2013](lync-server-2013-additional-software-requirements.md) ）。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-128">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="6cfa4-129">所有伺服器角色所需的其他軟體</span><span class="sxs-lookup"><span data-stu-id="6cfa4-129">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="6cfa4-130">在所有伺服器角色上，您也必須確定已安裝 Windows PowerShell 命令列介面3.0 和 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-130">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="6cfa4-131">此外，在任何要執行 Lync Server 系統管理工具的電腦上，Windows PowerShell 命令列介面3.0 和 Microsoft .NET Framework 4.5 都是必要的。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-131">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="6cfa4-132">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="6cfa4-132">Windows PowerShell 3.0</span></span>

<span data-ttu-id="6cfa4-133">Lync Server 2013 需要您在您的 Lync Server 拓撲中的每一部電腦上安裝 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-133">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="6cfa4-134">如需安裝 Windows PowerShell 3.0 的詳細資訊，請參閱[安裝 windows PowerShell 3.0 的 Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-134">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6cfa4-135">在 Windows Server &nbsp; 2008 &nbsp; R2 上使用 SP1，windows PowerShell 命令列介面3.0 無法在安裝 Microsoft .net Framework 4.5 之前安裝。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-135">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="6cfa4-136">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6cfa4-136">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="6cfa4-137">當您在 Windows Server 2012 或 Windows Server 2012 R2 上的伺服器上安裝 Microsoft .NET Framework 4.5，以執行 Lync Server 2013 時，您必須執行一個額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-137">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="6cfa4-138">安裝 .NET Framework 4.5 後，請使用伺服器管理員安裝 HTTP 啟用。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-138">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="6cfa4-139">**在 Windows Server 2012 或 Windows Server 2012 R2 上安裝 .NET 4.5 HTTP 啟用**</span><span class="sxs-lookup"><span data-stu-id="6cfa4-139">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="6cfa4-140">在 [**開始**] 功能表上，按一下 [**程式**]，然後按一下 [系統**管理工具**]，再按一下 [**伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-140">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="6cfa4-141">在 [伺服器管理員] 的 [**功能摘要**] 下，選擇 [**新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-141">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="6cfa4-142">展開 **.Net Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-142">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="6cfa4-143">選取 [ **WCF 啟用**] （如果尚未選取）。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-143">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="6cfa4-144">然後選取 [ **HTTP 啟用**]。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-144">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="6cfa4-145">按 **[下一步**]，然後依照提示完成安裝。</span><span class="sxs-lookup"><span data-stu-id="6cfa4-145">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

