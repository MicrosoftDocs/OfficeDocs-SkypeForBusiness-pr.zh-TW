---
title: Lync Server 2013： Active Directory 基礎結構需求
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
ms.openlocfilehash: 46435a3683465c1e31406e46181df8ffa069615e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529610"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="e3a64-102">Lync Server 2013 的 Active Directory 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="e3a64-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3a64-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e3a64-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e3a64-104">在開始準備 Lync Server 2013 的 Active Directory 網域服務的程式之前，請確定您的 Active Directory 基礎結構符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="e3a64-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="e3a64-105">所有的網域控制站 (包含您部署 Lync Server 之樹系中的所有通用類別目錄伺服器) ，請執行下列其中一個作業系統：</span><span class="sxs-lookup"><span data-stu-id="e3a64-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="e3a64-106">Windows Server 2012 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="e3a64-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="e3a64-107">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="e3a64-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="e3a64-108">Windows Server 2008 R2 operating system</span><span class="sxs-lookup"><span data-stu-id="e3a64-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="e3a64-109">Windows Server 2008 作業系統</span><span class="sxs-lookup"><span data-stu-id="e3a64-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="e3a64-110">Windows Server 2008 Enterprise 32-位</span><span class="sxs-lookup"><span data-stu-id="e3a64-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="e3a64-111">32位或64位版本的 Windows Server 2003 R2 作業系統</span><span class="sxs-lookup"><span data-stu-id="e3a64-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="e3a64-112">32位或64位版本的 Windows Server 2003 作業系統</span><span class="sxs-lookup"><span data-stu-id="e3a64-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="e3a64-113">所有部署 Lync Server 的網域都會引發為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的網域功能等級。</span><span class="sxs-lookup"><span data-stu-id="e3a64-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="e3a64-114">您部署 Lync Server 的樹系會引發為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的樹系功能層級。</span><span class="sxs-lookup"><span data-stu-id="e3a64-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3a64-115">若要變更您的網域或樹系功能等級，請參閱 TechNet 文件庫中的「提升網域和樹系功能等級」 <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> 。</span><span class="sxs-lookup"><span data-stu-id="e3a64-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="e3a64-116">在每個部署 Lync Server 電腦或使用者的網域中部署通用類別目錄。</span><span class="sxs-lookup"><span data-stu-id="e3a64-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="e3a64-117">Lync Server 2013 支援 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 及 Windows Server 2003 作業系統中的通用群組。</span><span class="sxs-lookup"><span data-stu-id="e3a64-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="e3a64-118">萬用群組的成員可以包含網域樹或樹系中任何網域的其他群組和帳戶，而且可以將網域樹或樹系中任何網域的權限指派給它。</span><span class="sxs-lookup"><span data-stu-id="e3a64-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="e3a64-119">通用群組支援（結合系統管理員委派）可簡化 Lync Server 部署的管理。</span><span class="sxs-lookup"><span data-stu-id="e3a64-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="e3a64-120">例如，不需要為了讓系統管理員能夠同時管理兩個網域，而將某個網域加入另一個網域。</span><span class="sxs-lookup"><span data-stu-id="e3a64-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

