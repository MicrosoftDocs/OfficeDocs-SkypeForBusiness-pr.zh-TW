---
title: 還原鏡像的 Enterprise Edition 後端伺服器-主要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c4d942bc4f08c12e2ff63250d1b87807a50963
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

如果您在鏡像設定中有 Enterprise Edition 後端伺服器，且只有主資料庫失敗，請遵循本節中的程式。 如果主資料庫和鏡像都失敗，請參閱[在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 若只有鏡像失敗，請參閱[在 Lync server 2013-鏡像中還原鏡像的 Enterprise Edition 後端伺服器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。 若主控中央管理存放區的資料庫失敗，請參閱[在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是後端伺服器的 Enterprise Edition 成員伺服器失敗，請參閱[在 Lync server 2013 中還原 Enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

建議您先取得系統的影像複本，再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生問題。 在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。

在本主題中，範例主要資料庫會具有 BE1.contoso.com FQDN) 的完整功能變數名稱 (，而且鏡像資料庫的 FQDN 為 BE2.contoso.com。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>若要還原 Enterprise Edition 後端伺服器主資料庫

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  強制所有已設定的資料庫容錯移轉至鏡像。 針對您在此伺服器上設定的每個資料庫類型，輸入下列 Cmdlet：
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    例如：
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > 若您已設定後端資料庫以使用具有見證的同步鏡像，將自動進行容錯移轉。

    
    </div>

4.  完成容錯移轉之後，請執行下列作業：
    
      - 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
      - 停用後臺鏡像在後端伺服器上：按一下 [ **Enterprise Edition 前端**集區] 底下的 [集區]，然後選取 [**編輯屬性**]。 在 [**一般**] 索引標籤的 [**關聯**] 下，清除 [**啟用 SQL Server 儲存區鏡像**] 核取方塊。 請視需要執行這項作業以進行封存與監控。 然後按一下 **[確定]**。
    
      - 以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [**拓撲**]，然後按一下 [**發佈**]。
    
      - 選取 [仍可正常運作的後端 (BE2.contoso.com) 成為新的 SQL 存放區。 若要執行此動作，請在 [ **Enterprise Edition 前端**集區] 底下的集區上按一下滑鼠右鍵，然後選取 [**編輯屬性**]。 在 [**一般**] 索引標籤的 [**關聯**] 下，于範例中的範例中，輸入 [ **SQL Server 儲存區**] 欄位中的功能後端的 FQDN (，BE2.contoso.com) 。
    
      - 以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [**拓撲**]，然後按一下 [**發佈**]。
    
      - 重新開機服務，讓每個伺服器都可以讀取新的拓撲。 從 Lync Server 管理命令介面，在屬於此集區的每部前端伺服器上執行下列 Cmdlet：
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  卸載鏡像。 在 Lync Server 管理命令介面中，執行下列 Cmdlet：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    請對此伺服器上的所有資料庫類型執行這項作業。

6.  在此範例中建立具有相同 FQDN (的全新或全新伺服器，DB1.contoso.com) 為失敗的電腦，安裝作業系統，然後還原或重新註冊憑證。 這台伺服器將會做為新的鏡像運作。

7.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入新伺服器。

8.  安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗之前相同。

9.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。

10. 使用拓撲產生器來安裝鏡像資料庫。 執行下列步驟：
    
      - 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
      - 在後端伺服器上啟用鏡像。 若要執行此動作，請在 [ **Enterprise Edition 前端**集區] 底下的集區上按一下滑鼠右鍵，然後選取 [**編輯屬性**]。 在 [**一般**] 索引標籤的 [**關聯**] 下，選取 [**啟用 SQL Server 儲存區鏡像**] 核取方塊。 若有必要，也要進行封存與監控。
        
        然後在 [**鏡像 SQL Server 儲存區**] 欄位中，輸入新伺服器的 FQDN (n 此範例，BE1.contoso.com) 。 然後按一下 **[確定]**。
    
      - 以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [**拓撲**]，然後按一下 [**安裝資料庫**]。
    
      - 遵循 [**安裝資料庫**] 嚮導。 在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。
    
      - 依照嚮導執行，直到您到達提示 [**建立鏡像資料庫**]。 選取您要安裝的資料庫，然後完成此程式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

