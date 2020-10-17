---
title: Lync Server 2013：規劃以角色為基礎的存取控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65f6411023c80a527cff31c389a8283d090dfc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528030"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="2ae40-102">在 Lync Server 2013 中規劃以角色為基礎的存取控制</span><span class="sxs-lookup"><span data-stu-id="2ae40-102">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae40-103">_**主題上次修改日期：** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="2ae40-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="2ae40-104">為了讓您委派管理工作，同時維持高安全性的安全性，Lync Server 2013 提供角色型存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="2ae40-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="2ae40-105">使用 RBAC，指派使用者給系統管理角色，即可授與系統管理權限。</span><span class="sxs-lookup"><span data-stu-id="2ae40-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="2ae40-106">Lync Server 2013 包含一組豐富的內建管理角色，也可讓您建立新角色，並為每個新角色指定自訂 Cmdlet 清單。</span><span class="sxs-lookup"><span data-stu-id="2ae40-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="2ae40-107">您也可以將 Cmdlet 的指令碼新增至預先定義與自訂 RBAC 角色之允許的工作中。</span><span class="sxs-lookup"><span data-stu-id="2ae40-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="2ae40-108">更佳的伺服器安全性與集中性</span><span class="sxs-lookup"><span data-stu-id="2ae40-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="2ae40-109">透過 RBAC，存取和授權是以使用者的 Lync Server 角色為基礎。</span><span class="sxs-lookup"><span data-stu-id="2ae40-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="2ae40-110">如此一來便可讓「最低權限」的安全性實務發揮效用，限制系統管理員與使用者擁有執行工作必要的權限。</span><span class="sxs-lookup"><span data-stu-id="2ae40-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2ae40-111">使用 Lync Server 控制台或 Lync Server 管理命令介面時，RBAC 限制只適用于以遠端方式運作的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="2ae40-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="2ae40-112">位於執行 Lync Server 之伺服器上的使用者，不受 RBAC 限制。</span><span class="sxs-lookup"><span data-stu-id="2ae40-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="2ae40-113">因此，您的 Lync 伺服器實體安全性很重要，必須保留 RBAC 限制。</span><span class="sxs-lookup"><span data-stu-id="2ae40-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="2ae40-114">角色與範圍</span><span class="sxs-lookup"><span data-stu-id="2ae40-114">Roles and Scope</span></span>

<span data-ttu-id="2ae40-p104">在 RBAC，*「角色」* 已經過啟用可使用 Cmdlet 的清單，主要是提供特定類型的系統管理員或技術人員使用。*「範圍」* 指的是角色中定義的 Cmdlet 賴以操作的物件集合。範圍影響的物件可能是使用者帳戶 (依組織單位分組) 或伺服器 (依網站分組)。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="2ae40-118">下表列出 Lync Server 中的預先定義的角色，並提供每個任務類型的一般綜述。</span><span class="sxs-lookup"><span data-stu-id="2ae40-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="2ae40-119">第四欄會針對每個 Lync Server role 顯示類似的 Microsoft Exchange 伺服器角色（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="2ae40-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="2ae40-120">預先定義的系統管理角色</span><span class="sxs-lookup"><span data-stu-id="2ae40-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ae40-121">角色</span><span class="sxs-lookup"><span data-stu-id="2ae40-121">Role</span></span></th>
<th><span data-ttu-id="2ae40-122">允許的工作</span><span class="sxs-lookup"><span data-stu-id="2ae40-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="2ae40-123">Active Directory 基礎群組</span><span class="sxs-lookup"><span data-stu-id="2ae40-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="2ae40-124">Exchange 相等項目</span><span class="sxs-lookup"><span data-stu-id="2ae40-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ae40-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-p106">可執行所有系統管理工作並修改所有設定，包括建立角色及指派使用者給角色。可新增新的網站、集區與服務，藉以擴充部署項目。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-129">組織管理</span><span class="sxs-lookup"><span data-stu-id="2ae40-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae40-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-131">可以啟用和停用 Lync Server 的使用者、移動使用者並指派現有的原則給使用者。</span><span class="sxs-lookup"><span data-stu-id="2ae40-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="2ae40-132">無法修改原則。</span><span class="sxs-lookup"><span data-stu-id="2ae40-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-134">郵件收件者</span><span class="sxs-lookup"><span data-stu-id="2ae40-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae40-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-136">可建立、設定及管理語音相關的設定及原則。</span><span class="sxs-lookup"><span data-stu-id="2ae40-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-138">不適用</span><span class="sxs-lookup"><span data-stu-id="2ae40-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae40-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-p108">可對伺服器與相關服務進行管理、監控及疑難排解。可防止對伺服器進行全新的連線作業、停止與啟動服務，以及套用軟體更新。無法進行具有全域組態影響的變更。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-144">伺服器管理</span><span class="sxs-lookup"><span data-stu-id="2ae40-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae40-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-146">可檢視部署情況 (包括使用者與伺服器資訊) 以監控部署運作情況。</span><span class="sxs-lookup"><span data-stu-id="2ae40-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-148">僅供檢視的組織管理</span><span class="sxs-lookup"><span data-stu-id="2ae40-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae40-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="2ae40-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="2ae40-p109">可檢視部署內容，包括使用者內容與原則。可執行特定疑難排解工作。無法變更使用者內容或原則、伺服器組態或相關服務。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="2ae40-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="2ae40-154">HelpDesk</span><span class="sxs-lookup"><span data-stu-id="2ae40-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae40-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-156">可修改封存組態與原則。</span><span class="sxs-lookup"><span data-stu-id="2ae40-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-158">保留管理、法務保存措施</span><span class="sxs-lookup"><span data-stu-id="2ae40-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae40-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-160">可管理網站內的回應群組應用程式組態。</span><span class="sxs-lookup"><span data-stu-id="2ae40-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-162">不適用</span><span class="sxs-lookup"><span data-stu-id="2ae40-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae40-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-p110">最低層級的增強型 9-1-1 (E9-1-1) 管理權限，包括建立 E9-1-1 位置與網路識別碼，並將這些識別碼彼此關聯。此角色一律指派全域範圍。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-167">不適用</span><span class="sxs-lookup"><span data-stu-id="2ae40-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ae40-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="2ae40-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="2ae40-169">可管理特定回應群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="2ae40-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="2ae40-171">不適用</span><span class="sxs-lookup"><span data-stu-id="2ae40-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ae40-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-173">可管理常設聊天功能和特定的常設聊天室。</span><span class="sxs-lookup"><span data-stu-id="2ae40-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="2ae40-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="2ae40-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2ae40-175">不適用</span><span class="sxs-lookup"><span data-stu-id="2ae40-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ae40-176">所有在 Lync Server 中發運的預先定義的角色都具有全域範圍。</span><span class="sxs-lookup"><span data-stu-id="2ae40-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="2ae40-177">為了遵循最低權限實務，當使用者只需要管理有限的伺服器或使用者時，請勿將全域範圍的角色指派給他們。</span><span class="sxs-lookup"><span data-stu-id="2ae40-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="2ae40-178">要達到這個目的，請依據現有的角色建立相關角色，但在範圍上稍做限制即可。</span><span class="sxs-lookup"><span data-stu-id="2ae40-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="2ae40-179">建立有範圍的角色</span><span class="sxs-lookup"><span data-stu-id="2ae40-179">Creating a Scoped Role</span></span>

