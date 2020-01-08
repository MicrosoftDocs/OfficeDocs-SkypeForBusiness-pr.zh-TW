---
title: 還原鏡像企業版後端伺服器-鏡像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>在 Lync Server 2013 中還原鏡像企業版後端伺服器-鏡像

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

如果您在鏡像設定中有企業版後端伺服器，而且只有鏡像失敗，請遵循本節中的程式。 如果主資料庫和鏡像都未通過，請參閱[在 Lync Server 2013 中還原企業版後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 如果只有主要失敗，請參閱[在 Lync Server 2013 中還原鏡像企業版後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。 如果裝載中央管理儲存區的資料庫失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是後端伺服器的企業版成員伺服器失敗，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

我們建議您先取得系統的影像複本，然後再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生的問題。 您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>若要還原企業版後端伺服器鏡像資料庫

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  卸載鏡像。 首先，請輸入下列 Cmdlet：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    針對此伺服器上的所有資料庫類型執行此動作。

4.  建立乾淨或新伺服器，其具有與失敗的電腦相同的完整功能變數名稱（FQDN）（DB1.contoso.com），安裝作業系統，然後還原或重新註冊證書。 這個伺服器將做為新的鏡像。

5.  從屬於 [RTCUniversalServerAdmins] 群組成員的使用者帳戶登入新的伺服器。

6.  安裝 SQL Server 2012 或 SQL Server 2008 R2，讓實例名稱保持與失敗前相同。

7.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。

8.  使用拓撲建立器來安裝鏡像資料庫。 執行下列動作：
    
      - 啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
      - 以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲圖**]，然後按一下 [**安裝資料庫**]。
    
      - 遵循 [**安裝資料庫**] 嚮導。 在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。
    
      - 遵循嚮導，直到出現 [**建立鏡像資料庫**] 的提示。 選取您要安裝的資料庫，並完成這個程式。
        
        <div>
        

        > [!TIP]
        > 您可以使用<STRONG>CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不是執行拓撲建立器。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

