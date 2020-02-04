---
title: Lync Server 2013：Active Directory 基礎結構需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75278700623ae7251fe7cebec36e959a38f325dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="03cd3-102">Lync Server 2013 的 Active Directory 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="03cd3-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03cd3-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="03cd3-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="03cd3-104">開始準備 Lync Server 2013 的 Active Directory 網域服務的程式之前，請確認您的 Active Directory 基礎結構符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="03cd3-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="03cd3-105">在您部署 Lync Server 的林中，所有網網域控制站（包含所有通用類別目錄伺服器）都可執行下列其中一個作業系統：</span><span class="sxs-lookup"><span data-stu-id="03cd3-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="03cd3-106">Windows Server 2012 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="03cd3-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="03cd3-107">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="03cd3-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="03cd3-108">Windows Server 2008 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="03cd3-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="03cd3-109">Windows Server 2008 作業系統</span><span class="sxs-lookup"><span data-stu-id="03cd3-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="03cd3-110">Windows Server 2008 企業版32位</span><span class="sxs-lookup"><span data-stu-id="03cd3-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="03cd3-111">32位或64位版本的 Windows Server 2003 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="03cd3-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="03cd3-112">32位或64位版本的 Windows Server 2003 作業系統</span><span class="sxs-lookup"><span data-stu-id="03cd3-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="03cd3-113">您在其中部署 Lync Server 的所有網域都會出現在 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows server 2008 或至少 Windows Server 2003 的網域功能層級。</span><span class="sxs-lookup"><span data-stu-id="03cd3-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="03cd3-114">您在其中部署 Lync Server 的林會引發到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能層級。</span><span class="sxs-lookup"><span data-stu-id="03cd3-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03cd3-115">若要變更您的網域或林功能層級，請參閱 TechNet Library 中的「提升網域和林<A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>功能層級」。</span><span class="sxs-lookup"><span data-stu-id="03cd3-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="03cd3-116">全域編目是在您部署 Lync Server 電腦或使用者的每個網域中部署。</span><span class="sxs-lookup"><span data-stu-id="03cd3-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="03cd3-117">Lync Server 2013 支援 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 和 Windows Server 2003 作業系統中的通用群組。</span><span class="sxs-lookup"><span data-stu-id="03cd3-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="03cd3-118">通用群組的成員可以包含網域樹狀結構或林中任何網域的其他群組和帳戶，而且可以在網域樹狀結構或樹林中的任何網域中指派許可權。</span><span class="sxs-lookup"><span data-stu-id="03cd3-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="03cd3-119">通用群組支援，與系統管理員委派結合，簡化 Lync Server 部署的管理。</span><span class="sxs-lookup"><span data-stu-id="03cd3-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="03cd3-120">例如，您不需要將一個網域新增至另一個網域，就能讓系統管理員同時管理兩者。</span><span class="sxs-lookup"><span data-stu-id="03cd3-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