<span data-ttu-id="2ae40-180">建立範圍有限的角色 (有範圍的角色) 時，您必須指定範圍及其所依據的現有角色，以及要指派該角色的 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="2ae40-181">您指定的 Active Directory 群組必須事先建立好。</span><span class="sxs-lookup"><span data-stu-id="2ae40-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="2ae40-182">以下 Cmdlet 將示範如何建立範圍有限的角色 (該角色擁有其中一個預先定義管理角色的權限，但範圍有限)。</span><span class="sxs-lookup"><span data-stu-id="2ae40-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="2ae40-183">它會建立名為的新角色 `Site01 Server Administrators` 。</span><span class="sxs-lookup"><span data-stu-id="2ae40-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="2ae40-184">此角色具有預先定義的 CsServerAdministrator 角色功能，但僅適用位於 Site01 網站的伺服器。</span><span class="sxs-lookup"><span data-stu-id="2ae40-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="2ae40-185">若要讓此 Cmdlet 正常運作，必須已定義 Site01 網站，且名為的通用安全性群組 `Site01 Server Administrators` 必須已經存在。</span><span class="sxs-lookup"><span data-stu-id="2ae40-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="2ae40-186">在執行此指令程式之後，所有屬於該群組成員的使用者， `Site01 Server Administrators` 都會擁有 Site01 中伺服器的伺服器管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="2ae40-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="2ae40-187">此外，以後新增至此通用安全性群組的任何使用者也會取得此角色的許可權。</span><span class="sxs-lookup"><span data-stu-id="2ae40-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="2ae40-188">請注意，角色本身和指派給它的通用安全性群組都是呼叫的 `Site01 Server Administrators` 。</span><span class="sxs-lookup"><span data-stu-id="2ae40-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="2ae40-189">以下範例將限制使用者範圍，而非伺服器範圍。</span><span class="sxs-lookup"><span data-stu-id="2ae40-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="2ae40-190">它會建立一個 `Sales Users Administrator` 角色，以管理銷售組織單位中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2ae40-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="2ae40-191">若要使用此 Cmdlet，必須已建立 SalesUsersAdministrator 通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="2ae40-192">建立新角色</span><span class="sxs-lookup"><span data-stu-id="2ae40-192">Creating a New Role</span></span>

