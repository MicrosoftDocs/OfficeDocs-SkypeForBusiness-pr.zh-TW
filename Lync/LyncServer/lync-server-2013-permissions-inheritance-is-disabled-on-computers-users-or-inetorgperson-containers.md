---
title: Lync Server 2013： 在電腦、 使用者或 InetOrgPerson 容器權限繼承已停用
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
ms.openlocfilehash: 7c67bda331532a11904b3edec469bceaa7e4f15b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="33805-102">在電腦、 使用者或 Lync Server 2013 中的 InetOrgPerson 容器已停用權限繼承</span><span class="sxs-lookup"><span data-stu-id="33805-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33805-103">_**上次修改主題：** 2014年-12 月 19 日_</span><span class="sxs-lookup"><span data-stu-id="33805-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="33805-104">在鎖定的 Active Directory 網域服務、 使用者和電腦物件通常放在特定組織單位 (Ou) 與停用來協助保護系統管理委派，並啟用使用群組原則物件 (Gpo) 的權限繼承若要強制執行安全性原則。</span><span class="sxs-lookup"><span data-stu-id="33805-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="33805-105">網域準備和伺服器啟用設定存取控制項目 (Ace) 所需的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="33805-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="33805-106">停用權限繼承時，Lync Server 的安全性群組無法繼承這些 Ace。</span><span class="sxs-lookup"><span data-stu-id="33805-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="33805-107">當這些權限不會繼承而來時，Lync Server 安全性群組不能存取設定，並會產生下列兩個問題：</span><span class="sxs-lookup"><span data-stu-id="33805-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="33805-108">Lync Server 的安全性群組來管理使用者、 Inetorgperson 及連絡人，及操作伺服器，需要每位使用者的屬性集、 即時通訊 (RTC)、 RTC 使用者搜尋，以及公用資訊的網域準備程序來設定的 Ace.</span><span class="sxs-lookup"><span data-stu-id="33805-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="33805-109">當已停用權限繼承時，安全性群組不會繼承這些 Ace，並無法管理伺服器或使用者。</span><span class="sxs-lookup"><span data-stu-id="33805-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="33805-110">若要探索伺服器和集區，在執行 Lync Server 的伺服器自信地仰賴所啟用的電腦相關的物件，包括 Microsoft 容器和伺服器物件上設定的 Ace。</span><span class="sxs-lookup"><span data-stu-id="33805-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="33805-111">停用權限繼承時，安全性群組、 伺服器和集區不會繼承這些 Ace 並無法利用這些 Ace。</span><span class="sxs-lookup"><span data-stu-id="33805-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="33805-112">若要解決這些問題，Lync 伺服器還提供**Grant-csoupermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33805-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="33805-113">此 cmdlet 會設定必要的 Lync Server Ace 直接在指定的容器及組織單位和內的容器或組織單位的物件。</span><span class="sxs-lookup"><span data-stu-id="33805-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="33805-114">設定權限的使用者、 InetOrgPerson 和 Contact 物件執行網域準備之後</span><span class="sxs-lookup"><span data-stu-id="33805-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="33805-115">其中權限繼承已停用，網域準備作業不會設定必要的 Ace 容器或組織單位保留使用者或 InetOrgPerson 鎖定的 Active Directory 環境中的網域內的物件。</span><span class="sxs-lookup"><span data-stu-id="33805-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="33805-116">在此情況下，您必須在每個容器或 OU 具有使用者或已停用與的權限繼承的 InetOrgPerson 物件執行**Grant-csoupermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33805-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="33805-117">如果您有在中央樹系拓撲，您也必須容器或 Ou 保留連絡人物件上執行此程序。</span><span class="sxs-lookup"><span data-stu-id="33805-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="33805-118">如需中央樹系拓撲的詳細資訊，請參閱支援文件中的[Lync Server 2013 中支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="33805-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="33805-119">ObjectType 參數會指定的物件類型。</span><span class="sxs-lookup"><span data-stu-id="33805-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="33805-120">OU 參數會指定組織單位。</span><span class="sxs-lookup"><span data-stu-id="33805-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="33805-121">此 cmdlet 會直接在指定的容器或 Ou，以及容器內的 User 或 InetOrgPerson 物件上新增必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="33805-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="33805-122">如果執行此命令時的 OU 的 User 或 InetOrgPerson 物件的子 Ou，將不會於這些套用權限。</span><span class="sxs-lookup"><span data-stu-id="33805-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="33805-123">您必須個別執行每一個子 OU 上的命令。</span><span class="sxs-lookup"><span data-stu-id="33805-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="33805-124">這是常見的案例與 Lync 主控部署例如上層 OU = OCS 租用戶，DC = CONTOSO，DC = LOCAL 和子 OU = Tenant1，OU = OCS 租用戶，DC = CONTOSO，DC = LOCAL。</span><span class="sxs-lookup"><span data-stu-id="33805-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="33805-125">您需要的使用者權限等同於 Domain Admins 群組成員資格，才能執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33805-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="33805-126">如果已驗證的使用者 Ace 也已移除鎖定的環境中，您必須授與此帳戶相關容器的讀取權限 Ace 或[驗證使用者權限已移除 Lync Server 2013 中](lync-server-2013-authenticated-user-permissions-are-removed.md)所述的樹系根網域中的 Ou，或使用是 Enterprise Admins 群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="33805-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="33805-127">**若要設定所需的 Ace User、 InetOrgPerson 和 Contact 物件**</span><span class="sxs-lookup"><span data-stu-id="33805-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="33805-128">登入已加入網域的 Domain Admins 群組成員或具有相等使用者權限的帳戶的電腦。</span><span class="sxs-lookup"><span data-stu-id="33805-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="33805-129">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="33805-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="33805-130">執行：</span><span class="sxs-lookup"><span data-stu-id="33805-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="33805-131">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="33805-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="33805-132">例如：</span><span class="sxs-lookup"><span data-stu-id="33805-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="33805-133">在 [記錄檔中，尋找**\<成功\>** 執行結果結尾的每個工作以驗證已設定的權限，，然後關閉 [記錄] 視窗。</span><span class="sxs-lookup"><span data-stu-id="33805-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="33805-134">或者，您可以執行下列命令，以判斷是否已設定的權限：</span><span class="sxs-lookup"><span data-stu-id="33805-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="33805-135">例如：</span><span class="sxs-lookup"><span data-stu-id="33805-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="33805-136">執行網域準備之後設定電腦物件權限</span><span class="sxs-lookup"><span data-stu-id="33805-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="33805-137">在鎖定的 Active Directory 環境中已停用權限繼承，網域準備作業不會保留網域內的電腦物件的 Ou 的容器上設定必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="33805-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="33805-138">在此情況下，您必須在每個容器或 OU 已執行已停用權限繼承的 Lync Server 的電腦上執行**Grant-csoupermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33805-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="33805-139">ObjectType 參數會指定的物件類型。</span><span class="sxs-lookup"><span data-stu-id="33805-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="33805-140">此程序會直接在指定容器上新增必要的 Ace。</span><span class="sxs-lookup"><span data-stu-id="33805-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="33805-141">您需要的使用者權限等同於 Domain Admins 群組成員資格，才能執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33805-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="33805-142">如果也已移除已驗證的使用者 Ace，您必須授與此帳戶[驗證的使用者權限會移除 Lync Server 2013 中](lync-server-2013-authenticated-user-permissions-are-removed.md)所述的樹系根網域中相關容器的讀取權限 Ace，或使用 Enterprise Admins 群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="33805-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="33805-143">**若要設定所需的 Ace computer 物件**</span><span class="sxs-lookup"><span data-stu-id="33805-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="33805-144">登入以屬於 Domain Admins 群組的成員或具有相等使用者權限帳戶的網域電腦。</span><span class="sxs-lookup"><span data-stu-id="33805-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="33805-145">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="33805-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="33805-146">執行：</span><span class="sxs-lookup"><span data-stu-id="33805-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="33805-147">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="33805-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="33805-148">例如：</span><span class="sxs-lookup"><span data-stu-id="33805-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="33805-149">範例記錄檔 c:\\記錄\\OUPermissions.xml，您會尋找**\<成功\>** 執行結果結尾的每個工作並確認沒有任何錯誤，，然後關閉 [記錄檔。</span><span class="sxs-lookup"><span data-stu-id="33805-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="33805-150">您可以執行下列 cmdlet 來測試權限：</span><span class="sxs-lookup"><span data-stu-id="33805-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="33805-151">例如：</span><span class="sxs-lookup"><span data-stu-id="33805-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33805-152">如果您在鎖定的 Active Directory 環境中的樹系根網域上執行網域準備，請注意 Lync Server 需要的 Active Directory 架構和設定容器權限。</span><span class="sxs-lookup"><span data-stu-id="33805-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="33805-153">預設驗證使用者的權限，則會移除結構描述或組態容器中 AD&nbsp;DS，只有 Schema Admins 群組成員 （適用於結構描述容器） 或 （適用於 Configuration] 容器中） 的 Enterprise Admins 群組有權存取指定的容器。</span><span class="sxs-lookup"><span data-stu-id="33805-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="33805-154">因為 Setup.exe，Lync Server 管理命令介面指令程式，以及 Lync Server 控制台需要存取這些容器，否則執行安裝的使用者具有等同於結構描述的使用者權限，則將會失敗的系統管理工具的設定和安裝Admins 與 Enterprise Admins 群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="33805-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="33805-155">若要補救這種情況下，您必須授與 RTCUniversalGlobalWriteGroup 群組的讀取和寫入存取權的架構和設定容器。</span><span class="sxs-lookup"><span data-stu-id="33805-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

