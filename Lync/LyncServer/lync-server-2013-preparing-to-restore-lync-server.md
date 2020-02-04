---
title: Lync Server 2013：準備還原 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2e6516ee1162c02f2bebc8c385c2f41e87d7781
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>準備還原 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在您開始還原伺服器和資料庫失敗之後，您必須判斷下列事項：

  - 需要還原的專案。

  - 您需要還原的硬體、軟體、資料及工具。

<div>

## <a name="determining-what-to-restore"></a>決定要還原的專案

本主題說明如何還原出現在伺服器、pool 或中央管理儲存層級的 Lync Server 中斷。 如果中央管理儲存失敗，您的 Lync Server 部署會繼續運作，但是您無法變更任何設定。 如果後端伺服器或標準版伺服器發生故障，使用者池就會停止運作。 如果任何其他伺服器失敗，失敗的大小取決於伺服器所執行的伺服器角色，以及伺服器是否託管一個或多個資料庫。

### <a name="what-to-restore"></a>要還原的專案

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果失敗</th>
<th>請參閱本節內容：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>標準版伺服器</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">在 Lync Server 2013 中還原標準版伺服器</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理存放區</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">在 Lync Server 2013 中還原託管中央管理儲存區的伺服器</a></p></td>
</tr>
<tr class="odd">
<td><p>企業版後端</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync Server 2013 中還原企業版後端伺服器</a></p></td>
</tr>
<tr class="even">
<td><p>企業版鏡像後端主要伺服器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">在 Lync Server 2013 中還原鏡像企業版後端伺服器-主要</a></p></td>
</tr>
<tr class="odd">
<td><p>企業版鏡像後端副伺服器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013 中還原鏡像企業版後端伺服器-鏡像</a></p></td>
</tr>
<tr class="even">
<td><p>任何執行伺服器角色的企業版伺服器，例如前端伺服器、Edge 伺服器、控制器、中繼伺服器、或持久聊天伺服器。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync Server 2013 中還原企業版成員伺服器</a></p></td>
</tr>
<tr class="odd">
<td><p>整個 Lync 伺服器池</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">在 Lync Server 2013 中還原 Lync Server 文件庫</a></p></td>
</tr>
<tr class="even">
<td><p>企業版檔存放區</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">在 Lync Server 2013 中還原檔案存放區</a></p></td>
</tr>
<tr class="odd">
<td><p>獨立監視資料庫或封存資料庫</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">在 Lync Server 2013 中還原監視或封存資料</a></p></td>
</tr>
<tr class="even">
<td><p>獨立持續聊天資料庫</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">在 Lync Server 2013 中還原持續聊天資料</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>收集硬體、軟體和工具

當您還原伺服器時，必須從新的或乾淨的電腦開始。 此外，您必須具備下列硬體和軟體：

  - 以相同的完整功能變數名稱（FQDN）為失敗的乾淨或新伺服器。
    
    <div>
    

    > [!IMPORTANT]  
    > 當您安裝作業系統時，請確定您沒有刪除 Active Directory 網域服務中的電腦帳戶，並確認該帳戶的群組許可權已保留。

    
    </div>

  - 作業系統的安裝軟體。 若要安裝作業系統，請使用貴組織建立的伺服器部署程式和配置。 您應該在還原服務時，使用這些程式和設定需求。

  - SQL Server 2012 或 SQL Server 2008 R2 的安裝軟體。 若要安裝資料庫伺服器，請使用適當版本的 SQL Server 以及由貴組織建立的資料庫伺服器部署程式和設定。 您應該在還原服務時，使用這些程式和設定需求。
    
    <div>
    

    > [!NOTE]  
    > 除非您已預先安裝 SQL Server 2012 或 SQL Server 2008 R2，否則 Lync Server 部署嚮導會在每個標準版 server 和任何其他的 Lync Server 伺服器上自動安裝 SQL Server 2012 Express。伺服器。

    
    </div>

  - 用來製作系統影像的軟體。
    
    <div>
    

    > [!TIP]  
    > 我們建議您在安裝作業系統與 SQL Server 之後，在開始還原前，拍攝系統的影像複本，以便在還原期間發生問題時，使用這個影像做為回滾點。

    
    </div>

  - Lync Server 2013 安裝軟體。 Lync Server 部署嚮導位於 [Lync Server 安裝] 資料夾或 [ \\安裝程式\\amd64\\] 的媒體中。

在還原期間，您可以使用下列工具：

  - Lync Server 管理命令介面 Cmdlet

  - 匯入-CsUserData

  - 還原 Windows 資料夾的工具

  - 拓撲建立器

  - SQL Server 資料庫實用程式，例如 SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>準備還原伺服器

在您還原伺服器之前，您必須執行下列步驟：

1.  安裝作業系統。

2.  如果伺服器是後端伺服器，請安裝 SQL Server 2012 或 SQL Server 2008 R2。

3.  還原或重新註冊您的憑證。 如需有關憑證的詳細資料，請參閱[Lync Server 2013：資料中的備份和還原需求](lync-server-2013-backup-and-restoration-requirements-data.md)中的「其他備份需求」。

4.  開始進行還原前，請先拍攝系統的影像，以做為復原點，以防還原期間發生的問題。

<div>


> [!NOTE]  
> Lync Server 部署嚮導與本主題中的程式所述的 Cmdlet，以及相關主題，以設定所有必要的存取控制清單（Acl）。



</div>

確認您要還原之元件所需的硬體和軟體在開始還原之前都可以使用。 安裝作業系統與 SQL Server 之後，您可以在遠端執行下列幾個還原程式中的步驟。 程式中會注明例外狀況。

您也應該擁有貴組織的備份和還原方案，以及上次備份中的資訊（例如此檔中的工作表中的資訊）（如需詳細資訊，請參閱[Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)），然後再開始還原。

</div>

</div>

<span> </span>

</div>

</div>

</div>

