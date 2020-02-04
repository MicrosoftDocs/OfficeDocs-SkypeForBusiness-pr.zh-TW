---
title: Lync Server 2013：還原標準版伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ecc58dc2683cd07b83a8c57385593961c3e985
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中還原標準版伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

如果沒有託管中央管理儲存區的標準版伺服器失敗，請遵循本節中的程式。 如果中央管理儲存區失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。

<div>


> [!TIP]  
> 我們建議您先取得系統的影像複本，然後再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生的問題。 您可能會想要在安裝作業系統與 SQL Server 之後進行影像複製，然後還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>若要還原標準版伺服器

1.  從包含與失敗電腦相同的完整功能變數名稱（FQDN）的乾淨或新伺服器開始，安裝作業系統，然後還原或重新註冊證書。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程式來執行此步驟。

    
    </div>

2.  從屬於 [RTCUniversalServerAdmins] 群組和 [本機管理員] 群組成員的使用者帳戶登入您要還原的伺服器。

3.  將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放位置並共用資料夾，以還原檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > 已還原之檔案存放區的路徑和檔案名應該與已備份的檔案存放區完全相同，以便使用檔案的元件可以存取它們。

    
    </div>

4.  執行拓撲建造器：
    
    1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
    2.  按一下 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。
    
    3.  選取拓撲，然後按一下 [**儲存**]。 按一下 **[是]** 以確認您的選取專案。

5.  流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。 使用 Lync Server 部署嚮導來執行下列動作：
    
    1.  執行**步驟1：安裝本機配置存放區**以安裝本機配置檔案。
    
    2.  執行**步驟2：設定或移除 Lync Server 元件**以安裝 lync server 伺服器角色。
    
    3.  執行**步驟3：要求、安裝或指派憑證**來指派憑證。
    
    4.  執行**步驟4：啟動服務**以在伺服器上啟動服務。
    
    如需執行 [部署嚮導] 的詳細資訊，請參閱您要還原之伺服器角色的部署檔。

6.  若要還原使用者資料，請執行下列動作：
    
    1.  從 $Backup\\將 ExportedUserData 複製到本機目錄。
    
    2.  您必須先停止 Lync services，才能還原使用者資料。 若要這麼做，請輸入：
        
            Stop-CsWindowsService
    
    3.  若要還原使用者資料，請在命令列輸入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  輸入以下內容以重新開機 Lync services：
        
            Start-CsWindowsService

7.  如果您已在此標準版伺服器上部署回應群組，請還原回應群組設定資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。

8.  如果您已在此標準版伺服器上部署持久的聊天，請還原持久聊天資料庫（mgc）。
    
    如果您使用 SQL Server 備份來備份永久性聊天資料庫，請使用 SQL Server 還原程式來還原它。
    
    如果您使用 Export CsPersistentChatData Cmdlet 來備份，請使用匯入-CsPersistentChatData 將其還原。

</div>

</div>

<span> </span>

</div>

</div>

</div>

