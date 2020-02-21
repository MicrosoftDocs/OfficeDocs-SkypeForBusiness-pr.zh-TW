---
title: Lync Server 2013： 啟用常設聊天室伺服器原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bfc0f8ed1160d29eb68fc00172c77b466692327
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>啟用 Lync Server 2013 中的常設聊天室伺服器原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

在 Lync Server 2013 控制台中，您可以使用 [**常設聊天室原則**] 頁面上的 [**常設聊天室**] 群組來管理在全域、 集區、 網站或使用者層級，包括設定預設的全域原則，並建立一或多個額外的使用者與您的部署的網站原則的原則。 Persistent Chat Server 啟用使用者的原則，然後 Persistent Chat Server 的環境會出現在其 Lync 2013 用戶端。

<div>


> [!NOTE]  
> 在拓撲中，具有全面性的 Persistent Chat Server 網站原則套用每個使用者的集區，或每個使用者的網站，或每位使用者。



</div>

當您部署 Persistent Chat Server，並設定，但不是會刪除時，會自動建立的全域原則。 由於全域原則會套用至所有使用者，所以不需要為每個使用者個別設定。

您可以建立及設定多個網站與使用者原則，以及全域原則，讓使用者 for Persistent Chat Server。 集區與站台 Persistent Chat Server 原則會覆寫全域常設聊天室伺服器原則，但僅會針對該網站的使用者。 對於獲指派指使用原則的使用者，使用者原則會優先於其全域、集區和網站原則。

<div>


> [!NOTE]  
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器將 Persistent Chat Server 支援新增至拓撲，並再發行拓撲。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">新增 Persistent Chat Server 至 Lync Server 2013 中部署</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [針對常設聊天室 Lync Server 2013 中設定的全域原則](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [常設聊天室 Lync Server 2013 中建立的網站原則](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [針對常設聊天室 Lync Server 2013 中建立使用者原則](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [常設聊天室原則套用至使用者或 Lync Server 2013 中的使用者群組](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

