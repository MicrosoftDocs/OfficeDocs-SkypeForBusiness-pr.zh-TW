---
title: Lync Server 2013：Active Directory 網域服務支援
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
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="889fc-102">Lync Server 2013 中的 Active Directory 網域服務支援</span><span class="sxs-lookup"><span data-stu-id="889fc-102">Active Directory Domain Services support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="889fc-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="889fc-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="889fc-104">Lync Server 2013 使用中央管理儲存區來儲存伺服器與服務的設定資料，而不是依賴 Active Directory 網域服務來取得此資訊，就像過去的情況。</span><span class="sxs-lookup"><span data-stu-id="889fc-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="889fc-105">Lync Server 2013 仍會在 AD DS 中儲存下列專案：</span><span class="sxs-lookup"><span data-stu-id="889fc-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="889fc-106">**架構延伸**</span><span class="sxs-lookup"><span data-stu-id="889fc-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="889fc-107">使用者物件延伸</span><span class="sxs-lookup"><span data-stu-id="889fc-107">User object extensions</span></span>
    
      - <span data-ttu-id="889fc-108">Lync Server 2010 和 Office 通訊伺服器 2007 R2 類別的延伸，以維持與舊版支援版本的向後相容性</span><span class="sxs-lookup"><span data-stu-id="889fc-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="889fc-109">**資料**（儲存在 Lync Server 2013 延伸架構和現有的類別中）</span><span class="sxs-lookup"><span data-stu-id="889fc-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="889fc-110">使用者 SIP URI 和其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="889fc-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="889fc-111">應用程式的連絡人物件（例如，回應群組應用程式與會議助理應用程式）</span><span class="sxs-lookup"><span data-stu-id="889fc-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="889fc-112">針對向後相容性發佈的資料</span><span class="sxs-lookup"><span data-stu-id="889fc-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="889fc-113">中央管理儲存體的服務控制點（SCP）</span><span class="sxs-lookup"><span data-stu-id="889fc-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="889fc-114">Kerberos 驗證帳戶（選擇性電腦物件）</span><span class="sxs-lookup"><span data-stu-id="889fc-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="889fc-115">本節說明 Lync Server 2013 的 AD DS 支援需求。</span><span class="sxs-lookup"><span data-stu-id="889fc-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="889fc-116">如需拓撲支援的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="889fc-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="889fc-117">支援的網網域控制站作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="889fc-118">Lync Server 2013 支援執行下列作業系統的網網域控制站：</span><span class="sxs-lookup"><span data-stu-id="889fc-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="889fc-119">Windows Server 2012 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="889fc-120">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="889fc-121">Windows Server 2008 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="889fc-122">Windows Server 2008 作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="889fc-123">Windows Server 2008 企業版32位</span><span class="sxs-lookup"><span data-stu-id="889fc-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="889fc-124">32位或64位版本的 Window Server 2003 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="889fc-125">32位或64位版本的 Windows Server 2003 作業系統</span><span class="sxs-lookup"><span data-stu-id="889fc-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="889fc-126">林及網域功能層級</span><span class="sxs-lookup"><span data-stu-id="889fc-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="889fc-127">您必須將您將 Lync Server 2013 部署至 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的網域功能層級的所有網域。</span><span class="sxs-lookup"><span data-stu-id="889fc-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="889fc-128">您在其中部署 Lync Server 2013 的所有林都必須在 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能層級引發。</span><span class="sxs-lookup"><span data-stu-id="889fc-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="889fc-129">支援唯讀網網域控制站</span><span class="sxs-lookup"><span data-stu-id="889fc-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="889fc-130">Lync Server 2013 支援包括唯讀網網域控制站或唯讀通用類別目錄伺服器的 Active Directory 網域服務部署，只要有可寫入的網網域控制站可用。</span><span class="sxs-lookup"><span data-stu-id="889fc-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="889fc-131">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="889fc-131">Domain Names</span></span>

<span data-ttu-id="889fc-132">Lync Server 不支援單一標示的網域。</span><span class="sxs-lookup"><span data-stu-id="889fc-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="889fc-133">例如，支援名為**contoso. local**的根網域的林，但不支援名為**local**的根網域。</span><span class="sxs-lookup"><span data-stu-id="889fc-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="889fc-134">如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「使用單標籤 DNS 名稱設定 Windows 網域的相關資訊」 [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)。</span><span class="sxs-lookup"><span data-stu-id="889fc-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="889fc-135">Lync Server 不支援重新命名網域。</span><span class="sxs-lookup"><span data-stu-id="889fc-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="889fc-136">如果您需要重新命名部署 Lync Server 的網域，您必須先卸載 Lync Server，然後重新命名網域，然後重新安裝 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="889fc-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="889fc-137">已鎖定 AD DS 環境</span><span class="sxs-lookup"><span data-stu-id="889fc-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="889fc-138">在鎖定的 AD DS 環境中，使用者和電腦物件通常是以停用許可權繼承的特定組織單位（Ou）來進行，以協助保護系統管理委派，並允許使用群組原則物件（Gpo）強制執行安全性原則。</span><span class="sxs-lookup"><span data-stu-id="889fc-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="889fc-139">Lync Server 2013 可以在鎖定的 Active Directory 環境中部署。</span><span class="sxs-lookup"><span data-stu-id="889fc-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="889fc-140">如需有關在鎖定環境中部署 Lync Server 所需功能的詳細資訊，請參閱部署檔中的[Lync server 2013 中的 [準備已鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)]。</span><span class="sxs-lookup"><span data-stu-id="889fc-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

