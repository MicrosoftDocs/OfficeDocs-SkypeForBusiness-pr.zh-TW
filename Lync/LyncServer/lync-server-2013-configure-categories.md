---
title: Lync Server 2013：設定類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb70397514589ac6f3cc74d84a6ae7509c9baa5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>在 Lync Server 2013 中設定類別

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在 [Lync Server 2013 控制台] 中，您可以使用 [ **Persistent Chat** ] 頁面的 [**類別**] 區段來設定類別。 Persistent 聊天室類別是用來組織聊天室的邏輯結構。 類別會定義一組預設的存取控制清單 (ACLs)，用於控制可建立或加入聊天室的使用者及使用者群組。 您可以利用類別在組織內不同的子部門之間強制執行道德管束。

聊天室類別可包含聊天室，但不可包含其他類別。 每個類別分別說明其內容與中繼資料，例如「名稱」與「描述」。 此外，您可以設定類別中的內容以控制所屬聊天室的行為，例如聊天室是否允許「邀請」或「檔案上傳」，或包含「交談記錄」。

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>設定聊天室的類別

1.  使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 您也可以使用 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱部署檔中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。

    
    </div>

3.  在左導覽列中，按一下 [常設聊天室]****，然後按一下 [類別]****。
    
    若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。

4.  在 **[類別]** 頁面上，按一下 **[新增]** 或 **[編輯]**。

5.  在 [**選取服務**] 中，選取對應至需要建立類別之 Persistent Chat Server 集區的服務。 服務是 persistent chat Server 集區，Persistent Chat (用戶端) 使用它來識別類別所屬的集區。 類別只能隸屬于一部 Persistent Chat Server 集區，無法移至另一個集區，或與另一個集區共用。

6.  在 **[新類別]** 中，執行下列作業：
    
    1.  在 **[名稱]** 中，指定新聊天室類別的名稱。
    
    2.  在 **[描述]** 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。
    
    3.  如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 **[啟用邀請]** 核取方塊。 如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。 如果會議室已開啟邀請，當新成員新增至聊天室時，他或她會在其 Persistent Chat 用戶端中取得新聊天室的通知。
    
    4.  如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 **[啟用檔案上傳]** 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。
        
        <div>
        

        > [!IMPORTANT]  
        > 因為自訂應用程式或舊版群組聊天用戶端使用 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，所以群組聊天可將檔案張貼至聊天室，因此會在伺服器上強制執行此設定。 Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。

        
        </div>
    
    5.  若要控制聊天記錄，請選取或清除 [**啟用聊天記錄**] 核取方塊。 如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。 如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。 這個選項可用於指派給不需要保存交談記錄的即時、臨時共同作業的聊天室。

7.  在 **[編輯類別]** 中，執行下列作業：
    
      - 在 [**成員資格**] 的 [**允許的成員**] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等) ，允許將其新增為屬於類別之聊天室的成員。 類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。
    
      - 在 [**成員資格**] 的 [**拒絕的成員**] 區段中，新增或移除與被聊天室拒絕的成員有關聯的使用者及其他 Active Directory 主體。
    
      - 在 [**成員資格**] 的 [建立**者**] 區段中，新增或移除與類別建立者相關聯的使用者及其他 Active Directory 主體。 建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。

8.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

