---
title: 升級或更新後端伺服器或 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3afeee91457b2d10f506be81a146643a4598c9f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506640"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中升級或更新後端伺服器或 Standard Edition Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

本主題說明如何在 Enterprise Edition 後端伺服器或 Standard Edition server 上安裝更新。

如果後端伺服器停機至少30分鐘，則使用者可能會進入復原模式。 當升級完成且後端伺服器重新連接至集區中的前端伺服器後，使用者會傳回完整功能。 如果升級所需的時間少於30分鐘，使用者將不會受到影響。

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新後端伺服器或 Standard Edition server

1.  以 CsAdministrator 角色成員身分登入您要升級的伺服器。

2.  下載更新，並將其解壓縮至本機硬碟。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  停止 Lync Server 服務。 在命令列中輸入：
    
        Stop-CsWindowsService

5.  停止全球資訊網服務。 在命令列中輸入：
    
        net stop w3svc

6.  關閉所有的 Lync Server 管理命令介面視窗。

7.  安裝更新。

8.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

9.  停用 Lync Server 服務以捕獲通用群組件快取 (GAC) – d 元件。 在命令列中輸入：
    
        Stop-CsWindowsService

10. 重新啟動全球資訊網服務。 在命令列中輸入：
    
        net start w3svc

11. 執行下列其中一項，將 LyncServerUpdateInstaller.exe 所做的變更套用至 SQL Server 資料庫：
    
      - 如果這是 Enterprise Edition 後端伺服器，且此伺服器上沒有組合資料庫（例如封存或監控資料庫），請在命令列輸入下列命令：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - 如果這是 Enterprise Edition 後端伺服器，且此伺服器上有組合資料庫，請在命令列輸入下列命令：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 如果這是 Standard Edition server，請在命令列輸入下列命令：
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

