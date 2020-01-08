---
title: 移轉程序 - 詳細資料
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>移轉程序 - 詳細資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

使用下列先決條件及詳細步驟，將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、持續聊天伺服器。

<div>

## <a name="prerequisites-for-migration"></a>遷移的先決條件

在將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、持續聊天伺服器前，請確定您已符合下列先決條件。

1.  部署至少一個 Lync Server 2013 池。 如果您有多個 Lync Server 2013 池，請決定將哪個 Lync Server 2013 池作為新 Lync Server 2013 持久性聊天伺服器池的主池。

2.  安裝 Lync Server 2013，持續聊天伺服器池。 它將會是空白（無類別、會議室或增益集）。 在您遷移舊版類別、會議室或增益集之前，您可以在 Lync Server 2013 （持久的聊天伺服器部署）中建立會議室、類別或增益集。
    
    <div>
    

    > [!IMPORTANT]  
    > 請注意，這些新建立的專案可能會與您遷移的舊版專案發生衝突。 避免任何命名衝突;否則，當您遷移舊版資料時，會覆寫這些資料。

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>準備來源資料以供遷移

請執行下列步驟，以正確準備您的來來源資料以供遷移。

1.  針對 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天備份源資料庫。 如需有關備份 SQL Server 的詳細資訊，請參閱「備份概述（SQL Server <http://go.microsoft.com/fwlink/p/?linkid=254851>）」。
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory 網域服務應該是相同的。 做為遷移的條件，您無法在不同的部署（尤其是在不同的 Active Directory 林中）遷移到某個池。

    
    </div>

2.  檢查您的 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天聊天室和類別設定。 您現有舊版部署中的類別、會議室或增益集的任何變更都將由群組聊天系統管理工具來完成。
    
    <div>
    

    > [!TIP]  
    > Lync Server 2013 中的類別、會議室或增益集的任何變更，都是由 Lync Server 的 [控制台] 或 [Windows PowerShell Cmdlet] 執行。

    
    </div>
    
    請依照下列步驟，為您的舊版系統做好遷移準備。
    
    1.  永久聊天伺服器支援單一等級的類別，不像一組深階層的類別。 遷移之後，子類別會以完整的父類別名稱作為首碼。 您可能會想要簡化並拼合現有的類別結構，讓產生的結構符合您的需求。
    
    2.  驗證根類別的**管理員**。 如果此階層有任何管理員，則在遷移之後，這些使用者會被新增為系統**管理員所有的會議室**。 如果這不是貴組織的需求，您必須從 root 類別中移除這些管理員。
    
    3.  確認會議室名稱的長度。 遷移之後，由於簡化的類別結構，如果該會議室存在於子類別底下，則其會以完整的父類別名稱作為首碼。 命名限制是256個字元，包括父類別名稱。 您必須確認會議室名稱的長度，而且可能會縮短長度（如果太長的話）。
    
    4.  在 Lync Server 2013 中，如果 [類別**邀請**] 設定設為 true，您可以選擇 [true] 或 [false]，以在該類別下的會議室進行邀請。 不過，如果 [類別邀請] 設定設為 [false]，該類別下的會議室會關閉邀請。 在遷移之前，您必須先重設舊版 Lync 伺服器群組聊天伺服器版本中的邀請設定（如果您想要在特定類別中存在會議室）。 否則，在遷移期間，Lync Server 2013 會顯示警告，並將房間設定為預設值 false。
    
    5.  如果您使用的是聊天室中的檔案，您必須在遷移之後，將檔案手動儲存至新的持久聊天檔案存放區。 工具不會執行此動作。
    
    6.  如果您有同盟使用者和聯盟使用者的聊天室，請注意持續聊天伺服器不支援同盟。 將會遷移含聯盟使用者的聊天室;不過，使用者本身將無法存取內容，因為不支援聯盟存取。
    
    7.  找出您不想要遷移的那些聊天室，並將它們標示為 [已停用]。
    
    8.  找出您要將聊天室內容移植到哪個日期之後。 例如，您可能不想要在2010年1月1日之前遷移郵件，因為這些訊息可能已過時或與遷移無關。

</div>

<div>

## <a name="performing-the-migration"></a>執行遷移

請執行下列步驟以遷移舊版群組聊天伺服器。

1.  關閉 Lync Server 2010、群組聊天、Office 通訊伺服器 2007 R2 群組聊天或 Lync Server 2013、持續聊天伺服器服務。 所有服務都必須停止，所以請在有足夠的停機時間時，進行規劃以進行這項作業。 如先前所述，請務必備份您目前的 [群組聊天] 資料庫。

