---
title: 還原鏡像的 Enterprise Edition 後端伺服器-鏡像
description: 還原鏡像的 Enterprise Edition 後端伺服器-鏡像。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 011c0aaa10ffed6fef7d579dbc16993fd3341070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543799"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-鏡像

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

如果您在鏡像設定中有 Enterprise Edition 後端伺服器，且只有鏡像失敗，請遵循本節中的程式。 如果主資料庫和鏡像都失敗，請參閱 [在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 若只有主要的失敗，請參閱 [在 Lync server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。 若主控中央管理存放區的資料庫失敗，請參閱 [在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是後端伺服器的 Enterprise Edition 成員伺服器失敗，請參閱 [在 Lync server 2013 中還原 Enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

建議您先取得系統的影像複本，再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生問題。 在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>若要還原 Enterprise Edition 後端伺服器鏡像資料庫

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  卸載鏡像。 首先，輸入下列 Cmdlet：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    請對此伺服器上的所有資料庫類型執行這項作業。

4.  建立全新或新的伺服器，其具有相同的完整功能變數名稱 (FQDN)  (DB1.contoso.com) 作為失敗的電腦，安裝作業系統，然後還原或重新註冊憑證。 這台伺服器將會做為新的鏡像運作。

5.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入新伺服器。

6.  安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗之前相同。

7.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。

8.  使用拓撲產生器來安裝鏡像資料庫。 請執行下列步驟：
    
      - 啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
      - 以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [ **拓撲**]，然後按一下 [ **安裝資料庫**]。
    
      - 遵循 [ **安裝資料庫** ] 嚮導。 在 [ **建立資料庫** ] 頁面上，選取您要重新建立的資料庫。
    
      - 依照嚮導執行，直到出現 [ **建立鏡像資料庫** ] 的提示。 選取您要安裝的資料庫並完成此程式。
        
        <div>
        

        > [!TIP]
        > 您可以使用 <STRONG>Install-CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不是執行拓撲產生器。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

