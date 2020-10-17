---
title: 部署 Lync Server 2013 試驗集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df30b2aa45fe9519d724f904e8b375bed794042
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502952"
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

遷移至 Lync Server 2013 所需的第一步是部署試驗集區。 試驗集區是您用 Office 通訊伺服器 2007 R2 部署來測試 Lync Server 2013 共存的位置。 共存是一種暫時的狀態，會持續進行，直到您將所有使用者和集區移至 Lync Server 2013 為止。

當您部署試驗集區時，會用到 [定義新前端集區精靈]。 您應該在您的 Office 通訊伺服器 2007 R2 集區中，部署 Lync Server 2013 試驗集區中的相同功能和工作負載。 如果您已部署封存伺服器、監控伺服器或 System Center Operations Manager 以封存或監控您的 Office 通訊伺服器 2007 R2 環境，而且您想要在整個遷移期間繼續封存或監控，您也必須在試驗環境中部署這些功能。 您部署的版本若要封存或監視您的 Office 通訊伺服器 2007 R2 環境，將不會在 Lync Server 2013 環境中捕獲資料。

<div>


> [!NOTE]  
> 下列程序討論在整個試驗集區部署程序中，應考量的功能和設定。 本節只著重在部署試驗集區時應該考量的要點。 如需詳細步驟，請參閱 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A> 部署指南。



</div>

**部署 Lync Server 2013 試驗集區**

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  開啟拓撲產生器，並選擇建立新拓撲。

3.  輸入主要 SIP 網域。
    
    ![建立新的拓撲，定義主域頁面](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "建立新的拓撲，定義主域頁面")

4.  繼續完成精靈直到您達到 [定義新前端集區精靈]****。 按 [下一步]。

5.  輸入集區 FQDN。 當您定義試驗集區時，您可以選擇部署 Enterprise Edition 前端集區或 Standard Edition server。 Lync Server 2013 不需要您的試驗集區功能符合您舊版集區中部署的功能。
    
    <div>
    

    > [!WARNING]  
    > 您為試驗集區所定義的集區或伺服器完整網域名稱 (FQDN) 不得重複。 它不符合目前部署的 Office 通訊伺服器 2007 R2 集區或任何其他目前已部署的伺服器的名稱。

    
    </div>
    
    ![[定義前端集區 FQDN] 頁面](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "[定義前端集區 FQDN] 頁面")

6.  定義將要新增至集區的電腦。
    
    ![[定義新前端集區] 對話方塊](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "[定義新前端集區] 對話方塊")

7.  在「選取功能」**** 頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。 例如，如果您只部署立即訊息 (IM) 和目前狀態功能，則可以選取 [會議] 核取方塊以允許多方 IM，但是不要選取 [電話撥入式 (PSTN) 會議]、[企業語音] 或 [通話許可控制] 核取方塊，因為這些功能代表語音、視訊和共同作業會議功能。 如需選取功能的其他資訊，請參閱部署檔中的在 [Lync server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。
    
    ![前端集區選取功能頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端集區選取功能頁面")

8.  在 [ **選取組合伺服器角色** ] 頁面上，建議您在 Lync server 2013 中組合轉送伺服器。 當您將舊版拓撲與 Lync Server 2013 合併時，我們必須先組合 Office 通訊伺服器 2007 R2 轉送伺服器。 在合併拓撲並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留組合轉送伺服器，或在將轉送伺服器角色移2013至獨立伺服器時，將其變更為獨立伺服器。
    
    ![前端集區選取 [組合伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端集區選取 [組合伺服器角色] 頁面")

9.  在「建立伺服器角色與此前端集區的關聯」**** 頁面上，於試驗集區部署期間，請勿選擇 [啟用要由此前端集區的媒體元件使用的 Edge 集區]**** 選項。此為您會在移轉後期階段時才啟用及上線的功能。目前請將此設定保留清空。
    
    ![[建立伺服器角色與前端集區的關聯] 頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "[建立伺服器角色與前端集區的關聯] 頁面")

10. 在「選取 Office Web Apps Server」**** 頁面上，按一下 [新增]****，並指定應用程式伺服器的 FQDN。
    
    ![定義新的 Office Web Apps Server FQDN 屬性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新的 Office Web Apps Server FQDN 屬性")

11. 在 [ **定義封存 SQL Server 存放區** ] 頁面上，選取先前針對 Lync Server 2013 建立的 SQL Server 實例。
    
    ![定義封存 SQL Server 儲存區頁面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定義封存 SQL Server 儲存區頁面")

12. 在 [ **定義監控 SQL Server 存放區** ] 頁面上，選取先前針對 Lync Server 2013 建立的 SQL Server 實例。 按一下 [完成]****。

13. 從拓撲產生器最上面的節點，用滑鼠右鍵按一下 [Lync Server]****，再按一下 [編輯內容]****。 按一下 [簡單 URL]****。

14. 更新 [系統管理存取 URL]****。
    
    ![編輯屬性、簡單 URLs 頁面](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "編輯屬性、簡單 URLs 頁面")
    
    如需簡單 URLs 的其他資訊，請參閱部署檔中的主題 [編輯或設定簡單 URLs Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) 。

15. 從 [編輯內容]**** 中，按一下 [中央管理伺服器]****。

16. 從下拉式清單中，選取 [Lync Server 2013 集區]。
    
    ![編輯屬性、中央管理伺服器頁面](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "編輯屬性、中央管理伺服器頁面")

17. 按一下 [確定]，以關閉「編輯內容」**** 頁面。

18. 從 [動作]**** 功能表中，選取 [發行拓撲]****。

19. 當發行程序完成時，按一下 [完成]****。

20. 返回至 [Lync Server 2013 部署嚮導]，按一下 [ **安裝或更新 Lync Server 系統**]。
    
    ![Lync Server 2013 部署嚮導](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 部署嚮導")

若要安裝設定存放區的本機複本並啟動必要的服務，請參閱部署檔中的 [設定前端伺服器和前端集區的 Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 。


</div>

<span> </span>

</div>

</div>

</div>

