---
title: Lync Server 2013：建立常設聊天室的網站原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be98028bf06c20c82dca98fc3bc20d25e97a94c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中建立常設聊天室的網站原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

針對您已部署的每個網站，您可以建立特定于網站的持久聊天原則。

網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。

<div>


> [!NOTE]  
> 若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。 如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。<BR>若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>建立網站的持續聊天原則

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室原則]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。

    
    </div>

4.  按一下 [新增]****，然後按一下 [站台原則]****。

5.  在 [選取站台] **** 中，按一下要套用原則的網站。

6.  在 [新增常設聊天室原則] **** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新網站原則的名稱 (例如，Redmond)。
    
      - 在 [描述]**** 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。
    
      - 若要控制未特別透過網站原則控制之所有網站的常設聊天室，請選取或清除 [啟用常設聊天室]**** 核取方塊。

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

