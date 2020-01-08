---
title: 將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-25_

從 Lync Server 2010 遷移至 Lync Server 2013 之後，您必須將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013 前端伺服器或伺服器池，才能移除舊版 Lync Server 2010 伺服器。

[中央管理伺服器] 是單一主要/多重複本系統，其中資料庫的讀/寫複本是由包含中央管理伺服器的前端伺服器所保留。 拓朴中的每個電腦（包括包含中央管理伺服器的前端伺服器）在安裝期間都有在電腦上安裝的 SQL Server 資料庫中的中央管理儲存資料（預設為 RTCLOCAL）的唯讀複本部署. 本機資料庫會按照 Lync Server 複本複製器代理程式（在所有電腦上以服務形式執行）的方式來接收復制副本更新。 中央管理伺服器上的實際資料庫名稱與局部複本是 XDS，這是由 XDS 和 XDS 檔案組成。 主資料庫位置是由 Active Directory 網域服務中的服務控制點（SCP）所參照。 所有使用中央管理伺服器來管理和設定 Lync Server 的工具，都使用 SCP 來尋找中央管理儲存區。

成功移動中央管理伺服器之後，您應該從原始前端伺服器移除中央管理伺服器資料庫。 如需有關移除中央管理伺服器資料庫的詳細資訊，請參閱[移除前端池的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。

您可以在 Lync Server 管理命令介面中使用 Windows PowerShell Cmdlet **CsManagementServer** ，將資料庫從 lync SERVER 2010 sql server 資料庫移至 lync SERVER 2013 sql server 資料庫，然後更新 SCP 以指向 lync Server 2013 中央管理伺服器位置。

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>在移動中央管理伺服器前準備 Lync Server 2013 前端伺服器

在移動 Lync Server 2010 中央管理伺服器之前，請使用本節中的程式來準備 Lync Server 2013 前端伺服器。

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>準備企業版前端池

1.  在您想要重設中央管理伺服器位置的 Lync Server 2013 企業版前端池上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。 您也必須在您要安裝中央管理儲存區的資料庫上，同時擁有 SQL Server 資料庫系統管理員的使用者權利和許可權。

2.  開啟 Lync Server 管理命令介面。

3.  若要在 Lync Server 2013 SQL Server 資料庫中建立新的中央管理儲存體，請在 Lync Server 管理命令介面中，輸入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  確認**Lync Server 前端**服務的狀態為 [**已啟動**]。

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>準備標準版的前端伺服器

1.  在您想要重設中央管理伺服器位置的 Lync Server 2013 標準版前端伺服器上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。

2.  開啟 [Lync Server 部署] 嚮導。

3.  在 Lync Server 部署嚮導中，按一下 [**準備第一個標準版 Server**]。

4.  在 [**執行命令**] 頁面上，SQL Server Express 已安裝為中央管理伺服器。 已建立必要的防火牆規則。 完成資料庫與必備軟體的安裝後，按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 初始安裝可能需要一些時間，且 [命令輸出摘要] 畫面沒有顯示更新。 這是由 SQL Server Express 的安裝所造成。 如果您需要監視資料庫的安裝，請使用 [工作管理員] 來監視設定。

    
    </div>

5.  若要在 Lync Server 2013 標準版前端伺服器上建立新的中央管理存放區，請在 Lync Server 管理命令介面中，鍵入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  確認**Lync Server 前端**服務的狀態為 [**已啟動**]。

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>若要將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013

1.  在將是中央管理伺服器的 Lync Server 2013 伺服器上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。 您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。

2.  開啟 Lync Server 管理命令介面。

3.  在 Lync Server 管理命令介面中，鍵入：
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 如果<CODE>Enable-CsTopology</CODE>未成功，請解決導致命令無法完成的問題，然後再繼續進行。 如果<STRONG>啟用-CsTopology</STRONG>未成功，移動就會失敗，而且可能會讓您的拓撲處於沒有中央管理儲存區的狀態。

    
    </div>

4.  在 Lync Server 2013 前端伺服器或頂層端池的 Lync Server 管理命令介面中，鍵入：
    
        Move-CsManagementServer

5.  Lync Server 管理命令介面會顯示伺服器、檔案儲存區、資料庫儲存區，以及目前狀態與建議狀態的服務連接點。 仔細閱讀資訊並確認這是您想要的來源和目的地。 鍵入**Y**繼續，或輸入**N**以停止移動。

6.  查看**移動流覽 CsManagementServer**命令產生的任何警告或錯誤，並加以解決。

7.  在 Lync Server 2013 Server 上，開啟 Lync Server 部署嚮導。

8.  在 Lync Server 部署嚮導中，按一下 [**安裝或更新 Lync Server System**]，按一下 [**步驟2：設定] 或 [移除 Lync server 元件**]，按一下 **[下一步]**，查看摘要，然後按一下 **[完成]**。

9.  在 Lync Server 2010 Server 上，開啟 Lync Server 部署嚮導。

10. 在 Lync Server 部署嚮導中，按一下 [**安裝或更新 Lync Server System**]，按一下 [**步驟2：設定] 或 [移除 Lync server 元件**]，按一下 **[下一步]**，查看摘要，然後按一下 **[完成]**。

11. 重新開機 Lync Server 2013 伺服器。 這是必要的，因為群組成員資格變更為 access 中央管理伺服器資料庫。

12. 若要確認正在進行與新中央管理存放區的複製，請在 Lync Server 管理命令介面中輸入：
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > 複製可能需要一些時間來更新所有目前的複本。

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>若要在移動後移除 Lync Server 2010 中央管理儲存檔案

1.  在 Lync Server 2010 Server 上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。 您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。

2.  開啟 Lync Server 管理命令介面
    
    <div>
    

    > [!WARNING]  
    > 在複製完成且穩定之前，請勿繼續移除先前的資料庫檔案。 如果您在完成複製之前移除檔案，您將會中斷複製程式，並將新移動的中央管理伺服器保持在未知狀態。 使用 Cmdlet <STRONG>CsManagementStoreReplicationStatus</STRONG>來確認複製狀態。

    
    </div>

3.  若要從 Lync Server 2010 中央管理伺服器移除中央管理儲存資料庫檔案，請輸入：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    例如：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    其中， \<SQL Server\>的 FQDN 是企業版部署中的 Lync Server 2010 後端伺服器，或是標準版 Server 的 fqdn。

</div>

</div>

<span> </span>

</div>

</div>

</div>

