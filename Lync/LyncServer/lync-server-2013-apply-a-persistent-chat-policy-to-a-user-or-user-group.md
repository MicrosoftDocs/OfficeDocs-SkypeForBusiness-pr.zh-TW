---
title: Lync Server 2013：將常設聊天室原則套用至使用者或使用者群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2fbed0a752c1bf97bab5a4f67fadf12d8077a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>在 Lync Server 2013 中將常設聊天室原則套用至使用者或使用者群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

如果使用者已啟用 Lync Server 2013，您可以將適當的原則套用至特定的使用者，以啟用或停用持久聊天伺服器。

<div>


> [!NOTE]  
> 若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。 如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。<BR>若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。



</div>

使用本主題中的程式，將先前建立的持續聊天使用者原則套用至一或多個使用者帳戶或使用者群組。

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>若要將持續性聊天使用者原則套用到使用者帳戶

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [使用者]****，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [**永久聊天原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的持久聊天使用者原則。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設的有效原則。 伺服器會自動套用這些設定。

    
    </div>

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