2.  以永久聊天管理員 RBAC 角色（CsPersistentChatAdministrator）的成員身分執行 Windows PowerShell **Export CsPersistentChatData** Cmdlet。 如需匯出/匯入 Cmdlet 的詳細資料，請參閱[在 Lync server 2013 中使用 Windows PowerShell Cmdlet 來疑難排解永久聊天伺服器](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。
    
    檢查匯出的內容。

3.  在您準備好要匯入之前，請先關閉 Lync Server 2013、持續聊天伺服器服務。 所有服務都必須停止，所以請在有足夠的停機時間時，進行規劃以進行這項作業。

4.  如果您已在 Lync Server 2013 部署中建立了任何類別、會議室或增益集，請執行持久聊天資料庫的備份。 匯出/匯入程式將能將舊版資料合併到 Lync Server 2013 部署，但如果不小心覆寫內容，您就會想要備份資料庫（例如，如果命名衝突仍然存在）。

5.  使用 [ **WhatIf** ] 命令執行 Windows PowerShell **Import CsPersistentChatData** Cmdlet （匯入工具），以使用已遷移的資料來填入持久性聊天伺服器池的後端伺服器。 在處理常式中會進行一些轉換，以適應簡化的管理模型。 修正所出現的任何錯誤或警告。

6.  以永久聊天系統管理員 RBAC 角色（CsPersistentChatAdministrator）的成員身分執行永久聊天伺服器 Windows PowerShell 匯**入-CsPersistentChatData** Cmdlet。 如需匯出/匯入 Cmdlet 的詳細資料，請參閱[在 Lync server 2013 中使用 Windows PowerShell Cmdlet 來疑難排解永久聊天伺服器](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。

7.  您必須將所有上傳的檔案（整個資料夾） XCOPY 為新的 Lync Server 2013、永久聊天檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 （用戶端）不支援上傳或查看聊天室中的檔案。 您仍然可以使用舊版用戶端來張貼及查看聊天室中的檔案。

    
    </div>

8.  將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天查閱伺服器 URI 移植至 Lync Server 2013，持續聊天伺服器連絡人物件。 如果您的 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組的聊天用戶端需要連線到最新的 Lync 2013、持續聊天（用戶端），而不需任何用戶端設定變更，就必須執行下列步驟：
    
      - 刪除 ocschat@\<功能變數名稱稱\>[.com 查閱伺服器使用者帳戶]。 這是用來指向 Lync Server 2010 中的查閱服務，群組聊天。 您可以在稍後卸載該池並移除信任的專案。
    
      - 若要建立舊版端點（持久聊天伺服器連絡人物件），請執行具有相同 SIP URI 的 Windows PowerShell Cmdlet （ **CsPersistentChatEndpoint**），讓舊版用戶端能在服務重新開機時有效運作。
    
    強制執行的遷移程式已完成。 Lync 2010 群組聊天（用戶端）或 Office Communicator 2007 R2 群組聊天（用戶端）現在可以透明地連線到新的持續聊天伺服器池。
    
    針對 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天，請遵循這些額外的解除授權步驟。

9.  開啟新的持續聊天伺服器池中的所有電腦，以啟動持續聊天伺服器服務。

10. 使用 Lync Server [控制台] 和 [Windows PowerShell Cmdlet] 驗證資料是否已順利遷移。

11. 從群組聊天伺服器池中的電腦卸載 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組聊天。

12. 使用 Windows PowerShell Cmdlet 刪除受信任的應用程式和受信任的應用程式池。 此選項會從 [中央管理] 存放區及與 Active Directory 中相關聯的信任服務專案（TSEs）刪除這些專案。 或者，此步驟的運作方式是使用 [拓撲建立器] （信任的應用程式/池也有一個專用節點）。

13. 您現在可以透過新的用戶端開始啟用持續聊天伺服器功能。 如需啟用持久聊天伺服器的詳細資料，請參閱[在 Lync server 2013 中部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 支援多個持續聊天伺服器池。 不過，我們支援將 Lync 2010 群組聊天或 Office 通訊伺服器 2007 R2&nbsp;群組聊天池遷移至單一 Lync server 2013、持續聊天伺服器池。 您可以在您的部署中新增其他新的持久性聊天伺服器池，以符合法規需求（例如，將資料保留在指定的地理位置）。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

