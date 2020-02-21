---
title: Lync Server 2013： 變更封存資料庫選項
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
ms.openlocfilehash: a820ca891ceb8196f8b4e0d2e023799f36e9e9ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Lync Server 2013 中的變更封存資料庫選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

如果您部署的任何使用者的封存儲存區中使用 SQL Server 儲存區的封存，您可以在儲存變更時進行下列資料庫：

  - 封存存放區使用不同的 SQL Server 資料庫。 這包括主要封存資料庫與您使用 SQL Server 鏡像的任何資料庫。

  - 切換到 [Microsoft Exchange 整合來儲存封存資料和 Exchange 2013 伺服器上的檔案。 如果您的所有使用者都位於您的 Exchange 2013 伺服器，而且您想要使用 Microsoft Exchange 儲存區中部署的所有使用者，您應該從拓撲移除 SQL Server 儲存區資料庫。

若要讓這些變更其中一項，您必須執行拓撲產生器、 進行的變更，並再一次發行拓撲。 若要這麼做，您可以使用拓撲產生器]。 除非您有不位於 Exchange 2013 伺服器的 Lync 使用者未指定**封存 SQL Server 儲存區**，或**啟用 SQL Server 儲存區鏡像**資訊。

<div>

## <a name="to-change-your-archiving-database-option"></a>變更封存資料庫選項

1.  在電腦上，執行 Lync Server 2013 中，或 Lync Server 系統管理工具安裝，登入使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶）。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要元件新增至拓撲，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且您使用 Lync Server 2013 檔案存放區 （亦即，以便拓撲產生器可以設定必要的判別存取控制清單 （在檔案共用上具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶Dacl)，或具有相等的權限的帳戶。

    
    </div>

2.  啟動拓撲產生器]。

3.  在主控台樹狀目錄中，瀏覽至部署封存的前端集區，然後按一下要變更資料庫選項的前端集區名稱。

4.  在 [動作]**** 功能表上，按一下 [編輯屬性]****。

5.  在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。

6.  向下捲動至 **[封存]**。

7.  在 **[封存]** 中，執行下列動作：
    
      - 如要變更至不同的現有 SQL Server 儲存區，在 [封存 SQL Server 儲存區]**** 的下拉式清單方塊中，執行下列動作：
        
          - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。
        
          - 如要指定新的 SQL Server 儲存區，按一下 **[新增]**，然後在 **[定義新的 SQL Server 儲存區]** 對話方塊中，執行下列動作：
            
              - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。
            
              - 若要指定新的 SQL Server 儲存區，按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列動作：
                
                  - 在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的伺服器的 FQDN。
                
                  - 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
                
                  - 如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。
    
      - 如要新增 SQL Server 儲存區作為鏡像，或者變更至不同的現有 SQL Server 儲存區作為 SQL Server 儲存區鏡像，則選取 **[啟用 SQL Server 儲存區鏡像]**，然後執行下列動作：
        
          - 若要使用現有的 SQL Server 儲存區作為鏡像，在 [**封存 SQL Server 儲存區鏡像**] 下拉式清單方塊中，按一下您想要用於鏡像的 SQL Server 存放區的名稱。
        
          - 若要指定新的 SQL Server 儲存區作為鏡像，請按一下 [**新增**]，然後在 [**定義新 SQL Server 儲存區**] 對話方塊中，執行下列其中一項：
            
            1.  在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 儲存區的 SQL server 的 FQDN。
            
            2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
            
            3.  如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。
        
          - 如果您啟用 SQL Server 鏡像，並且想要新增或變更 SQL Server 鏡像見證 （第三個，個別的 SQL Server 執行個體，可偵測主要 SQL Server 伺服器的健康狀況和鏡像執行個體），選取 [**使用 SQL Server 鏡像見證啟用自動容錯移轉**] 核取方塊，，然後執行下列其中一項：
            
            1.  在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 鏡像見證伺服器的 FQDN。
            
            2.  按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。
            
            3.  如果指定的 SQL Server 執行個體在鏡像關聯中，選取 [**此 SQL 執行個體為鏡像關係**] 核取方塊，，然後在 [**鏡像連接埠號碼**，指定的連接埠號碼。
    
      - 若要切換至 Microsoft Exchange 整合來儲存封存資料和 Exchange 2013 伺服器 （如果您在部署中的所有使用者都位於您的 Exchange 2013 伺服器） 上的檔案，請刪除封存資料庫的所有資訊。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您有任何不位於 Exchange 2013 伺服器的 Lync 使用者時，請勿刪除 SQL Server 存放區資訊。

    
    </div>

8.  如要儲存設定，按一下 **[確定]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 在拓撲產生器所進行的變更才會生效直到您發佈新拓撲。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">發佈更新過的拓撲，以新增 Lync Server 2013 中的封存資料庫</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

