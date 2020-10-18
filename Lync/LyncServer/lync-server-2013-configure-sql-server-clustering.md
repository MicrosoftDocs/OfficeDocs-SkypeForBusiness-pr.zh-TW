---
title: Lync Server 2013：設定 SQL Server 叢集
description: Lync Server 2013：設定 SQL Server 叢集。
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
ms.openlocfilehash: 1f4b81b62d086de27659f564427ad6adde99ecac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576749"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>設定 Lync Server 2013 的 SQL Server 叢集

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-10_

Microsoft Lync Server 2013 支援 SQL Server 2012 和 SQL Server 2008 R2 的群集。 如需支援內容的詳細資訊，請參閱 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。

安裝及部署 Enterprise Edition 前端伺服器及後端資料庫之前，您應該先安裝及設定 SQL Server 叢集。 如需 SQL Server 2012 中容錯移轉叢集的最佳作法和設定指示，請參閱 <https://technet.microsoft.com/library/hh231721.aspx> 。 如需 SQL Server 2008 中的容錯移轉叢集，請參閱 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。

在安裝 SQL Server 時，應安裝 SQL Server Management Studio 以管理資料庫的位置與記錄檔位置。 您在安裝 SQL Server 時，可以選用性元件的形式安裝 SQL Server Management Studio。

<div>


> [!IMPORTANT]  
> 若要在 SQL Server 伺服器上安裝及部署資料庫，您必須是資料庫檔案安裝所在之 SQL Server 伺服器的 SQL Server sysadmin 群組成員。 如果您不是 SQL Server sysadmin 群組的成員，則必須要求將自己新增至該群組，直到資料庫檔案完成部署為止。 如果您無法成為 sysadmin 群組的成員，則應將用以設定及部署資料庫的指令碼提供給 SQL Server 資料庫系統管理員。 如需適當的使用者權限及完成程式所需許可權的詳細資訊，請參閱 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>設定 SQL Server 叢集

1.  完成 SQL Server 叢集的安裝和設定之後，您可以使用 SQL server 叢集的) 設定 (中所設定的 SQL server 實例虛擬叢集名稱，在拓撲產生器中定義 SQL Server 存放區，並使用 SQL Server 資料庫的設定。 不同於單一 SQL Server 伺服器，針對叢集 SQL Server 伺服器，您會使用虛擬節點完整網域名稱 (FQDN)。
    
    <div>
    

    > [!NOTE]  
    > 您不需要為拓撲產生器設定個別的 Windows Server 叢集節點。 您將只會使用虛擬 SQL Server 叢集名稱。

    
    </div>

2.  如果您使用拓撲產生器來部署資料庫，您必須是 SQL Server 系統管理員群組的成員。 如果您是 SQL Server sysadmin 群組的成員，但是您在網域中沒有許可權 (例如，SQL Server 資料庫系統管理員角色) ，則您具有建立資料庫的許可權，但無法在 Lync Server 中讀取必要的資訊。 如需部署 Lync Server 所需之使用者權利的詳細資訊，請參閱 [Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。

3.  使用 SQL Server Management Studio，確定資料庫資料夾與記錄檔資料夾的預設值均正確對應至 SQL Server 叢集中的共用磁碟。如果您要使用拓撲產生器建立資料庫，則必須執行此程序。
    
    <div>
    

    > [!NOTE]  
    > 如果您未安裝 SQL Server Management Studio，可於此時安裝，方法是重新執行 SQL Server 安裝，然後將管理工具選取為現有 SQL Server 部署的新增功能。

    
    </div>

4.  使用拓撲產生器或 Windows PowerShell Cmdlet，為 SQL Server 服務器安裝資料庫。 若要使用拓撲產生器，請使用下列程式。 若要使用 Windows PowerShell Cmdlet，請參閱 [在 Lync server 2013 中使用 Lync Server 管理命令介面進行資料庫安裝](lync-server-2013-database-installation-using-lync-server-management-shell.md)。

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>使用拓撲產生器建立資料庫

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
    <div>
    

    > [!WARNING]  
    > 下列程式假設您已在拓撲產生器中定義及設定拓撲。 如需定義拓撲的詳細資訊，請參閱<A href="lync-server-2013-defining-and-configuring-the-topology.md">在 Lync Server 2013 中定義及設定拓撲</A>。 若要使用拓撲產生器來發行拓撲及設定資料庫，您必須以具有正確使用者權限與群組成員資格的使用者身分登入。 如需有關必要許可權和群組成員資格的詳細資訊，請參閱 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。

    
    </div>

2.  在 [拓撲產生器] 中，當您發佈拓撲時，請在 [ **建立資料庫** ] 頁面上，按一下 [ **高級**]。

3.  **[選取資料庫檔案位置]** 頁面上有兩個選項，可決定資料庫檔案部署至 SQL Server 叢集的方式。請選取下列其中一項：
    
      - **自動判斷資料庫檔案位置。** 此選項會使用演算法，根據 SQL Server 伺服器上的磁碟機設定來決定資料庫記錄檔與資料檔的位置。 檔案將以此方式分配，以期達到最佳效能。
    
      - [使用 SQL Server 執行個體預設值]。 選取此選項後，將會根據 SQL Server 執行個體設定安裝記錄檔與資料檔。 在資料庫檔案部署至 SQL Server 後，SQL Server 資料庫系統管理員可能會依據您特定的 SQL Server 設定需求而重新配置檔案位置，以期達到最佳效能。

4.  完成拓撲發行作業，並確認作業期間未發生任何錯誤。

</div>

</div>

<span> </span>

</div>

</div>

</div>

