---
title: Lync Server 2013：準備還原 Lync Server
description: Lync Server 2013：準備還原 Lync Server。
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
ms.openlocfilehash: 1875a691cfb70a6a824ab19bfde3dee4d699e48a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579949"
---
# <a name="preparing-to-restore-lync-server-2013"></a>準備還原 Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

當您在失敗後開始還原伺服器及資料庫之前，您必須確定下列各項：

  - 需要還原的專案。

  - 還原所需的硬體、軟體、資料及工具。

<div>

## <a name="determining-what-to-restore"></a>決定要還原的專案

本主題說明如何還原發生在伺服器、集區或中央管理存放區層級的 Lync Server 中斷。 若中央管理存放區失敗，您的 Lync Server 部署仍可運作，但您無法變更任何設定。 如果後端伺服器或 Standard Edition Server 失敗，使用者集區便會停止運作。 如果任何其他伺服器失敗，失敗的程度取決於伺服器執行的伺服器角色，以及伺服器是否主控一或多個資料庫。

### <a name="what-to-restore"></a>要還原的專案

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若失敗</th>
<th>請參閱本節內容：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">在 Lync Server 2013 中還原 Standard Edition server</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理存放區</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">在 Lync Server 2013 中還原主控中央管理存放區的伺服器</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition 後端</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 鏡像後端主伺服器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition 鏡像後端次要伺服器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-鏡像</a></p></td>
</tr>
<tr class="even">
<td><p>任何執行伺服器角色的 Enterprise Edition 伺服器，例如前端伺服器、Edge Server、Director、轉送伺服器或 Persistent Chat Server。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync Server 2013 中還原 Enterprise Edition 成員伺服器</a></p></td>
</tr>
<tr class="odd">
<td><p>整個 Lync 伺服器集區</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">在 Lync Server 2013 中還原 Lync Server 集區</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 檔存放區</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">在 Lync Server 2013 中還原檔存放區</a></p></td>
</tr>
<tr class="odd">
<td><p>獨立監控資料庫或封存資料庫</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">在 Lync Server 2013 中還原監控或封存資料</a></p></td>
</tr>
<tr class="even">
<td><p>獨立的持久聊天資料庫</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">在 Lync Server 2013 中還原 Persistent Chat 資料</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>收集硬體、軟體及工具

當您還原伺服器時，您必須從新的或全新的電腦開始。 此外，您必須具備下列可用的硬體和軟體：

  - 具有相同完整功能變數名稱 (FQDN) 伺服器失敗的乾淨或新伺服器。
    
    <div>
    

    > [!IMPORTANT]  
    > 當您安裝作業系統時，請確定您未刪除 Active Directory 網域服務中的電腦帳戶，並確認已保留帳戶的群組許可權。

    
    </div>

  - 作業系統的安裝軟體。 若要安裝作業系統，請使用伺服器部署程式和組織建立的設定。 當您還原服務時，您應該會有這些程式和設定需求可供使用。

  - SQL Server 2012 或 SQL Server 2008 R2 的安裝軟體。 若要安裝資料庫伺服器，請使用適當版本的 SQL Server，以及組織所建立的資料庫伺服器部署程式和設定。 當您還原服務時，您應該會有這些程式和設定需求可供使用。
    
    <div>
    

    > [!NOTE]  
    > 安裝本機設定存放區時，Lync Server 部署嚮導會在每個 Standard Edition 伺服器和任何其他 Lync Server 伺服器上自動安裝 SQL Server 2012 Express，除非您已在伺服器上預先安裝 SQL Server 2012 或 SQL Server 2008 R2。

    
    </div>

  - 用來製作系統映射的軟體。
    
    <div>
    

    > [!TIP]  
    > 建議您在安裝作業系統和 SQL Server 之後，在您開始還原之前，取得系統的影像複本，如此一來，您就可以使用此映射做為回退點，以防還原期間發生問題。

    
    </div>

  - Lync Server 2013 安裝軟體。 Lync Server 部署嚮導位於 Lync Server 安裝資料夾或 media at \\ setup \\ amd64 \\Setup.exe。

在還原期間，您可以使用下列工具：

  - Lync Server 管理命令介面 Cmdlet

  - Import-CsUserData

  - 還原 Windows 資料夾的工具

  - 拓撲產生器

  - SQL Server 資料庫公用程式，例如 SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>準備還原伺服器

在還原伺服器之前，您必須執行下列步驟：

1.  安裝作業系統。

2.  如果伺服器是後端伺服器，請安裝 SQL Server 2012 或 SQL Server 2008 R2。

3.  還原或重新註冊憑證。 如需憑證的詳細資訊，請參閱 [Lync Server 2013： data](lync-server-2013-backup-and-restoration-requirements-data.md)中的「其他備份需求」的備份和還原需求。

4.  開始還原之前，請先取得系統的映射，以做為回退點，以防還原期間發生問題。

<div>


> [!NOTE]  
> Lync Server 部署嚮導和本主題中的程式所述的指令程式和相關主題，設定所有必要的存取控制清單 (ACLs) 。



</div>

確認您要還原之元件所需的硬體和軟體是否可供您開始還原。 安裝作業系統和 SQL Server 之後，您可以從遠端執行下列還原程式中的大部分步驟。 例外狀況會注明在程式中。

您也應該將組織的備份及還原計劃及最後一次備份中的資訊，例如本文的工作表中的資訊 (如需詳細資訊，請參閱 [Lync Server 2013) 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md) （在您開始還原之前）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

