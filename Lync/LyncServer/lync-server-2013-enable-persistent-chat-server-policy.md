---
title: Lync Server 2013：啟用常設聊天室伺服器原則
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
ms.openlocfilehash: 27d87277c813c24ae36de14430bc711d991d7181
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>在 Lync Server 2013 中啟用常設聊天室伺服器原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [**永久**聊天] 群組的 [**持續聊天原則**] 頁面，管理全域、池、網站或使用者層級的原則，包括設定預設全域原則，並為您的部署建立一或多個額外的使用者和網站原則。 如果使用者依原則啟用持久聊天伺服器，則會在其 Lync 2013 用戶端中顯示持續聊天伺服器的環境。

<div>


> [!NOTE]  
> 在拓撲中，持續式聊天伺服器網站原則會全域、每個使用者的池子或每個使用者的網站，或每個使用者。



</div>

全域原則是在您部署持久聊天伺服器時自動建立，而且可以設定，但不能刪除。 由於全域原則會套用至所有使用者，所以不需要為每個使用者個別設定。

您可以建立及設定多個網站和使用者原則，搭配全域原則，可讓使用者使用持久聊天伺服器。 文件庫和網站持續聊天伺服器原則會覆寫全域持久聊天伺服器原則，但只適用于該網站的使用者。 針對受指派使用原則的使用者，使用者原則會優先於全域、集區和網站原則。

<div>


> [!NOTE]  
> 若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。 如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定常設聊天室的全域原則](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中建立常設聊天室的網站原則](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中建立常設聊天室的使用者原則](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中將常設聊天室原則套用至使用者或使用者群組](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

