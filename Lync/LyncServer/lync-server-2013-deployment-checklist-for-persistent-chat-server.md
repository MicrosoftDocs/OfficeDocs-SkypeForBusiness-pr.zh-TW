---
title: Lync Server 2013： Persistent Chat Server 的部署檢查清單
description: Lync Server 2013： Persistent Chat Server 的部署檢查清單。
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
ms.openlocfilehash: 28d96da5e2961634e6a81450796e5d1ae3426819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568289"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中 Persistent Chat Server 的部署檢查清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

部署 Lync Server 2013，Persistent Chat Server 需要您以正確順序進行部署，而且您已完成所有必要的部署步驟。

<div>

## <a name="deployment-sequence"></a>部署順序

您可以在部署初始拓撲（包括至少一個 Lync Server 2013、前端集區或一部 Lync Server 2013，Standard Edition server）之後，部署 Persistent Chat Server。 本主題說明如何將 Persistent Chat Server 新增至現有的部署。

</div>

<div>

## <a name="deployment-process"></a>部署程式

下表列出部署 Persistent Chat Server 的基本步驟，並提供詳細資訊的連結。

### <a name="persistent-chat-server-deployment-process"></a>Persistent Chat Server 部署程式

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
<th>必要的角色和群組成員資格</th>
<th>相關主題</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備硬體和軟體</strong></p></td>
<td><p>在符合系統需求的硬體上，安裝下列各項：</p>
<ul>
<li><p>在 Persistent Chat Server 前端伺服器上：</p></li>
</ul>
<ul>
<li><p>符合系統需求的作業系統</p></li>
<li><p>執行 Lync Server 2013 之電腦的軟體必要條件</p></li>
<li><p>會裝載 Persistent Chat Server 資料庫之伺服器上的 SQL Server</p></li>
</ul>
<p>如果需要 Persistent Chat Server 規範：</p>
<ul>
<li><p>伺服器上將主控 Persistent Chat Server 規範資料庫的 SQL Server</p></li>
</ul></td>
<td><p>屬於本機 Administrators 群組成員的任何使用者。</p></td>
<td><p>支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></p>
<p>支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">決定 Lync Server 2013 的系統需求</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中 Persistent Chat Server 的技術需求</a></p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓撲以支援 Persistent Chat Server (及（選用）持續性聊天規範) </strong></p></td>
<td><p>執行拓撲產生器，將 Persistent Chat Server 集區新增至您的拓撲：</p>
<ul>
<li><p>將 Persistent Chat Server 元件新增至拓撲</p></li>
<li><p>為 Persistent Chat Server store (和備份 SQL Server 建立 SQL Server 資料庫，以進行嚴重損壞修復) </p></li>
<li><p>定義新的 Lync 檔存放區，或使用現有的 Lync 檔案存放區做為持久聊天伺服器檔案</p></li>
<li><p>關聯可將要求路由傳送至此 Persistent Chat Server 集區的 Lync Server 2013 集區</p></li>
</ul>
<p>如果需要持久聊天規範：</p>
<ul>
<li><p>新增 Persistent 聊天室規範存放區</p></li>
<li><p>按一下 [Persistent Chat Server 集區定義] 核取方塊以啟用相容性</p></li>
<li><p>發行拓撲</p></li>
</ul>
<p>如果您在 Standard Edition 上安裝 Persistent Chat Server，則 Persistent Chat Server 集區的完整功能變數名稱 (FQDN) 必須符合 Standard Edition server，而且 SQL Server 資料庫會在 Standard Edition server 上的 SQL Server Express 實例上組合</p></td>
<td><p>若要定義拓撲，則為本機使用者群組成員的帳戶。</p>
<p>若要發行拓撲，則為 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，而且使用者應在 Lync 檔存放區上 (讀取/寫入/修改) 的「完全控制」許可權，以取得 Persistent Chat Server 檔案 (，讓拓撲產生器可以設定必要的 Dacl) 。</p></td>
<td><p>在部署檔中<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將 Persistent Chat Server 新增至 Lync server 2013</a>中的部署</p></td>
</tr>
<tr class="odd">
<td><p><strong>部署常設聊天室伺服器</strong></p></td>
<td><p>在所有執行 Persistent Chat Server 的電腦上執行 Lync Server 安裝程式。 Persistent Chat Server 安裝程式已整合至 Lync Server 2013 部署嚮導，提供下列指示：</p>
<ul>
<li><p>部署本機管理存放區</p></li>
<li><p>安裝 Persistent Chat Server 服務</p></li>
<li><p>要求並指派憑證</p></li>
<li><p>執行並啟動服務</p></li>
</ul></td>
<td><p>屬於本機 Administrators 群組成員的任何使用者。</p></td>
<td><p>部署檔中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 部署 Persistent Chat Server</a></p></td>
</tr>
<tr class="even">
<td><p><strong>建立常設聊天室系統管理員</strong></p></td>
<td><p>將使用者新增至 CsPersistentChatAdministrator 安全性群組。</p></td>
<td><p>任何屬於網域管理員成員的使用者。</p></td>
<td><p>在部署檔中的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 中新增 Persistent Chat 系統管理員</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>設定 Persistent Chat Server</strong></p></td>
<td><p>設定使用者：</p>
<ul>
<li><p>使用者必須啟用該原則，才能存取 Persistent Chat Server。 根據預設，會為所有使用者關閉原則，並且可以在全域/網站/集區/使用者範圍上定義。</p></li>
<li><p>進行設定</p></li>
</ul></td>
<td><p>使用者必須是 CsPersistentChatAdministrator 的成員。 若要變更原則，使用者至少必須在 CsUserAdministrator 中。</p></td>
<td><p>在部署檔中的<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 中設定 Persistent Chat Server</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 您可以部署一或多個 Persistent Chat Server 集區。 由於法規原因，我們支援多個 Persistent Chat Server 集區，因此需要在特定區域中產生的資料保持在該地區內。 例如，如果您在芝加哥部署了 Persistent Chat Server 集區，而另一個在蘇黎世中遵循的是瑞士的資料法規，只要使用者有存取權，使用者就可以在 Persistent Chat Server 集區中連接至聊天室。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

