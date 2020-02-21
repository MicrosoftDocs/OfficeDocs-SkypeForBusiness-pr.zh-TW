---
title: 'Lync Server 2013: Active Directory 網域服務支援'
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
ms.openlocfilehash: 8bee58b0a35d2a3a322d799f2aadc9ba3b9c1bd9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="ca15d-102">Lync Server 2013 中的 active Directory 網域服務支援</span><span class="sxs-lookup"><span data-stu-id="ca15d-102">Active Directory Domain Services support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca15d-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="ca15d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ca15d-104">Lync Server 2013 使用的中央管理存放區來儲存伺服器和服務，而不要依賴此資訊，如同在過去的 Active Directory 網域服務的組態資料。</span><span class="sxs-lookup"><span data-stu-id="ca15d-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="ca15d-105">Lync Server 2013 仍然會儲存在 AD DS 中的下列：</span><span class="sxs-lookup"><span data-stu-id="ca15d-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="ca15d-106">**架構延伸模組**</span><span class="sxs-lookup"><span data-stu-id="ca15d-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="ca15d-107">使用者物件延伸</span><span class="sxs-lookup"><span data-stu-id="ca15d-107">User object extensions</span></span>
    
      - <span data-ttu-id="ca15d-108">Lync Server 2010 和 Office Communications Server 2007 R2 類別，以維持與舊版回溯相容性的延伸支援的版本</span><span class="sxs-lookup"><span data-stu-id="ca15d-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="ca15d-109">**資料**（儲存在 Lync Server 2013 延伸架構和現有類別中）</span><span class="sxs-lookup"><span data-stu-id="ca15d-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="ca15d-110">使用者的 SIP URI 和其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="ca15d-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="ca15d-111">應用程式 （例如，回應群組應用程式與會議服務員應用程式） 的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="ca15d-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="ca15d-112">發行的回溯相容性資料</span><span class="sxs-lookup"><span data-stu-id="ca15d-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="ca15d-113">服務控制點 (SCP) 的中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="ca15d-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="ca15d-114">Kerberos 驗證帳戶 （選擇性的電腦物件）</span><span class="sxs-lookup"><span data-stu-id="ca15d-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="ca15d-115">本節說明 Lync Server 2013 的 AD DS 支援需求。</span><span class="sxs-lookup"><span data-stu-id="ca15d-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="ca15d-116">如需詳細資訊的拓樸的相關支援，請參閱支援文件中的[Lync Server 2013 中支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="ca15d-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="ca15d-117">支援的網域控制站作業系統</span><span class="sxs-lookup"><span data-stu-id="ca15d-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="ca15d-118">Lync Server 2013 支援執行下列作業系統的網域控制站：</span><span class="sxs-lookup"><span data-stu-id="ca15d-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="ca15d-119">Windows Server 2012 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="ca15d-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="ca15d-120">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="ca15d-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="ca15d-121">Windows Server 2008 R2 operating system</span><span class="sxs-lookup"><span data-stu-id="ca15d-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="ca15d-122">Windows Server 2008 作業系統</span><span class="sxs-lookup"><span data-stu-id="ca15d-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="ca15d-123">Windows Server 2008 Enterprise 32 位元</span><span class="sxs-lookup"><span data-stu-id="ca15d-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="ca15d-124">32 位元或 64 位元版本的 Window Server 2003 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="ca15d-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="ca15d-125">32 位元或 64 位元版本的 Windows Server 2003 作業系統</span><span class="sxs-lookup"><span data-stu-id="ca15d-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="ca15d-126">樹系和網域功能等級</span><span class="sxs-lookup"><span data-stu-id="ca15d-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="ca15d-127">您必須提高您將 Lync Server 2013 部署至 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008] 或是在網域功能等級的所有網域最低的 Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="ca15d-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="ca15d-128">您將部署 Lync Server 2013 的所有樹系必須引發為 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008] 或是在樹系功能等級最低的 Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="ca15d-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="ca15d-129">支援唯讀網域控制站</span><span class="sxs-lookup"><span data-stu-id="ca15d-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="ca15d-130">Lync Server 2013 支援包含唯讀網域控制站或唯讀通用類別目錄伺服器的 Active Directory 網域服務部署，只要有可用的可寫入的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="ca15d-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="ca15d-131">網域名稱</span><span class="sxs-lookup"><span data-stu-id="ca15d-131">Domain Names</span></span>

<span data-ttu-id="ca15d-132">Lync Server 不支援單一標示的網域。</span><span class="sxs-lookup"><span data-stu-id="ca15d-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="ca15d-133">例如，根網域名稱為 **contoso.local** 的樹系是受支援的，名為 **local** 的根網域則不受支援。</span><span class="sxs-lookup"><span data-stu-id="ca15d-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="ca15d-134">如需詳細資訊，請參閱 Microsoft 知識庫文章 300684，「 設定資訊視窗具有單一標籤 DNS 名稱的網域 」， [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752)。</span><span class="sxs-lookup"><span data-stu-id="ca15d-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca15d-135">Lync Server 不支援重新命名的網域。</span><span class="sxs-lookup"><span data-stu-id="ca15d-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="ca15d-136">如果您需要重新命名其中部署 Lync Server 的網域，您需要先解除安裝 Lync Server]，然後重新命名網域，並再重新安裝 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="ca15d-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="ca15d-137">鎖定 AD DS 環境</span><span class="sxs-lookup"><span data-stu-id="ca15d-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="ca15d-138">在鎖定的 AD DS 環境中，User 及 Computer 物件通常會放在特定組織單位 (Ou) 中停用來協助保護系統管理委派，並啟用使用群組原則物件 (Gpo) 強制執行權限繼承安全性原則。</span><span class="sxs-lookup"><span data-stu-id="ca15d-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="ca15d-139">可以在鎖定的 Active Directory 環境中部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ca15d-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="ca15d-140">如需什麼是必要鎖定的環境中部署 Lync Server 的詳細資訊，請參閱部署文件中的[準備鎖定的 Active Directory 網域服務在 Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="ca15d-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

