---
title: Lync Server 2013：變更封存資料庫選項
description: Lync Server 2013：變更封存資料庫選項。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3751be63e17688ad9258b9773a1a5397b67952
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543579"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a>在 Lync Server 2013 中變更封存資料庫選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您使用 SQL Server storage 部署封存，以封存任何使用者的儲存體，您可以進行下列資料庫儲存變更：

  - 使用不同的 SQL Server 資料庫來封存儲存體。 這包括主要封存資料庫和您用來進行 SQL Server 鏡像的任何資料庫。

  - 切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 2013 伺服器上。 如果您的所有使用者都位於 Exchange 2013 伺服器上，而您想要將 Microsoft Exchange storage 用於部署中的所有使用者，則應該從拓撲中移除 SQL Server 儲存區資料庫。

若要進行這項變更，您必須執行拓撲產生器、進行變更，然後重新發佈拓撲。 您可以使用拓撲產生器來執行這項作業。 除非您的 Lync 使用者不是位於 Exchange 2013 伺服器上，否則請勿指定封存 **Sql server 儲存區** 或 **啟用 SQL server 儲存區鏡像** 資訊。

<div>

## <a name="to-change-your-archiving-database-option"></a>變更封存資料庫選項

1.  在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將元件新增至拓撲），則必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶。而且具有在您用於 Lync Server 2013 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的任意自由存取控制清單 (dacl) ，或具有 (同等權利的帳戶。

    
    </div>

2.  啟動拓撲產生器。

3.  在主控台樹狀目錄中，瀏覽至部署封存的前端集區，然後按一下要變更資料庫選項的前端集區名稱。

4.  在 [動作]**** 功能表上，按一下 [編輯屬性]****。

5.  在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。

6.  向下捲動至 **[封存]**。

7.  在 **[封存]** 中，執行下列動作：
    
      - 如要變更至不同的現有 SQL Server 儲存區，在 [封存 SQL Server 儲存區]**** 的下拉式清單方塊中，執行下列動作：
        
          - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。
        
          - 如要指定新的 SQL Server 儲存區，按一下 **[新增]**，然後在 **[定義新的 SQL Server 儲存區]** 對話方塊中，執行下列動作：
            
              - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。
            
              - 若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：
                
                  - 在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。
                
                  - 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
                
                  - 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
      - 如要新增 SQL Server 儲存區作為鏡像，或者變更至不同的現有 SQL Server 儲存區作為 SQL Server 儲存區鏡像，則選取 **[啟用 SQL Server 儲存區鏡像]**，然後執行下列動作：
        
          - 若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。
        
          - 若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：
            
            1.  在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。
            
            2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
            
            3.  如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
        
          - 如果您啟用 SQL Server 鏡像，並且想要新增或變更 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 服務器的健康情況及鏡像實例) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：
            
            1.  在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。
            
            2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。
            
            3.  如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
      - 若要切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 2013 伺服器上 (如果您部署中的所有使用者都位於 Exchange 2013 伺服器) 上，請刪除封存資料庫的所有資訊。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您有任何 Lync 使用者不是位於 Exchange 2013 伺服器上，請勿刪除 SQL Server 儲存區資訊。

    
    </div>

8.  如要儲存設定，按一下 **[確定]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 在您發佈新的拓撲之前，您在拓撲產生器中所做的變更不會生效。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">發行更新的拓撲以在 Lync Server 2013 中新增封存資料庫</A> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

