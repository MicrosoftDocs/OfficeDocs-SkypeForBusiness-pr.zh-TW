---
title: Lync Server 2013：強化及保護伺服器及應用程式
description: Lync Server 2013：強化及保護伺服器及應用程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1205439208dfdadf5396b976d5d4876fb0aa24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567439"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="8f522-103">強化及保護 Lync Server 2013 的伺服器和應用程式</span><span class="sxs-lookup"><span data-stu-id="8f522-103">Hardening and protecting servers and applications for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f522-104">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="8f522-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="8f522-105">您應根據該特定元件的最佳作法來增強並保護作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="8f522-105">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="8f522-106">本節說明如何增強應用程式伺服器，並使用群組原則來實作安全性鎖定。</span><span class="sxs-lookup"><span data-stu-id="8f522-106">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f522-107">您也可以強化和保護用於 Microsoft Lync Server 2013 部署的資料庫。</span><span class="sxs-lookup"><span data-stu-id="8f522-107">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="8f522-108">如需詳細資訊，請參閱 <A href="lync-server-2013-hardening-and-protecting-databases.md">強化及保護 Lync Server 2013 的資料庫</A>。</span><span class="sxs-lookup"><span data-stu-id="8f522-108">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="8f522-109">保障應用程式伺服器的安全</span><span class="sxs-lookup"><span data-stu-id="8f522-109">Securing Application Servers</span></span>

<span data-ttu-id="8f522-p103">若是應用程式伺服器，則應增強作業系統和應用程式。例如，專門用來執行 Microsoft Internet Security and Acceleration (ISA) Server 2006 的 Windows Server 2008 電腦應在作業系統和應用程式方面加以增強。首要目標應該是盡量減少執行的服務數量，以及伺服器提供的服務數量。</span><span class="sxs-lookup"><span data-stu-id="8f522-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="8f522-113">保障虛擬伺服器的安全</span><span class="sxs-lookup"><span data-stu-id="8f522-113">Securing Virtual Servers</span></span>

<span data-ttu-id="8f522-114">虛擬伺服器快照中包含了伺服器資料磁碟的複本，以及記憶體內部資料的傾印檔；兩者皆可能含有機密的密碼編譯資料，容易遭受攻擊。</span><span class="sxs-lookup"><span data-stu-id="8f522-114">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="8f522-115">若是以虛擬化實作的生產伺服器，則應停用所有伺服器快照，或嚴密地管理。</span><span class="sxs-lookup"><span data-stu-id="8f522-115">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="8f522-116">如需保護 Hyper-V 虛擬伺服器的詳細資訊，請參閱 Hyper-V Security Guide at： [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) 。</span><span class="sxs-lookup"><span data-stu-id="8f522-116">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="8f522-117">群組原則</span><span class="sxs-lookup"><span data-stu-id="8f522-117">Group Policy</span></span>

<span data-ttu-id="8f522-p105">在 Windows Server 2008 和 Windows Server 2008 R2 中，群組原則提供目錄式的桌面設定管理。您可以透過在下列各項的群組原則物件 (GPO) 內定義 [電腦及使用者] 設定，使用群組原則來實作安全性鎖定：</span><span class="sxs-lookup"><span data-stu-id="8f522-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="8f522-120">登錄型原則</span><span class="sxs-lookup"><span data-stu-id="8f522-120">Registry-based policies</span></span>

  - <span data-ttu-id="8f522-121">安全性</span><span class="sxs-lookup"><span data-stu-id="8f522-121">Security</span></span>

  - <span data-ttu-id="8f522-122">軟體安裝</span><span class="sxs-lookup"><span data-stu-id="8f522-122">Software installation</span></span>

  - <span data-ttu-id="8f522-123">指令碼</span><span class="sxs-lookup"><span data-stu-id="8f522-123">Scripts</span></span>

  - <span data-ttu-id="8f522-124">資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="8f522-124">Folder redirection</span></span>

  - <span data-ttu-id="8f522-125">遠端安裝服務</span><span class="sxs-lookup"><span data-stu-id="8f522-125">Remote installation services</span></span>

<span data-ttu-id="8f522-126">為了提供使用者介面以設定這些設定，系統管理範本隨附于作業系統版本、service pack 發行及部分應用程式（包括 Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="8f522-126">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="8f522-127">Communicator .adm 檔案是隨 Lync Server 2013 提供的系統管理範本，會安裝至% windir% \\ inf \\ 目錄，並提供群組原則設定的介面。</span><span class="sxs-lookup"><span data-stu-id="8f522-127">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="8f522-128">Communicator.adm 中的每一項設定都會對應到登錄中，影響應用程式行為的設定。</span><span class="sxs-lookup"><span data-stu-id="8f522-128">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="8f522-129">這些設定可以從 GPedit.dll 存取，該檔案可在 Active Directory [使用者和電腦] 主控台以及群組原則管理主控台 (GPMC) 中找到。</span><span class="sxs-lookup"><span data-stu-id="8f522-129">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="8f522-130">群組原則安全性設定</span><span class="sxs-lookup"><span data-stu-id="8f522-130">Group Policy Security Settings</span></span>

<span data-ttu-id="8f522-131">群組原則中包含了從 GPedit.dll 存取 GPO 時 (位於電腦設定/Windows 設定/安全性設定底下) 的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="8f522-131">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="8f522-132">您可以匯入安全性範本來設定 GPO 的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="8f522-132">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="8f522-133">《 Windows Server 2008 安全性指南》 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 及 Windows server 2008 R2 安全性符合性管理工具組 [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) 包含一些範例範本，您可以修改這些範本以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="8f522-133">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="8f522-134">最佳作法</span><span class="sxs-lookup"><span data-stu-id="8f522-134">Best Practices</span></span>

  - <span data-ttu-id="8f522-135">增強所有伺服器的作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="8f522-135">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="8f522-136">保護伺服器快照並強化所有虛擬伺服器的安全性。</span><span class="sxs-lookup"><span data-stu-id="8f522-136">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="8f522-137">使用群組原則實作安全性鎖定。</span><span class="sxs-lookup"><span data-stu-id="8f522-137">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

