---
title: Lync Server 2013： 容錯回復常設聊天室伺服器
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
ms.openlocfilehash: 1da806e476635543e0afeafee8b7c195cf21cfc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>容錯回復 Lync Server 2013 中的常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

此程序概要說明從 Persistent Chat Server 失敗，復原，並重新建立從主要資料中心作業的必要步驟。

常設聊天室伺服器失敗期間的主要資料中心遭受完全中斷與主要和鏡像資料庫變成無法使用。 主要資料中心會容錯移轉至備份伺服器。

在備份主要資料中心，及重建伺服器後，下列程序會還原正常作業。 此程序假設主要資料中心已從總中斷中復原和，mgc 資料庫 mgccomp 資料庫已重建並重新安裝使用拓撲產生器。

此程序也假設沒有新的鏡像和備份伺服器已部署在容錯移轉期間，且部署的唯一伺服器為備份伺服器和及其鏡像伺服器，[容錯 over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md)中所定義。

災難導致主要伺服去失敗，作業轉移至備份伺服器，因為災難發生前設定就存在，設計這些步驟就是用來還原設定。

<div>

## <a name="to-fail-back-persistent-chat-server"></a>容錯回復常設聊天室伺服器

1.  清除 [常設聊天室伺服器作用中的伺服器] 清單中的所有伺服器使用`Set-CsPersistentChatActiveServer`從 Lync Server 管理命令介面指令程式。 如此將會停止所有常設聊天室伺服器無法連線至 mgc 資料庫，以及 mgccomp 資料庫容錯回復期間。
    
    <div>
    

    > [!IMPORTANT]  
    > 次要資料庫上的 SQL Server 代理程式常設聊天室伺服器後端伺服器應該執行的特殊權限的帳戶。 具體來說，帳戶必須包括： 
    > <UL>
    > <LI>
    > <P>對備份所在位置之網路共用的讀取存取權。</P>
    > <LI>
    > <P>對備份複製目的位置之特定本機目錄的寫入存取權。</P></LI></UL>

    
    </div>

2.  停用備份 MGC 資料庫上的鏡像：
    
    1.  使用 SQL Server Management Studio，連線至備份 mgc 執行個體。
    
    2.  用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[鏡像]**。
    
    3.  按一下 **[移除鏡像]**。
    
    4.  按一下 **[確定]**。
    
    5.  使用 Mgccomp 資料庫執行相同步驟。

3.  備份 MGC 資料庫以便將其還原至新的主要資料庫：
    
    1.  使用 SQL Server Management Studio，連線至備份 mgc 執行個體。
    
    2.  用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[備份]**。**[備份資料庫]** 對話方塊隨即顯示。
    
    3.  在 **[備份類型]** 中選取 **[完整]**。
    
    4.  針對 **[備份元件]** 按一下 **[資料庫]**。
    
    5.  接受 **[名稱]** 中建議的預設備份組名稱，或為備份組輸入不同名稱。
    
    6.  *\<選用\>* 在 [**描述**] 中，輸入備份組的描述。
    
    7.  從目的地清單移除預設備份位置。
    
    8.  使用您為記錄傳送建立的共用位置路徑來將檔案新增至清單。主要資料庫和備份資料庫均可使用此路徑。
    
    9.  按一下 **[確定]** 以關閉對話方塊並開始備份程序。

4.  使用先前步驟中建立的備份資料庫來還原主要資料庫。
    
    1.  使用 SQL Server Management Studio，連線至主要 mgc 執行個體。
    
    2.  以滑鼠右鍵按一下 MGC 資料庫，依序指向 **[工作]** 和 **[還原]**，然後按一下 **[資料庫]**。**[還原資料庫]** 對話方塊隨即顯示。
    
    3.  選取 **[來源裝置]**。
    
    4.  按一下開啟 **[指定備份]** 對話方塊的 [瀏覽] 按鈕。在 **[備份媒體]** 中，選取 **[檔案]**。按一下 **[新增]**，選取您在步驟 3 中建立的備份檔案，然後按一下 **[確定]**。
    
    5.  在 **[選取要還原的備份組]** 中選取備份。
    
    6.  在 **[選取頁面]** 窗格中按一下 **[選項]**。
    
    7.  在 **[還原選項]** 中選取 **[覆寫現有資料庫]**。
    
    8.  在 **[復原狀態]** 中選取 **[讓資料庫保持備妥可用]**。
    
    9.  按一下 **[確定]** 開始復原程序。

5.  設定 SQL Server 記錄傳送的主要資料庫。 請遵循[Configuring Persistent Chat Server 的高可用性和災害復原 Lync Server 2013 中的](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)，以建立主要 mgc 資料庫的記錄傳送中的程序。

6.  設定作用中 Persistent Chat Server 的伺服器。 從 Lync Server 管理命令介面中，使用**Set-cspersistentchatactiveserver** cmdlet 可設定的作用中的伺服器清單。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。

    
    </div>

還原為正常狀態的集區執行下列 Windows PowerShell 命令：

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

請參閱如需詳細資訊[Set-cspersistentchatstate](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

