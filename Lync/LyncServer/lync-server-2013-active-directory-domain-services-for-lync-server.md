---
title: Lync Server 2013： Lync Server 的 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00038dce85a7461be37456d9dee263a71f60c113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="ec324-102">Lync Server 2013 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="ec324-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec324-103">_**主題上次修改日期：** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="ec324-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="ec324-104">Active Directory 網域服務可做為 Windows Server 2003、Windows Server 2008、Windows Server 2012 及 Windows Server 2012 R2 網路的目錄服務。</span><span class="sxs-lookup"><span data-stu-id="ec324-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="ec324-105">Active Directory 網域服務也充當建立 Microsoft Lync Server 2013 安全性基礎結構的基礎。</span><span class="sxs-lookup"><span data-stu-id="ec324-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="ec324-106">本節的目的是說明 Lync Server 2013 如何使用 Active Directory 網域服務，為 IM、Web 會議、媒體及語音建立信任的環境。</span><span class="sxs-lookup"><span data-stu-id="ec324-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="ec324-107">如需有關 Active Directory 網域服務之 Lync 伺服器擴充功能的詳細資料，以及準備您的環境使用 Active Directory 網域服務，請參閱部署檔中的[準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="ec324-108">如需 Windows Server 網路中之 Active Directory 網域服務角色的詳細資料，請參閱您所使用之作業系統版本的文件。</span><span class="sxs-lookup"><span data-stu-id="ec324-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="ec324-109">Lync Server 2013 使用 Active Directory 網域服務來儲存：</span><span class="sxs-lookup"><span data-stu-id="ec324-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="ec324-110">在樹系中執行 Lync Server 2013 的所有伺服器都需要的全域設定。</span><span class="sxs-lookup"><span data-stu-id="ec324-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="ec324-111">識別樹系中所有執行 Lync Server 2013 之伺服器的角色的服務資訊。</span><span class="sxs-lookup"><span data-stu-id="ec324-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="ec324-112">一些使用者設定。</span><span class="sxs-lookup"><span data-stu-id="ec324-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="ec324-113">Active Directory 基礎結構</span><span class="sxs-lookup"><span data-stu-id="ec324-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="ec324-114">Active Directory 的基礎結構需求如下：</span><span class="sxs-lookup"><span data-stu-id="ec324-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="ec324-115">網域控制站的作業系統需求</span><span class="sxs-lookup"><span data-stu-id="ec324-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="ec324-116">網域和樹系功能等級需求</span><span class="sxs-lookup"><span data-stu-id="ec324-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="ec324-117">通用類別目錄網域需求</span><span class="sxs-lookup"><span data-stu-id="ec324-117">Global catalog domain requirements</span></span>

<span data-ttu-id="ec324-118">如需詳細資訊，請參閱部署檔中的[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="ec324-119">Active Directory 網域服務準備工作</span><span class="sxs-lookup"><span data-stu-id="ec324-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec324-120">建議您將通用設定部署到設定容器，而不要部署到系統容器。</span><span class="sxs-lookup"><span data-stu-id="ec324-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="ec324-121">這樣不會增強安全性，但可以為某些 Active Directory 網域服務拓撲增進延展性。</span><span class="sxs-lookup"><span data-stu-id="ec324-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="ec324-122">如果您是從 Microsoft Office 通訊伺服器2007進行遷移，但已使用系統容器，但計畫使用設定容器，您必須先將設定移至系統容器，再進行任何升級準備。</span><span class="sxs-lookup"><span data-stu-id="ec324-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="ec324-123">若要將系統容器設定遷移至設定容器，請參閱 Office 通訊伺服器2007全域設定遷移工具，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> 。</span><span class="sxs-lookup"><span data-stu-id="ec324-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="ec324-124">部署 Lync Server 2013 時，第一步是準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="ec324-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="ec324-125">準備 Lync Server 2013 的 Active Directory 網域服務包含下列三個步驟：</span><span class="sxs-lookup"><span data-stu-id="ec324-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="ec324-126">**準備架構**。</span><span class="sxs-lookup"><span data-stu-id="ec324-126">**Prepare Schema**.</span></span> <span data-ttu-id="ec324-127">這項工作會延伸 Active Directory 網域服務中的架構，以包含 Lync Server 2013 特有的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="ec324-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="ec324-128">如需準備架構的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中執行 Active Directory 架構準備工作](lync-server-2013-running-schema-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="ec324-129">如需詳細資訊，請參閱[從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="ec324-130">**準備樹**系。</span><span class="sxs-lookup"><span data-stu-id="ec324-130">**Prepare Forest**.</span></span> <span data-ttu-id="ec324-131">這項工作會在樹系根網域中建立通用設定和物件，以及控管這些設定和物件存取權的萬用服務和系統管理群組。</span><span class="sxs-lookup"><span data-stu-id="ec324-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="ec324-132">如需準備樹系的詳細資訊，請參閱部署檔中的對[Lync Server 2013 執行樹系準備工作](lync-server-2013-running-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ec324-133">**準備網域**。</span><span class="sxs-lookup"><span data-stu-id="ec324-133">**Prepare Domain**.</span></span> <span data-ttu-id="ec324-134">這項工作會將必要的存取控制項目 (ACE) 新增至萬用群組，而這些群組會授與權限來裝載和管理網域內的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec324-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="ec324-135">在您想要部署執行 Lync Server 2013 之伺服器的所有網域，以及 Lync Server 使用者所在的任何網域，都必須完成此工作。</span><span class="sxs-lookup"><span data-stu-id="ec324-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="ec324-136">如需有關準備網域的詳細資訊，請參閱部署檔中的[執行 Lync Server 2013 的網域準備工作](lync-server-2013-running-domain-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ec324-137">有關準備 Active Directory 的完整程式，以及執行每個步驟所需的權利和許可權，請參閱部署檔中的[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="ec324-138">萬用群組</span><span class="sxs-lookup"><span data-stu-id="ec324-138">Universal Groups</span></span>

<span data-ttu-id="ec324-139">在準備樹系的過程中，Lync Server 2013 會在 Active Directory 網域服務中建立各種通用群組，而這些群組具有存取及管理全域設定和服務的許可權。</span><span class="sxs-lookup"><span data-stu-id="ec324-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="ec324-140">這些萬用群組包括：</span><span class="sxs-lookup"><span data-stu-id="ec324-140">These universal groups include:</span></span>

  - <span data-ttu-id="ec324-141">**系統管理群組**。</span><span class="sxs-lookup"><span data-stu-id="ec324-141">**Administrative groups**.</span></span> <span data-ttu-id="ec324-142">這些群組會定義 Lync Server 網路的基本系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="ec324-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="ec324-143">樹系準備過程中，會將這些系統管理員群組新增至 Lync Server 基礎結構群組。</span><span class="sxs-lookup"><span data-stu-id="ec324-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="ec324-144">**服務群組**。</span><span class="sxs-lookup"><span data-stu-id="ec324-144">**Service groups**.</span></span> <span data-ttu-id="ec324-145">這些群組是存取 Lync Server 所提供之各種服務所需的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="ec324-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="ec324-146">**基礎結構群組**。</span><span class="sxs-lookup"><span data-stu-id="ec324-146">**Infrastructure groups**.</span></span> <span data-ttu-id="ec324-147">這些群組提供訪問 Lync Server 基礎結構特定區域的許可權。</span><span class="sxs-lookup"><span data-stu-id="ec324-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="ec324-148">其功能就如系統管理群組的元件，因此您不應修改這些群組或直接將使用者新增到其中。</span><span class="sxs-lookup"><span data-stu-id="ec324-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="ec324-149">在樹系準備過程中，會將特定服務和管理群組新增至適當的基礎結構群組。</span><span class="sxs-lookup"><span data-stu-id="ec324-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="ec324-150">如需在準備 Lync Server 的 AD 時所建立之特定通用群組的詳細資訊，以及新增至基礎結構群組的服務和管理群組，請參閱部署檔中的[Lync Server 2013 中的樹系準備所進行的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec324-151">Lync Server 2013 支援 Windows Server 2012 中執行 Lync Server 2013 之伺服器的通用群組，以及網域控制站的 Windows Server 2003 作業系統。</span><span class="sxs-lookup"><span data-stu-id="ec324-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="ec324-152">萬用群組的成員可以包含網域樹或樹系中任何網域的其他群組和帳戶，而且可以將網域樹或樹系中任何網域的權限指派給它。</span><span class="sxs-lookup"><span data-stu-id="ec324-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="ec324-153">通用群組支援（結合系統管理員委派）可簡化 Lync Server 部署的管理。</span><span class="sxs-lookup"><span data-stu-id="ec324-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="ec324-154">例如，不需要為了讓系統管理員能夠同時管理兩個網域，而將某個網域加入另一個網域。</span><span class="sxs-lookup"><span data-stu-id="ec324-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="ec324-155">角色型存取控制</span><span class="sxs-lookup"><span data-stu-id="ec324-155">Role-Based Access Control</span></span>

<span data-ttu-id="ec324-156">除了建立泛型服務和管理群組，以及將服務和系統管理群組新增至適當的通用群組以外，樹系準備也會建立 Role-Based 的存取控制 (RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="ec324-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="ec324-157">如需「樹系準備」所建立之特定 RBAC 群組的詳細資訊，請參閱部署檔中的[Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md)中的「樹系準備」所做的變更。</span><span class="sxs-lookup"><span data-stu-id="ec324-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="ec324-158">如需 RBAC 群組的詳細資訊，請參閱[以角色為基礎的存取控制 (Lync Server 2013 的 RBAC) ](lync-server-2013-role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="ec324-159">存取控制項目 (ACE) 及繼承</span><span class="sxs-lookup"><span data-stu-id="ec324-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="ec324-160">樹系準備會同時建立私人與公用 ACE，並針對其建立的萬用群組新增 ACE。</span><span class="sxs-lookup"><span data-stu-id="ec324-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="ec324-161">它會在 Lync Server 所使用的全域設定容器上建立特定的專用 Ace。</span><span class="sxs-lookup"><span data-stu-id="ec324-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="ec324-162">這個容器只會由 Lync Server 使用，而且可以位於設定容器或根域的系統容器中，視您儲存全域設定的位置而定。</span><span class="sxs-lookup"><span data-stu-id="ec324-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="ec324-p114">網域準備步驟會將必要的存取控制項目 (ACE) 新增至萬用群組，而這些群組會授與權限來裝載和管理網域內的使用者。網域準備作業會在網域根目錄和三個內建容器上建立 ACE：使用者、電腦和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="ec324-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="ec324-165">如需由樹系準備和網域準備所建立及新增之公用 Ace 的詳細資訊，請參閱在「lync server 2013」中的[樹系準備工作中所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)，以及部署檔中的[lync server 2013](lync-server-2013-changes-made-by-domain-preparation.md)中所做的變更。</span><span class="sxs-lookup"><span data-stu-id="ec324-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ec324-166">組織經常會鎖定 Active Directory 網域服務 (AD DS)，以減低安全性風險。</span><span class="sxs-lookup"><span data-stu-id="ec324-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="ec324-167">不過，鎖定的 Active Directory 環境可以限制 Lync Server 2013 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="ec324-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="ec324-168">其中包括從容器和 OU 移除 ACE，以及停用 User、Contact、InetOrgPerson 或 Computer 物件的權限繼承。</span><span class="sxs-lookup"><span data-stu-id="ec324-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="ec324-169">在鎖定的 Active Directory 環境中，必須在需要權限的容器和 OU 上手動設定權限。</span><span class="sxs-lookup"><span data-stu-id="ec324-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="ec324-170">如需詳細資訊，請參閱部署檔中的在[Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="ec324-171">伺服器資訊</span><span class="sxs-lookup"><span data-stu-id="ec324-171">Server Information</span></span>

<span data-ttu-id="ec324-172">在啟用期間，Lync Server 2013 會將伺服器資訊發佈至 Active Directory 網域服務中的三個下列位置：</span><span class="sxs-lookup"><span data-stu-id="ec324-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="ec324-173">與安裝 Lync Server 2013 之實體電腦對應之每個 Active Directory 電腦物件上的服務連線點 (SCP) 。</span><span class="sxs-lookup"><span data-stu-id="ec324-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="ec324-174">**msRTCSIP-Pools** 類別容器中建立的伺服器物件。</span><span class="sxs-lookup"><span data-stu-id="ec324-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="ec324-175">拓撲產生器中指定的受信任伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec324-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="ec324-176">服務連線點</span><span class="sxs-lookup"><span data-stu-id="ec324-176">Service Connection Points</span></span>

<span data-ttu-id="ec324-177">Active Directory 網域服務中的每個 Lync Server 2013 物件都有一個名為 RTC 服務的 SCP，該 SCP 又包含一些屬性，用以識別每一部電腦並指定其所提供的服務。</span><span class="sxs-lookup"><span data-stu-id="ec324-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="ec324-178">其中較重要的 SCP 屬性包括 *serviceDNSName*、*serviceDNSNameType*、*serviceClassname* 和 *serviceBindingInformation*。</span><span class="sxs-lookup"><span data-stu-id="ec324-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="ec324-179">協力廠商資產管理應用程式可以透過查詢 SCP 屬性，在部署中擷取伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="ec324-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="ec324-180">Active Directory 伺服器物件</span><span class="sxs-lookup"><span data-stu-id="ec324-180">Active Directory Server Objects</span></span>

<span data-ttu-id="ec324-181">每個 Lync Server 2013 伺服器角色都有對應的 Active Directory 物件，其屬性可定義該角色所提供的服務。</span><span class="sxs-lookup"><span data-stu-id="ec324-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="ec324-182">此外，啟用 Standard Edition server 或建立 Enterprise Edition 集區時，Lync Server 2013 會在**msRTCSIP-Pools**容器中建立新的**msRTCSIP 集**區物件。</span><span class="sxs-lookup"><span data-stu-id="ec324-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="ec324-183">**msRTCSIP-Pool** 類別會指定集區的完整網域名稱 (FQDN)，以及集區前端和後端元件之間的關聯性。</span><span class="sxs-lookup"><span data-stu-id="ec324-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="ec324-184">Standard Edition 伺服器會視為邏輯集區，其前端和後端會配置在同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="ec324-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="ec324-185">受信任伺服器</span><span class="sxs-lookup"><span data-stu-id="ec324-185">Trusted Servers</span></span>

<span data-ttu-id="ec324-186">在 Lync Server 2013 中，受信任的伺服器是執行拓撲產生器和發行拓撲時所指定的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec324-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="ec324-187">發行的拓撲 (包括所有伺服器資訊) 會儲存在中央管理存放區中。</span><span class="sxs-lookup"><span data-stu-id="ec324-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="ec324-188">只有定義在中央管理存放區中的伺服器會受信任。</span><span class="sxs-lookup"><span data-stu-id="ec324-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="ec324-189">在 Lync Server 2013 中，信任的伺服器是符合下列條件的伺服器：</span><span class="sxs-lookup"><span data-stu-id="ec324-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="ec324-190">伺服器的 FQDN 出現在儲存於中央管理存放區的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="ec324-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="ec324-191">伺服器顯示來自受信任 CA 的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="ec324-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="ec324-192">如需詳細資訊，請參閱[Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec324-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="ec324-p120">如果不符合這些條件，則伺服器就不受信任，其連線也會遭拒。這項雙重需求能避免惡意伺服器嘗試佔用有效伺服器 FQDN 的可能 (即使不太可能) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="ec324-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="ec324-195">此外，若要啟用 Microsoft Office 通訊伺服器 2007 R2 和 Microsoft Office 通訊伺服器2007部署，以與 Lync Server 2013 伺服器通訊，Lync Server 2013 會在樹系準備期間建立容器，以存放舊版版本的信任伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="ec324-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="ec324-196">下表說明為與舊版部署相容而建立的容器。</span><span class="sxs-lookup"><span data-stu-id="ec324-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="ec324-197">為與舊版相容的受信任伺服器清單及其 Active Directory 容器</span><span class="sxs-lookup"><span data-stu-id="ec324-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec324-198">受信任的伺服器清單</span><span class="sxs-lookup"><span data-stu-id="ec324-198">Trusted server list</span></span></th>
<th><span data-ttu-id="ec324-199">Active Directory 容器</span><span class="sxs-lookup"><span data-stu-id="ec324-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec324-200">Standard Edition 伺服器和 Enterprise 集區前端伺服器</span><span class="sxs-lookup"><span data-stu-id="ec324-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ec324-201">RTC 服務/通用設定</span><span class="sxs-lookup"><span data-stu-id="ec324-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec324-202">會議伺服器</span><span class="sxs-lookup"><span data-stu-id="ec324-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="ec324-203">RTC 服務/信任的 MCU</span><span class="sxs-lookup"><span data-stu-id="ec324-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec324-204">Web 元件伺服器</span><span class="sxs-lookup"><span data-stu-id="ec324-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="ec324-205">RTC 服務/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="ec324-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec324-206">中繼伺服器及 Communicator Web Access Server、應用程式伺服器、含 QoE 的登錄器、A/V 會議服務 (還有協力廠商 SIP 伺服器)</span><span class="sxs-lookup"><span data-stu-id="ec324-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="ec324-207">RTC 服務/信任的服務</span><span class="sxs-lookup"><span data-stu-id="ec324-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec324-208">Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="ec324-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="ec324-209">Lync Server 2013 不支援 proxy 伺服器的回溯相容性</span><span class="sxs-lookup"><span data-stu-id="ec324-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ec324-210">若要支援先前版本的信任伺服器，您必須執行最佳作法分析工具。</span><span class="sxs-lookup"><span data-stu-id="ec324-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="ec324-211">如需執行最佳做法分析程式的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) 。</span><span class="sxs-lookup"><span data-stu-id="ec324-211">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

