---
title: Lync Server 2013：適用于 Lync Server 的 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="83774-102">Lync Server 2013 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="83774-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83774-103">_**主題上次修改日期：** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="83774-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="83774-104">Active Directory 網域服務的功能是 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 網路的目錄服務。</span><span class="sxs-lookup"><span data-stu-id="83774-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="83774-105">Active Directory 網域服務也會充當建立 Microsoft Lync Server 2013 安全基礎結構的基礎。</span><span class="sxs-lookup"><span data-stu-id="83774-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="83774-106">本節的目的是說明 Lync Server 2013 如何使用 Active Directory 網域服務來建立 IM、網路會議、媒體及語音的可信環境。</span><span class="sxs-lookup"><span data-stu-id="83774-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="83774-107">如需有關 Active Directory 網域服務的 Lync Server extensions 的詳細資料，以及如何為 Active Directory 網域服務準備您的環境，請參閱在部署檔中[為 Lync server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="83774-108">如需有關 Windows Server 網路中 Active Directory 網域服務角色的詳細資訊，請參閱您所使用之作業系統版本的相關檔。</span><span class="sxs-lookup"><span data-stu-id="83774-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="83774-109">Lync Server 2013 使用 Active Directory 網域服務來儲存：</span><span class="sxs-lookup"><span data-stu-id="83774-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="83774-110">在樹林中執行 Lync Server 2013 的所有伺服器都需要的全域設定。</span><span class="sxs-lookup"><span data-stu-id="83774-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="83774-111">服務資訊，可識別在樹林中執行 Lync Server 2013 的所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="83774-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="83774-112">部分使用者設定。</span><span class="sxs-lookup"><span data-stu-id="83774-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="83774-113">Active Directory 基礎結構</span><span class="sxs-lookup"><span data-stu-id="83774-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="83774-114">Active Directory 的基礎結構需求包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="83774-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="83774-115">網網域控制站的作業系統需求</span><span class="sxs-lookup"><span data-stu-id="83774-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="83774-116">網域和林功能層級需求</span><span class="sxs-lookup"><span data-stu-id="83774-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="83774-117">全域編目網域需求</span><span class="sxs-lookup"><span data-stu-id="83774-117">Global catalog domain requirements</span></span>

<span data-ttu-id="83774-118">如需詳細資訊，請參閱部署檔中[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="83774-119">Active Directory 網域服務準備</span><span class="sxs-lookup"><span data-stu-id="83774-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83774-120">我們建議您將全域設定部署到配置容器，而不是系統容器。</span><span class="sxs-lookup"><span data-stu-id="83774-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="83774-121">這不會增強安全性，但可能會針對某些 Active Directory 網域服務拓撲提供伸縮性改善。</span><span class="sxs-lookup"><span data-stu-id="83774-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="83774-122">如果您是從 Microsoft Office 通訊伺服器2007遷移，且已使用系統容器，但想要使用配置容器，您必須先移動系統容器中的設定，然後才能進行任何升級準備。</span><span class="sxs-lookup"><span data-stu-id="83774-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="83774-123">若要將您的系統容器設定遷移至 [設定] 容器，請參閱 Office 通訊伺服器 2007 <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>全域設定遷移工具，網址為。</span><span class="sxs-lookup"><span data-stu-id="83774-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="83774-124">部署 Lync Server 2013 時，第一個步驟是準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="83774-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="83774-125">為 Lync Server 2013 準備 Active Directory 網域服務的步驟包括下列三個步驟：</span><span class="sxs-lookup"><span data-stu-id="83774-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="83774-126">[**準備架構**]。</span><span class="sxs-lookup"><span data-stu-id="83774-126">**Prepare Schema**.</span></span> <span data-ttu-id="83774-127">此任務會將 Active Directory 網域服務中的架構擴大，以包含 Lync Server 2013 專用的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="83774-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="83774-128">如需準備架構的詳細資料，請參閱在部署檔中執行[Lync Server 2013 中的 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="83774-129">如需詳細資訊，請參閱[從 Office 通訊伺服器 2007 R2 遷移到 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="83774-130">**準備林**。</span><span class="sxs-lookup"><span data-stu-id="83774-130">**Prepare Forest**.</span></span> <span data-ttu-id="83774-131">這個工作會建立目錄林根網域中的全域設定和物件，以及控制存取這些設定和物件的泛型服務和系統管理群組。</span><span class="sxs-lookup"><span data-stu-id="83774-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="83774-132">如需準備林的詳細資料，請參閱在部署檔中[執行 Lync Server 2013 的林準備](lync-server-2013-running-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="83774-133">**準備網域**。</span><span class="sxs-lookup"><span data-stu-id="83774-133">**Prepare Domain**.</span></span> <span data-ttu-id="83774-134">這個工作會將必要的存取控制專案（Ace）新增到通用群組，以授與管理網域中的使用者的許可權。</span><span class="sxs-lookup"><span data-stu-id="83774-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="83774-135">在您想要部署執行 Lync Server 2013 的伺服器以及 Lync Server 使用者所駐留的任何網域時，必須在所有網域中完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="83774-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="83774-136">如需有關準備網域的詳細資訊，請參閱在部署檔中[執行 Lync Server 2013 的網域準備](lync-server-2013-running-domain-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="83774-137">如需有關準備 Active Directory 的完整程式，以及執行每個步驟所需的許可權和許可權，請參閱部署檔中[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="83774-138">通用群組</span><span class="sxs-lookup"><span data-stu-id="83774-138">Universal Groups</span></span>

<span data-ttu-id="83774-139">在準備林期間，Lync Server 2013 會在 Active Directory 網域服務中建立可存取及管理全域設定及服務許可權的各種通用群組。</span><span class="sxs-lookup"><span data-stu-id="83774-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="83774-140">這些通用群組包括：</span><span class="sxs-lookup"><span data-stu-id="83774-140">These universal groups include:</span></span>

  - <span data-ttu-id="83774-141">[系統**管理群組**]。</span><span class="sxs-lookup"><span data-stu-id="83774-141">**Administrative groups**.</span></span> <span data-ttu-id="83774-142">這些群組會定義 Lync Server 網路的基本系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="83774-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="83774-143">在林準備期間，這些系統管理員群組會新增至 Lync Server 基礎結構群組。</span><span class="sxs-lookup"><span data-stu-id="83774-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="83774-144">**服務群組**。</span><span class="sxs-lookup"><span data-stu-id="83774-144">**Service groups**.</span></span> <span data-ttu-id="83774-145">這些群組是用來存取 Lync Server 所提供的各種服務所需的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="83774-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="83774-146">**基礎結構群組**。</span><span class="sxs-lookup"><span data-stu-id="83774-146">**Infrastructure groups**.</span></span> <span data-ttu-id="83774-147">這些群組提供存取 Lync Server 基礎結構特定區域的許可權。</span><span class="sxs-lookup"><span data-stu-id="83774-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="83774-148">它們的功能是系統管理群組的元件，您不應該直接修改它們或直接將使用者新增至其中。</span><span class="sxs-lookup"><span data-stu-id="83774-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="83774-149">在林準備期間，系統會將特定的服務與管理群組新增至適當的基礎結構群組中。</span><span class="sxs-lookup"><span data-stu-id="83774-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="83774-150">如需在準備 Lync Server 的 AD 時所建立的特定通用群組，以及新增至基礎結構群組的服務和管理群組，請參閱在部署檔中的[Lync Server 2013 中所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83774-151">Lync Server 2013 支援執行 Lync Server 2013 之伺服器的 Windows Server 2012 中的通用群組，以及適用于網網域控制站的 Windows Server 2003 作業系統。</span><span class="sxs-lookup"><span data-stu-id="83774-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="83774-152">通用群組的成員可以包含網域樹狀結構或林中任何網域的其他群組和帳戶，而且可以在網域樹狀結構或樹林中的任何網域中指派許可權。</span><span class="sxs-lookup"><span data-stu-id="83774-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="83774-153">通用群組支援，與系統管理員委派結合，簡化 Lync Server 部署的管理。</span><span class="sxs-lookup"><span data-stu-id="83774-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="83774-154">例如，您不需要將一個網域新增至另一個網域，就能讓系統管理員同時管理兩者。</span><span class="sxs-lookup"><span data-stu-id="83774-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="83774-155">以角色為基礎的存取控制</span><span class="sxs-lookup"><span data-stu-id="83774-155">Role-Based Access Control</span></span>

<span data-ttu-id="83774-156">除了建立泛型服務與管理群組，以及將服務和系統管理群組新增至適當的通用群組之外，林準備也會建立以角色為基礎的存取控制（RBAC）群組。</span><span class="sxs-lookup"><span data-stu-id="83774-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="83774-157">如需林準備所建立之特定 RBAC 群組的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="83774-158">如需 RBAC 群組的詳細資訊，請參閱[Lync Server 2013 的角色式存取控制（RBAC）](lync-server-2013-role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="83774-159">存取控制專案（Ace）與繼承</span><span class="sxs-lookup"><span data-stu-id="83774-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="83774-160">林準備會建立私人和公用 Ace，並為它所建立的通用群組新增 Ace。</span><span class="sxs-lookup"><span data-stu-id="83774-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="83774-161">它會在 Lync Server 所使用的全域設定容器上建立特定的專用 Ace。</span><span class="sxs-lookup"><span data-stu-id="83774-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="83774-162">這個容器只能由 Lync Server 使用，且位於配置容器或根網域中的系統容器中，視您儲存全域設定的位置而定。</span><span class="sxs-lookup"><span data-stu-id="83774-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="83774-163">[網域準備] 步驟會將必要的存取控制專案（Ace）新增至通用群組，以便在網域中授與主機及管理使用者的許可權。</span><span class="sxs-lookup"><span data-stu-id="83774-163">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="83774-164">[網域準備] 會在網域根目錄和三個內建容器中建立 Ace：使用者、電腦及網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="83774-164">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="83774-165">如需由林準備及網域準備所建立和新增的公用 Ace 的詳細資料，請參閱[Lync server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)，以及部署檔中[由 lync server 2013 中的網域準備](lync-server-2013-changes-made-by-domain-preparation.md)所做的變更。</span><span class="sxs-lookup"><span data-stu-id="83774-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="83774-166">組織通常會鎖定 Active Directory 網域服務（AD DS），協助減輕安全性風險。</span><span class="sxs-lookup"><span data-stu-id="83774-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="83774-167">不過，鎖定的 Active Directory 環境可以限制 Lync Server 2013 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="83774-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="83774-168">這可能包括從容器和 Ou 中移除 Ace，以及在使用者、連絡人、InetOrgPerson 或電腦物件上停用許可權繼承。</span><span class="sxs-lookup"><span data-stu-id="83774-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="83774-169">在鎖定的 Active Directory 環境中，許可權必須在需要它們的容器和 Ou 上手動設定。</span><span class="sxs-lookup"><span data-stu-id="83774-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="83774-170">如需詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [準備已鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)]。</span><span class="sxs-lookup"><span data-stu-id="83774-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="83774-171">伺服器資訊</span><span class="sxs-lookup"><span data-stu-id="83774-171">Server Information</span></span>

<span data-ttu-id="83774-172">在啟用期間，Lync Server 2013 會將伺服器資訊發佈到 Active Directory 網域服務中的三個下列位置：</span><span class="sxs-lookup"><span data-stu-id="83774-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="83774-173">與安裝 Lync Server 2013 之物理電腦對應的每個 Active Directory 電腦物件上的服務連接點（SCP）。</span><span class="sxs-lookup"><span data-stu-id="83774-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="83774-174">在**MsRTCSIP 池**類別的容器中建立的伺服器物件。</span><span class="sxs-lookup"><span data-stu-id="83774-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="83774-175">在拓撲建立器中指定的信任伺服器。</span><span class="sxs-lookup"><span data-stu-id="83774-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="83774-176">服務連接點</span><span class="sxs-lookup"><span data-stu-id="83774-176">Service Connection Points</span></span>

<span data-ttu-id="83774-177">Active Directory 網域服務中的每個 Lync Server 2013 物件都有一個名為「RTC 服務」的 SCP，該伺服器又包含幾個屬性來識別每個電腦並指定它所提供的服務。</span><span class="sxs-lookup"><span data-stu-id="83774-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="83774-178">*ServiceDNSName*、 *serviceDNSNameType*、 *serviceClassname*和*serviceBindingInformation*等更重要的 SCP 屬性。</span><span class="sxs-lookup"><span data-stu-id="83774-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="83774-179">協力廠商資產管理應用程式可透過查詢這些與其他 SCP 屬性來在整個部署中檢索伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="83774-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="83774-180">Active Directory Server 物件</span><span class="sxs-lookup"><span data-stu-id="83774-180">Active Directory Server Objects</span></span>

<span data-ttu-id="83774-181">每個 Lync Server 2013 伺服器角色都有對應的 Active Directory 物件，其屬性會定義該角色所提供的服務。</span><span class="sxs-lookup"><span data-stu-id="83774-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="83774-182">此外，當您啟用標準版伺服器或建立企業版文件庫時，Lync Server 2013 會在**MsRTCSIP pool**容器中建立新的**msRTCSIP 池**物件。</span><span class="sxs-lookup"><span data-stu-id="83774-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="83774-183">**MsRTCSIP 池**類別指定了池子的完整功能變數名稱（FQDN），以及該池前端與後端元件之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="83774-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="83774-184">（標準版伺服器會被視為在單一電腦上 collocated 其前端和後端的邏輯池）。</span><span class="sxs-lookup"><span data-stu-id="83774-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="83774-185">受信任的伺服器</span><span class="sxs-lookup"><span data-stu-id="83774-185">Trusted Servers</span></span>

<span data-ttu-id="83774-186">在 Lync Server 2013 中，[受信任的伺服器] 是您執行拓撲建立器併發布拓撲時指定的伺服器。</span><span class="sxs-lookup"><span data-stu-id="83774-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="83774-187">已發佈的拓撲（包括所有伺服器資訊）都儲存在中央管理儲存區中。</span><span class="sxs-lookup"><span data-stu-id="83774-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="83774-188">只有在中央管理存儲區中定義的伺服器才是受信任的。</span><span class="sxs-lookup"><span data-stu-id="83774-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="83774-189">在 Lync Server 2013 中，受信任的伺服器是符合下列準則的一種：</span><span class="sxs-lookup"><span data-stu-id="83774-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="83774-190">伺服器的 FQDN 會出現在儲存在中央管理存放區的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="83774-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="83774-191">伺服器會從信任的 CA 中出示有效的憑證。</span><span class="sxs-lookup"><span data-stu-id="83774-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="83774-192">如需詳細資訊，請參閱[Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83774-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="83774-193">如果缺少其中一個準則，則伺服器不受信任，且無法與它連線。</span><span class="sxs-lookup"><span data-stu-id="83774-193">If either of these criteria is missing, the server is not trusted and connection with it is refused.</span></span> <span data-ttu-id="83774-194">這種雙重需求可以避免可能的情況下，惡意伺服器企圖利用有效伺服器的 FQDN 來取得的攻擊。</span><span class="sxs-lookup"><span data-stu-id="83774-194">This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="83774-195">此外，若要啟用 Microsoft Office 通訊伺服器 2007 R2 和 Microsoft Office 通訊伺服器2007部署，以使用 Lync Server 2013 伺服器進行通訊，Lync Server 2013 會在目錄林準備期間建立容器，以保留清單早期版本的受信任伺服器。</span><span class="sxs-lookup"><span data-stu-id="83774-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="83774-196">下表說明為啟用與舊版部署相容性而建立的容器。</span><span class="sxs-lookup"><span data-stu-id="83774-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="83774-197">受信任的伺服器清單及其 Active Directory 容器，以與舊版版本相容</span><span class="sxs-lookup"><span data-stu-id="83774-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83774-198">受信任的伺服器清單</span><span class="sxs-lookup"><span data-stu-id="83774-198">Trusted server list</span></span></th>
<th><span data-ttu-id="83774-199">Active Directory 容器</span><span class="sxs-lookup"><span data-stu-id="83774-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83774-200">標準版伺服器與企業版池前端伺服器</span><span class="sxs-lookup"><span data-stu-id="83774-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="83774-201">RTC 服務/全域設定</span><span class="sxs-lookup"><span data-stu-id="83774-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83774-202">會議服務器</span><span class="sxs-lookup"><span data-stu-id="83774-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="83774-203">RTC 服務/信任的 MCUs</span><span class="sxs-lookup"><span data-stu-id="83774-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83774-204">網頁元件伺服器</span><span class="sxs-lookup"><span data-stu-id="83774-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="83774-205">RTC 服務/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="83774-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83774-206">中繼伺服器與 Communicator Web Access 伺服器、應用程式伺服器、QoE 的註冊機構、A/V 會議服務（也是協力廠商 SIP 伺服器）</span><span class="sxs-lookup"><span data-stu-id="83774-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="83774-207">RTC 服務/受信任的服務</span><span class="sxs-lookup"><span data-stu-id="83774-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83774-208">Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="83774-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="83774-209">Lync Server 2013 不支援 proxy 伺服器的向後相容性</span><span class="sxs-lookup"><span data-stu-id="83774-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83774-210">若要支援舊版版本的信任伺服器，您必須執行最佳做法分析程式工具。</span><span class="sxs-lookup"><span data-stu-id="83774-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="83774-211">如需執行最佳做法分析程式的詳細資訊[http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="83774-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

