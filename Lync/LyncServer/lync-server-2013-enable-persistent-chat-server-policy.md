---
title: Lync Server 2013：啟用 Persistent Chat Server policy
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
ms.openlocfilehash: 794fe378f9e7d8024f4bc06000d6d7d1cd89481e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528570"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 Persistent Chat Server 原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 [Lync Server 2013 控制台] 中，您可以使用**Persistent chat**群組的**持續聊天原則**頁面，管理全域、集區、網站或使用者層級的原則，包括設定預設全域原則，以及為部署建立一或多個額外的使用者和網站原則。 如果使用者依原則啟用 Persistent Chat Server，則 Persistent Chat Server 環境會出現在其 Lync 2013 用戶端中。

<div>


> [!NOTE]  
> 在拓撲中，Persistent Chat Server 網站原則會全域、依使用者的集區或每位使用者的網站或每位使用者來套用。



</div>

當您部署 Persistent Chat Server 時，會自動建立全域原則，而且可以設定，但不能刪除。 由於全域原則會套用至所有使用者，所以不需要為每個使用者個別設定。

您可以建立及設定多個網站和使用者原則，以及全域原則，讓使用者能夠使用 Persistent Chat Server。 Pool 和 site Persistent Chat Server policy 會覆寫全域 Persistent Chat Server policy，但僅限於該網站的使用者。 對於獲指派指使用原則的使用者，使用者原則會優先於其全域、集區和網站原則。

<div>


> [!NOTE]  
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定持久聊天的全域原則](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中建立持久聊天的網站原則](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中建立持久聊天的使用者原則](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [將 Persistent 聊天原則套用至 Lync Server 2013 中的使用者或使用者群組](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

