---
title: 遷移程式-詳細資料
description: 遷移程式-詳細資料。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569579"
---
# <a name="migration-process---details"></a>遷移程式-詳細資料

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

使用下列必要條件和詳細步驟，將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、Persistent Chat Server。

<div>

## <a name="prerequisites-for-migration"></a>遷移的必要條件

在將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、Persistent Chat Server 之前，請確定您已符合下列必要條件。

1.  部署至少一個 Lync Server 2013 集區。 如果您有多個 Lync Server 2013 集區，請決定哪個 Lync Server 2013 集區將會成為新 Lync Server 2013 Persistent Chat Server 集區的主集區。

2.  安裝 Lync Server 2013，Persistent Chat Server 集區。  (無類別、會議室或增益集) ，它將會是空的。 在遷移舊版類別、聊天室或增益集之前，您可以在 Lync Server 2013 中建立聊天室、類別或增益集。
    
    <div>
    

    > [!IMPORTANT]  
    > 請注意，這些新建立的專案可能會與您遷移的舊版專案產生衝突。 避免任何命名衝突;否則，在遷移舊版資料時，將會覆寫這些資料。

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>準備要遷移的來來源資料

請執行下列步驟，正確準備您的來來源資料以進行遷移。

1.  備份 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天的來源資料庫。 如需備份 SQL Server 的詳細資訊，請參閱《備份一覽 (SQL Server) 」 <https://go.microsoft.com/fwlink/p/?linkid=254851> 。
    
    <div>
    

    > [!IMPORTANT]  
    > Active Directory 網域服務應該相同。 作為遷移的條件，您無法在不同的 Active Directory 樹系) 中，以不同的部署 (方式遷移至集區。

    
    </div>

2.  檢查您的 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天聊天室和類別設定。 您現有舊版部署中的類別、聊天室或增益集的任何變更，都是由 Group Chat 系統管理工具進行。
    
    <div>
    

    > [!TIP]  
    > Lync server 2013 中的類別、會議室或增益集的任何變更，都是由 Lync Server 控制台或 Windows PowerShell Cmdlet 執行。

    
    </div>
    
    請遵循下列步驟，為遷移準備舊版系統。
    
    1.  Persistent Chat Server 支援單一等級的類別，不同于一組 deep 階層的類別。 遷移後，子類別會以完整的父類別名稱做為首碼。 您可能想要簡化及展隨現有的類別結構，讓產生的結構符合您的需求。
    
    2.  驗證根類別的 **管理員** 。 如果此層級有任何主管，則遷移後，系統會將這些使用者新增為 **管理員** 。 如果這不是組織的必要條件，您必須從 root 類別中移除這些管理員。
    
    3.  驗證會議室名稱的長度。 遷移後，由於簡化的類別結構，如果子類別的聊天室存在，則會以完整的父類別名稱做為加上首碼。 命名限制為256個字元，包含父類別名稱。 您必須確認會議室名稱的長度，而且可能會縮短長度（如果這些名稱過長）。
    
    4.  在 [Lync Server 2013] 中，如果類別 **邀請** 設定設定為 true，您可以選擇 true 或 false，以在該類別下的聊天室邀請。 不過，如果類別邀請設定設定為 false，則該類別下的會議室會關閉邀請。 在遷移之前，您必須重設舊版 Lync Server 群組聊天伺服器版本中的邀請設定（如果您想要讓 () 在特定類別下存在）。 否則，在遷移期間，Lync Server 2013 會顯示警告，並將聊天室的預設值設為 false。
    
    5.  如果您使用聊天室中的檔案，您必須在遷移後，手動將檔案以 XCOPY 方式新增至新的持久聊天檔存放區。 工具不會這麼做。
    
    6.  如果您有同盟使用者與同盟使用者和聊天室，請注意 Persistent Chat Server 不支援同盟。 會遷移具有同盟使用者的聊天室;不過，由於不支援同盟存取，使用者本身將無法存取內容。
    
    7.  識別您不想遷移的聊天室，將其標記為 [已停用]。
    
    8.  識別您想要遷移聊天室內容的日期以外的日期。 例如，您可能不想要遷移超過2010年1月1日的郵件，因為這些郵件可能已過時，或與遷移無關。

</div>

<div>

## <a name="performing-the-migration"></a>執行遷移

請執行下列步驟，以遷移舊版群組聊天伺服器。

1.  關閉 Lync Server 2010、群組聊天、Office 通訊伺服器 2007 R2 群組聊天或 Lync Server 2013、Persistent Chat Server 服務。 所有服務都必須停止，所以計畫在有足夠的停機時間時執行此作業。 如先前所述，請務必備份目前的群組聊天資料庫。

2.  以 Persistent Chat 系統管理員 RBAC 角色的成員身分 (CsPersistentChatAdministrator) 執行 Windows PowerShell **Export-CsPersistentChatData** Cmdlet。 如需匯出/匯入 Cmdlet 的詳細資訊，請參閱 [在 Lync server 2013 中使用 Windows PowerShell Cmdlet 疑難排解 Persistent Chat Server](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。
    
    檢查匯出的內容。

3.  在您準備匯入之前，請關閉 Lync Server 2013，Persistent Chat Server 服務。 所有服務都必須停止，所以規劃若有足夠的停機時間，請執行此動作。

4.  在遷移之前，如果您已在 Lync Server 2013 部署中建立任何類別、聊天室或增益集，請執行 Persistent Chat 資料庫的備份。 匯出/匯入程式可將舊版資料合併至 Lync Server 2013 部署，但是您會想要備份資料庫，以防無意中覆寫內容 (例如，如果仍然存在命名衝突) 。

5.  執行 Windows PowerShell **Import-CsPersistentChatData** Cmdlet (Import tool) ，使用 **WhatIf** 命令，以使用已遷移的資料填入 Persistent Chat Server 集區的後端伺服器。 在處理過程中會進行部分轉換，以容納簡化的管理模型。 修正出現的任何錯誤或警告。

6.  執行 Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** Cmdlet 作為 Persistent CHAT administrator RBAC role 的成員 (CsPersistentChatAdministrator) 。 如需匯出/匯入 Cmdlet 的詳細資訊，請參閱 [在 Lync server 2013 中使用 Windows PowerShell Cmdlet 疑難排解 Persistent Chat Server](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。

7.  您必須將所有上傳的檔案 (整個資料夾中) 新增至新的 Lync Server 2013，Persistent Chat file store。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (用戶端) 不支援上傳或查看聊天室中的檔案。 您仍然可以使用舊版用戶端來開機自檢及查看聊天室中的檔案。

    
    </div>

8.  Port the Lync Server 2010，Group Chat 或 Office 通訊伺服器 2007 R2 Group Chat Lookup Server URI 至 Lync Server 2013，Persistent Chat Server contact 物件。 如果您的 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組聊天用戶端需要連線至最新的 Lync 2013、Persistent Chat (用戶端) 不需要任何用戶端設定變更，則需要下列步驟：
    
      - 刪除 ocschat@ \<domainName\> .Com 查閱伺服器使用者帳戶。 這是用來指向 Lync Server 2010，Group Chat 中的查閱服務。 您可以在稍後卸載集區和移除信任的專案。
    
      - 使用相同的 SIP URI 來執行 Windows PowerShell Cmdlet **New-CsPersistentChatEndpoint**，以建立舊版端點 (Persistent Chat Server contact 物件) ，如此一來，舊版用戶端才能有效地在服務重新開機時運作。
    
    強制執行的遷移程式已完成。 Lync 2010 Group Chat (用戶端) 或 Office Communicator 2007 R2 Group Chat (用戶端) 可以立即連線到新的 Persistent Chat Server 集區。
    
    請遵循下列有關 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天的額外解除的步驟。

9.  開啟新的 Persistent Chat Server 集區中的所有電腦，以啟動 Persistent Chat Server 服務。

10. 使用 Lync Server 控制台和 Windows PowerShell Cmdlet，確認資料已成功遷移。

11. 從群組聊天伺服器集區中的電腦卸載 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組聊天。

12. 使用 Windows PowerShell Cmdlet 刪除受信任的應用程式和信任的應用程式集區。 這會從中央管理存放區中刪除這些專案，以及從 Active Directory (TSEs) 相關聯的信任服務專案。 或者，此步驟的運作方式是使用拓撲產生器 (信任的應用程式/集區有專用的節點，也就是) 。

13. 您現在可以開始透過新用戶端來啟用 Persistent Chat Server 功能。 如需啟用 Persistent Chat Server 的詳細資訊，請參閱 [在 Lync server 2013 中部署 Persistent Chat server](lync-server-2013-deploying-persistent-chat-server.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 支援多個 Persistent Chat Server 集區。 不過，我們支援將 Lync 2010 群組聊天或 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天集區遷移至單一 Lync server 2013，Persistent Chat server 集區。 您可以在部署中新增其他的持久聊天伺服器集區，以符合法規需求 (例如，在指定的地理位置內保留資料) 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

