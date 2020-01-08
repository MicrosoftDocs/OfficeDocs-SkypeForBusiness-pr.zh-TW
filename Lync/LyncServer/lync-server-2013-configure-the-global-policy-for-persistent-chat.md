---
title: Lync Server 2013：設定常設聊天室的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中設定常設聊天室的全域原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

您可以單獨使用預設的全域原則，為您部署中的所有使用者啟用持續聊天設定。 您也可以為網站和使用者指定其他原則，以控制特定使用者和網站是否已啟用或停用持續性聊天。

您無法刪除全域原則。 如果您嘗試將它刪除，設定就會重設為預設值。

<div>


> [!NOTE]  
> 若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。 如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。<BR>若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>設定持續聊天的全域原則

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱在作業檔中[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。

    
    </div>

3.  在 Lync Server [控制台] 中，按一下 [**持續聊天**]，然後按一下 [**永久聊天原則**]。

4.  按一下原則清單中的 [全域]****，按一下 [編輯]****，然後按一下 [顯示詳細資料]****。

5.  在 [編輯常設聊天室原則 - 全域] **** 中，執行下列動作：
    
      - 如果不想要使用全域的預設設定，請在 [名稱] **** 中指定全域原則的新名稱。
    
      - 在 [**描述**] 中，提供使用者原則的詳細資料（例如，CentralSiteName 的全域原則）。
    
      - 若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的持續聊天，請選取或清除 [**啟用持續聊天**] 核取方塊。

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

