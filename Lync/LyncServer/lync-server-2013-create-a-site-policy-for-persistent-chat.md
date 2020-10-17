---
title: Lync Server 2013：建立持久聊天的網站原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0762a7a74e8a88c2ca67e78e5cf2a9f1b032fa15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501870"
---
# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中建立持久聊天的網站原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

您可以針對已部署的每個網站，建立網站特定的持久聊天原則。

網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。

<div>


> [!NOTE]  
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。<BR>若要設定 Persistent Chat Server 設定設定，請參閱部署檔中的 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全域或適用于 Lync server 2013 中的 Persistent Chat server 集區的「設定持久聊天伺服器選項</A> 」。



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>若要建立網站的持續聊天原則

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室原則]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。

    
    </div>

4.  按一下 [新增]****，然後按一下 [站台原則]****。

5.  在 [選取站台]**** 中，按一下要套用該原則的網站。

6.  在 [新增常設聊天室原則]**** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新網站原則的名稱 (例如，Redmond)。
    
      - 在 [描述]**** 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。
    
      - 若要控制未特別透過網站原則控制之所有網站的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。

7.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

