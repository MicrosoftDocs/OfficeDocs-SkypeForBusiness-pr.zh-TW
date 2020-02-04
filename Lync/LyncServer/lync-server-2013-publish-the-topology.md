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
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發行拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-01_

若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。 您也可以委派適當的管理員權力和許可權。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。

在拓撲建立器中定義拓朴之後，您必須將拓撲發佈到中央管理儲存體。 [中央管理] 儲存區提供可靠、schematized 的資料儲存，以定義、設定、維護、管理、描述及操作 Lync Server 2013 部署。 它也會驗證資料，以協助確保配置一致性。 此設定資料的所有變更都會出現在中央管理商店，消除「不同步」問題。 唯讀複本會將資料複製到拓撲中的所有伺服器，包括邊緣伺服器。

<div>


> [!NOTE]  
> SQL Server 需要至少 20 GB 的可用磁碟空間，才能成功發佈初始拓撲，並建立中央管理伺服器。



</div>

<div>


> [!NOTE]  
> 僅限 Enterprise Edition：若要發佈拓朴，SQL Server 的後端伺服器必須在線上，且在適當的地方出現防火牆例外狀況。 如需指定防火牆例外狀況的詳細資料，請參閱<A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">瞭解使用 Lync Server 2013 的 SQL Server 防火牆需求</A>。 如需有關設定 SQL Server 的詳細資訊，請參閱<A href="lync-server-2013-configure-sql-server-for-lync-server.md">設定 Lync server 2013 的 SQL Server</A>。



</div>

<div>

## <a name="to-publish-a-topology"></a>發佈拓撲

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  選取以從本機檔案開啟拓撲。 如果您在已定義拓撲的電腦上，這會位於您在先前步驟中儲存它的位置。 通常，這會是設定拓朴之使用者的 [檔] 資料夾。

3.  以滑鼠右鍵按一下**Lync Server 2013**節點，然後按一下 [**發佈拓撲**]。

4.  在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。

5.  在 [**建立資料庫**] 頁面上，選取您要發佈的資料庫。
    
    <div>
    

    > [!NOTE]  
    > 如果您沒有建立資料庫的適當許可權，您可以清除這些資料庫旁邊的核取方塊，而具有適當許可權的人員就可以在稍後建立資料庫。 如需詳細資訊，請參閱<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。

    
    </div>

6.  您也可以按一下 [**高級**]。 [高級 SQL Server 資料檔位置] 選項可讓您選取下列選項：
    
      - **自動判斷資料庫檔案位置**：此選項會將記錄和資料檔案散佈到最佳位置，以根據您的 SQL server 伺服器上的磁片設定來判斷最佳的操作效能。
    
      - **使用 SQL Server 實例預設值**–此選項使用實例設定，將記錄和資料檔案放到 SQL server 的伺服器。 這個選項不會使用 SQL Server server 伺服器的操作功能來判斷記錄和資料的最佳位置。 SQL Server 系統管理員通常會將記錄和資料檔移至適合 SQL Server 服務器與組織管理程式的位置。
    
    按一下 **[確定]**，然後按 **[下一步**]。

7.  在 [**選取中央管理伺服器**] 頁面上，選取 [前端] 池。

8.  您也可以按一下 [**高級**]。 [高級 SQL Server 資料檔位置] 選項可讓您選取下列選項：
    
      - **自動判斷資料庫檔案位置**：此選項會將記錄和資料檔案散佈到最佳位置，以根據您的 SQL server 伺服器上的磁片設定來判斷最佳的操作效能。
    
      - **使用 SQL Server 實例預設值**–此選項使用實例設定，將記錄和資料檔案放到 SQL server 的伺服器。 這個選項不會使用 SQL Server server 伺服器的操作功能來判斷記錄和資料的最佳位置。 SQL Server 系統管理員通常會將記錄和資料檔移至適合 SQL Server 服務器與組織管理程式的位置。
    
    按一下 [確定]****。

9.  按一下 **[下一步]** 以完成發佈程式。

10. 發佈程式完成後，請按一下 **[完成]**。
    
    成功發佈拓撲之後，您就可以開始在拓撲中執行 Lync Server 2013 的每個伺服器上安裝中央管理儲存的本機複本。 我們建議您從第一個前端池開始。

</div>

<div>

## <a name="see-also"></a>請參閱


[針對 Lync Server 2013 設定前端伺服器和前端集區](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

