---
title: Lync Server 2013：常設聊天室伺服器的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中的常設聊天室伺服器的部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

若要部署 Lync Server 2013，持久的聊天伺服器需要您以正確的順序部署它，且您已完成所有必要的部署步驟。

<div>

## <a name="deployment-sequence"></a>部署順序

您可以在部署初始拓撲（包括至少一個 Lync Server 2013、前端池或一個 Lync Server 2013，標準版伺服器）之後，部署持續式聊天伺服器。 本主題描述如何將持久聊天伺服器新增至現有的部署。

</div>

<div>

## <a name="deployment-process"></a>部署程式

下表列出部署持久聊天伺服器的基本步驟，並提供更多詳細資料的連結。

### <a name="persistent-chat-server-deployment-process"></a>持續聊天伺服器部署程式

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>工作</th>
<th>步驟</th>
<th>必要角色和群組成員資格</th>
<th>相關主題</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備的硬體和軟體</strong></p></td>
<td><p>在符合系統需求的硬體上，安裝下列各項：</p>
<ul>
<li><p>在永久聊天伺服器前端伺服器上：</p></li>
</ul>
<ul>
<li><p>符合系統需求的作業系統</p></li>
<li><p>運行 Lync Server 2013 之電腦的軟體先決條件</p></li>
<li><p>伺服器上將主控持久聊天伺服器資料庫的 SQL Server</p></li>
</ul>
<p>如果需要持續聊天伺服器合規性：</p>
<ul>
<li><p>伺服器上將託管持久聊天伺服器合規性資料庫的 SQL Server</p></li>
</ul></td>
<td><p>屬於本機管理員群組成員的任何使用者。</p></td>
<td><p>支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></p>
<p>支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">判定 Lync Server 2013 的系統需求</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中持續聊天伺服器的技術需求</a></p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓朴，以支援持續聊天伺服器（以及可隨意進行的聊天合規性）</strong></p></td>
<td><p>執行拓撲建立器，以新增持久聊天伺服器池至您的拓撲：</p>
<ul>
<li><p>新增持久聊天伺服器元件至拓撲</p></li>
<li><p>建立持久聊天伺服器存放區的 SQL Server 資料庫（以及災害復原的備份 SQL Server）</p></li>
<li><p>定義新的 Lync 檔案存放區，或使用現有的 Lync 檔案存放區儲存持久聊天伺服器檔案</p></li>
<li><p>將可傳送要求的 Lync Server 2013 池與此持續聊天伺服器池建立關聯</p></li>
</ul>
<p>如果需要持續聊天合規性：</p>
<ul>
<li><p>新增持久聊天合規性存放區</p></li>
<li><p>按一下 [持續聊天伺服器池定義] 核取方塊以啟用合規性</p></li>
<li><p>發行拓撲</p></li>
</ul>
<p>如果您在標準版上安裝持續式聊天伺服器，則持久性聊天伺服器池的完整功能變數名稱（FQDN）必須符合標準版伺服器，且 SQL Server 資料庫在標準版的 SQL Server Express 實例上是 collocated 的。Edition 伺服器</p></td>
<td><p>若要定義拓撲，該帳戶是 [本機使用者] 群組的成員。</p>
<p>若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，而且使用者在 Lync 檔案存放區上也應該有完整的控制許可權（讀取/寫入/修改），以取得持續聊天伺服器檔案（讓拓撲產生器可以設定所需的 Dacl）。</p></td>
<td><p>在部署檔的<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增持久聊天伺服器到您的部署</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>部署常設聊天室伺服器</strong></p></td>
<td><p>在執行永久聊天伺服器的所有電腦上執行 Lync Server 設定。 [永久聊天伺服器] 安裝程式已整合至 Lync Server 2013 部署嚮導，並提供下列指示：</p>
<ul>
<li><p>部署本機管理存放區</p></li>
<li><p>安裝永久性聊天伺服器服務</p></li>
<li><p>要求並指派憑證</p></li>
<li><p>執行並啟動服務</p></li>
</ul></td>
<td><p>屬於本機管理員群組成員的任何使用者。</p></td>
<td><p>部署檔中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 部署持續聊天伺服器</a></p></td>
</tr>
<tr class="even">
<td><p><strong>建立常設聊天室系統管理員</strong></p></td>
<td><p>將使用者新增至 CsPersistentChatAdministrator 安全性群組。</p></td>
<td><p>屬於網域管理員成員的任何使用者。</p></td>
<td><p>在部署檔的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 中新增持續性聊天系統管理員</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>設定常設聊天室伺服器</strong></p></td>
<td><p>設定使用者：</p>
<ul>
<li><p>使用者必須由原則啟用，才能存取持久聊天伺服器。 根據預設，對於所有使用者而言，原則都是關閉的，而且可以在全域/網站/池/使用者範圍中定義。</p></li>
<li><p>設定設定</p></li>
</ul></td>
<td><p>使用者必須是 CsPersistentChatAdministrator 的成員。 若要變更原則，使用者至少必須在 CsUserAdministrator 中。</p></td>
<td><p>在部署檔中的<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 中設定持續聊天伺服器</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 您可以部署一或多個持久聊天伺服器池。 我們支援多個持續聊天伺服器池，以確保在指定區域中產生的資料必須留在該區域。 例如，如果您是在芝加哥部署持續式聊天伺服器池，而另一個是在蘇黎世中遵守瑞士資料的規章，使用者只要有存取權，就能連線到持久性聊天伺服器池中的聊天室。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

