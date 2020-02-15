---
title: Lync Server 2013： 建立回應群組代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b4f97ad93ecdbfef9e8e170c999f8c9860f830
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>建立回應群組代理群組 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

當您建立代理群組時，需要選取指派給該群組的代理，並指定額外的群組設定，例如路由方法以及代理是否可以登入和登出群組。

使用者必須登入內外的群組中，也就是不同於簽署或退出 Lync Server，代理程式稱為*正式代理程式*。 正式代理必須先登入此群組，才可以接聽路由傳送到此群組的電話。 對於以兼職身分接聽群組來電的代理而言，這可能相當實用。 正式代理程式登入出其群組]，即可開啟 [Windows Internet Explorer 網際網路瀏覽器，並顯示網頁主控台 Lync 2013 中的功能表項目。

未登入或登出群組的代理人稱為 *「非正式代理人」*。 非正式代理程式會自動登入至群組時登入 Lync Server，以及他們無法登出群組。

<div>


> [!NOTE]  
> 只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

[建立或修改 Lync Server 2013 中的代理程式群組](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

