---
title: Lync Server 2013：發行拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46212fc9910885ed1d6d833ef0f4b30c3a49b7c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發佈拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-01_

若要在新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。 您也可以委派適當的系統管理員權利和使用權限。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組中的成員資格。

在拓撲產生器中定義拓撲之後，您必須將拓撲發行至中央管理存放區。 中央管理存放區為定義、設定、維護、管理、描述及操作 Lync Server 2013 部署所需的資料提供了可靠且 schematized 的儲存。 它也會驗證資料，以協助確保設定的一致性。 對此設定資料所做的所有變更都會發生在中央管理存放區，消除「不同步」的問題。 資料的唯讀複本會複製到拓撲中的所有伺服器，包括 Edge Server。

<div>


> [!NOTE]  
> SQL Server 至少需要 20 GB 的可用磁碟空間，才可成功發行初始拓撲，並建立中央管理伺服器。



</div>

<div>


> [!NOTE]  
> 僅限 Enterprise Edition：若要發行拓撲，SQL Server 後端伺服器必須上線，並納入防火牆例外中以供人存取。 如需指定防火牆例外狀況的詳細資訊，請參閱 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">瞭解 SQL Server 的防火牆需求（含 Lync Server 2013</A>）。 如需設定 SQL Server 的詳細資訊，請參閱 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE SQL Server For Lync Server 2013</A>。



</div>

<div>

## <a name="to-publish-a-topology"></a>若要發行拓撲

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  選取本機檔案以開啟其中的拓撲。如果您在操作當初用於定義拓撲的電腦，檔案就位於您在稍早步驟儲存該檔案的位置。此位置通常是當初設定拓撲的使用者的 Documents 資料夾。

3.  在 [ **Lync Server 2013** ] 節點上按一下滑鼠右鍵，然後按一下 [ **發行拓撲**]。

4.  在 **[發行拓撲]** 頁面上，按 **[下一步]**。

5.  在 **[建立資料庫]** 頁面上，選取您要發行的資料庫。
    
    <div>
    

    > [!NOTE]  
    > 如果您不具有建立某些資料庫的適當權限，可以清除那些資料庫旁邊的核取方塊，讓具有適當權限的其他人稍後再來建立資料庫。 如需詳細資訊，請參閱 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。

    
    </div>

6.  (選用) 按一下 **[進階]**。 [Advanced SQL Server 資料檔案] 位置選項可讓您選取下列選項：
    
      - **自動判斷資料庫檔案位置** – 此選項會根據 SQL Server 型伺服器上的磁碟組態，判斷最佳的運作效能，將記錄和資料檔案分散至最佳位置。
    
      - **使用 SQL Server 執行個體預設值** – 此選項會使用執行個體設定值，將記錄和資料檔案存放在 SQL Server 型伺服器上。此選項不使用 SQL Server 型伺服器的運作功能來判斷記錄和資料的最佳位置。SQL Server 系統管理員通常會將記錄和資料檔案移至對於 SQL Server 型伺服器和組織管理程序而言適合的位置。
    
    依序按一下 **[確定]** 和 **[下一步]**。

7.  在 [ **選取中央管理伺服器** ] 頁面上，選取前端集區。

8.  (選用) 按一下 **[進階]**。 [高級 SQL Server 資料檔案] 位置選項可讓您選取下列選項：
    
      - **自動判斷資料庫檔案位置** – 此選項會根據 SQL Server 型伺服器上的磁碟組態，判斷最佳的運作效能，將記錄和資料檔案分散至最佳位置。
    
      - **使用 SQL Server 執行個體預設值** – 此選項會使用執行個體設定值，將記錄和資料檔案存放在 SQL Server 型伺服器上。此選項不使用 SQL Server 型伺服器的運作功能來判斷記錄和資料的最佳位置。SQL Server 系統管理員通常會將記錄和資料檔案移至對於 SQL Server 型伺服器和組織管理程序而言適合的位置。
    
    按一下 **[確定]**。

9.  按 **[下一步]** 完成發行程序。

10. 當發行程序完成時，按一下 **[完成]**。
    
    成功發佈拓撲之後，您可以開始在拓撲中執行 Lync Server 2013 的各部伺服器上安裝中央管理存放區的本機複本。 建議您從第一部前端集區開始。

</div>

<div>

## <a name="see-also"></a>另請參閱


[為 Lync Server 2013 設定前端伺服器和前端集區](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

