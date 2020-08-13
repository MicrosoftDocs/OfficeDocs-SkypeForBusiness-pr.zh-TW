---
title: 將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90af32fce28d87b211a0829c5c863c9277129c86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-25_

從 Lync Server 2010 遷移至 Lync Server 2013 之後，您必須將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013 前端伺服器或集區，才能移除舊版 Lync Server 2010 伺服器。

中央管理伺服器是單一主/多個複本系統，其中包含中央管理伺服器的前端伺服器會持有資料庫的讀/寫副本。 拓撲中的每一部電腦（包括包含中央管理伺服器的前端伺服器）在安裝及部署期間，RTCLOCAL 會在電腦上安裝的預設) SQL Server (資料庫中的中央管理存放區資料的唯讀副本。 本機資料庫會透過 Lync Server 複本複製器代理程式，以在所有電腦上執行為服務的方式接收復本更新。 中央管理伺服器及本機複本上之實際資料庫的名稱是 XDS，這是由 XDS 及 XDS 檔所組成。 Master 資料庫位置是由 Active Directory 網域服務中 (SCP) 的服務控制點所參照。 所有使用中央管理伺服器來管理及設定 Lync Server 的工具，都使用 SCP 來尋找中央管理存放區。

順利移動中央管理伺服器後，應從原始前端伺服器移除中央管理伺服器資料庫。 如需移除中央管理伺服器資料庫的詳細資訊，請參閱[移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。

您可以使用 Lync Server 管理命令介面中的 [Windows PowerShell Cmdlet **Move-CsManagementServer** ，將資料庫從 lync SERVER 2010 sql server 資料庫移至 lync SERVER 2013 sql server 資料庫，然後將 SCP 更新為指向 lync Server 2013 中央管理伺服器位置。

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>在移動中央管理伺服器之前，準備 Lync Server 2013 前端伺服器

使用本節中的程式，準備 Lync Server 2013 前端伺服器，然後再移動 Lync Server 2010 中央管理伺服器。

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>準備 Enterprise Edition 前端集區

1.  在您想要重新放置中央管理伺服器的 Lync Server 2013 Enterprise Edition 前端集區上，登入安裝了 Lync Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。 您也必須在您要安裝中央管理存放區的資料庫上，具有 SQL Server 資料庫的 sysadmin 使用者權利和許可權。

2.  開啟 Lync Server 管理命令介面。

3.  若要在 Lync Server 2013 SQL Server 資料庫中建立新的中央管理存放區，請在 Lync Server 管理命令介面中輸入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  確認 **Lync Server 前端**服務的狀態為 [已啟動]****。

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>準備 Standard Edition 前端伺服器

1.  在您想要重新放置中央管理伺服器的 Lync Server 2013 Standard Edition 前端伺服器上，登入安裝了 Lync Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。

2.  開啟 Lync Server 部署嚮導。

3.  在 [Lync Server 部署嚮導] 中，按一下 [**準備第一個 Standard Edition Server**]。

4.  在 [**執行命令**] 頁面上，SQL Server Express 是以中央管理伺服器的方式安裝。 已建立所需的防火牆規則。 在完成資料庫和必要軟體的安裝時，請按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 如果命令輸出摘要畫面沒有可見的更新，則初始安裝可能需要一些時間。 這是因為安裝 SQL Server Express。 如果您需要監控資料庫的安裝，請使用 [工作管理員] 來監控安裝程式。

    
    </div>

5.  若要在 Lync Server 2013 Standard Edition 前端伺服器上建立新的中央管理存放區，請在 Lync Server 管理命令介面中輸入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  確認 **Lync Server 前端**服務的狀態為 [已啟動]****。

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013

1.  在將成為中央管理伺服器的 Lync Server 2013 伺服器上，登入安裝了 Lync Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。 您也必須具有 SQL Server 資料庫管理員使用者權限。

2.  開啟 Lync Server 管理命令介面。

3.  在 Lync Server 管理命令介面中，輸入：
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 若 <CODE>Enable-CsTopology</CODE> 未成功，請解決問題，使命令無法完成，再繼續進行。 如果<STRONG>Enable-CsTopology</STRONG>不成功，移動會失敗，而且可能會使拓撲處於沒有中央管理存放區的狀態。

    
    </div>

4.  在 lync Server 2013 前端伺服器或前端集區的 Lync Server 管理命令介面中，輸入：
    
        Move-CsManagementServer

5.  Lync Server 管理命令介面會顯示伺服器、檔案存放區、資料庫儲存區，以及目前狀態和建議狀態的服務連線點。 請詳細閱讀資訊，並確認預期的來源與目的地是否無誤。 輸入 [Y]**** 繼續或 [N]**** 停止移動。

6.  檢閱由 **Move-CsManagementServer** 命令所產生的任何警告或錯誤，並加以解決。

7.  在 Lync Server 2013 伺服器上，開啟 [Lync Server 部署嚮導]。

8.  在 [Lync Server 部署嚮導] 中，按一下 [**安裝或更新 Lync Server 系統**]，按一下 [**步驟2：安裝或移除 lync server 元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。

9.  在 Lync Server 2010 伺服器上，開啟 [Lync Server 部署嚮導]。

10. 在 [Lync Server 部署嚮導] 中，按一下 [**安裝或更新 Lync Server 系統**]，按一下 [**步驟2：安裝或移除 lync server 元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。

11. 重新開機 Lync Server 2013 伺服器。 因為存取中央管理伺服器資料庫的群組成員資格變更，所以需要這麼做。

12. 若要確認有新中央管理存放區的複寫發生，請在 Lync Server 管理命令介面中輸入：
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > 複寫可能要花一些時間來更新所有目前的複本。

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>移動後移除 Lync Server 2010 中央管理存放區檔案

1.  在 Lync Server 2010 Server 上：登入安裝了 Lync Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。 您也必須具有 SQL Server 資料庫管理員使用者權限。

2.  開啟 Lync Server 管理命令介面
    
    <div>
    

    > [!WARNING]  
    > 請先確認複寫已完成且狀態穩定後，再繼續移除之前的資料庫檔案。 若要在完成複寫之前移除檔案，您會中斷複寫處理常式，並將新移動的中央管理伺服器保持在未知的狀態。 請使用 <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> Cmdlet 來確認複寫狀態。

    
    </div>

3.  若要從 Lync Server 2010 中央管理伺服器移除中央管理存放區資料庫檔案，請輸入：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    例如：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    其中， \< SQL Server 的 FQDN \> 是 Enterprise edition 部署的 Lync Server 2010 後端伺服器，或 Standard Edition SERVER 的 fqdn。

</div>

</div>

<span> </span>

</div>

</div>

</div>

