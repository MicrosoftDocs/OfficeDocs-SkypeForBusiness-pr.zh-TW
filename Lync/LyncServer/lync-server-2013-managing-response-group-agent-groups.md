---
title: Lync Server 2013：管理回應群組代理程式群組
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
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>在 Lync Server 2013 中管理回應群組代理群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[代理人] 群組由一組指派給回應群組的人員所組成。 當您建立 [代理群組] 時，請選取指派給群組的 agent，並指定其他群組設定，例如路由方法，以及代理程式是否可以登入和登出群組。

<div>


> [!NOTE]  
> 使用者必須先啟用企業語音，才能將其新增至代理群組。 如需如何啟用企業語音的使用者的詳細資料，請參閱<A href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中啟用企業語音的使用者</A>。



</div>

<div>


> [!NOTE]  
> 只有內部部署使用者可以使用代理程式。 如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。



</div>

必須登入和登出群組的代理程式（與登入或登出 Lync Server 不同）稱為*正式代理程式*。 正式的代理程式必須先登入群組，才能接收路由到群組的呼叫。 此功能對從群組接聽通話的工程師很有用。 正式的代理程式可在 Lync 2013 中按一下功能表項目來登入和登出其群組，以開啟 Windows Internet Explorer Internet 瀏覽器，並顯示網頁主控台。

未登入或登出群組的工程師稱為*非正式代理*程式。 非正式的代理程式會在登入 Lync Server 時自動登入該群組，且無法登出群組。

<div>


> [!IMPORTANT]  
> 當您將使用者指派為回應群組代理程式時，如果他們已啟用隱私權模式，就必須搜尋「RGS 目前狀態觀察程式」連絡人，然後將他們新增到他們的連絡人清單。 已啟用隱私權模式的代理，但其 [連絡人] 清單中沒有「RGS 目前狀態觀察程式」，就無法接收回應群組的呼叫。 未啟用隱私權模式的代理不會受到影響。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中建立或修改代理群組](lync-server-2013-create-or-modify-an-agent-group.md)

  - [刪除 Lync Server 2013 中的代理群組](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

