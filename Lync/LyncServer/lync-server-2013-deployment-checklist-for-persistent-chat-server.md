---
title: 'Lync Server 2013: Persistent Chat Server 的部署檢查清單'
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
ms.openlocfilehash: a67d8a755a5647424a00aa7e534f736a4c0b5aa3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Persistent Chat Server in Lync Server 2013 的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10-16_

部署 Lync Server 2013，Persistent Chat Server 需要您將它部署以正確的順序，以及您完成所有必要的部署步驟。

<div>

## <a name="deployment-sequence"></a>部署順序

在部署初始拓撲，包括至少一個 Lync Server 2013 中，前端集區或一 Lync Server 2013 Standard Edition server 之後，您可以部署 Persistent Chat Server。 本主題說明如何部署常設聊天室伺服器新增至現有的部署。

</div>

<div>

## <a name="deployment-process"></a>部署程序

下表列出部署常設聊天室伺服器的基本步驟，並提供連結如需詳細資訊。

### <a name="persistent-chat-server-deployment-process"></a>常設聊天室伺服器部署程序

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
<li><p>在 [常設聊天室伺服器前端伺服器：</p></li>
</ul>
<ul>
<li><p>符合系統需求的作業系統</p></li>
<li><p>執行 Lync Server 2013 的電腦的軟體先決條件</p></li>
<li><p>在將主控 Persistent Chat Server 資料庫的伺服器上的 SQL Server</p></li>
</ul>
<p>如果需要常設聊天室伺服器規範：</p>
<ul>
<li><p>將裝載常設聊天室伺服器規範資料庫的伺服器上的 SQL Server</p></li>
</ul></td>
<td><p>使用屬於本機 Administrators 群組的任何使用者。</p></td>
<td><p>支援文件中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a></p>
<p>支援文件中的 [ <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">決定您的 Lync Server 2013 的系統需求</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Persistent Chat Server in Lync Server 2013 的技術需求</a></p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓撲以支援 Persistent Chat Server （並選擇性地常設聊天室規範）</strong></p></td>
<td><p>執行拓撲產生器來將 Persistent Chat Server 集區新增至您的拓撲：</p>
<ul>
<li><p>Persistent Chat Server 元件新增至拓撲</p></li>
<li><p>建立 SQL Server 資料庫 Persistent Chat Server 儲存區 （及嚴重損壞修復備份 SQL Server）</p></li>
<li><p>定義新的 Lync 檔案存放區，或使用現有的 Lync 檔案存放區 Persistent Chat Server 檔案</p></li>
<li><p>建立可以將要求路由傳送到此 Persistent Chat Server 集區的 Lync Server 2013 集區的關聯</p></li>
</ul>
<p>如果需要常設聊天室規範：</p>
<ul>
<li><p>新增常設聊天室規範存放區</p></li>
<li><p>按一下 [常設聊天室伺服器集區定義核取方塊，來啟用規範</p></li>
<li><p>發行拓撲</p></li>
</ul>
<p>如果您在 Standard Edition 上安裝 Persistent Chat Server，Persistent Chat Server 集區的完整的網域名稱 (FQDN) 必須符合 Standard Edition server，並在標準的 SQL Server Express 執行個體上組合的 SQL Server 資料庫Edition 伺服器</p></td>
<td><p>若要定義拓樸，屬於本機 Users 群組帳戶。</p>
<p>若要發行拓樸，屬於 Domain Admins 群組和 RTCUniversalServerAdmins 群組，以及使用者帳戶應該也具備完全控制權限 （讀取/寫入/修改） Persistent Chat Server 檔案 Lync 檔案存放區 （以便拓撲產生器可以設定必要的 Dacl）。</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">新增常設聊天室伺服器的 Lync Server 2013 部署</a>中部署文件</p></td>
</tr>
<tr class="odd">
<td><p><strong>部署常設聊天室伺服器</strong></p></td>
<td><p>在執行 Persistent Chat Server 的所有電腦上執行 Lync Server 安裝程式。 Persistent Chat Server 安裝程式已整合至 Lync Server 2013 部署精靈，可提供下列指示：</p>
<ul>
<li><p>部署本機管理存放區</p></li>
<li><p>安裝 Persistent Chat Server 服務</p></li>
<li><p>要求並指派憑證</p></li>
<li><p>執行及啟動服務</p></li>
</ul></td>
<td><p>使用屬於本機 Administrators 群組的任何使用者。</p></td>
<td><p>部署文件中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>建立常設聊天室管理員</strong></p></td>
<td><p>將使用者新增至 CsPersistentChatAdministrator 安全性群組。</p></td>
<td><p>屬於網域 administrators 成員的任何使用者。</p></td>
<td><p>部署文件中的 [<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">新增 Lync Server 2013 常設聊天室管理員</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>設定常設聊天室伺服器</strong></p></td>
<td><p>設定使用者：</p>
<ul>
<li><p>使用者已啟用原則，才能存取 Persistent Chat Server。 依預設，此原則已關閉的所有使用者，並可以定義於全域/網站/集區/使用者範圍。</p></li>
<li><p>進行設定</p></li>
</ul></td>
<td><p>使用者必須是 CsPersistentChatAdministrator 的成員。 若要變更原則，使用者必須在 CsUserAdministrator，在最低限度下。</p></td>
<td><p>部署文件中的<a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 您可以部署一個或多個 Persistent Chat Server 集區。 我們基於法規的原因： 在特定區域所產生的資料，才能留在該區域支援多個 Persistent Chat Server 集區。 例如，如果您部署中芝加哥，Persistent Chat Server 集區，另一個 Zurich 遵守法規瑞士中的資料中，使用者可以連線至兩個 Persistent Chat Server 集區中的會議室提供他們具有其存取。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

