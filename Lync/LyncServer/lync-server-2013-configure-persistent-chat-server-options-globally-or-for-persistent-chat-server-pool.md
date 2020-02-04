---
title: Lync Server 2013：以全域方式設定或針對常設聊天室伺服器集區設定常設聊天室伺服器選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86ee77dd34e3a43ea62ac6cffaf4af952b1c447e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>在 Lync Server 2013 中以全域方式設定或針對常設聊天室伺服器集區設定常設聊天室伺服器選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [**永久**聊天] 頁面上的 [**持續聊天**設定] 區段，設定全域聊天設定，並將其套用至所有持續聊天伺服器池，或適用于特定的持續聊天伺服器池。

<div>


> [!NOTE]  
> 若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。 如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>若要全域設定持續聊天選項

1.  使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室設定]****。

4.  在 [**永久聊天**設定] 頁面上，按一下 [**新增]，** 然後按一下 [**網站**設定]。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您想要將設定套用到部署于網站中的所有持續聊天伺服器池，請選擇此選項。 如果您想要將設定套用至特定的持續聊天伺服器池，請按一下 [<STRONG>池</STRONG>設定]。

    
    </div>

5.  在 [**選取網站**] 中，選取要針對持續聊天伺服器網站設定進行設定的網站。

6.  在 [新增常設聊天室設定] **** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新組態設定的名稱。依預設，網站名稱已存在。
    
      - 在 [預設聊天記錄] **** 中，定義在第一次要求時，每個聊天室要處理的聊天訊息數量。依預設，此數量為 30。此為全域預設值，系統管理員可針對每個類別停用聊天記錄。
        
        <div>
        

        > [!IMPORTANT]  
        > Persistent 聊天伺服器會將這些郵件緩存在記憶體中，因此如果您增加這個數位，就會快取其他訊息。 您可以隨時利用搜尋來存取記錄內容。 預設數量只會決定最初連線至聊天室所看到的訊息數量上限。

        
        </div>
    
      - 在 [檔案大小上限 (KB)]**** 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]**** 設定來啟用檔案上傳)。
        
        <div>
        

        > [!IMPORTANT]  
        > 此設定會在伺服器上強制執行，因為自訂應用程式或前一個群組聊天用戶端&nbsp;使用 Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync server 2010，群組聊天可以將檔案張貼到聊天室。 Lync 2013 用戶端沒有檔案上傳/下載功能，因此如果您有純粹的 Lync 2013 部署或 Lync 2013 用戶端，則無法在永久聊天伺服器聊天室中張貼檔案。

        
        </div>
    
      - 在 [參與者更新限制] **** 中選取參與者更新的限制。 持續聊天伺服器會傳送名單資訊（連接到聊天室的人員）給所有參與者，直到連線的使用者數目達到這個數位為止。 此數量預設為 75。 這個限制指示指定房間中的參與者數量超過最大值，而持續聊天伺服器則會停止傳送名單的連線用戶端的名單更新。
    
      - (選用) 在 [聊天室管理 URL] **** 中，選取聊天室管理 URL。這是 Web 自訂聊天室管理的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項留白。設定此 URL 後，系統就會將其作為內部和外部聊天室管理 URL 進行套用。
        
        如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用永久性聊天伺服器軟體發展工具組（SDK）來建立自訂的聊天室管理解決方案，並將 URL 放在這裡。 此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。

7.  按一下 [認可]****。

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>針對特定的持久性聊天伺服器池設定持續聊天選項

1.  使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台]，或開啟瀏覽器視窗，然後輸入系統管理員 URL。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室設定]****。

4.  在 [常設聊天室設定] **** 頁面上，按一下 [新增]****，然後按一下 [集區組態]****。

5.  在 [**選取服務**] 中，選取與持久聊天伺服器池相關聯的服務進行設定。

6.  在 [新增常設聊天室設定] **** 中，執行下列動作：
    
      - 在 [名稱] **** 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。
    
      - 在 [預設聊天記錄] **** 中，定義在第一次要求時，每個聊天室要處理的聊天訊息數量。依預設，此數量為 30。此為全域預設值，系統管理員可針對每個類別停用聊天記錄。
        
        <div>
        

        > [!IMPORTANT]  
        > Persistent 聊天伺服器會將這些郵件緩存在記憶體中，因此如果您增加這個數位，就會快取其他訊息。 您可以隨時利用搜尋來存取記錄內容。 預設數量只會決定最初連線至聊天室所看到的訊息數量上限。

        
        </div>
    
      - 在 [檔案大小上限 (KB)]**** 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]**** 設定來啟用檔案上傳)。
        
        <div>
        

        > [!IMPORTANT]  
        > 此設定會在伺服器上強制執行，因為自訂應用程式或前一個群組聊天用戶端&nbsp;（Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync server 2010，群組聊天）可以張貼檔案至聊天室。 Lync 2013 用戶端沒有檔案上傳/下載功能，因此如果您有純粹的 Lync 2013 部署或 Lync 2013 用戶端，則無法在永久聊天伺服器聊天室中張貼檔案。

        
        </div>
    
      - 在 [參與者更新限制] **** 中選取參與者更新的限制。 持續聊天伺服器會傳送名單資訊（連接到聊天室的人員）給所有參與者，直到連線的使用者數目達到這個數位為止。 此數量預設為 75。 這個限制指示指定房間中的參與者數量超過最大值，而持續聊天伺服器則會停止傳送名單的連線用戶端的名單更新。
    
      - 在 [聊天室管理 URL] **** 中選取聊天室管理 URL。這是 Web 聊天室管理部署的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項保留空白。
        
        如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用永久性聊天伺服器軟體發展工具組（SDK）來建立自訂的聊天室管理解決方案，並將 URL 放在這裡。 此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

