---
title: Lync Server 2013：設定持久聊天的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9c4596749e1c4bf4c9f4002b33234c83afa1fd5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中設定持久聊天的全域原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

您可以單獨使用預設全域原則，為部署中的所有使用者啟用 Persistent Chat 設定。 您也可以為網站和使用者指定其他原則，以控制是否啟用或停用特定使用者和網站的持續性聊天。

您無法刪除全域原則。 如果您嘗試刪除，則設定會重設為預設值。

<div>


> [!NOTE]  
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。 如需詳細資訊，請參閱部署檔中的在<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A>。<BR>若要設定 Persistent Chat Server 設定設定，請參閱部署檔中的<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全域或適用于 Lync server 2013 中的 Persistent Chat server 集區的「設定持久聊天伺服器選項</A>」。



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>設定持久聊天的全域原則

1.  使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 Operations 檔中的[Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱部署檔中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。

    
    </div>

3.  在 [Lync Server 控制台] 中，按一下 [ **Persistent chat**]，然後按一下 [ **persistent chat Policy**]。

4.  依序按一下原則清單中的 [全域]****、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [編輯常設聊天室原則 - 全域]**** 中，執行下列動作：
    
      - 如果您不想要使用預設值 [全域]，請在 [名稱]**** 中指定全域原則的新名稱。
    
      - 在 [**描述**] 中，提供 (使用者原則的詳細資訊（例如 centralSiteName) 的全域原則）。
    
      - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的持續性聊天，請選取或清除 [**啟用持續性聊天**] 核取方塊。

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

