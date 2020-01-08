---
title: Lync Server 2013：為聊天室設定增益集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中為聊天室設定增益集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [**永久聊天**] 頁面上的**增益集**區段，將 url 與持續聊天室建立關聯。 這些 Url 會出現在 [交談擴充性] 窗格的 [聊天室] 中的 [Lync 2013 用戶端] 中。 系統管理員必須在已註冊的增益集清單中新增增益集，且聊天室管理員/創意者必須將會議室與其中一個已註冊的增益集建立關聯，才能讓使用者在他們的 Lync 2013 用戶端中看到此升級。

增益集可擴充聊天室體驗。 典型的增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號張貼到聊天室時截獲，並在 [擴充性] 窗格中顯示股票歷程記錄。 其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>設定聊天室的增益集

1.  使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [增益集]****。
    
    如果有多個持續聊天伺服器池部署，請從下拉式清單中選取適當的 [資源]。

4.  在 [增益集]**** 頁面上，按一下 [新增]****。

5.  在 [**選取服務**] 中，選取與您需要建立增益集的持續聊天伺服器池相對應的服務。 增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。

6.  在 [新增增益集]**** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新增益集的名稱。
    
      - 在 [URL]**** 中，指定要與增益集建立關聯的 URL。URL 限為 http 和 https 通訊協定。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  


[使用 Windows PowerShell Cmdlet 設定常設聊天室伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

