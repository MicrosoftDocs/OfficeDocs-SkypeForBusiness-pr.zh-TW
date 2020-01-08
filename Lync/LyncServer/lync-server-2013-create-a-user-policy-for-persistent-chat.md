---
title: Lync Server 2013：建立常設聊天室的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1d2cd767af4cbee7c416dc8f600ed9e9e192a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中建立常設聊天室的使用者原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 Lync Server [控制台] 中，您可以定義可指派給**使用者**使用者的使用者原則。

使用者原則優先於全域與網站原則，但僅限於對其指派該使用者原則的特定使用者。

<div>


> [!NOTE]  
> 若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。 如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。<BR>若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>建立持續聊天的使用者原則

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室原則]****。

4.  依序按一下 [新增]**** 和 [使用者原則]****。

5.  在 [新增常設聊天室原則] **** 中，執行下列動作：
    
      - 在 [名稱] **** 中，指定新使用者原則的名稱。
    
      - 在 [**描述**] 中，提供使用者原則的詳細資料（例如，針對特定使用者的持續聊天原則）。
    
      - 若要控制未透過使用者原則明確控制之所有使用者的持續聊天，請選取或清除 [**啟用持續聊天**] 核取方塊。

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

