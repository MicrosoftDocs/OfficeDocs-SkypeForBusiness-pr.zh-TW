---
title: 升級或更新後端伺服器或標準版伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中升級或更新後端伺服器或標準版伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

本主題說明如何在企業版後端伺服器或標準版伺服器上安裝更新。

如果後端伺服器在您升級時至少有30分鐘的時間，使用者可能會進入復原模式。 完成升級後，後端伺服器再次與池中的前端伺服器連線之後，使用者就會回到完整功能。 如果升級所需的時間少於30分鐘，使用者將不會受到影響。

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新後端伺服器或標準版伺服器

1.  以 CsAdministrator 角色成員的身分登入您要升級的伺服器。

2.  下載更新並將它解壓縮到本機硬碟。

3.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  停止 Lync Server 服務。 在命令列中，輸入：
    
        Stop-CsWindowsService

5.  停止萬維網服務。 在命令列中，輸入：
    
        net stop w3svc

6.  關閉所有 Lync Server 管理命令介面視窗。

7.  安裝更新。

8.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

9.  再次停止 Lync Server services，以捕捉通用群組件緩存（GAC）-d 元件。 在命令列中，輸入：
    
        Stop-CsWindowsService

10. 重新開機萬維網服務。 在命令列中，輸入：
    
        net start w3svc

11. 執行下列其中一項操作，將 LyncServerUpdateInstaller 所做的變更套用至 SQL Server 資料庫：
    
      - 如果這是企業版後端伺服器，且此伺服器上沒有 collocated 資料庫（例如 [封存] 或 [監視資料庫]），請在命令列中輸入下列內容：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - 如果這是企業版後端伺服器，且此伺服器上有 collocated 資料庫，請在命令列中輸入下列內容：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 如果這是標準版 server，請在命令列輸入以下命令：
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

