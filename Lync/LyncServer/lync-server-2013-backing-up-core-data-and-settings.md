---
title: Lync Server 2013：備份核心資料和設定
description: Lync Server 2013：備份核心資料和設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637eeb950a3b8380f6e756f46a5083f51b5d7e1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543739"
---
# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>在 Lync Server 2013 中備份核心資料和設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-23_

下列程式會使用 Lync Server 管理命令介面 Cmdlet，為核心服務的設定和資料建立備份檔案。 如需本節所用工具（包括其所在位置）的詳細資訊，請參閱 [Lync Server 2013 中的備份和還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。 如需備份封存與監控資料的詳細資訊，請參閱 [在 Lync Server 2013 中備份封存和監控資料庫](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。

<div>


> [!NOTE]  
> 本節中備份中央管理存放區的步驟包括設定和設定進行封存及監視。



</div>

您可以本機或遠端執行本節中說明的 Cmdlet。

<div>

## <a name="to-back-up-core-data-and-settings"></a>若要備份核心資料與設定

1.  以屬於 RTCUniversalServerAdmins 群組成員身分的使用者帳戶，登入內部部署中的任何電腦。

2.  若要儲存您在下列步驟中所建立的備份，請建立新的共用資料夾，並將 **$Backup** 所參照的路徑更新為新的共用資料夾。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  備份中央管理存放區設定檔。 在命令列輸入下列命令：
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > 這個步驟會將您的 Lync 伺服器拓撲、原則及設定匯出至檔案。 在備份拓撲資料部分，無需其他步驟。

    
    </div>

5.  將備份的中央管理存放區配置檔案複製到 $Backup \\ 。

6.  備份位置資訊服務資料。在命令列輸入下列命令：
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  將備份的位置資訊服務配置檔案複製到 $Backup \\ 。

8.  在每個前端集區和每個 Standard Edition server 的後端資料庫上備份使用者資料。 在命令列輸入下列命令：
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    例如：
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  將備份的使用者檔案複製到 $Backup \\ 。

10. 在執行回應群組應用程式的每個集區上，備份回應群組設定。 執行下列動作：
    
    1.  在命令列中輸入：
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        例如：
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. 將備份的回應群組配置檔案複製到 $Backup \\ 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

