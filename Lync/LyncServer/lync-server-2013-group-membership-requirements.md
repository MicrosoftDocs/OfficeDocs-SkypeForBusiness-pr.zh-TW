---
title: Lync Server 2013：群組成員資格需求
description: Lync Server 2013：群組成員資格需求。
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
ms.openlocfilehash: 3f18fb6fbc782ecd41b7a782965f2cd6a82f6fd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554459"
---
# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="0d0b3-103">Lync Server 2013 的群組成員資格需求</span><span class="sxs-lookup"><span data-stu-id="0d0b3-103">Group membership requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d0b3-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="0d0b3-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="0d0b3-105">下表摘要說明人員應該歸屬的群組，以便成功安裝、管理和疑難排解 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-105">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d0b3-106">Lync Server 2013 可執行檔</span><span class="sxs-lookup"><span data-stu-id="0d0b3-106">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="0d0b3-107">需要的群組成員資格</span><span class="sxs-lookup"><span data-stu-id="0d0b3-107">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d0b3-108"><strong>Setup.exe</strong> –啟動 Lync Server 2013 系統管理工具安裝的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-108"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="0d0b3-109">電腦上執行可執行檔的 Local Administrators 群組成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-109">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="0d0b3-110">[網域使用者] 群組的成員，以讀取 Active Directory 網域服務中的資訊。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-110">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="0d0b3-111">此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-111">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="0d0b3-112">您也可以委派安裝權限給您不想授予 Domain Admins 群組成員資格的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-112">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="0d0b3-113">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-granting-setup-permissions.md">授予 Lync Server 2013 的安裝許可權</A> 。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-113">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d0b3-114"><strong>Deploy.exe</strong> – 由 setup.exe 呼叫，deploy.exe 負責部署伺服器角色的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-114"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="0d0b3-115">電腦上執行可執行檔的 Local Administrators 群組成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-115">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="0d0b3-116">讀取 AD DS 中資訊的 Domain Users 群組成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-116">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="0d0b3-117">此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-117">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="0d0b3-118">需要有 RtcUniversalReadOnlyAdmins 群組的成員資格，才可讀取中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-118">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0d0b3-119">如果您正在執行 Windows Vista 作業系統或 Windows 7 作業系統，系統會提示使用者帳戶控制 (UAC) 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-119">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="0d0b3-120">如果您是用標準使用者帳戶登入，則在出現具有安裝軟體權限的帳戶提示時，您會需要身為 Local Administrators 群組成員的某個人提供憑證。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-120">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d0b3-121"><strong>Bootstrapper.exe</strong> – 由 setup.exe 呼叫，bootstrapper.exe 負責部署和設定伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-121"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="0d0b3-p105">電腦上執行可執行檔的 Local Administrators 群組成員。執行 Bootstrapper.exe 的 RTCUniversalServerAdmins 群組成員。讀取 AD DS 中資訊的 Domain Users 群組成員。此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d0b3-126"><strong>TopologyBuilder</strong> –以嚮導為導向的使用者介面，用來建立、查看、調整和驗證 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-126"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="0d0b3-127">電腦上執行可執行檔以檢視拓撲的 Local Administrators 群組成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-127">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="0d0b3-128">變更組態設定的 RTCUniversalServerAdmins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-128">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="0d0b3-129">發行拓撲的 RTCUniversalServerAdmins 群組和 Domain Admins 群組成員，或 RTCUniversalServerAdmins 群組成員 (僅限於群組被授予委派安裝權限時)。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-129">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="0d0b3-130">如需委派設定許可權以允許 RTCUniversalServerAdmins 群組成員發佈拓撲的詳細資訊，而不是 Domain Admins 群組的成員，請參閱部署檔中的授與 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的設定許可權</a> 。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-130">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d0b3-131"><strong>AdminUIHost</strong> –以 Web 為基礎的圖形使用者介面，用以管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-131"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="0d0b3-132">CsAdministrator 群組成員，或指派了特定系統管理工作的其他角色型存取控制 (RBAC) 角色成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-132">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="0d0b3-133">Lync Server 2013 控制台會執行 Lync Server 2013 管理命令介面 Cmdlet，以實現設定變更。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-133">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="0d0b3-134">如需可執行檔預先定義角色和 Cmdlet 成員的清單，請參閱規劃檔中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</a> 。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-134">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d0b3-135">已<strong>載入 Lync server 2013 模組的PowerShell.exe</strong> –具有 lync server 2013 管理專用 Cmdlet 的命令列系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-135"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="0d0b3-136">CsAdministrator 群組成員，或指派特定 Cmdlet 的其他 RBAC 角色成員。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-136">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="0d0b3-137">如需可執行檔預先定義角色和 Cmdlet 成員的清單，請參閱規劃檔中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</a> 。</span><span class="sxs-lookup"><span data-stu-id="0d0b3-137">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="0d0b3-138">或者，下列一或多個群組成員 (視 Cmdlet 而定)：</span><span class="sxs-lookup"><span data-stu-id="0d0b3-138">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d0b3-139">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0d0b3-139">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="0d0b3-140">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0d0b3-140">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="0d0b3-141">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="0d0b3-141">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

