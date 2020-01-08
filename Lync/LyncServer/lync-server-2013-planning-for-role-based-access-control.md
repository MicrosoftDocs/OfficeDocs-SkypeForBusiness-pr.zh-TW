---
title: Lync Server 2013：規劃角色型存取控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="ed7f2-102">在 Lync Server 2013 中規劃角色型存取控制</span><span class="sxs-lookup"><span data-stu-id="ed7f2-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed7f2-103">_**主題上次修改日期：** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="ed7f2-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="ed7f2-104">為了讓您能夠委派系統管理工作，同時維持高安全性的標準，Lync Server 2013 提供了角色式存取控制（RBAC）。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="ed7f2-105">使用 RBAC，系統會將使用者指派給管理角色，以獲得系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="ed7f2-106">Lync Server 2013 包含一組豐富的內建管理角色，也可讓您建立新的角色，並為每個新角色指定自訂的 Cmdlet 清單。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="ed7f2-107">您也可以為預先定義及自訂 RBAC 角色，新增 Cmdlet 指令碼至其允許的工作中。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="ed7f2-108">更好的伺服器安全性與集中化</span><span class="sxs-lookup"><span data-stu-id="ed7f2-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="ed7f2-109">使用 RBAC、存取和授權是完全根據使用者的 Lync 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="ed7f2-110">這可讓您使用「最低許可權」的安全性做法，只為管理員和使用者授予其工作所需的權力。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed7f2-111">RBAC 限制只適用于使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 進行遠端作業的管理員。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="ed7f2-112">坐在執行 Lync Server 伺服器的使用者不受 RBAC 限制。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="ed7f2-113">因此，您的 Lync 伺服器的物理安全性對於保留 RBAC 限制是很重要的。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="ed7f2-114">角色和範圍</span><span class="sxs-lookup"><span data-stu-id="ed7f2-114">Roles and Scope</span></span>

<span data-ttu-id="ed7f2-115">在 RBAC 中，*角色*可讓您使用一份 Cmdlet 清單，專門針對特定類型的系統管理員或技術人員提供此功能。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="ed7f2-116">*範圍*是角色中定義的 Cmdlet 可以執行的一組物件。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="ed7f2-117">範圍所影響的物件可以是使用者帳戶（依組織單位分組）或伺服器（依網站分組）。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="ed7f2-118">下表列出 Lync Server 中的預先定義角色，並簡要說明每個作業所能執行的工作類型。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="ed7f2-119">第四欄顯示與每個 Lync 伺服器角色相似的 Microsoft Exchange Server 角色（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="ed7f2-120">預先定義的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="ed7f2-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed7f2-121">角色</span><span class="sxs-lookup"><span data-stu-id="ed7f2-121">Role</span></span></th>
<th><span data-ttu-id="ed7f2-122">允許的工作</span><span class="sxs-lookup"><span data-stu-id="ed7f2-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="ed7f2-123">基礎 Active Directory 群組</span><span class="sxs-lookup"><span data-stu-id="ed7f2-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="ed7f2-124">Exchange 對等</span><span class="sxs-lookup"><span data-stu-id="ed7f2-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed7f2-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-126">可以執行所有系統管理工作並修改所有設定，包括建立角色並將使用者指派給角色。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="ed7f2-127">可以新增網站、池及服務來展開部署。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-129">組織管理</span><span class="sxs-lookup"><span data-stu-id="ed7f2-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed7f2-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-131">可以啟用和停用 Lync Server 的使用者、移動使用者，以及將現有的原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="ed7f2-132">無法修改原則。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-134">郵件收件者</span><span class="sxs-lookup"><span data-stu-id="ed7f2-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed7f2-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-136">可以建立、設定及管理語音相關設定與原則。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-138">不適用</span><span class="sxs-lookup"><span data-stu-id="ed7f2-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed7f2-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-140">可以管理、監控及疑難排解伺服器和服務。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="ed7f2-141">可以避免新的伺服器連線、停止及啟動服務，以及套用軟體更新。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="ed7f2-142">無法對全域設定影響進行變更。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-144">伺服器管理</span><span class="sxs-lookup"><span data-stu-id="ed7f2-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed7f2-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-146">可以查看部署，包括使用者和伺服器資訊，以便監視部署健康情況。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-148">僅供查看的組織管理</span><span class="sxs-lookup"><span data-stu-id="ed7f2-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed7f2-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="ed7f2-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-150">可以查看部署，包括使用者的屬性和原則。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="ed7f2-151">可以執行特定的疑難排解工作。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="ed7f2-152">無法變更使用者屬性或原則、伺服器設定或服務。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="ed7f2-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-154">技術</span><span class="sxs-lookup"><span data-stu-id="ed7f2-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed7f2-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-156">可以修改封存配置和原則。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-158">保留管理，法律封存</span><span class="sxs-lookup"><span data-stu-id="ed7f2-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed7f2-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-160">可管理網站內回應群組應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-162">不適用</span><span class="sxs-lookup"><span data-stu-id="ed7f2-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed7f2-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-164">增強型9-1-1 （E9-1-1）管理的最低許可權等級，包括建立 E9-1 個位置和網路識別碼，並將它們相互關聯。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="ed7f2-165">這個角色永遠會指派給全域範圍。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-167">不適用</span><span class="sxs-lookup"><span data-stu-id="ed7f2-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed7f2-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="ed7f2-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-169">可以管理特定的回應群組。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="ed7f2-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-171">不適用</span><span class="sxs-lookup"><span data-stu-id="ed7f2-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed7f2-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-173">可以管理持續聊天功能與特定的持續聊天室。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="ed7f2-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ed7f2-175">不適用</span><span class="sxs-lookup"><span data-stu-id="ed7f2-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed7f2-176">所有在 Lync Server 隨附的預先定義角色都有全域範圍。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="ed7f2-177">若要遵循最低許可權做法，請不要將使用者指派給擁有全域範圍的角色（如果他們只要管理有限的一組伺服器或使用者）。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="ed7f2-178">若要完成此作業，您可以建立以現有角色為基礎的角色，但範圍較有限。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="ed7f2-179">建立作用中角色</span><span class="sxs-lookup"><span data-stu-id="ed7f2-179">Creating a Scoped Role</span></span>

