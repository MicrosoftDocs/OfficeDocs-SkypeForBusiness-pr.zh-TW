---
title: Lync Server 2013：群組成員資格需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aed308674cc334cfb8f3d4f214ce7388ae89fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="6566a-102">Lync Server 2013 的群組成員資格需求</span><span class="sxs-lookup"><span data-stu-id="6566a-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6566a-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6566a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6566a-104">下表摘要列出人員應該歸屬的群組，以便成功安裝、管理和疑難排解 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6566a-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6566a-105">Lync Server 2013 可執行檔</span><span class="sxs-lookup"><span data-stu-id="6566a-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="6566a-106">需要群組成員資格</span><span class="sxs-lookup"><span data-stu-id="6566a-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6566a-107"><strong>Setup.exe：</strong>啟動 Lync Server 2013 系統管理工具安裝的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="6566a-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="6566a-108">執行可執行檔之電腦上的本機管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="6566a-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="6566a-109">[網域使用者] 群組的成員，以讀取 Active Directory 網域服務中的資訊。</span><span class="sxs-lookup"><span data-stu-id="6566a-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="6566a-110">之所以需要此許可權等級，是因為在本機電腦上自動安裝必要的 MSI 套件時，必須具備允許讀取和寫入受保護的本機電腦資源（例如程式檔案目錄）和受保護的許可權的許可權。[本機電腦] 配置單元之類的註冊表。</span><span class="sxs-lookup"><span data-stu-id="6566a-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="6566a-111">您也可以將設定許可權委派給您不想在網域管理員群組中授與其成員資格的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6566a-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="6566a-112">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的授權設定許可權</A>。</span><span class="sxs-lookup"><span data-stu-id="6566a-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6566a-113"><strong>.Deploy</strong> （由 setup.exe）所呼叫的是，部署 .exe 負責部署伺服器角色的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="6566a-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="6566a-114">執行可執行檔之電腦上的本機管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="6566a-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="6566a-115">[網域使用者] 群組的成員，以朗讀 AD DS 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="6566a-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="6566a-116">之所以需要此許可權等級，是因為在本機電腦上自動安裝必要的 MSI 套件時，必須具備允許讀取和寫入受保護的本機電腦資源（例如程式檔案目錄）和受保護的許可權的許可權。[本機電腦] 配置單元之類的註冊表。</span><span class="sxs-lookup"><span data-stu-id="6566a-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="6566a-117">RtcUniversalReadOnlyAdmins 群組中的成員資格是讀取中央管理儲存區所必需的。</span><span class="sxs-lookup"><span data-stu-id="6566a-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6566a-118">如果您執行的是 Windows Vista 作業系統或 Windows 7 作業系統，系統會提示您 [使用者帳戶控制] （UAC）繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="6566a-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="6566a-119">如果您是使用標準使用者帳戶登入，您將需要擁有本機管理員群組成員的使用者在系統提示有安裝軟體許可權的帳戶時提供認證。</span><span class="sxs-lookup"><span data-stu-id="6566a-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6566a-120"><strong>Cscript.exe （</strong>由 setup.exe 呼叫）是由 setup.exe 負責部署和設定伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="6566a-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="6566a-121">執行可執行檔之電腦上的本機管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="6566a-121">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="6566a-122">RTCUniversalServerAdmins 群組的成員，以執行引導程式。</span><span class="sxs-lookup"><span data-stu-id="6566a-122">Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe.</span></span> <span data-ttu-id="6566a-123">[網域使用者] 群組的成員，以朗讀 AD DS 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="6566a-123">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="6566a-124">之所以需要此許可權等級，是因為在本機電腦上自動安裝必要的 MSI 套件時，必須具備允許讀取和寫入受保護的本機電腦資源（例如程式檔案目錄）和受保護的許可權的許可權。[本機電腦] 配置單元之類的註冊表。</span><span class="sxs-lookup"><span data-stu-id="6566a-124">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6566a-125"><strong>TopologyBuilder</strong> –由嚮導驅動的使用者介面，用以建立、查看、調整和驗證 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="6566a-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="6566a-126">執行可執行檔之電腦上的本機管理員群組成員，以查看拓撲。</span><span class="sxs-lookup"><span data-stu-id="6566a-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="6566a-127">[RTCUniversalServerAdmins] 群組的成員，以變更配置設定。</span><span class="sxs-lookup"><span data-stu-id="6566a-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="6566a-128">RTCUniversalServerAdmins 群組和網域系統管理員群組的成員，或 RTCUniversalServerAdmins 群組的成員（只有在群組已獲委派設定許可權），才能發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="6566a-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="6566a-129">如需委派設定許可權以允許 RTCUniversalServerAdmins 群組的成員發佈拓撲的詳細資料，而不是網域管理員群組的成員，請參閱在部署檔中的<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的授權設定許可權</a>。</span><span class="sxs-lookup"><span data-stu-id="6566a-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6566a-130"><strong>AdminUIHost</strong> –用於管理 Lync Server 2013 的 Web 型圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="6566a-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="6566a-131">指派特定系統管理工作的另一個角色式存取控制（RBAC）角色之 CsAdministrator 群組或成員的成員。</span><span class="sxs-lookup"><span data-stu-id="6566a-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="6566a-132">Lync Server 2013 的 [控制台] 會執行 Lync Server 2013 管理命令介面 Cmdlet，以實現設定變更。</span><span class="sxs-lookup"><span data-stu-id="6566a-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="6566a-133">如需預先定義的角色和 Cmdlet 成員的清單，請參閱規劃檔中的<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</a>。</span><span class="sxs-lookup"><span data-stu-id="6566a-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6566a-134">已<strong>載入 Lync server 2013 模組的 PowerShell</strong> （具有專用來管理 lync Server 2013 之 Cmdlet 的命令列管理工具）。</span><span class="sxs-lookup"><span data-stu-id="6566a-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="6566a-135">已指派特定 Cmdlet 之 CsAdministrator 群組或另一個 RBAC 角色成員的成員。</span><span class="sxs-lookup"><span data-stu-id="6566a-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="6566a-136">如需預先定義的角色和 Cmdlet 成員的清單，請參閱規劃檔中的<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</a>。</span><span class="sxs-lookup"><span data-stu-id="6566a-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="6566a-137">或者，下列一或多個群組的成員，視 Cmdlet 而定：</span><span class="sxs-lookup"><span data-stu-id="6566a-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="6566a-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6566a-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="6566a-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="6566a-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="6566a-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="6566a-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

