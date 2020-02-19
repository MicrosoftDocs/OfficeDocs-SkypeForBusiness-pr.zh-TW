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
ms.openlocfilehash: e6d9fe9db5ad22a0d6ad2d68d0afdbd5b0969608
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>在 Lync Server 2013 常設聊天室伺服器資料表的清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

常設聊天室資料庫結構描述是由下列表格所組成。

<div>

## <a name="active-directory-sync"></a>Active Directory 同步處理


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料表</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013 中的 tblADCookie</a></p></td>
<td><p>包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 cookie。 每個資料列會對應至 Persistent Chat Server 主動監視變更 Active Directory 網域服務網域。 （僅限 Active Directory 網域的相關 Persistent Chat Server 此表格中表示）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></p></td>
<td><p>包含稍後的 Active Directory 同步處理步驟尚未處理，且已在 Active Directory 同步處理的第一個步驟中使用的暫時表格 （搭配 tblADUpdates 表格） 的其中一個群組的成員資格變更 （新增和移除成員）。</p>
<p>僅針對 tblPrincipal 表格中所列或具有已提列成員的群組，存放及/或處理其成員資格變更。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></p></td>
<td><p>包含要更新的 Active Directory 同步處理步驟尚未處理的 Active Directory 網域服務變更，並為下列其中一個 Active Directory 的第一個步驟中使用的暫時表格 （搭配 tblPrincipalMemberDifference 表格）同步處理。</p>
<p>變更為 [Active Directory 儲存、 處理，或僅針對 tblPrincipal 表格中已提列的主體。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblprincipalmembers 表格</a></p></td>
<td><p>包含主體成員資格。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblprincipalmeta 表格</a></p></td>
<td><p>包含必須從 Active Directory 重新整理的主體。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></p></td>
<td><p>包含不會重新整理基於某些理由，通常是由於 Active Directory 存取錯誤的關係。</p>
<p>本表格之用途僅為提供資訊參考用。其內容無法使用。</p>
<p>tblPrincipalMeta 表格中會存放具有無法正確重新整理之關係的主體，並給予其另一次重新整理的機會。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主體、關係、節點、範圍與角色


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料表</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的參照 tblPrincipalType</a></p></td>
<td><p>含有主體類型以分類 tblPrincipal 表格中的項目。此表格是靜態的，其會在資料庫建立期間設定，且不會變更。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></p></td>
<td><p>內含所有主體，包括使用者、資料夾及群組等。 Persistent Chat Server 會處理此為單層異質性清單。 各欄位會依據每個主體的類型而定。</p>
<p>大部分的這些原則會儲存在 Active Directory 中的物件快取的副本。 建立快取的複本主體中的 Active Directory 物件的資料表指<em>佈建</em>。</p>
<p>部分主體比其他人，更積極地建立，且會刻意略過某些 Active Directory 物件。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 Principalaffiliations</a></p></td>
<td><p>包含主體關係，可描述 Active Directory 安全性群組、 Active Directory 容器等成員資格。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></p></td>
<td><p>受管理的 Lync Server Control Panel 中會包含類別節點。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013 中的 tblRoleType</a></p></td>
<td><p>含有角色類型，以及其相關的權限設定。 此查閱表格是靜態的。</p></td>
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
<td><p>包含硬式編碼&quot;可見度&quot;和&quot;行為&quot;tblNode 表格中所用的屬性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></p></td>
<td><p>包含的硬式編碼值&quot;可見度 」 和 「 行為&quot;tblNode 表格中所用的屬性。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>邀請、聊天以及其他用戶端支援


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料表</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013 中的 tblPrincipalInvites</a></p></td>
<td><p>包含系統中所有啟用自動邀請的節點之所有已佈建使用者的邀請。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013 中的 tblChat</a></p></td>
<td><p>包含所有聊天訊息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tbllastinviteid 表格</a></p></td>
<td><p>含有為每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tbllastchatid 表格</a></p></td>
<td><p>含有為每個使用者產生 (也用於 tblChat 表格) 的最後一個聊天 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></p></td>
<td><p>包含使用者用戶端喜好設定 (僅限舊版用戶端使用)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></p></td>
<td><p>包含用於檔案傳輸的臨時權杖。 每次上傳或下載檔案時的常設聊天室服務會產生語彙基元，用戶端用來存取 Web 服務檔案存放區。</p></td>
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
<th>資料表</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity 在 Lync Server 2013</a></p></td>
<td><p>包含作用中 Persistent Chat Server 集區伺服器。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">Lync Server 2013 中的 tblAdminLock</a></p></td>
<td><p>包含執行某些管理員命令所需的管理員鎖定。tblSystemRevision 表格中的系統修訂項目會在每次解除鎖定後遞增。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013 中的 tblSystemRevision</a></p></td>
<td><p>包含所用的修訂編號項目 (搭配 tblAdminLock 表格) 以用於封存多部伺服器間的一致性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013 中的 tblActivePeers</a></p></td>
<td><p>包含常設聊天室服務之間的目前端對端連線。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></p></td>
<td><p>包含 Persistent Chat Server 不支援的組態。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

