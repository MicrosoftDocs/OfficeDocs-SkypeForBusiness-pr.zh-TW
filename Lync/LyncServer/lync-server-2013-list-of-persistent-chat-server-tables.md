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

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013 中的常設聊天室伺服器清單表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

持續聊天資料庫架構是由下清單格所組成。

<div>

## <a name="active-directory-sync"></a>Active Directory 同步處理


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></p></td>
<td><p>包含目前的輕型目錄存取通訊協定（LDAP）同步處理 cookie。 每個資料列都會對應到一個 Active Directory 網域服務網域，持久聊天伺服器會積極監視所做的變更。 （只有與持久聊天伺服器相關的 Active Directory 網域才會顯示在這個表格中。）</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></p></td>
<td><p>包含尚未由後續 Active Directory 同步處理步驟處理的群組成員資格變更（已新增和移除的成員），而且是 Active Directory 同步處理第一個步驟中所使用的其中一個臨時資料表（以及 tblADUpdates 資料表）。</p>
<p>成員資格變更只會儲存在 tblPrincipal 資料表中所列的群組中，或在其中已列出成員。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></p></td>
<td><p>包含對 Active Directory 網域服務所做的變更，這些變更尚未由後續的 Active Directory 同步處理步驟所處理，而且是 Active Directory 第一個步驟中所使用的其中一個臨時資料表（以及 tblPrincipalMemberDifference 資料表）非同步.</p>
<p>對 Active Directory 所做的變更只會儲存在 tblPrincipal 資料表中所列的主體中，或同時進行處理。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></p></td>
<td><p>包含主體成員資格。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></p></td>
<td><p>包含必須從 Active Directory 進行更新的主體。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></p></td>
<td><p>包含無法因某種原因而重新整理的隸屬關係，通常是因為 Active Directory 存取錯誤。</p>
<p>此表格僅供提供資訊之用途。 不會使用其內容。</p>
<p>具有無法正確更新之隸屬關係的主體會保留在 tblPrincipalMeta 資料表中，並會提供另一個機會進行重新整理。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主體、隸屬關係、節點、範圍和角色


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的 tblPrincipalType</a></p></td>
<td><p>包含對 tblPrincipal 資料表中的內容進行分類的主要類型。 此資料表是靜態的。 它是在資料庫建立期間設定，不會變更。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></p></td>
<td><p>包含所有主體（使用者、資料夾、群組等）。 持續性聊天伺服器會將它處理為平面異類清單。 各種資料行都是以每個主體的類型為基礎。</p>
<p>大多數的主體都是儲存在 Active Directory 中的物件的快取複本。 在這些 Active Directory 物件的主要目錄中建立快取複本的參照稱為 [<em>預配</em>]。</p>
<p>有些原則的建立比其他人更主動，且某些 Active Directory 物件會完全忽略。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></p></td>
<td><p>包含描述 Active Directory 安全性群組中的成員資格、Active Directory 容器等的主體隸屬關係。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></p></td>
<td><p>包含 [Lync Server 控制台] 中所管理的類別節點。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></p></td>
<td><p>包含角色類型及其相關聯的許可權集。 這個查閱表格是靜態的。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013 中的 tblScopePrincipal</a></p></td>
<td><p>包含指派給節點的範圍。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013 中的 tblPrincipalRole</a></p></td>
<td><p>包含指派給節點的角色。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013 中的 tblSiopWhiteList</a></p></td>
<td><p>包含可與節點相關聯的已註冊增益集。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013 中的 tblEnumAttribute</a></p></td>
<td><p>只包含 tblNode 資料表&quot;中&quot;所&quot;使用&quot;的硬編碼可見度及行為屬性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></p></td>
<td><p>包含 tblNode 資料表中使用的&quot;硬編碼可見度 "And&quot; " 行為屬性的值。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>邀請、聊天及其他用戶端支援


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></p></td>
<td><p>在系統中包含已啟用自動邀請的所有節點的所有已預配使用者的邀請。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></p></td>
<td><p>包含所有聊天訊息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tblLastInviteId</a></p></td>
<td><p>包含每位使用者所產生（並在 tblPrincipalInvites 資料表中使用）的上一個邀請 ID。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tblLastChatId</a></p></td>
<td><p>包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></p></td>
<td><p>包含使用者用戶端喜好設定（僅供舊版用戶端使用）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></p></td>
<td><p>包含用於檔案傳輸用途的臨時權杖。 每次上傳或下載檔案時，Persistent 聊天服務會產生一個權杖供用戶端用來存取 Web 服務檔存放區。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>伺服器支援


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></p></td>
<td><p>包含持續聊天伺服器池中的作用中伺服器。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></p></td>
<td><p>包含管理員鎖，可執行某些系統管理員命令。 TblSystemRevision 資料表中的系統修訂專案會在每次解除鎖定之後增加。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></p></td>
<td><p>包含所使用的修訂數輸入（以及 tblAdminLock 資料表），以在多個伺服器間保持一致性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></p></td>
<td><p>包含持續聊天服務之間的目前對等連線。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></p></td>
<td><p>包含持續聊天伺服器不支援的設定。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