<span data-ttu-id="2ae40-p115">若要建立一個新角色能夠存取非預先定義角色中的一組 Cmdlet、指令碼或模組，您可再次從使用其中一個預先定義角色為範本開始。請注意，角色可執行的指令碼和模組必須儲存於下列位置：</span><span class="sxs-lookup"><span data-stu-id="2ae40-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="2ae40-195">Lync 模組路徑，也就是預設的 C： \\ Program files the the Program files the \\ \\ Microsoft Lync Server 2013 module \\ \\ lync</span><span class="sxs-lookup"><span data-stu-id="2ae40-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="2ae40-196">使用者腳本路徑，也就是預設的 C： \\ Program files \\ 常見的檔案 \\ Microsoft Lync Server 2013 \\ AdminScripts</span><span class="sxs-lookup"><span data-stu-id="2ae40-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="2ae40-197">若要建立新角色，需使用 **New-CsAdminRole** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ae40-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="2ae40-198">在執行 **New-CsAdminRole**之前，您必須先建立將與此角色關聯的基礎通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="2ae40-199">下列 Cmdlet 可作為建立新角色的範例。</span><span class="sxs-lookup"><span data-stu-id="2ae40-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="2ae40-200">他們會建立名為的新角色類型 `MyHelpDeskScriptRole` 。</span><span class="sxs-lookup"><span data-stu-id="2ae40-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="2ae40-201">新角色具有預先定義 CsHelpDesk 角色的功能，可在名為“testscript”的指令碼中額外執行各項功能。</span><span class="sxs-lookup"><span data-stu-id="2ae40-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="2ae40-202">為了讓此 Cmdlet 能夠運作，您必須先建立通用安全性群組 MyHelpDeskScriptRole。</span><span class="sxs-lookup"><span data-stu-id="2ae40-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="2ae40-203">此 Cmdlet 執行後，就能將使用者直接指派給此角色 (此時使用者擁有全域範圍)，或是依據此角色建立有範圍的角色，如本文件先前在〈建立有範圍的角色〉中所述。</span><span class="sxs-lookup"><span data-stu-id="2ae40-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="2ae40-204">指派角色給使用者</span><span class="sxs-lookup"><span data-stu-id="2ae40-204">Assigning Roles to Users</span></span>

<span data-ttu-id="2ae40-205">每個 Lync Server 角色都與基礎 Active Directory 通用安全性群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="2ae40-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="2ae40-206">您新增至基礎群組的任何使用者都可獲得該角色的功能。</span><span class="sxs-lookup"><span data-stu-id="2ae40-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="2ae40-207">上述各節的範例會建立新的角色，並將現有的通用安全性群組指派給新的角色。</span><span class="sxs-lookup"><span data-stu-id="2ae40-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="2ae40-208">若要將現有角色指派給一或多位使用者，請將這些使用者新增至與該角色關聯的群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="2ae40-209">您可以將個別使用者和通用安全性群組新增至這些群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="2ae40-210">例如，會自動將 **CsAdministrator** 角色授與 Active Directory 中的 **CS Administrators** 通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="2ae40-211">當您部署 Lync Server 時，會在 Active Directory 中建立此通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="2ae40-212">若要授予使用者或群組這個權限，您只需將其新增至 **CS 系統管理員**群組。</span><span class="sxs-lookup"><span data-stu-id="2ae40-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="2ae40-213">您可以將使用者新增至對應每個群組的 Active Directory 基礎群組，藉此賦予其多重 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="2ae40-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="2ae40-214">請注意，當您建立角色時，後續新增至該 Active Directory 基礎群組的使用者將會繼承該角色的權限。</span><span class="sxs-lookup"><span data-stu-id="2ae40-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="2ae40-215">修改角色功能</span><span class="sxs-lookup"><span data-stu-id="2ae40-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="2ae40-p121">您可以修改角色可執行的 Cmdlet 和指令碼清單；也可同時修改自訂角色可執行的 Cmdlet 和指令碼，但僅能修改預先定義角色的指令碼。每個鍵入的 Cmdlet 均可新增、移除或更換 Cmdlet 或指令碼。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="2ae40-219">若要修改角色，請使用 **Set-CsAdminRole** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ae40-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="2ae40-220">下列 Cmdlet 會從角色移除一個腳本。</span><span class="sxs-lookup"><span data-stu-id="2ae40-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="2ae40-221">規劃 RBAC</span><span class="sxs-lookup"><span data-stu-id="2ae40-221">Planning for RBAC</span></span>

<span data-ttu-id="2ae40-222">針對您的 Lync Server 部署提供任何類型的管理許可權的每個使用者，請明確考慮他們需要執行的工作，然後將其指派給其工作所需的最低許可權和範圍的角色。</span><span class="sxs-lookup"><span data-stu-id="2ae40-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="2ae40-223">必要時可以使用 **Set-CsAdminRole** Cmdlet 建立只擁有其任務所需 Cmdlet 的新角色。</span><span class="sxs-lookup"><span data-stu-id="2ae40-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="2ae40-p124">具有 CsAdministrator 角色的使用者可以建立所有種類的角色，包括依據 CsAdministrator 建立的角色，並將其指派給使用者。最佳做法是將 CsAdministrator 角色指派給非常少數的受信任使用者。</span><span class="sxs-lookup"><span data-stu-id="2ae40-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

