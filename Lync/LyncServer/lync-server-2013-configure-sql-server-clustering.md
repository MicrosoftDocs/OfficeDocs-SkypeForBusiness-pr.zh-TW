---
title: Lync Server 2013：設定 SQL Server 群集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>設定 Lync Server 2013 的 SQL Server 群集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-10_

Microsoft Lync Server 2013 支援 SQL Server 2012 與 SQL Server 2008 R2 的群集。 如需支援內容的詳細資訊，請參閱[Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。

您應該先設定並設定 SQL Server 群集，才能安裝及部署企業版前端伺服器和後端資料庫。 如需 SQL Server 2012 中容錯移轉叢集的最佳做法及設定指示<http://technet.microsoft.com/en-us/library/hh231721.aspx>，請參閱。 針對 SQL Server 2008 中的容錯移轉叢集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>，請參閱。

當您安裝 SQL Server 時，您應該安裝 SQL Server Management Studio 來管理資料庫及記錄檔位置的位置。 當您安裝 SQL Server 時，系統會將 SQL Server Management Studio 作為選用元件進行安裝。

<div>


> [!IMPORTANT]  
> 若要在 SQL Server 的伺服器上安裝及部署資料庫，您必須是安裝資料庫檔案之 SQL server 系統管理員群組的成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求您先將其新增至群組，直到部署資料庫檔案。 如果您無法成為 sysadmin 群組的成員，您應該使用腳本來提供您的 SQL Server 資料庫系統管理員，以設定及部署資料庫。 如需有關完成程式所需的適當使用者權利和許可權的詳細資訊，請參閱<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>設定 SQL Server 群集

1.  完成 SQL Server 群集的安裝與設定之後，您可以使用 SQL Server 實例的虛擬叢集名稱（如 SQL Server 群集設定中的設定）和實例，在拓撲建立器中定義 SQL Server storeSQL Server 資料庫的名稱。 不同于單一 SQL Server 的伺服器，您會針對群集 SQL Server 式伺服器使用虛擬節點的完整功能變數名稱（FQDN）。
    
    <div>
    

    > [!NOTE]  
    > 個別的 Windows Server 叢集節點不需要針對拓撲建立器進行設定。 您只會使用虛擬 SQL Server 群集名稱。

    
    </div>

2.  如果您使用拓撲建立器來部署資料庫，您必須是 SQL Server 系統管理員群組的成員。 如果您是 SQL Server 系統管理員群組的成員，但您在網域中沒有許可權（例如，SQL Server 資料庫系統管理員角色），您就擁有建立資料庫的許可權，但無法在 Lync Server 中讀取必要的資訊。 如需有關部署 Lync Server 所需的使用者權利和許可權的詳細資訊，請參閱[Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。

3.  使用 SQL Server Management Studio，確保將資料庫檔案夾及記錄檔案資料夾預設值正確對應至 SQL Server 群集中的共用磁片。 如果您要使用拓撲建立器建立資料庫，這是必要的程式。
    
    <div>
    

    > [!NOTE]  
    > 如果您沒有安裝 SQL Server Management Studio，您可以重新執行 SQL Server 安裝，然後選取 [管理工具] 做為現有 SQL Server 部署的新增功能，以進行安裝。

    
    </div>

4.  使用 [拓撲建立器] 或 [Windows PowerShell Cmdlet]，為 SQL Server server 伺服器安裝資料庫。 若要使用拓撲產生器，請使用下列程式。 若要使用 Windows PowerShell Cmdlet，請參閱[在 lync server 2013 中使用 Lync Server 管理命令介面進行資料庫安裝](lync-server-2013-database-installation-using-lync-server-management-shell.md)。

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>使用拓撲產生器建立資料庫

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
    <div>
    

    > [!WARNING]  
    > 下列程式假設您已在拓撲產生器中定義並設定您的拓撲。 如需定義拓朴的詳細資料，請參閱<A href="lync-server-2013-defining-and-configuring-the-topology.md">在 Lync Server 2013 中定義及設定拓撲</A>。 若要使用 [拓撲建立器] 發佈拓撲及設定資料庫，您必須以具備正確的使用者權利和群組成員資格的使用者身分登入。 如需有關所需許可權和群組成員資格的詳細資料，請參閱<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。

    
    </div>

2.  在拓撲建立器中發佈拓撲時，請在 [**建立資料庫**] 頁面上，按一下 [**高級**]。

3.  [**選取資料庫檔案位置**] 頁面有兩個選項，可決定資料庫檔案將如何部署至 SQL Server 群集。 選取下列其中一項：
    
      - **自動判斷資料庫檔案位置。** 這個選項會根據 SQL Server server 上的磁片磁碟機配置，使用演算法來判斷資料庫記錄和資料檔案位置。 這些檔案的發佈方式就是嘗試提供最佳效能。
    
      - 使用 SQL Server 執行個體預設值。 選取此選項時，系統會根據 SQL Server 實例設定來安裝記錄和資料檔案。 將資料庫檔案部署至 SQL Server 之後，您的 SQL Server 資料庫管理員可能會想要重新置放檔案，以針對您特定的 SQL Server 設定需求來優化效能。

4.  完成拓撲發佈並確認作業期間沒有發生任何錯誤。

</div>

</div>

<span> </span>

</div>

</div>

</div>

