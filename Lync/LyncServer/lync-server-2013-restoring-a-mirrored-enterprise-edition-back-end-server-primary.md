---
title: 還原鏡像企業版後端伺服器-主要
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
ms.openlocfilehash: 07546b59839631cbd558e91e3e617fefd1c6e362
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>在 Lync Server 2013 中還原鏡像企業版後端伺服器-主要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

如果您在鏡像設定中有企業版後端伺服器，而且只有主資料庫發生故障，請依照本節中的程式執行。 如果主資料庫和鏡像都未通過，請參閱[在 Lync Server 2013 中還原企業版後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 如果只有鏡像失敗，請參閱[在 Lync Server 2013-mirror 中還原鏡像企業版後端伺服器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。 如果裝載中央管理儲存區的資料庫失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是後端伺服器的企業版成員伺服器失敗，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

我們建議您先取得系統的影像複本，然後再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生的問題。 您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。

在本主題中，範例主資料庫將會有 BE1.contoso.com 的完整功能變數名稱（FQDN），而鏡像資料庫將擁有 FQDN （BE2.contoso.com）。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>若要還原企業版後端伺服器的主資料庫

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  強制所有已設定的資料庫都能容錯移轉到鏡像。 針對您在此伺服器上設定的每個資料庫類型，輸入下列 Cmdlet：
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    例如：
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > 如果您已將後端資料庫設定為使用與見證的同步處理鏡像，則會自動進行容錯移轉。

    
    </div>

4.  完成容錯移轉之後，請執行下列動作：
    
      - 啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
      - 停用後端伺服器上的鏡像：以滑鼠右鍵按一下 [**企業版頂層端池**] 下的 [池]，然後選取 [**編輯屬性**]。 在 [**一般**] 索引標籤的 [**關聯**] 底下，清除 [**啟用 SQL Server store 鏡像**] 核取方塊。 如有需要，請執行此動作以進行封存和監視。 然後按一下 **[確定]**。
    
      - 以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲**]，然後按一下 [**發佈**]。
    
      - 選取 [仍正常運作的後端（BE2.contoso.com）] 做為新的 SQL store。 若要這樣做，請以滑鼠右鍵按一下 [**企業版頂層端池**] 底下的 [池]，然後選取 [**編輯屬性**]。 在 [**一般**] 索引標籤的 [**關聯**性] 底下，于 [ **SQL Server store** ] 欄位中輸入 [作用中後端] 的 FQDN （在我們的範例中為 BE2.contoso.com）。
    
      - 以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲**]，然後按一下 [**發佈**]。
    
      - 重新開機服務，讓每個伺服器都能讀取新的拓撲。 從 Lync Server 管理命令介面，在屬於此 pool 的每個前端伺服器上執行下列 Cmdlet：
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  卸載鏡像。 從 Lync Server 管理命令介面，執行下列 Cmdlet：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    針對此伺服器上的所有資料庫類型執行此動作。

6.  在失敗的電腦上建立具有相同 FQDN （在這個範例中為 DB1.contoso.com）的乾淨或新伺服器、安裝作業系統，然後還原或重新註冊證書。 這個伺服器將做為新的鏡像。

7.  從屬於 [RTCUniversalServerAdmins] 群組成員的使用者帳戶登入新的伺服器。

8.  安裝 SQL Server 2012 或 SQL Server 2008 R2，讓實例名稱保持與失敗前相同。

9.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。

10. 使用拓撲產生器來安裝鏡像資料庫。 請執行下列步驟：
    
      - 啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
      - 在後端伺服器上啟用鏡像。 若要這樣做，請以滑鼠右鍵按一下 [**企業版頂層端池**] 底下的 [池]，然後選取 [**編輯屬性**]。 在 [**一般**] 索引標籤的 [**關聯**] 底下，選取 [**啟用 SQL Server store 鏡像**] 核取方塊。 如有需要，也可以進行封存和監視。
        
        接著，在 [**鏡像 SQL Server store** ] 欄位中，輸入新伺服器的 FQDN （n 這個範例，BE1.contoso.com）。 然後按一下 **[確定]**。
    
      - 以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲圖**]，然後按一下 [**安裝資料庫**]。
    
      - 遵循 [**安裝資料庫**] 嚮導。 在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。
    
      - 依照嚮導進行，直到出現提示，然後**建立鏡像資料庫**。 選取您要安裝的資料庫，然後完成這個程式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

