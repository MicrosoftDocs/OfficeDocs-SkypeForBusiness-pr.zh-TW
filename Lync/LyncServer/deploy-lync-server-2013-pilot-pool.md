---
title: 部署 Lync Server 2013 試用版池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe36710ab0acee23af1d8b83adece108cf86c4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>部署 Lync Server 2013 試用版池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-22_

遷移至 Lync Server 2013 所需的第一個步驟是部署試驗區。 試驗池是您使用 Lync Server 2010 部署來測試 Lync Server 2013 的共存位置。 [共存] 是一個暫時的狀態，一直持續到您將所有使用者和池移至 Lync Server 2013 為止。

當您部署試生產池時，請使用 [定義新的前端池] 嚮導。 您應該在 lync Server 2010 池中部署 Lync Server 2013 試驗池中的相同功能和工作負載。 如果您已部署封存伺服器、監視伺服器或 System Center Operations Manager 以進行封存或監視您的 Lync Server 2010 環境，而且您想要在整個遷移期間繼續進行封存或監視，您也必須部署這些您的試點環境中的功能。 您部署以封存或監視 Lync Server 2010 環境的版本，將無法在 Lync Server 2013 環境中捕獲資料。

<div>


> [!NOTE]  
> 下列程式討論您在整個試驗池部署程式中應考慮的功能和設定。 此區段只會醒目提示您要考慮的重要重點，做為您的試驗池部署的一部分。 如需詳細步驟，請參閱<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。



</div>

**部署 Lync Server 2013 試用版池**

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

2.  展開樹狀結構，直到您到達**Lync Server 2013** **企業版前端池**為止。

3.  以滑鼠右鍵按一下 [**企業版頂層端池**]，然後選取 [**新的前端池**]。
    
    ![拓撲產生器伺服器集區選取子功能表](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓撲產生器伺服器集區選取子功能表")

4.  輸入 [池 FQDN]。 當您定義您的試驗池時，您可以選擇部署企業版的前端池或標準版伺服器。 Lync Server 2013 不需要您的試點專案池功能與舊版池中部署的功能相符。
    
    <div>
    

    > [!WARNING]  
    > 您為試驗池定義的「池」或「伺服器」完整功能變數名稱（FQDN）必須是唯一的。 它無法與目前已部署的 Lync Server 2010 池或任何其他目前部署的伺服器名稱相符。

    
    </div>
    
    ![[定義新前端集區精靈 FQDN] 頁面](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "[定義新前端集區精靈 FQDN] 頁面")

5.  在 [**選取功能**] 頁面上，選取您要用於此前端池之功能的核取方塊。 例如，如果您只部署立即訊息（IM）和目前狀態功能，您可以選取 [會議] 核取方塊以允許多方 IM，但不會選取 [撥入（PSTN）會議]、[企業語音] 或 [通話許可控制] 核取方塊。因為它們代表語音、影片和共同作業會議功能。 如需有關選取功能的其他資訊，請參閱部署檔中的[Lync server 2013 中的定義及設定前端池或標準版伺服器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。
    
    ![前端集區的 [選取功能] 頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端集區的 [選取功能] 頁面")

6.  在 [**選取 collocated 伺服器角色**] 頁面上，我們建議您 Collocate Lync server 2013 中的中繼伺服器。 當您將舊版拓撲與 Lync Server 2013 合併時，我們會要求您先 collocate Lync Server 2010 轉送伺服器。 在合併拓朴並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留 collocated 轉送伺服器，或在部署期間將轉送伺服器角色移至 Lync Server 2013 時，將它變更為獨立伺服器。程式.
    
    ![前端集區的 [選取組合的伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端集區的 [選取組合的伺服器角色] 頁面")

7.  在 [**將伺服器角色與此前端池建立關聯**] 頁面上的 [試驗池] 部署期間，請不要選擇 [**啟用此前端池的媒體元件要使用 Edge 池**] 選項。 這是您將在稍後的遷移階段啟用並加入線上的功能。 暫時清除此設定。
    
    ![[建立伺服器角色與前端集區的關聯] 頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "[建立伺服器角色與前端集區的關聯] 頁面")

8.  在 [**選取 Office Web Apps 伺服器**] 頁面上，按一下 [**新增**]，然後指定應用程式伺服器的 FQDN。
    
    ![定義新 Office Online Server FQDN 內容](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新 Office Online Server FQDN 內容")

9.  在**定義 [封存 Sql Server store** ] 頁面上，定義 [lync server 封存與監控的 sql server store] 時，請選取舊版 lync server 2013 建立的 sql server 實例。
    
    ![[定義封存 SQL Server 存放區] 頁面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "[定義封存 SQL Server 存放區] 頁面")

10. 若要發佈拓撲，請以滑鼠右鍵按一下**Lync Server**節點，然後按一下 [**發佈拓撲**]。
    
    ![顯示設定拓撲的拓撲產生器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "顯示設定拓撲的拓撲產生器")

11. 發佈程式完成後，請按一下 **[完成]**。

若要安裝 configuration store 的本機複本並啟動必要的服務，請參閱部署檔中的[Lync Server 2013 設定前端伺服器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。


</div>

<span> </span>

</div>

</div>

</div>

