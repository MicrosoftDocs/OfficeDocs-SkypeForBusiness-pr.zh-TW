---
title: Lync Server 2013：全域設定或針對 Persistent Chat Server 集區設定持久聊天伺服器選項
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
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520460"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>在 Lync Server 2013 中全域設定或針對 Persistent Chat Server 集區設定 Persistent Chat Server 選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 [Lync Server 2013 控制台] 中，您可以使用 [**持續性聊天**] 頁面的 [**持續聊天**設定] 區段，設定全域聊天設定，其適用于所有持久聊天伺服器集區，或特定 Persistent chat server 集區。

<div>


> [!NOTE]  
> 若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>若要以全域方式設定持久聊天選項

1.  使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室組態]****。

4.  在 [ **Persistent Chat Configuration** ] 頁面上，按一下 [ **新增]，** 然後按一下 [ **網站**設定]。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您想要將設定套用至網站中部署的所有 Persistent Chat Server 集區，請選擇此選項。 若要將設定套用至特定的 Persistent Chat Server 集區，請按一下 [ <STRONG>集</STRONG> 區設定]。

    
    </div>

5.  在 [ **選取網站**] 中，選取要為 Persistent Chat Server Site configuration 設定的網站。

6.  在 [新增常設聊天室組態]**** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新組態設定的名稱。依預設，網站名稱已存在。
    
      - 在 [預設聊天記錄]**** 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。
        
        <div>
        

        > [!IMPORTANT]  
        > Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。 您可以隨時利用搜尋來存取記錄內容。 預設數目只會決定最初連線至聊天室所看到的訊息數目上限。

        
        </div>
    
      - 在 [檔案大小上限 (KB)]**** 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]**** 設定來啟用檔案上傳)。
        
        <div>
        

        > [!IMPORTANT]  
        > 由於自訂應用程式或先前群組聊天用戶端使用 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，群組聊天可將檔案張貼至聊天室，因此會在伺服器上強制執行此設定。 Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。

        
        </div>
    
      - 在 [參與者更新限制]****，選取參與者更新的限制。 Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。 此數目預設為 75。 此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。
    
      - (選用) 在 [聊天室管理 URL]****, 中，選取聊天室管理 URL。這是 Web 聊天室部署的 URL。如果您不需要自訂聊天室管理，而直接使用預設設定，請將此選項留白。設定好此 URL 之後，其就會套用至內部和外部聊天室管理 URL。
        
        如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。 此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。

7.  按一下 [認可]****。

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>設定特定 Persistent Chat Server 集區的持續聊天選項

1.  使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  從 [ **開始** ] 功能表中，選取 [Lync Server 控制台]，或開啟瀏覽器視窗，然後輸入管理 URL。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [常設聊天室組態]****。

4.  在「常設聊天室組態」**** 頁面上，按一下 [新增]****，然後按一下 [集區組態]****。

5.  在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。

6.  在 [新增常設聊天室組態]**** 中，執行下列動作：
    
      - 在 [名稱]**** 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。
    
      - 在 [預設聊天記錄]**** 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。
        
        <div>
        

        > [!IMPORTANT]  
        > Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。 您可以隨時利用搜尋來存取記錄內容。 預設數目只會決定最初連線至聊天室所看到的訊息數目上限。

        
        </div>
    
      - 在 [檔案大小上限 (KB)]**** 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]**** 設定來啟用檔案上傳)。
        
        <div>
        

        > [!IMPORTANT]  
        > 由於自訂應用程式或先前群組聊天用戶端 (Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，所以群組聊天) 可以在聊天室中張貼檔案，因此會在伺服器上強制執行此設定。 Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。

        
        </div>
    
      - 在 [參與者更新限制]****，選取參與者更新的限制。 Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。 此數目預設為 75。 此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。
    
      - 在 [聊天室管理 URL]**** 中，選取聊天室管理 URL。這是 Web 型聊天室管理部署的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項保留空白。
        
        如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。 此 URL 會接著傳送至下游用戶端，因此，當使用者嘗試檢視/建立聊天室時，則會將使用者其導向至您的自訂聊天室管理解決方案。

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