<span data-ttu-id="ed7f2-180">當您建立擁有有限範圍（作用中角色）的角色時，您會指定該範圍，以及它所依據的現有角色，以及要指派給該角色的 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="ed7f2-181">您指定的 Active Directory 群組必須已建立。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="ed7f2-182">下列 Cmdlet 是建立具有其中一個預先定義之系統管理角色之許可權但範圍有限的角色的範例。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="ed7f2-183">它會建立名`Site01 Server Administrators`為的新角色。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="ed7f2-184">角色具有預先定義之 CsServerAdministrator 角色的功能，但只適用于位於 Site01 網站的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="ed7f2-185">若要使用此 Cmdlet，必須已定義 Site01 網站，且名為`Site01 Server Administrators`的通用安全性群組必須已經存在。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="ed7f2-186">執行此 Cmdlet 之後，所有是`Site01 Server Administrators`群組成員的使用者將擁有 Site01 中伺服器的伺服器系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="ed7f2-187">此外，稍後新增到此通用安全性群組的任何使用者也會取得此角色的許可權。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="ed7f2-188">請注意，角色本身以及指派給它的通用安全性群組都會被叫`Site01 Server Administrators`用。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="ed7f2-189">下列範例會限制使用者範圍，而不是伺服器範圍。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="ed7f2-190">它會建立`Sales Users Administrator`一個角色來管理組織單位中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="ed7f2-191">必須先建立 SalesUsersAdministrator 通用安全性群組，才能使用此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="ed7f2-192">建立新的角色</span><span class="sxs-lookup"><span data-stu-id="ed7f2-192">Creating a New Role</span></span>

