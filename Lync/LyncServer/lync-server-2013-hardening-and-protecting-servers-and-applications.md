---
title: Lync Server 2013：增強及保護伺服器和應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="d0e67-102">增強及保護 Lync Server 2013 的伺服器和應用程式</span><span class="sxs-lookup"><span data-stu-id="d0e67-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0e67-103">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="d0e67-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="d0e67-104">您應該根據該特定元件的最佳做法，加強及保護您的作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0e67-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="d0e67-105">本節說明如何加強應用程式伺服器，並使用群組原則來實現安全性 lockdowns。</span><span class="sxs-lookup"><span data-stu-id="d0e67-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0e67-106">您也可以加強及保護 Microsoft Lync Server 2013 部署所用的資料庫。</span><span class="sxs-lookup"><span data-stu-id="d0e67-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="d0e67-107">如需詳細資訊，請參閱<A href="lync-server-2013-hardening-and-protecting-databases.md">強化及保護 Lync Server 2013 的資料庫</A>。</span><span class="sxs-lookup"><span data-stu-id="d0e67-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="d0e67-108">保護應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="d0e67-108">Securing Application Servers</span></span>

<span data-ttu-id="d0e67-109">針對應用程式伺服器，應加強作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0e67-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="d0e67-110">例如，專用來執行 Microsoft 網際網路安全性和加速（ISA） Server 2006 的 Windows Server 2008 電腦應該從作業系統和應用程式的觀點加強。</span><span class="sxs-lookup"><span data-stu-id="d0e67-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="d0e67-111">最小化由伺服器執行並提供的服務數目，應該是主要目標。</span><span class="sxs-lookup"><span data-stu-id="d0e67-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="d0e67-112">保護虛擬伺服器</span><span class="sxs-lookup"><span data-stu-id="d0e67-112">Securing Virtual Servers</span></span>

<span data-ttu-id="d0e67-113">虛擬伺服器快照包含伺服器資料磁片的複本，也包含記憶體內資料的轉儲，這兩者都可能包含可能會造成攻擊的敏感密碼資料。</span><span class="sxs-lookup"><span data-stu-id="d0e67-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="d0e67-114">針對使用虛擬化而實施的生產伺服器，您應該停用所有的伺服器快照，或以控制的方式進行管理。</span><span class="sxs-lookup"><span data-stu-id="d0e67-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="d0e67-115">如需安全的 Hyper-v 虛擬伺服器的詳細資料，請參閱以下網址的 Hyper-v 安全指南[http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)：。</span><span class="sxs-lookup"><span data-stu-id="d0e67-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="d0e67-116">群組原則</span><span class="sxs-lookup"><span data-stu-id="d0e67-116">Group Policy</span></span>

<span data-ttu-id="d0e67-117">在 Windows Server 2008 和 Windows Server 2008 R2 中，群組原則提供以目錄為基礎的桌面建構管理。</span><span class="sxs-lookup"><span data-stu-id="d0e67-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="d0e67-118">您可以使用群組原則，在群群組原則物件（GPO）中定義電腦和使用者設定，以執行安全性 lockdowns：</span><span class="sxs-lookup"><span data-stu-id="d0e67-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="d0e67-119">以註冊表為基礎的原則</span><span class="sxs-lookup"><span data-stu-id="d0e67-119">Registry-based policies</span></span>

  - <span data-ttu-id="d0e67-120">安全性</span><span class="sxs-lookup"><span data-stu-id="d0e67-120">Security</span></span>

  - <span data-ttu-id="d0e67-121">軟體安裝</span><span class="sxs-lookup"><span data-stu-id="d0e67-121">Software installation</span></span>

  - <span data-ttu-id="d0e67-122">上下</span><span class="sxs-lookup"><span data-stu-id="d0e67-122">Scripts</span></span>

  - <span data-ttu-id="d0e67-123">資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="d0e67-123">Folder redirection</span></span>

  - <span data-ttu-id="d0e67-124">遠端安裝服務</span><span class="sxs-lookup"><span data-stu-id="d0e67-124">Remote installation services</span></span>

<span data-ttu-id="d0e67-125">為了提供管理員設定這些設定的使用者介面，系統會隨附作業系統版本、service pack 發行以及部分應用程式（包括 Lync Server 2013）隨附的系統管理範本。</span><span class="sxs-lookup"><span data-stu-id="d0e67-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="d0e67-126">Communicator .adm 檔案是一個隨附 Lync Server 2013 的系統管理範本，會安裝到% windir%\\inf\\目錄，並提供群組原則設定的介面。</span><span class="sxs-lookup"><span data-stu-id="d0e67-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="d0e67-127">Communicator. adm 中的每個設定都對應到會影響應用程式行為的註冊表中的設定。</span><span class="sxs-lookup"><span data-stu-id="d0e67-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="d0e67-128">您可以從 [Active Directory 使用者和電腦] 主機和 [群組原則管理主控台（GPMC）] 中的 [從 Gpedit.msc] 存取設定。</span><span class="sxs-lookup"><span data-stu-id="d0e67-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="d0e67-129">群組原則安全性設定</span><span class="sxs-lookup"><span data-stu-id="d0e67-129">Group Policy Security Settings</span></span>

<span data-ttu-id="d0e67-130">從 Gpedit.msc 存取 [電腦設定]/[Windows 設定]/[安全性設定] 底下，群組原則包含 GPO 的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="d0e67-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="d0e67-131">您可以匯入安全性範本來設定 GPO 的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="d0e67-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="d0e67-132">Windows Server 2008 安全指南，位於[http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186)與 windows Server 2008 R2 安全性合規性管理工具組[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882)中，其中包含幾個範例範本，您可以修改這些範本來符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="d0e67-132">The Windows Server 2008 Security Guide at [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="d0e67-133">最佳做法</span><span class="sxs-lookup"><span data-stu-id="d0e67-133">Best Practices</span></span>

  - <span data-ttu-id="d0e67-134">強化所有伺服器作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0e67-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="d0e67-135">保護伺服器快照，並增強所有虛擬伺服器的安全性。</span><span class="sxs-lookup"><span data-stu-id="d0e67-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="d0e67-136">使用群組原則來實施安全性 lockdowns。</span><span class="sxs-lookup"><span data-stu-id="d0e67-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

