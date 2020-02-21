---
title: Lync Server 2013： 增強及保護伺服器和應用程式
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
ms.openlocfilehash: e2a8de372a8ca0ae6ec8c80a147eb74ffb01d0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="82689-102">增強及保護伺服器和 Lync Server 2013 的應用程式</span><span class="sxs-lookup"><span data-stu-id="82689-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82689-103">_**上次修改主題：** 2013年-12-05_</span><span class="sxs-lookup"><span data-stu-id="82689-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="82689-104">您應根據該特定元件的最佳作法來增強並保護作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="82689-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="82689-105">本節說明如何增強應用程式伺服器，並使用群組原則來實作安全性鎖定。</span><span class="sxs-lookup"><span data-stu-id="82689-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82689-106">您也可以強化並保護您的 Microsoft Lync Server 2013 部署使用的資料庫。</span><span class="sxs-lookup"><span data-stu-id="82689-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="82689-107">如需詳細資訊，請參閱<A href="lync-server-2013-hardening-and-protecting-databases.md">強化及保護 Lync Server 2013 的資料庫</A>。</span><span class="sxs-lookup"><span data-stu-id="82689-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="82689-108">保障應用程式伺服器的安全</span><span class="sxs-lookup"><span data-stu-id="82689-108">Securing Application Servers</span></span>

<span data-ttu-id="82689-p103">若是應用程式伺服器，則應增強作業系統和應用程式。例如，專門用來執行 Microsoft Internet Security and Acceleration (ISA) Server 2006 的 Windows Server 2008 電腦應在作業系統和應用程式方面加以增強。首要目標應該是盡量減少執行的服務數量，以及伺服器提供的服務數量。</span><span class="sxs-lookup"><span data-stu-id="82689-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="82689-112">保障虛擬伺服器的安全</span><span class="sxs-lookup"><span data-stu-id="82689-112">Securing Virtual Servers</span></span>

<span data-ttu-id="82689-113">虛擬伺服器快照中包含了伺服器資料磁碟的複本，以及記憶體內部資料的傾印檔；兩者皆可能含有機密的密碼編譯資料，容易遭受攻擊。</span><span class="sxs-lookup"><span data-stu-id="82689-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="82689-114">若是以虛擬化實作的生產伺服器，則應停用所有伺服器快照，或嚴密地管理。</span><span class="sxs-lookup"><span data-stu-id="82689-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="82689-115">如需保護 HYPER-V 虛擬伺服器的詳細資訊，請參閱在 HYPER-V 安全性指南： [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)。</span><span class="sxs-lookup"><span data-stu-id="82689-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="82689-116">群組原則</span><span class="sxs-lookup"><span data-stu-id="82689-116">Group Policy</span></span>

<span data-ttu-id="82689-p105">在 Windows Server 2008 和 Windows Server 2008 R2 中，群組原則提供目錄式的桌面設定管理。您可以透過在下列各項的群組原則物件 (GPO) 內定義 [電腦及使用者] 設定，使用群組原則來實作安全性鎖定：</span><span class="sxs-lookup"><span data-stu-id="82689-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="82689-119">登錄型原則</span><span class="sxs-lookup"><span data-stu-id="82689-119">Registry-based policies</span></span>

  - <span data-ttu-id="82689-120">安全性</span><span class="sxs-lookup"><span data-stu-id="82689-120">Security</span></span>

  - <span data-ttu-id="82689-121">軟體安裝</span><span class="sxs-lookup"><span data-stu-id="82689-121">Software installation</span></span>

  - <span data-ttu-id="82689-122">指令碼</span><span class="sxs-lookup"><span data-stu-id="82689-122">Scripts</span></span>

  - <span data-ttu-id="82689-123">資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="82689-123">Folder redirection</span></span>

  - <span data-ttu-id="82689-124">遠端安裝服務</span><span class="sxs-lookup"><span data-stu-id="82689-124">Remote installation services</span></span>

<span data-ttu-id="82689-125">若要提供系統管理員設定這些設定的使用者介面，系統管理範本所隨附的作業系統版本、 service pack 版本和某些應用程式，包括 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="82689-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="82689-126">檔案是隨附於 Lync Server 2013 系統管理範本 Communicator.adm 安裝至 %windir%\\inf\\目錄，並提供介面至群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="82689-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="82689-127">Communicator.adm 中的每一項設定都會對應到登錄中，影響應用程式行為的設定。</span><span class="sxs-lookup"><span data-stu-id="82689-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="82689-128">這些設定可以從 GPedit.dll 存取，該檔案可在 Active Directory [使用者和電腦] 主控台以及群組原則管理主控台 (GPMC) 中找到。</span><span class="sxs-lookup"><span data-stu-id="82689-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="82689-129">群組原則安全性設定</span><span class="sxs-lookup"><span data-stu-id="82689-129">Group Policy Security Settings</span></span>

<span data-ttu-id="82689-130">群組原則中包含了從 GPedit.dll 存取 GPO 時 (位於電腦設定/Windows 設定/安全性設定底下) 的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="82689-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="82689-131">您可以匯入安全性範本來設定 GPO 的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="82689-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="82689-132">Windows Server 2008 安全性指南 》，[https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186)和 Windows Server 2008 R2 Security Compliance Management Toolkit 在[https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882)包含您可以修改以符合您需求的範例範本數目。</span><span class="sxs-lookup"><span data-stu-id="82689-132">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="82689-133">最佳作法</span><span class="sxs-lookup"><span data-stu-id="82689-133">Best Practices</span></span>

  - <span data-ttu-id="82689-134">增強所有伺服器的作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="82689-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="82689-135">保護伺服器快照並強化所有虛擬伺服器的安全性。</span><span class="sxs-lookup"><span data-stu-id="82689-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="82689-136">使用群組原則實作安全性鎖定。</span><span class="sxs-lookup"><span data-stu-id="82689-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