<span data-ttu-id="ed7f2-193">若要建立能夠存取不在其中一個預先定義的角色或一組腳本或模組的一組 Cmdlet 的角色，您也可以使用其中一個預先定義的角色做為範本來開始。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="ed7f2-194">請注意，角色可以執行的腳本和模組必須儲存在下列位置：</span><span class="sxs-lookup"><span data-stu-id="ed7f2-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="ed7f2-195">Lync\\模組路徑，預設為 C： Program files\\常見檔案\\Microsoft Lync Server 2013\\模組 Lync\\</span><span class="sxs-lookup"><span data-stu-id="ed7f2-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="ed7f2-196">使用者腳本\\路徑，預設為 C： Program files\\常見檔案\\Microsoft Lync Server 2013 AdminScripts\\</span><span class="sxs-lookup"><span data-stu-id="ed7f2-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="ed7f2-197">若要建立新的角色，您可以使用**CsAdminRole** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="ed7f2-198">在執行**新的 CsAdminRole**之前，您必須先建立將與此角色相關聯的基礎通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="ed7f2-199">下列 Cmdlet 是建立新角色的範例。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="ed7f2-200">它們會建立名`MyHelpDeskScriptRole`為的新角色類型。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="ed7f2-201">新角色具有預先定義的 CsHelpDesk 角色的功能，而且還可以在名為 "testscript" 的腳本中執行這些函數。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="ed7f2-202">若要使用此 Cmdlet，您必須先建立通用安全性群組 MyHelpDeskScriptRole。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="ed7f2-203">在執行此 Cmdlet 之後，您可以直接將使用者指派給這個角色（在這種情況下，它們擁有全域範圍），或根據這個角色建立作用中的角色，如在此檔中建立作用中的角色中所述。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="ed7f2-204">指派角色給使用者</span><span class="sxs-lookup"><span data-stu-id="ed7f2-204">Assigning Roles to Users</span></span>

<span data-ttu-id="ed7f2-205">每個 Lync 伺服器角色都會與基礎 Active Directory 通用安全群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="ed7f2-206">您新增至基礎群組的任何使用者都會取得該角色的功能。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="ed7f2-207">上述各節中的範例都建立了新的角色，並將現有的通用安全性群組指派給新的角色。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="ed7f2-208">若要將現有的角色指派給一或多個使用者，請將這些使用者新增到與該角色相關聯的群組。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="ed7f2-209">您可以將個別使用者和通用安全性群組新增到這些群組中。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="ed7f2-210">例如，系統會自動將**CsAdministrator**角色授與 Active Directory 中的**CS 系統管理員**通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="ed7f2-211">當您部署 Lync Server 時，會在 Active Directory 中建立這個 [通用安全性群組]。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="ed7f2-212">若要授予使用者或群組此許可權，您只要將其新增至 [ **CS 管理員**] 群組即可。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="ed7f2-213">您可以將多個 RBAC 角色新增到對應到每個角色的基礎 Active Directory 群組，以取得該使用者。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="ed7f2-214">請注意，當您建立角色時，稍後新增至基礎 Active Directory 群組的使用者會獲得該角色的功能。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="ed7f2-215">修改角色的功能</span><span class="sxs-lookup"><span data-stu-id="ed7f2-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="ed7f2-216">您可以修改角色可以執行的 Cmdlet 與腳本清單。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="ed7f2-217">您可以同時修改自訂角色可以執行的 Cmdlet 與腳本，但您只能修改預先定義角色的腳本。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="ed7f2-218">您輸入的每個 Cmdlet 都可以新增、移除或取代 Cmdlet 或腳本。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="ed7f2-219">若要修改角色，請使用**CsAdminRole** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="ed7f2-220">下列 Cmdlet 會從角色中移除一個腳本。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="ed7f2-221">RBAC 的規劃</span><span class="sxs-lookup"><span data-stu-id="ed7f2-221">Planning for RBAC</span></span>

<span data-ttu-id="ed7f2-222">針對您的 Lync Server 部署，要取得任何類型的管理許可權的每個使用者，請考慮他們需要執行的工作，然後將他們指派給其工作所需的最少許可權和範圍。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="ed7f2-223">如有需要，您可以使用**CsAdminRole** Cmdlet 來建立只有此人的工作所需的 Cmdlet 的新角色。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="ed7f2-224">擁有 CsAdministrator 角色的使用者可以建立所有類型的角色，包括以 CsAdministrator 為基礎的角色，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="ed7f2-225">最佳做法是將 CsAdministrator 角色指派給一組非常小的信任使用者。</span><span class="sxs-lookup"><span data-stu-id="ed7f2-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

