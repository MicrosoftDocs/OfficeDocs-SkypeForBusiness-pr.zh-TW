---
title: Lync Server 2013：Computers、Users 或 InetOrgPerson 容器已停用權限繼承
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="00446-102">Lync Server 2013 中的 Computers、Users 或 InetOrgPerson 容器已停用權限繼承</span><span class="sxs-lookup"><span data-stu-id="00446-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00446-103">_**主題上次修改日期：** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="00446-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="00446-104">在鎖定的 Active Directory 網域服務中，使用者和電腦物件通常都是以停用許可權繼承的特定組織單位（Ou）來進行，以協助保護系統管理委派，以及啟用群組原則物件（Gpo）的使用。強制執行安全性原則。</span><span class="sxs-lookup"><span data-stu-id="00446-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="00446-105">網域準備和伺服器啟用：設定 Lync Server 2013 所需的存取控制專案（Ace）。</span><span class="sxs-lookup"><span data-stu-id="00446-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="00446-106">當權限繼承停用時，Lync Server 安全性群組無法繼承這些 Ace。</span><span class="sxs-lookup"><span data-stu-id="00446-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="00446-107">如果不繼承這些許可權，Lync Server 安全性群組將無法存取設定，而且會發生下列兩個問題：</span><span class="sxs-lookup"><span data-stu-id="00446-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="00446-108">若要管理使用者、InetOrgPersons 和連絡人，以及使用伺服器，Lync Server 安全性群組需要在每個使用者的屬性集、即時通訊（RTC）、RTC 使用者搜尋及公用資訊的網域準備程式中設定 Ace.</span><span class="sxs-lookup"><span data-stu-id="00446-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="00446-109">當權限繼承停用時，安全性群組不會繼承這些 Ace，也不能管理伺服器或使用者。</span><span class="sxs-lookup"><span data-stu-id="00446-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="00446-110">若要探索伺服器和池，執行 Lync Server 的伺服器依賴在與電腦相關物件上啟用的 Ace，包括 Microsoft 容器和 Server 物件。</span><span class="sxs-lookup"><span data-stu-id="00446-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="00446-111">停用許可權繼承之後，安全性群組、伺服器和池就不會繼承這些 Ace，也不能利用這些 Ace。</span><span class="sxs-lookup"><span data-stu-id="00446-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="00446-112">為了解決這些問題，Lync Server 提供**授與 CsOuPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00446-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="00446-113">這個 Cmdlet 會將所需的 Lync Server Ace 直接設定在指定的容器、組織單位和容器或組織單位中的物件上。</span><span class="sxs-lookup"><span data-stu-id="00446-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="00446-114">在執行網域準備之後，設定使用者、InetOrgPerson 和連絡人物件的許可權</span><span class="sxs-lookup"><span data-stu-id="00446-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="00446-115">在已停用許可權繼承的鎖定 Active Directory 環境中，[網域準備] 不會在擁有網域中的使用者或 InetOrgPerson 物件的容器或組織單位上，設定必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="00446-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="00446-116">在這種情況下，您必須在擁有已停用許可權繼承的使用者或 InetOrgPerson 物件的每個容器或 OU 上執行**Grant CsOuPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00446-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="00446-117">如果您有中央林拓朴，您也必須在擁有連絡人物件的容器或 Ou 上執行此程式。</span><span class="sxs-lookup"><span data-stu-id="00446-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="00446-118">如需中央林拓撲的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="00446-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="00446-119">ObjectType 參數會指定物件類型。</span><span class="sxs-lookup"><span data-stu-id="00446-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="00446-120">OU 參數會指定組織單位。</span><span class="sxs-lookup"><span data-stu-id="00446-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="00446-121">這個 Cmdlet 會將所需的 Ace 直接新增到容器中指定的容器或 Ou，以及使用者或 InetOrgPerson 物件。</span><span class="sxs-lookup"><span data-stu-id="00446-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="00446-122">如果執行此命令的 OU 具有使用者或 InetOrgPerson 物件的子 Ou，則這些許可權不會套用在這些物件上。</span><span class="sxs-lookup"><span data-stu-id="00446-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="00446-123">您將需要個別在每個子 OU 上執行命令。</span><span class="sxs-lookup"><span data-stu-id="00446-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="00446-124">這是使用 Lync 主機部署的常見案例，例如父 OU = OCS 租使用者、DC = CONTOSO、DC = LOCAL 和 child OU = Tenant1，OU = OCS 承租人，DC = CONTOSO，DC = LOCAL。</span><span class="sxs-lookup"><span data-stu-id="00446-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="00446-125">您需要與 Domain 管理員群組成員資格同等的使用者權限，才能執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00446-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="00446-126">如果已在鎖定環境中移除經過驗證的使用者 Ace，您必須在[Lync Server 2013 中已移除已驗證的使用者許可權](lync-server-2013-authenticated-user-permissions-are-removed.md)，或使用企業系統管理員群組成員的帳戶，在林根網域的相關容器或 ou 中授與此帳戶讀取存取 ace。</span><span class="sxs-lookup"><span data-stu-id="00446-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="00446-127">**若要為使用者、InetOrgPerson 和連絡人物件設定必要的 Ace**</span><span class="sxs-lookup"><span data-stu-id="00446-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="00446-128">使用網域系統管理員群組的成員或擁有同等使用者許可權的帳戶登入加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="00446-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="00446-129">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="00446-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="00446-130">用盡</span><span class="sxs-lookup"><span data-stu-id="00446-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="00446-131">如果您沒有指定 Domain 參數，則預設值為本地域。</span><span class="sxs-lookup"><span data-stu-id="00446-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="00446-132">例如：</span><span class="sxs-lookup"><span data-stu-id="00446-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="00446-133">在記錄檔中，在每個工作的結尾尋找\*\* \<成功\> \*\*執行結果，以確認許可權已設定，然後關閉 [記錄] 視窗。</span><span class="sxs-lookup"><span data-stu-id="00446-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="00446-134">或者，您可以執行下列命令來判斷是否已設定許可權：</span><span class="sxs-lookup"><span data-stu-id="00446-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="00446-135">例如：</span><span class="sxs-lookup"><span data-stu-id="00446-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="00446-136">在執行網域準備之後，設定電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="00446-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="00446-137">在已停用許可權繼承的鎖定 Active Directory 環境中，[網域準備] 不會在擁有網域中電腦物件的容器或 Ou 上設定必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="00446-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="00446-138">在這種情況下，您必須在運行 Lync Server 且已停用許可權繼承之電腦的每個容器或 OU 上執行**授與 CsOuPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00446-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="00446-139">ObjectType 參數會指定物件類型。</span><span class="sxs-lookup"><span data-stu-id="00446-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="00446-140">此程式會將所需的 Ace 直接新增到指定的容器。</span><span class="sxs-lookup"><span data-stu-id="00446-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="00446-141">您需要與 Domain 管理員群組成員資格同等的使用者權限，才能執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00446-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="00446-142">如果已移除經過驗證的使用者 Ace，您必須在林根網域的相關容器上授與此帳戶的讀取存取 Ace，如在[Lync Server 2013 中移除已驗證的使用者許可權，](lync-server-2013-authenticated-user-permissions-are-removed.md)或使用的是企業系統管理員群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="00446-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="00446-143">**若要設定電腦物件所需的 Ace**</span><span class="sxs-lookup"><span data-stu-id="00446-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="00446-144">以網域系統管理員群組成員或具有同等使用者許可權的帳戶登入網域電腦。</span><span class="sxs-lookup"><span data-stu-id="00446-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="00446-145">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="00446-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="00446-146">用盡</span><span class="sxs-lookup"><span data-stu-id="00446-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="00446-147">如果您沒有指定 Domain 參數，則預設值為本地域。</span><span class="sxs-lookup"><span data-stu-id="00446-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="00446-148">例如：</span><span class="sxs-lookup"><span data-stu-id="00446-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="00446-149">在範例記錄檔案 C：\\記錄\\OUPermissions 中，您會在每個工作結束時尋找\*\* \<成功\> \*\*執行結果，並確認沒有錯誤，然後關閉記錄。</span><span class="sxs-lookup"><span data-stu-id="00446-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="00446-150">您可以執行下列 Cmdlet 來測試許可權：</span><span class="sxs-lookup"><span data-stu-id="00446-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="00446-151">例如：</span><span class="sxs-lookup"><span data-stu-id="00446-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00446-152">如果您在已鎖定的 Active Directory 環境中，在林根網域上執行網域準備，請注意 Lync Server 需要存取 Active Directory 架構和配置容器。</span><span class="sxs-lookup"><span data-stu-id="00446-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="00446-153">如果從 AD&nbsp;DS 中的架構或配置容器中移除預設的經過驗證的使用者許可權，則只有架構管理員群組的成員（適用于架構容器）或企業系統管理員群組（適用于配置容器）才能存取指定的容器。</span><span class="sxs-lookup"><span data-stu-id="00446-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="00446-154">因為 setup.exe、Lync Server 管理命令介面 Cmdlet 和 Lync Server 控制台需要存取這些容器，否則，除非執行安裝的使用者具有對架構的使用者權限，否則系統管理工具的安裝和安裝將會失敗。系統管理員和企業管理員群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="00446-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="00446-155">若要修正這種情況，您必須授與 RTCUniversalGlobalWriteGroup 群組讀取、寫入架構和配置容器的許可權。</span><span class="sxs-lookup"><span data-stu-id="00446-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

