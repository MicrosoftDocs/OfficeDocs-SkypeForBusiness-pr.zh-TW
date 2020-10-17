---
title: Lync Server 2013：將封存資料庫新增至 Lync Server 2013 拓撲
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
ms.openlocfilehash: ebc2f06e6e3fa2646989e4697354c71f7f0249da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521390"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>將封存資料庫新增至 Lync Server 2013 拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

您必須先將封存納入拓撲中，才能設定部署來支援封存。 本主題中的資訊說明如何使用拓撲產生器，將封存新增至現有的拓撲。

<div>


> [!NOTE]  
> 若要使用 Microsoft Exchange 整合將封存資料和檔案儲存在部署中的所有使用者的 Exchange 2013 伺服器上，請勿指定「封存 <STRONG>Sql server 儲存區</STRONG> 」或「 <STRONG>使用 SQL server 儲存區鏡像</STRONG> 資訊」。



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>新增封存資料庫支援至拓撲

1.  在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將伺服器新增至拓撲），則必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶。而且具有在您用於 Lync server 2013 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的自由存取控制清單 (dacl) ，或具有同等 (權利的帳戶。

    
    </div>

2.  啟動拓撲產生器。

3.  在主控台樹狀目錄中，瀏覽至要部署封存的前端集區，然後按一下要部署封存的前端集區名稱。

4.  在 [動作]**** 功能表中，按一下 [編輯內容]****。

5.  在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。

6.  向下捲動至 [封存]****。

7.  選取 [封存]**** 核取方塊。

8.  在 **[封存 SQL Server 儲存區** ] 底下，執行下列其中一項操作：
    
      - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。 如果您的所有使用者都位於 Microsoft Exchange Server 2013 或更新版本，您可以在 Exchange 中封存所有使用者的 Lync 通訊。 在此情況下，您不需要設定 SQL Server 封存儲存區。
    
      - 若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：
        
          - 在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。
        
          - 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
        
          - 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。

9.  若要使用 SQL Server 儲存區鏡像，請選取 **[啟用 Sql Server 儲存區鏡像**]，然後執行下列動作：
    
      - 若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。
    
      - 若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：
        
        1.  在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。
        
        2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
        
        3.  如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
      - 如果您啟用 SQL Server 鏡像，而且想要包含 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 服務器的健康情況及鏡像實例) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：
        
        1.  在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。
        
        2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。
        
        3.  如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。

10. 若要儲存設定，請按一下 [確定]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

