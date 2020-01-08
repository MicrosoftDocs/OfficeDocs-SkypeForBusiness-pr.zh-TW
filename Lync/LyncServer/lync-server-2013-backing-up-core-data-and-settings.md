---
title: Lync Server 2013：備份核心資料和設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1737dac3369361b0937e6b870839e11e5706e41a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>在 Lync Server 2013 中備份核心資料和設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-23_

下列程式會使用 Lync Server 管理命令介面 Cmdlet 來為核心服務的設定和資料建立備份檔案。 如需本節中使用之工具的詳細資料（包括這些工具的位置），請參閱[Lync Server 2013 中的備份和還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。 如需備份封存與監控資料的詳細資訊，請參閱[在 Lync Server 2013 中備份封存與監控資料庫](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。

<div>


> [!NOTE]  
> 此區段中的步驟來備份中央管理存放區，包括用於封存與監控的設定和設定。



</div>

您可以在本機或遠端執行此區段所述的 Cmdlet。

<div>

## <a name="to-back-up-core-data-and-settings"></a>若要備份核心資料和設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入內部部署中的任何電腦。

2.  若要儲存您在下列步驟中建立的備份，請建立新的共用資料夾，並將 **$Backup**參照的路徑更新為新的共用資料夾。

3.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  備份中央管理儲存區設定檔。 在命令列中，輸入下列內容：
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > 此步驟會將您的 Lync Server 拓撲、原則和設定設定匯出至檔案。 不需要執行任何其他步驟，即可備份拓撲資料。

    
    </div>

5.  將已備份的中央管理儲存配置檔案複製到 $Backup\\。

6.  備份位置資訊服務資料。 在命令列中，輸入下列內容：
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  將備份的位置資訊服務配置檔案複製到 $Backup\\。

8.  在前端資料庫和每個標準版伺服器的每個後端資料庫上備份使用者資料。 在命令列中，輸入下列內容：
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    例如：
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  將已備份的使用者檔案複製到\\$Backup。

10. 在執行回應群組應用程式的每個池中，備份回應群組設定。 請執行下列步驟：
    
    1.  在命令列中，輸入：
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        例如：
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. 將已備份的回應群組設定檔案複製到\\$Backup。

</div>

</div>

<span> </span>

</div>

</div>

</div>

