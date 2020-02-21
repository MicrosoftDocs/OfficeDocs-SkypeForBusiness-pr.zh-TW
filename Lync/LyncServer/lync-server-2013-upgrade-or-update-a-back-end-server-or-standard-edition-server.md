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
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>升級或更新 Lync Server 2013 中的後端伺服器或 Standard Edition 伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

本主題說明如何在 Enterprise Edition 後端伺服器或 Standard Edition server 上安裝更新。

如果後端伺服器是向下至少 30 分鐘，當您升級時，使用者可能會再進入恢復能力模式。 當完成升級，且在後端伺服器再次連線與前端伺服器集區中時，使用者會傳回完整的功能。 如果升級花低於 30 分鐘，使用者不會受到影響。

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>若要更新後端伺服器或 Standard Edition server

1.  以 CsAdministrator 角色成員身分登入您要升級的伺服器。

2.  下載更新，並將它擷取至本機硬碟機。

3.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

4.  停止 Lync Server 服務。 在命令列中輸入：
    
        Stop-CsWindowsService

5.  停止全球資訊網服務。 在命令列中輸入：
    
        net stop w3svc

6.  關閉所有 Lync Server 管理命令介面視窗。

7.  安裝更新。

8.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

9.  停止 Lync Server 服務再次來捕捉全域組件快取 (GAC) – d 組件。 在命令列中輸入：
    
        Stop-CsWindowsService

10. 重新啟動全球資訊網服務。 在命令列中輸入：
    
        net start w3svc

11. 執行下列其中一項，將 LyncServerUpdateInstaller.exe 所做的變更套用至 SQL Server 資料庫：
    
      - 如果這是 Enterprise Edition 後端伺服器，而且沒有組合的資料庫，在此伺服器上，例如封存或監控資料庫，然後在命令列輸入下列：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - 如果這是 Enterprise Edition 後端伺服器，而且此伺服器上有組合的資料庫，然後在命令列輸入下列：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 如果這是 Standard Edition 伺服器，請在命令列輸入下列命令：
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

