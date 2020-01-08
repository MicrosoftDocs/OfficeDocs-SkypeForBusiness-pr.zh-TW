---
title: Lync Server 2013：還原企業版後端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中還原企業版後端伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

在下列兩種情況下，請使用本主題中所述的程式：

  - 鏡像企業版 Server 後端伺服器的主要和鏡像資料庫都會失敗。

  - 無法鏡像的企業版後端伺服器失敗。

如果您擁有鏡像的企業版版本後端，且只有鏡像或主資料庫發生故障，請參閱[在 Lync server 2013 中還原鏡像的企業版後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)是還原主要資料庫，以及[在 Lync Server 2013 中還原鏡像企業版後端伺服器-鏡像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)以還原鏡像。

如果中央管理儲存區失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是後端伺服器的企業版成員伺服器失敗，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

<div>


> [!TIP]  
> 我們建議您先取得系統的影像複本，然後再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生的問題。 您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>若要還原企業版後端伺服器

1.  從包含與失敗電腦相同的完整功能變數名稱（FQDN）的乾淨或新伺服器開始，安裝作業系統，然後還原或重新註冊證書。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程式來執行此步驟。

    
    </div>

2.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  安裝 SQL Server 2012 或 SQL Server 2008 R2，讓實例名稱保持與失敗前相同。
    
    <div>
    

    > [!NOTE]  
    > 根據您的部署，後端伺服器可能會包含多個 collocated 或個別的資料庫。 遵循相同的程式，安裝您最初用來部署伺服器的 SQL Server，包括 SQL Server 許可權和登錄名。

    
    </div>

4.  安裝 SQL Server 之後，請執行下列動作：
    
    1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
    2.  按一下 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。
    
    3.  選取拓撲，然後按一下 [**儲存**]。 按一下 **[是]** 以確認您的選取專案。
    
    4.  以滑鼠右鍵按一下**Lync Server 2013**節點，然後按一下 [**發佈拓撲**]。
    
    5.  遵循 [**發佈拓撲**嚮導]。 在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。
        
        <div>
        

        > [!NOTE]  
        > [<STRONG>建立資料庫</STRONG>] 頁面上只會顯示獨立的資料庫。

        
        </div>
    
    6.  如果您要還原已鏡像的後端，請繼續追蹤其餘的嚮導，直到出現提示**建立鏡像資料庫**為止。 選取您要安裝的資料庫，並完成程式。
    
    7.  依照嚮導的其餘部分進行，然後按一下 **[完成**]。
    
    <div>
    

    > [!TIP]  
    > 您可以使用<STRONG>CsDatabase</STRONG> Cmdlet 來建立每個資料庫，以及<STRONG>安裝 CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不需要執行拓撲建立器。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

    
    </div>

5.  若要還原使用者資料，請執行下列動作：
    
    1.  從 $Backup\\將 ExportedUserData 複製到本機目錄。
    
    2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。
    
    3.  您必須先停止 Lync services，才能還原使用者資料。 若要這麼做，請輸入：
        
            Stop-CsWindowsService
    
    4.  若要還原使用者資料，請在命令列輸入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  輸入以下內容以重新開機 Lync Services：
        
            Start-CsWindowsService

6.  如果您已在此池中部署回應群組，請還原回應群組設定資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。

7.  如果您要還原包含封存或監視資料庫的後端伺服器，請使用 SQL Server 工具（例如 SQL Server Management Studio）還原存檔或監視資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原監視或封存資料](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

