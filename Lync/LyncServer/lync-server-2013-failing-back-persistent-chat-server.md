---
title: Lync Server 2013：容錯回復常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca00a71c88b917b9e59f2e9039e7960b51f64157
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中容錯回復常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

此程式概述從持續聊天伺服器失敗復原所需的步驟，以及從主要資料中心重新建立作業。

在持續聊天伺服器發生故障期間，主要資料中心會受到完全停機，且主要和鏡像資料庫無法使用。 主要資料中心會容錯移轉至備份伺服器。

下列程式會在主要資料中心重新開機後還原正常作業，且已重建伺服器。 此程式假設主要資料中心已從總停機中復原，且 mgc 資料庫和 mgccomp 資料庫已使用拓撲產生器重建並重新安裝。

此程式也假設在容錯移轉期間沒有部署新的鏡像與備份伺服器，且部署的伺服器是備份伺服器及其鏡像伺服器，如在[Lync server 2013 的 [永久聊天伺服器] 中](lync-server-2013-failing-over-persistent-chat-server.md)定義。

這些步驟的設計目的是要在災難發生之前，復原配置，從而將主要伺服器的容錯移轉到備份伺服器。

<div>

## <a name="to-fail-back-persistent-chat-server"></a>若要自動容錯回復持久聊天伺服器

1.  使用 Lync Server 管理命令介面中的`Set-CsPersistentChatActiveServer` Cmdlet，從 [永久聊天伺服器] 活動伺服器清單中清除 [所有伺服器]。 這會在回切期間停止連線到 mgc 資料庫和 mgccomp 資料庫的所有持久聊天伺服器。
    
    <div>
    

    > [!IMPORTANT]  
    > 次要持續聊天伺服器上的 SQL Server 代理程式應該在特許帳戶下執行。 具體說來，帳戶必須包括： 
    > <UL>
    > <LI>
    > <P>讀取備份所要加入的網路共用的存取權。</P>
    > <LI>
    > <P>寫入要複本備份之特定本機目錄的存取權。</P></LI></UL>

    
    </div>

2.  停用備份 mgc 資料庫上的鏡像：
    
    1.  使用 SQL Server Management Studio，連線至備份 mgc 實例。
    
    2.  以滑鼠右鍵按一下 mgc 資料庫，指向 [**任務**]，然後按一下 [**鏡像**]。
    
    3.  按一下 [**移除鏡像**]。
    
    4.  按一下 [確定]****。
    
    5.  對 mgccomp 資料庫執行相同的步驟。

3.  備份 mgc 資料庫，以便將它還原到新的主資料庫：
    
    1.  使用 SQL Server Management Studio，連線至備份 mgc 實例。
    
    2.  以滑鼠右鍵按一下 mgc 資料庫，指向 [**任務**]，然後按一下 [**備份**]。 [**備份資料庫**] 對話方塊隨即出現。
    
    3.  在 [**備份類型**] 中，選取 [**全**選]。
    
    4.  針對 [**備份元件**]，按一下 [**資料庫**]。
    
    5.  要麼接受**名稱**中建議的預設備份組名稱，要麼為備份組輸入不同的名稱。
    
    6.  * \<選用\> *在 [**描述**] 中，輸入備份組的描述。
    
    7.  從目的地清單移除預設備份位置。
    
    8.  使用您為記錄傳送建立的共用位置路徑，將檔案新增至清單。 這個路徑可供主要資料庫和備份資料庫使用。
    
    9.  按一下 **[確定**] 以關閉對話方塊並開始備份程式。

4.  使用在上一個步驟中建立的備份資料庫來還原主要資料庫。
    
    1.  使用 SQL Server Management Studio，連線到主要的 mgc 實例。
    
    2.  以滑鼠右鍵按一下 mgc 資料庫，指向 [**任務**]，指向 [**還原**]，然後按一下 [**資料庫**]。 [**還原資料庫**] 對話方塊隨即出現。
    
    3.  選取 [**從裝置**]。
    
    4.  按一下 [流覽] 按鈕，即可開啟 [**指定備份**] 對話方塊。 在 [**備份媒體**] 中 **，選取 [** 檔案]。 按一下 [**新增**]，選取您在步驟3中建立的備份檔案，然後按一下 **[確定]**。
    
    5.  在 [**選取要還原的備份組**] 中，選取 [備份]。
    
    6.  按一下 [**選取頁面**] 窗格中的 [**選項**]。
    
    7.  在 [**還原選項**] 中，選取 **[覆寫現有的資料庫**]。
    
    8.  在 [**恢復狀態**] 中，選取 **[讓資料庫可供使用**]。
    
    9.  按一下 **[確定]** 以開始還原程式。

5.  為主要資料庫設定 SQL Server 記錄傳送。 請依照在[Lync server 2013 中設定持久聊天伺服器以取得高可用性和災難復原等](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)程式，為主要的 mgc 資料庫建立記錄傳送。

6.  設定持續聊天伺服器的使用中伺服器。 從 Lync Server 管理命令介面，使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內，或是在具有低延遲/高頻寬連接的資料中心中。

    
    </div>

將池還原至其正常狀態時，請執行下列 Windows PowerShell 命令：

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

如需詳細資訊，請參閱[CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

