---
title: Lync Server 2013：管理回應群組代理程式群組
description: Lync Server 2013：管理回應群組代理程式群組。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23a4f430981689f9794c05aa1472ff61cd32cd5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569389"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>在 Lync Server 2013 中管理回應群組代理群組

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

代理人群組是由一組指定用來接聽打給回應群組之電話的人員所組成。當您建立代理人群組時，需要選取指派給該群組的代理人，並指定其他群組設定，例如，路由方法，以及代理人是否可以登入和登出群組。

<div>


> [!NOTE]  
> 使用者必須啟用 Enterprise Voice 才能將其新增至代理人群組。 如需如何為使用者啟用 Enterprise Voice 的詳細資訊，請參閱 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">enable users For Enterprise voice In Lync Server 2013</A>。



</div>

<div>


> [!NOTE]  
> 只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。



</div>

必須登入和登出群組的代理（與 Lync 伺服器登入或登出不同）稱為「 *正式代理程式*」。 正式代理人必須先登入此群組，才可以接聽路由傳送到此群組的電話。 對於以兼職身分接聽群組來電的代理人而言，這可能相當實用。 正式代理程式會按一下 Lync 2013 中的功能表項目，以開啟 Windows Internet Explorer Internet browser 及顯示網頁主控台，以登入和登出其群組。

未登入或登出群組的代理人稱為 *「非正式代理人」*。 非正式代理程式會在登入 Lync Server 時自動登入群組，而且無法登出群組。

<div>


> [!IMPORTANT]  
> 當您將使用者指派為回應群組代理人時，如果他們已啟用隱私權模式，請通知他們需要搜尋 "RGS Presence Watcher" 連絡人並將他們新增到其連絡人清單。已啟用隱私權模式但其連絡人清單中沒有 "RGS Presence Watcher" 的代理人，無法接收到打給回應群組的電話。未啟用隱私權模式的代理人則不受影響。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中建立或修改代理程式群組](lync-server-2013-create-or-modify-an-agent-group.md)

  - [在 Lync Server 2013 中刪除代理群組](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

