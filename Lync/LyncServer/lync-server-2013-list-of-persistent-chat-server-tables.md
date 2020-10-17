---
title: Lync Server 2013： Persistent Chat Server 表格清單
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
ms.openlocfilehash: da3069fdd039cb394308f3901ae9805b9023e15d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513880"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013 中的 Persistent Chat Server 表格清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

Persistent Chat 資料庫架構是由下清單格所組成。

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
<td><p>包含目前的輕量目錄存取通訊協定 (LDAP) Sync cookie。 每一列都對應到 Persistent Chat Server 主動監控變更的 Active Directory 網域服務網域。 在此表格中只會顯示與 Persistent Chat Server 相關之 Active Directory 網域的 (。 ) </p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013 中的 tblPrincipalMemberDifference</a></p></td>
<td><p>包含的群組成員資格變更 (新增及移除的成員) 尚未由後續的 Active Directory 同步步驟處理，也就是其中一個臨時資料表 (以及 Active Directory 同步處理第一個步驟中所用 tblADUpdates 表) 。</p>
<p>僅針對 tblPrincipal 表格中所列或具有已提列成員的群組，存放及/或處理其成員資格變更。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013 中的 tblADUpdates</a></p></td>
<td><p>包含尚未由後續 Active Directory 同步步驟處理的 Active Directory 網域服務變更，也就是其中一個臨時表格 (，以及 Active Directory 同步處理第一個步驟中所用的 tblPrincipalMemberDifference 表格) 。</p>
<p>對於已列于 tblPrincipal 表格中的主體，會儲存、處理或處理 Active Directory 的變更。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013 中的 tblPrincipalMembers</a></p></td>
<td><p>包含主體成員資格。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013 中的 tblPrincipalMeta</a></p></td>
<td><p>包含必須從 Active Directory 重新整理的主體。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013 中的 tblSkippedAffiliations</a></p></td>
<td><p>包含因某些原因而無法重新整理的隸屬關係，通常是因為 Active Directory 存取錯誤。</p>
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
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013 中的 tblPrincipalType</a></p></td>
<td><p>含有主體類型以分類 tblPrincipal 表格中的項目。此表格是靜態的，其會在資料庫建立期間設定，且不會變更。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013 中的 tblPrincipal</a></p></td>
<td><p>內含所有主體，包括使用者、資料夾及群組等。 Persistent Chat Server 會以平坦的異類清單形式處理此。 各欄位會依據每個主體的類型而定。</p>
<p>大多數的主體是儲存在 Active Directory 中之物件的快取複本。 在這些 Active Directory 物件的主體表格中建立快取複本，稱為布<em>建。</em></p>
<p>有些主體的建立會比其他主體更主動，而且會完全忽略某些 Active Directory 物件。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013 中的 tblPrincipalAffiliations</a></p></td>
<td><p>包含主體隸屬關係，描述 Active Directory 安全性群組、Active Directory 容器等等中的成員資格。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013 中的 tblNode</a></p></td>
<td><p>包含在 Lync Server 控制台中管理的類別節點。</p></td>
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
<td><p>僅包含 tblNode 表格中所使用的硬式編碼 &quot; Visibility &quot; 和 &quot; 行為 &quot; 屬性。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013 中的 tblEnumValue</a></p></td>
<td><p>包含 &quot; tblNode 表格中所用的硬編碼 Visibility "和" 行為 &quot; 屬性值。</p></td>
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
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013 中的 tblLastInviteId</a></p></td>
<td><p>含有為每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013 中的 tblLastChatId</a></p></td>
<td><p>含有為每個使用者產生 (也用於 tblChat 表格) 的最後一個聊天 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013 中的 tblPreference</a></p></td>
<td><p>包含使用者用戶端喜好設定 (僅限舊版用戶端使用)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013 中的 tblFileToken</a></p></td>
<td><p>包含用於檔案傳輸的臨時權杖。 每次上傳或下載檔案時，Persistent 聊天服務都會產生一個權杖，用戶端會使用該權杖來存取 Web 服務檔案存放區。</p></td>
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
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013 中的 tblServerIdentity</a></p></td>
<td><p>包含 Persistent Chat Server 集區中的主動伺服器。</p></td>
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
<td><p>包含 Persistent Chat service 之間目前的對等連線。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013 中的 tblConfig</a></p></td>
<td><p>包含 Persistent Chat Server 不支援的設定。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

