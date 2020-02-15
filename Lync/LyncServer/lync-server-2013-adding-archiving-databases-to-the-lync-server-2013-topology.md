---
title: Lync Server 2013： 將封存資料庫新增至 Lync Server 2013 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73fe49aaf3a5b90a23bcfd6b99c9a5bb4476513
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>將封存資料庫新增至 Lync Server 2013 拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-10_

您必須先將封存納入拓撲中，才能設定部署來支援封存。 本主題中的資訊說明如何使用拓撲產生器來新增封存至您現有的拓撲。

<div>


> [!NOTE]  
> 如果您想要用於封存資料和 Exchange 2013 伺服器上的所有使用者的檔案儲存在您部署 Microsoft Exchange 整合，未指定<STRONG>封存 SQL Server 儲存區</STRONG>，或<STRONG>使用 SQL Server 儲存區鏡像</STRONG>的資訊。



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>新增封存資料庫支援至拓撲

1.  在電腦上，執行 Lync Server 2013 中，或 Lync Server 系統管理工具安裝，登入使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶）。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要的伺服器新增至拓撲，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且您使用 Lync Server 2013 檔案存放區 （亦即，以便拓撲產生器可以設定必要的判別存取控制清單 (Dacl) 的檔案共用具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶或具有相等的權限的帳戶。

    
    </div>

2.  啟動拓撲產生器]。

3.  在主控台樹狀目錄中，瀏覽至要部署封存的前端集區，然後按一下要部署封存的前端集區名稱。

4.  在 [動作]**** 功能表中，按一下 [編輯內容]****。

5.  在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。

6.  向下捲動至 [封存]****。

7.  選取 [封存]**** 核取方塊。

8.  在 [**封存 SQL Server 儲存區，** 執行下列其中一項：
    
      - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。 如果您的所有使用者位於 Microsoft Exchange Server 2013 或上方，您可以為所有使用者在 Exchange 中封存 Lync 通訊。 在此情況下，您不需要設定 SQL Server 封存存放區。
    
      - 若要指定新的 SQL Server 儲存區，按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列動作：
        
          - 在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的伺服器的 FQDN。
        
          - 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
        
          - 如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。

9.  如果您想要使用 SQL Server 儲存區鏡像，選取 [**啟用 SQL Server 儲存區鏡像**，，然後執行下列動作：
    
      - 若要使用現有的 SQL Server 儲存區作為鏡像，在 [**封存 SQL Server 儲存區鏡像**] 下拉式清單方塊中，按一下您想要用於鏡像的 SQL Server 存放區的名稱。
    
      - 若要指定新的 SQL Server 儲存區作為鏡像，請按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列其中一項：
        
        1.  在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的 SQL server 的 FQDN。
        
        2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
        
        3.  如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。
    
      - 如果您啟用 SQL Server 鏡像，並想要包含 SQL Server 鏡像見證 （第三個，個別的 SQL Server 執行個體，可偵測主要 SQL Server 伺服器的健康狀況和鏡像執行個體），選取 [**使用 SQL Server 鏡像見證啟用自動容錯移轉**] 核取方塊，，然後執行下列其中一項：
        
        1.  在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 鏡像見證伺服器的 FQDN。
        
        2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。
        
        3.  如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。

10. 若要儲存設定，請按一下 [確定]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

