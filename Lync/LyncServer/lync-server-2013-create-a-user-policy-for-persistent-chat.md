---
title: Lync Server 2013：建立持久聊天的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dba93ca943c16caa6ee4982533e59c958e60ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501840"
---
# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中建立持久聊天的使用者原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 [Lync Server 控制台] 中，您可以定義可指派給使用者使用者的使用者**原則。**

使用者原則會覆寫全域與網站原則，但僅限於指派?特定使用者的使用者原則。

<div>


> [!NOTE]  
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。<BR>若要設定 Persistent Chat Server 設定設定，請參閱部署檔中的 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全域或適用于 Lync server 2013 中的 Persistent Chat server 集區的「設定持久聊天伺服器選項</A> 」。



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>若要建立持久聊天的使用者原則

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室原則]****。

4.  按一下 [新增]****，然後按一下 [使用者原則]****。

5.  在 [新增常設聊天室原則]**** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新使用者原則的名稱。
    
      - 在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如，特定使用者) 的持續性聊天原則）。
    
      - 若要控制未特別透過使用者原則控制之所有使用者的持續聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

