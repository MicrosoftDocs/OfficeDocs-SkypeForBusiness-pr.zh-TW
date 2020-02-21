---
title: 'Lync Server 2013: Persistent Chat Server 表格清單'
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
ms.openlocfilehash: e65560cd792fe4132cf20f3b32824b2c828ae757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="69ce5-102">在 Lync Server 2013 常設聊天室伺服器資料表的清單</span><span class="sxs-lookup"><span data-stu-id="69ce5-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69ce5-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="69ce5-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="69ce5-104">常設聊天室資料庫結構描述是由下列表格所組成。</span><span class="sxs-lookup"><span data-stu-id="69ce5-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="69ce5-105">Active Directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="69ce5-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ce5-106">資料表</span><span class="sxs-lookup"><span data-stu-id="69ce5-106">Table</span></span></th>
<th><span data-ttu-id="69ce5-107">說明</span><span class="sxs-lookup"><span data-stu-id="69ce5-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-108"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-109">包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 cookie。</span><span class="sxs-lookup"><span data-stu-id="69ce5-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="69ce5-110">每個資料列會對應至 Persistent Chat Server 主動監視變更 Active Directory 網域服務網域。</span><span class="sxs-lookup"><span data-stu-id="69ce5-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="69ce5-111">（僅限 Active Directory 網域的相關 Persistent Chat Server 此表格中表示）。</span><span class="sxs-lookup"><span data-stu-id="69ce5-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-113">包含稍後的 Active Directory 同步處理步驟尚未處理，且已在 Active Directory 同步處理的第一個步驟中使用的暫時表格 （搭配 tblADUpdates 表格） 的其中一個群組的成員資格變更 （新增和移除成員）。</span><span class="sxs-lookup"><span data-stu-id="69ce5-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="69ce5-114">僅針對 tblPrincipal 表格中所列或具有已提列成員的群組，存放及/或處理其成員資格變更。</span><span class="sxs-lookup"><span data-stu-id="69ce5-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-115"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-116">包含要更新的 Active Directory 同步處理步驟尚未處理的 Active Directory 網域服務變更，並為下列其中一個 Active Directory 的第一個步驟中使用的暫時表格 （搭配 tblPrincipalMemberDifference 表格）同步處理。</span><span class="sxs-lookup"><span data-stu-id="69ce5-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="69ce5-117">變更為 [Active Directory 儲存、 處理，或僅針對 tblPrincipal 表格中已提列的主體。</span><span class="sxs-lookup"><span data-stu-id="69ce5-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-118"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblprincipalmembers 表格</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-119">包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="69ce5-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-120"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblprincipalmeta 表格</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-121">包含必須從 Active Directory 重新整理的主體。</span><span class="sxs-lookup"><span data-stu-id="69ce5-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-122"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-123">包含不會重新整理基於某些理由，通常是由於 Active Directory 存取錯誤的關係。</span><span class="sxs-lookup"><span data-stu-id="69ce5-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="69ce5-p102">本表格之用途僅為提供資訊參考用。其內容無法使用。</span><span class="sxs-lookup"><span data-stu-id="69ce5-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="69ce5-126">tblPrincipalMeta 表格中會存放具有無法正確重新整理之關係的主體，並給予其另一次重新整理的機會。</span><span class="sxs-lookup"><span data-stu-id="69ce5-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="69ce5-127">主體、關係、節點、範圍與角色</span><span class="sxs-lookup"><span data-stu-id="69ce5-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ce5-128">資料表</span><span class="sxs-lookup"><span data-stu-id="69ce5-128">Table</span></span></th>
<th><span data-ttu-id="69ce5-129">說明</span><span class="sxs-lookup"><span data-stu-id="69ce5-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-130"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的參照 tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-p103">含有主體類型以分類 tblPrincipal 表格中的項目。此表格是靜態的，其會在資料庫建立期間設定，且不會變更。</span><span class="sxs-lookup"><span data-stu-id="69ce5-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-134"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-135">內含所有主體，包括使用者、資料夾及群組等。</span><span class="sxs-lookup"><span data-stu-id="69ce5-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="69ce5-136">Persistent Chat Server 會處理此為單層異質性清單。</span><span class="sxs-lookup"><span data-stu-id="69ce5-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="69ce5-137">各欄位會依據每個主體的類型而定。</span><span class="sxs-lookup"><span data-stu-id="69ce5-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="69ce5-138">大部分的這些原則會儲存在 Active Directory 中的物件快取的副本。</span><span class="sxs-lookup"><span data-stu-id="69ce5-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="69ce5-139">建立快取的複本主體中的 Active Directory 物件的資料表指<em>佈建</em>。</span><span class="sxs-lookup"><span data-stu-id="69ce5-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="69ce5-140">部分主體比其他人，更積極地建立，且會刻意略過某些 Active Directory 物件。</span><span class="sxs-lookup"><span data-stu-id="69ce5-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-141"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 Principalaffiliations</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-142">包含主體關係，可描述 Active Directory 安全性群組、 Active Directory 容器等成員資格。</span><span class="sxs-lookup"><span data-stu-id="69ce5-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-143"><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-144">受管理的 Lync Server Control Panel 中會包含類別節點。</span><span class="sxs-lookup"><span data-stu-id="69ce5-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-145"><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-146">含有角色類型，以及其相關的權限設定。</span><span class="sxs-lookup"><span data-stu-id="69ce5-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="69ce5-147">此查閱表格是靜態的。</span><span class="sxs-lookup"><span data-stu-id="69ce5-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-148"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 中的 tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-149">包含指派給節點的範圍。</span><span class="sxs-lookup"><span data-stu-id="69ce5-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-150"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 中的 tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-151">包含指派給節點的角色。</span><span class="sxs-lookup"><span data-stu-id="69ce5-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-152"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 中的 tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-153">包含可與節點相關聯的已註冊增益集。</span><span class="sxs-lookup"><span data-stu-id="69ce5-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-154"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 中的 tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-155">包含硬式編碼&quot;可見度&quot;和&quot;行為&quot;tblNode 表格中所用的屬性。</span><span class="sxs-lookup"><span data-stu-id="69ce5-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-156"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-157">包含的硬式編碼值&quot;可見度 」 和 「 行為&quot;tblNode 表格中所用的屬性。</span><span class="sxs-lookup"><span data-stu-id="69ce5-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="69ce5-158">邀請、聊天以及其他用戶端支援</span><span class="sxs-lookup"><span data-stu-id="69ce5-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ce5-159">資料表</span><span class="sxs-lookup"><span data-stu-id="69ce5-159">Table</span></span></th>
<th><span data-ttu-id="69ce5-160">說明</span><span class="sxs-lookup"><span data-stu-id="69ce5-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-161"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-162">包含系統中所有啟用自動邀請的節點之所有已佈建使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="69ce5-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-163"><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-164">包含所有聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="69ce5-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-165"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tbllastinviteid 表格</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-166">含有為每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="69ce5-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-167"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tbllastchatid 表格</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-168">含有為每個使用者產生 (也用於 tblChat 表格) 的最後一個聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="69ce5-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-169"><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-170">包含使用者用戶端喜好設定 (僅限舊版用戶端使用)。</span><span class="sxs-lookup"><span data-stu-id="69ce5-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-171"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-172">包含用於檔案傳輸的臨時權杖。</span><span class="sxs-lookup"><span data-stu-id="69ce5-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="69ce5-173">每次上傳或下載檔案時的常設聊天室服務會產生語彙基元，用戶端用來存取 Web 服務檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="69ce5-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="69ce5-174">伺服器支援</span><span class="sxs-lookup"><span data-stu-id="69ce5-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69ce5-175">資料表</span><span class="sxs-lookup"><span data-stu-id="69ce5-175">Table</span></span></th>
<th><span data-ttu-id="69ce5-176">說明</span><span class="sxs-lookup"><span data-stu-id="69ce5-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity 在 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-178">包含作用中 Persistent Chat Server 集區伺服器。</span><span class="sxs-lookup"><span data-stu-id="69ce5-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-179"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-p108">包含執行某些管理員命令所需的管理員鎖定。tblSystemRevision 表格中的系統修訂項目會在每次解除鎖定後遞增。</span><span class="sxs-lookup"><span data-stu-id="69ce5-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-182"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-183">包含所用的修訂編號項目 (搭配 tblAdminLock 表格) 以用於封存多部伺服器間的一致性。</span><span class="sxs-lookup"><span data-stu-id="69ce5-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69ce5-184"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-185">包含常設聊天室服務之間的目前端對端連線。</span><span class="sxs-lookup"><span data-stu-id="69ce5-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69ce5-186"><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="69ce5-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69ce5-187">包含 Persistent Chat Server 不支援的組態。</span><span class="sxs-lookup"><span data-stu-id="69ce5-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

