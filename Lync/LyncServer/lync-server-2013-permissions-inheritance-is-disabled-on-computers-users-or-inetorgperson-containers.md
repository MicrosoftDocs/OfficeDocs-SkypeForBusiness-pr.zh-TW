---
title: Lync Server 2013：已在電腦、使用者或 InetOrgPerson 容器上停用許可權繼承
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd6e20c510c1a26b3fc367c853d08469798ff765
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524320"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="ebec4-102">已停用 Lync Server 2013 中電腦、使用者或 InetOrgPerson 容器的許可權繼承</span><span class="sxs-lookup"><span data-stu-id="ebec4-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebec4-103">_**主題上次修改日期：** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="ebec4-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="ebec4-104">在鎖定的 Active Directory 網域服務中，使用者和電腦物件通常會放在特定的組織單位中 () Ou 中，以停用許可權繼承，以協助保護系統管理委派，並啟用群組原則物件 (Gpo) 以強制執行安全性原則。</span><span class="sxs-lookup"><span data-stu-id="ebec4-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="ebec4-105">網域準備和伺服器啟用設定 (Ace) Lync Server 2013 所需的存取控制專案。</span><span class="sxs-lookup"><span data-stu-id="ebec4-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="ebec4-106">當停用許可權繼承時，Lync Server 安全性群組無法繼承這些 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="ebec4-107">當這些許可權不是繼承時，Lync Server 安全性群組無法存取設定，而且會出現下列兩個問題：</span><span class="sxs-lookup"><span data-stu-id="ebec4-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="ebec4-108">若要管理使用者、Inetorgperson 及連絡人，以及執行伺服器，Lync Server 安全性群組需要每個使用者之屬性集的網域準備程式設定 Ace、即時通訊 (RTC) 、RTC 使用者搜尋和公用資訊。</span><span class="sxs-lookup"><span data-stu-id="ebec4-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="ebec4-109">當停用許可權繼承時，安全性群組不會繼承這些 Ace，而且無法管理伺服器或使用者。</span><span class="sxs-lookup"><span data-stu-id="ebec4-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="ebec4-110">若要探索伺服器及集區，執行 Lync Server 的伺服器依賴于電腦相關物件（包括 Microsoft 容器和伺服器物件）上的啟動所設定的 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="ebec4-111">當停用許可權繼承時，安全性群組、伺服器及集區不會繼承這些 Ace，而且不能利用這些 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="ebec4-112">若要解決這些問題，Lync Server 會提供 **Grant-CsOuPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebec4-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="ebec4-113">這個 Cmdlet 會直接在指定的容器和組織單位上，以及容器或組織單位中的物件設定必要的 Lync Server Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="ebec4-114">在執行網域準備作業之後設定使用者、InetOrgPerson 及連絡人物件的許可權</span><span class="sxs-lookup"><span data-stu-id="ebec4-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="ebec4-115">在已停用許可權繼承的鎖定 Active Directory 環境中，網域準備不會在使用者或網域中的使用者或 InetOrgPerson 物件所在的容器或組織單位上，設定必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="ebec4-116">在此情況下，您必須在具有已停用許可權繼承的使用者或 InetOrgPerson 物件的每個容器或 OU 上執行 **Grant-CsOuPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebec4-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="ebec4-117">如果您有中央樹系拓撲，您也必須在保留連絡人物件的容器或 Ou 上執行此程式。</span><span class="sxs-lookup"><span data-stu-id="ebec4-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="ebec4-118">如需中央樹系拓撲的詳細資訊，請參閱支援檔中的 [支援的 Active Directory 拓撲（Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) ）。</span><span class="sxs-lookup"><span data-stu-id="ebec4-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="ebec4-119">ObjectType 參數會指定物件類型。</span><span class="sxs-lookup"><span data-stu-id="ebec4-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="ebec4-120">OU 參數會指定組織單位。</span><span class="sxs-lookup"><span data-stu-id="ebec4-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="ebec4-121">這個 Cmdlet 會直接在指定的容器或 Ou，以及容器中的使用者或 InetOrgPerson 物件上新增必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="ebec4-122">如果執行此命令的 OU 具有使用者或 InetOrgPerson 物件的子 Ou，則不會對這些物件套用許可權。</span><span class="sxs-lookup"><span data-stu-id="ebec4-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="ebec4-123">您將需要個別于每個子 OU 上執行命令。</span><span class="sxs-lookup"><span data-stu-id="ebec4-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="ebec4-124">這是 Lync 主機部署的常見案例，例如上層 OU = OCS 租使用者、DC = CONTOSO、DC = LOCAL and child OU = Tenant1，OU = OCS 租，DC = CONTOSO，DC = LOCAL。</span><span class="sxs-lookup"><span data-stu-id="ebec4-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="ebec4-125">您需要與 Domain Admins 群組成員資格同等的使用者權限，才可執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebec4-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="ebec4-126">如果已在鎖定的環境中移除已驗證的使用者 Ace，您必須在樹系根域中的相關容器或 Ou 上授與此帳戶讀取存取 Ace，如已 [驗證的使用者許可權已在 Lync Server 2013 中移除](lync-server-2013-authenticated-user-permissions-are-removed.md) ，或使用的是 Enterprise Admins 群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ebec4-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="ebec4-127">**為 User、InetOrgPerson 及 Contact 物件設定必要的 Ace**</span><span class="sxs-lookup"><span data-stu-id="ebec4-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="ebec4-128">使用 Domain Admins 群組的成員帳戶，或具有同等使用者權限的帳戶，登入加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="ebec4-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="ebec4-129">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ebec4-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ebec4-130">運行：</span><span class="sxs-lookup"><span data-stu-id="ebec4-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ebec4-131">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="ebec4-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="ebec4-132">例如：</span><span class="sxs-lookup"><span data-stu-id="ebec4-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="ebec4-133">在記錄檔中，查看 **\<Success\>** 每個任務結尾的執行結果，確認已設定許可權，然後關閉 [記錄] 視窗。</span><span class="sxs-lookup"><span data-stu-id="ebec4-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="ebec4-134">或者，您可以執行下列命令來判斷是否已設定許可權：</span><span class="sxs-lookup"><span data-stu-id="ebec4-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="ebec4-135">例如：</span><span class="sxs-lookup"><span data-stu-id="ebec4-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="ebec4-136">在執行網域準備之後設定電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="ebec4-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="ebec4-137">在已停用許可權繼承的鎖定 Active Directory 環境中，網域準備不會在保留網域中電腦物件的容器或 Ou 上，設定必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="ebec4-138">在此情況下，您必須在已停用許可權繼承的每個容器或 OU 上執行 **Grant-CsOuPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebec4-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="ebec4-139">ObjectType 參數會指定物件類型。</span><span class="sxs-lookup"><span data-stu-id="ebec4-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="ebec4-140">此程式會直接在指定的容器上新增必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="ebec4-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="ebec4-141">您需要與 Domain Admins 群組成員資格同等的使用者權限，才可執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebec4-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="ebec4-142">如果已移除已驗證的使用者 Ace，您必須授與樹系根域中相關容器上的此帳戶的讀取存取 Ace，如已 [驗證的使用者許可權已在 Lync Server 2013 中移除](lync-server-2013-authenticated-user-permissions-are-removed.md) ，或使用的是 Enterprise Admins 群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ebec4-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="ebec4-143">**設定電腦物件所需的 Ace**</span><span class="sxs-lookup"><span data-stu-id="ebec4-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="ebec4-144">使用 Domain Admins 群組的成員帳戶，或具有同等使用者權限的帳戶登入網域電腦。</span><span class="sxs-lookup"><span data-stu-id="ebec4-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="ebec4-145">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ebec4-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ebec4-146">運行：</span><span class="sxs-lookup"><span data-stu-id="ebec4-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="ebec4-147">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="ebec4-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="ebec4-148">例如：</span><span class="sxs-lookup"><span data-stu-id="ebec4-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="ebec4-149">在記錄檔 C： \\ LogsOUPermissions.xml 範例中 \\ ，您會在 **\<Success\>** 每個工作結束時尋找執行結果，並確認沒有任何錯誤，然後關閉記錄。</span><span class="sxs-lookup"><span data-stu-id="ebec4-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="ebec4-150">您可以執行下列 Cmdlet 來測試許可權：</span><span class="sxs-lookup"><span data-stu-id="ebec4-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ebec4-151">例如：</span><span class="sxs-lookup"><span data-stu-id="ebec4-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebec4-152">如果您在鎖定的 Active Directory 環境中，于樹系根域上執行網域準備，請注意，Lync Server 需要存取 Active Directory 架構和設定容器。</span><span class="sxs-lookup"><span data-stu-id="ebec4-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="ebec4-153">如果已從 AD DS 中的架構或設定容器移除預設已驗證使用者許可權 &nbsp; ，則只有 Schema Admins 群組 (的架構容器) 或 Enterprise admins 群組的成員可以存取指定的容器，) 設定容器或 Enterprise admins 群組 (。</span><span class="sxs-lookup"><span data-stu-id="ebec4-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="ebec4-154">因為 Setup.exe、Lync Server 管理命令介面指令程式和 Lync Server 控制台需要存取這些容器，否則，除非執行安裝的使用者具有對 Schema Admins 和 Enterprise Admins 群組成員資格的使用者權限，否則系統管理工具將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ebec4-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="ebec4-155">若要修正此狀況，您必須授與 RTCUniversalGlobalWriteGroup 群組讀取、寫入架構和設定容器的許可權。</span><span class="sxs-lookup"><span data-stu-id="ebec4-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

