---
title: Lync Server 2013： 群組成員資格需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8726d471b1db95aa67cca58a77452d9faa43df4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="68ffa-102">Lync Server 2013 的群組成員資格需求</span><span class="sxs-lookup"><span data-stu-id="68ffa-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ffa-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="68ffa-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="68ffa-104">下表摘要說明人員應具備成功安裝、 管理及疑難排解 Lync Server 2013 的群組。</span><span class="sxs-lookup"><span data-stu-id="68ffa-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68ffa-105">Lync Server 2013 可執行檔</span><span class="sxs-lookup"><span data-stu-id="68ffa-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="68ffa-106">需要的群組成員資格</span><span class="sxs-lookup"><span data-stu-id="68ffa-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ffa-107"><strong>Setup.exe</strong> – 啟動 Lync Server 2013 系統管理工具安裝的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="68ffa-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="68ffa-108">電腦上執行可執行檔的 Local Administrators 群組成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="68ffa-109">若要在 Active Directory 網域服務中讀取資訊的網域使用者群組的成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="68ffa-110">此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</span><span class="sxs-lookup"><span data-stu-id="68ffa-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="68ffa-111">您也可以委派安裝權限給您不想授予 Domain Admins 群組成員資格的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="68ffa-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="68ffa-112">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的 Granting 安裝程式權限</A>。</span><span class="sxs-lookup"><span data-stu-id="68ffa-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ffa-113"><strong>Deploy.exe</strong> – 由 setup.exe 呼叫，deploy.exe 負責部署伺服器角色的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="68ffa-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="68ffa-114">電腦上執行可執行檔的 Local Administrators 群組成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="68ffa-115">讀取 AD DS 中資訊的 Domain Users 群組成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="68ffa-116">此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</span><span class="sxs-lookup"><span data-stu-id="68ffa-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="68ffa-117">RtcUniversalReadOnlyAdmins 群組成員資格，才需要讀取的中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="68ffa-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="68ffa-118">如果您執行 Windows Vista 作業系統或 Windows 7 作業系統，將會提示您的使用者帳戶控制 (UAC) 繼續進行安裝。</span><span class="sxs-lookup"><span data-stu-id="68ffa-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="68ffa-119">如果您是用標準使用者帳戶登入，則在出現具有安裝軟體權限的帳戶提示時，您會需要身為 Local Administrators 群組成員的某個人提供憑證。</span><span class="sxs-lookup"><span data-stu-id="68ffa-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ffa-120"><strong>Bootstrapper.exe</strong> – 由 setup.exe 呼叫，bootstrapper.exe 負責部署和設定伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="68ffa-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="68ffa-p105">電腦上執行可執行檔的 Local Administrators 群組成員。執行 Bootstrapper.exe 的 RTCUniversalServerAdmins 群組成員。讀取 AD DS 中資訊的 Domain Users 群組成員。此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</span><span class="sxs-lookup"><span data-stu-id="68ffa-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ffa-125"><strong>TopologyBuilder</strong> – 精靈驅動的使用者介面來建立、 檢視、 調整以及驗證 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="68ffa-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="68ffa-126">電腦上執行可執行檔以檢視拓撲的 Local Administrators 群組成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="68ffa-127">變更組態設定的 RTCUniversalServerAdmins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="68ffa-128">發行拓撲的 RTCUniversalServerAdmins 群組和 Domain Admins 群組成員，或 RTCUniversalServerAdmins 群組成員 (僅限於群組被授予委派安裝權限時)。</span><span class="sxs-lookup"><span data-stu-id="68ffa-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="68ffa-129">如需有關委派設定權限，允許來發行拓撲不需要以 Domain Admins 群組成員的 RTCUniversalServerAdmins 群組成員的詳細資訊，請參閱部署文件中的<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的 Granting 安裝程式權限</a>。</span><span class="sxs-lookup"><span data-stu-id="68ffa-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ffa-130"><strong>AdminUIHost</strong> – 管理 Lync Server 2013 的 Web 型圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="68ffa-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="68ffa-131">CsAdministrator 群組成員，或指派了特定系統管理工作的其他角色型存取控制 (RBAC) 角色成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="68ffa-132">Lync Server 2013 控制台會藉由執行 Lync Server 2013 管理命令介面 cmdlet 實作組態變更。</span><span class="sxs-lookup"><span data-stu-id="68ffa-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="68ffa-133">如需預先定義的角色和成員允許執行指令程式的清單，請參閱規劃文件中的<a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</a>。</span><span class="sxs-lookup"><span data-stu-id="68ffa-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ffa-134"><strong>載入的 Lync Server 2013 模組的 PowerShell.exe</strong> – 指令程式特定的 Lync Server 2013 管理命令列系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="68ffa-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="68ffa-135">CsAdministrator 群組成員，或指派特定 Cmdlet 的其他 RBAC 角色成員。</span><span class="sxs-lookup"><span data-stu-id="68ffa-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="68ffa-136">如需預先定義的角色和成員允許執行指令程式的清單，請參閱規劃文件中的<a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</a>。</span><span class="sxs-lookup"><span data-stu-id="68ffa-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="68ffa-137">或者，下列一或多個群組成員 (視 Cmdlet 而定)：</span><span class="sxs-lookup"><span data-stu-id="68ffa-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="68ffa-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="68ffa-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="68ffa-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="68ffa-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="68ffa-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="68ffa-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

