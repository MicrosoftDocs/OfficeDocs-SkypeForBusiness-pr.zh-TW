---
title: 部署 Lync Server 2013 試驗集區
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
ms.openlocfilehash: 9489db1fef9b836749fe4f381e717a4d406f5938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502970"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a>部署 Lync Server 2013 試驗集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-22_

遷移至 Lync Server 2013 所需的第一步是部署試驗集區。 試驗集區是您用 Lync Server 2010 部署來測試 Lync Server 2013 共存的位置。 共存是一種暫時的狀態，會持續進行，直到您將所有使用者和集區移至 Lync Server 2013 為止。

當您部署試驗集區時，會用到 [定義新前端集區精靈]。 您應該在 lync server 2010 集區中的 Lync Server 2013 試驗集區中部署相同的功能和工作負載。 如果您已部署封存伺服器、監控伺服器或 System Center Operations Manager 以封存或監控 Lync Server 2010 環境，且您想要在整個遷移期間繼續封存或監控，您也必須在試驗環境中部署這些功能。 您部署以封存或監視 Lync Server 2010 環境的版本，將不會在 Lync Server 2013 環境中捕獲資料。

<div>


> [!NOTE]  
> 下列程序討論在整個試驗集區部署程序中，應考量的功能和設定。 本節只著重在部署試驗集區時應該考量的要點。 如需詳細步驟，請參閱 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A> 部署指南。



</div>

**部署 Lync Server 2013 試驗集區**

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  展開樹狀目錄，直到您進入 **Lync Server 2013** **Enterprise Edition 前端**集區。

3.  以滑鼠右鍵按一下 [ **Enterprise Edition 前端**集區]，然後選取 [ **新增前端集**區]。
    
    ![拓撲產生器伺服器集區選取子功能表](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓撲產生器伺服器集區選取子功能表")

4.  輸入集區 FQDN。 當您定義試驗集區時，您可以選擇部署 Enterprise Edition 前端集區或 Standard Edition server。 Lync Server 2013 不需要您的試驗集區功能符合您舊版集區中部署的功能。
    
    <div>
    

    > [!WARNING]  
    > 您為試驗集區所定義的集區或伺服器完整網域名稱 (FQDN) 不得重複。 它不符合目前部署的 Lync Server 2010 集區或任何其他目前部署的伺服器的名稱。

    
    </div>
    
    ![[定義新前端集區] [FQDN] 頁面](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "[定義新前端集區] [FQDN] 頁面")

5.  在「選取功能」**** 頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。 例如，如果您只部署立即訊息 (IM) 和目前狀態功能，則可以選取 [會議] 核取方塊以允許多方 IM，但是不要選取 [電話撥入式 (PSTN) 會議]、[企業語音] 或 [通話許可控制] 核取方塊，因為這些功能代表語音、視訊和共同作業會議功能。 如需選取功能的其他資訊，請參閱部署檔中的在 [Lync server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。
    
    ![前端集區選取功能頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端集區選取功能頁面")

6.  在 [ **選取組合伺服器角色** ] 頁面上，建議您在 Lync server 2013 中組合轉送伺服器。 當您將舊版拓撲與 Lync Server 2013 合併時，我們必須先組合 Lync Server 2010 轉送伺服器。 在合併拓撲並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留組合轉送伺服器，或在將轉送伺服器角色移2013至獨立伺服器時，將其變更為獨立伺服器。
    
    ![前端集區選取 [組合伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端集區選取 [組合伺服器角色] 頁面")

7.  在「建立伺服器角色與此前端集區的關聯」**** 頁面上，於試驗集區部署期間，請勿選擇 [啟用要由此前端集區的媒體元件使用的 Edge 集區]**** 選項。此為您會在移轉後期階段時才啟用及上線的功能。目前請將此設定保留清空。
    
    ![[建立伺服器角色與前端集區的關聯] 頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "[建立伺服器角色與前端集區的關聯] 頁面")

8.  在「選取 Office Web Apps Server」**** 頁面上，按一下 [新增]****，並指定應用程式伺服器的 FQDN。
    
    ![定義新的 Office Web Apps Server FQDN 屬性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新的 Office Web Apps Server FQDN 屬性")

9.  在 [ **定義封存 SQL Server 存放區** ] 頁面上，定義 lync server 封存與監控的 sql server 儲存區時，請選取先前針對 lync server 2013 建立的 sql server 實例。
    
    ![定義封存 SQL Server 儲存區頁面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定義封存 SQL Server 儲存區頁面")

10. 若要發行您的拓撲，請以滑鼠右鍵按一下 [ **Lync Server** ] 節點，然後按一下 [ **發行拓撲**]。
    
    ![顯示已設定拓撲的拓撲產生器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "顯示已設定拓撲的拓撲產生器")

11. 當發行程序完成時，按一下 **[完成]**。

若要安裝設定存放區的本機複本並啟動必要的服務，請參閱部署檔中的 [設定前端伺服器和前端集區的 Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 。


</div>

<span> </span>

</div>

</div>

</div>

