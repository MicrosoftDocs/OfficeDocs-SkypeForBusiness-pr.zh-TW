---
title: Lync Server 2013：常設聊天室伺服器清單表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="ea3f3-102">Lync Server 2013 中的常設聊天室伺服器清單表格</span><span class="sxs-lookup"><span data-stu-id="ea3f3-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea3f3-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ea3f3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ea3f3-104">持續聊天資料庫架構是由下清單格所組成。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="ea3f3-105">Active Directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="ea3f3-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3f3-106">表格</span><span class="sxs-lookup"><span data-stu-id="ea3f3-106">Table</span></span></th>
<th><span data-ttu-id="ea3f3-107">說明</span><span class="sxs-lookup"><span data-stu-id="ea3f3-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-108"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-109">包含目前的輕型目錄存取通訊協定（LDAP）同步處理 cookie。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="ea3f3-110">每個資料列都會對應到一個 Active Directory 網域服務網域，持久聊天伺服器會積極監視所做的變更。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="ea3f3-111">（只有與持久聊天伺服器相關的 Active Directory 網域才會顯示在這個表格中。）</span><span class="sxs-lookup"><span data-stu-id="ea3f3-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-113">包含尚未由後續 Active Directory 同步處理步驟處理的群組成員資格變更（已新增和移除的成員），而且是 Active Directory 同步處理第一個步驟中所使用的其中一個臨時資料表（以及 tblADUpdates 資料表）。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="ea3f3-114">成員資格變更只會儲存在 tblPrincipal 資料表中所列的群組中，或在其中已列出成員。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-115"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-116">包含對 Active Directory 網域服務所做的變更，這些變更尚未由後續的 Active Directory 同步處理步驟所處理，而且是 Active Directory 第一個步驟中所使用的其中一個臨時資料表（以及 tblPrincipalMemberDifference 資料表）非同步.</span><span class="sxs-lookup"><span data-stu-id="ea3f3-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="ea3f3-117">對 Active Directory 所做的變更只會儲存在 tblPrincipal 資料表中所列的主體中，或同時進行處理。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-118"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-119">包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-120"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-121">包含必須從 Active Directory 進行更新的主體。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-122"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-123">包含無法因某種原因而重新整理的隸屬關係，通常是因為 Active Directory 存取錯誤。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="ea3f3-124">此表格僅供提供資訊之用途。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-124">This table is for informational purposes only.</span></span> <span data-ttu-id="ea3f3-125">不會使用其內容。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="ea3f3-126">具有無法正確更新之隸屬關係的主體會保留在 tblPrincipalMeta 資料表中，並會提供另一個機會進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="ea3f3-127">主體、隸屬關係、節點、範圍和角色</span><span class="sxs-lookup"><span data-stu-id="ea3f3-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3f3-128">表格</span><span class="sxs-lookup"><span data-stu-id="ea3f3-128">Table</span></span></th>
<th><span data-ttu-id="ea3f3-129">說明</span><span class="sxs-lookup"><span data-stu-id="ea3f3-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-130"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的 tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-131">包含對 tblPrincipal 資料表中的內容進行分類的主要類型。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="ea3f3-132">此資料表是靜態的。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-132">This table is static.</span></span> <span data-ttu-id="ea3f3-133">它是在資料庫建立期間設定，不會變更。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-134"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-135">包含所有主體（使用者、資料夾、群組等）。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="ea3f3-136">持續性聊天伺服器會將它處理為平面異類清單。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="ea3f3-137">各種資料行都是以每個主體的類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="ea3f3-138">大多數的主體都是儲存在 Active Directory 中的物件的快取複本。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="ea3f3-139">在這些 Active Directory 物件的主要目錄中建立快取複本的參照稱為 [<em>預配</em>]。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="ea3f3-140">有些原則的建立比其他人更主動，且某些 Active Directory 物件會完全忽略。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-141"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-142">包含描述 Active Directory 安全性群組中的成員資格、Active Directory 容器等的主體隸屬關係。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-143"><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-144">包含 [Lync Server 控制台] 中所管理的類別節點。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-145"><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-146">包含角色類型及其相關聯的許可權集。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="ea3f3-147">這個查閱表格是靜態的。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-148"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 中的 tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-149">包含指派給節點的範圍。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-150"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 中的 tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-151">包含指派給節點的角色。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-152"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 中的 tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-153">包含可與節點相關聯的已註冊增益集。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-154"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 中的 tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-155">只包含 tblNode 資料表&quot;中&quot;所&quot;使用&quot;的硬編碼可見度及行為屬性。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-156"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-157">包含 tblNode 資料表中使用的&quot;硬編碼可見度 "And&quot; " 行為屬性的值。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="ea3f3-158">邀請、聊天及其他用戶端支援</span><span class="sxs-lookup"><span data-stu-id="ea3f3-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3f3-159">表格</span><span class="sxs-lookup"><span data-stu-id="ea3f3-159">Table</span></span></th>
<th><span data-ttu-id="ea3f3-160">說明</span><span class="sxs-lookup"><span data-stu-id="ea3f3-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-161"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-162">在系統中包含已啟用自動邀請的所有節點的所有已預配使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-163"><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-164">包含所有聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-165"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-166">包含每位使用者所產生（並在 tblPrincipalInvites 資料表中使用）的上一個邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-167"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-168">包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-169"><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-170">包含使用者用戶端喜好設定（僅供舊版用戶端使用）。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-171"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-172">包含用於檔案傳輸用途的臨時權杖。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="ea3f3-173">每次上傳或下載檔案時，Persistent 聊天服務會產生一個權杖供用戶端用來存取 Web 服務檔存放區。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="ea3f3-174">伺服器支援</span><span class="sxs-lookup"><span data-stu-id="ea3f3-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3f3-175">表格</span><span class="sxs-lookup"><span data-stu-id="ea3f3-175">Table</span></span></th>
<th><span data-ttu-id="ea3f3-176">說明</span><span class="sxs-lookup"><span data-stu-id="ea3f3-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-177"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-178">包含持續聊天伺服器池中的作用中伺服器。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-179"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-180">包含管理員鎖，可執行某些系統管理員命令。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="ea3f3-181">TblSystemRevision 資料表中的系統修訂專案會在每次解除鎖定之後增加。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-182"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-183">包含所使用的修訂數輸入（以及 tblAdminLock 資料表），以在多個伺服器間保持一致性。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3f3-184"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-185">包含持續聊天服務之間的目前對等連線。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3f3-186"><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="ea3f3-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ea3f3-187">包含持續聊天伺服器不支援的設定。</span><span class="sxs-lookup"><span data-stu-id="ea3f3-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

