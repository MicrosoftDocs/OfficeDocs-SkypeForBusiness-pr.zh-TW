---
title: Lync Server 2013： Active Directory 網域服務支援
description: Lync Server 2013： Active Directory 網域服務支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558679"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="b983b-103">Lync Server 2013 中的 Active Directory 網域服務支援</span><span class="sxs-lookup"><span data-stu-id="b983b-103">Active Directory Domain Services support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b983b-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b983b-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b983b-105">Lync Server 2013 使用中央管理存放區來儲存伺服器和服務的設定資料，而不是像過去這樣的資訊，而不是依賴此資訊的 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="b983b-105">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="b983b-106">Lync Server 2013 仍會在 AD DS 中儲存下列專案：</span><span class="sxs-lookup"><span data-stu-id="b983b-106">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="b983b-107">**架構擴充**</span><span class="sxs-lookup"><span data-stu-id="b983b-107">**Schema extensions**</span></span>
    
      - <span data-ttu-id="b983b-108">使用者物件擴充</span><span class="sxs-lookup"><span data-stu-id="b983b-108">User object extensions</span></span>
    
      - <span data-ttu-id="b983b-109">Lync Server 2010 和 Office 通訊伺服器 2007 R2 類別的延伸部分，以維護與舊版支援版本的回溯相容性</span><span class="sxs-lookup"><span data-stu-id="b983b-109">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="b983b-110">儲存在 Lync Server 2013 擴充架構和現有類別中的**資料** () </span><span class="sxs-lookup"><span data-stu-id="b983b-110">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="b983b-111">使用者 SIP URI 及其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="b983b-111">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="b983b-112">應用程式的連絡人物件 (例如，回應群組應用程式和會議助理應用程式) </span><span class="sxs-lookup"><span data-stu-id="b983b-112">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="b983b-113">為回溯相容性發佈的資料</span><span class="sxs-lookup"><span data-stu-id="b983b-113">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="b983b-114">中央管理存放區 (SCP) 的服務控制點</span><span class="sxs-lookup"><span data-stu-id="b983b-114">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="b983b-115">Kerberos 驗證帳戶 (選用的電腦物件) </span><span class="sxs-lookup"><span data-stu-id="b983b-115">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="b983b-116">本節說明 Lync Server 2013 的 AD DS 支援需求。</span><span class="sxs-lookup"><span data-stu-id="b983b-116">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="b983b-117">如需拓撲支援的詳細資訊，請參閱支援檔中的 [支援的 Active Directory 拓撲（Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) ）。</span><span class="sxs-lookup"><span data-stu-id="b983b-117">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="b983b-118">支援的網域控制站作業系統</span><span class="sxs-lookup"><span data-stu-id="b983b-118">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="b983b-119">Lync Server 2013 支援執行下列作業系統的網域控制站：</span><span class="sxs-lookup"><span data-stu-id="b983b-119">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="b983b-120">Windows Server 2012 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="b983b-120">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="b983b-121">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="b983b-121">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="b983b-122">Windows Server 2008 R2 operating system</span><span class="sxs-lookup"><span data-stu-id="b983b-122">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="b983b-123">Windows Server 2008 作業系統</span><span class="sxs-lookup"><span data-stu-id="b983b-123">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="b983b-124">Windows Server 2008 Enterprise 32-位</span><span class="sxs-lookup"><span data-stu-id="b983b-124">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="b983b-125">32位或64位版本的 Windows Server 2003 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="b983b-125">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="b983b-126">32位或64位版本的 Windows Server 2003 作業系統</span><span class="sxs-lookup"><span data-stu-id="b983b-126">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="b983b-127">樹系和網域功能等級</span><span class="sxs-lookup"><span data-stu-id="b983b-127">Forest and Domain Functional Level</span></span>

<span data-ttu-id="b983b-128">您必須將您部署 Lync Server 2013 的所有網域，都提升為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的網域功能等級。</span><span class="sxs-lookup"><span data-stu-id="b983b-128">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="b983b-129">您部署 Lync Server 2013 的所有樹系都必須引發為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的樹系功能等級。</span><span class="sxs-lookup"><span data-stu-id="b983b-129">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="b983b-130">Read-Only 網域控制站的支援</span><span class="sxs-lookup"><span data-stu-id="b983b-130">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="b983b-131">Lync Server 2013 支援包含唯讀網域控制站或唯讀通用類別目錄伺服器的 Active Directory 網域服務部署（只要有可用的可寫入網域控制站）。</span><span class="sxs-lookup"><span data-stu-id="b983b-131">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="b983b-132">功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="b983b-132">Domain Names</span></span>

<span data-ttu-id="b983b-133">Lync Server 不支援單一標示的網域。</span><span class="sxs-lookup"><span data-stu-id="b983b-133">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="b983b-134">例如，根網域名稱為 **contoso.local** 的樹系是受支援的，名為 **local** 的根網域則不受支援。</span><span class="sxs-lookup"><span data-stu-id="b983b-134">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="b983b-135">如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「如何針對具有單一標籤 DNS 名稱的網域設定 Windows」的相關資訊」 [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) 。</span><span class="sxs-lookup"><span data-stu-id="b983b-135">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b983b-136">Lync Server 不支援重新命名網域。</span><span class="sxs-lookup"><span data-stu-id="b983b-136">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="b983b-137">如果您需要重新命名已部署 Lync Server 的網域，您必須先卸載 Lync Server，然後重新命名網域，然後重新安裝 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b983b-137">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="b983b-138">鎖定的 AD DS 環境</span><span class="sxs-lookup"><span data-stu-id="b983b-138">Locked Down AD DS Environments</span></span>

<span data-ttu-id="b983b-139">在鎖定的 AD DS 環境中，使用者和電腦物件通常會放在特定的組織單位中 () Ou 中，以停用許可權繼承，以協助保護系統管理委派及啟用群組原則物件 (Gpo) 的使用，以強制執行安全性原則。</span><span class="sxs-lookup"><span data-stu-id="b983b-139">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="b983b-140">Lync Server 2013 可部署在鎖定的 Active Directory 環境中。</span><span class="sxs-lookup"><span data-stu-id="b983b-140">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="b983b-141">如需在鎖定環境中部署 Lync Server 所需之專案的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="b983b-141">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

