---
title: 部署 Lync Server 2013 試用版池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e9068ca3ff5a2827991869598a2066473cc5af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975507"
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

遷移至 Lync Server 2013 所需的第一個步驟是部署試驗區。 試驗池是您使用 Office 通訊伺服器 2007 R2 部署來測試 Lync Server 2013 的共存位置。 [共存] 是一個暫時的狀態，一直持續到您將所有使用者和池移至 Lync Server 2013 為止。

當您部署試生產池時，請使用 [定義新的前端池] 嚮導。 您應該在您的 Office 通訊伺服器 2007 R2 池中，部署 Lync Server 2013 試驗池中的相同功能和工作負載。 如果您已部署封存伺服器、監視伺服器或 System Center Operations Manager 以進行封存或監視您的 Office 通訊伺服器 2007 R2 環境，而您想要在整個遷移期間繼續進行封存或監視，您必須也可以在您的試點環境中部署這些功能。 您部署以封存或監視 Office 通訊伺服器 2007 R2 環境的版本，將無法在 Lync Server 2013 環境中捕獲資料。

<div>


> [!NOTE]  
> 下列程式討論您在整個試驗池部署程式中應考慮的功能和設定。 此區段只會醒目提示您要考慮的重要重點，做為您的試驗池部署的一部分。 如需詳細步驟，請參閱<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。



</div>

**部署 Lync Server 2013 試用版池**

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

2.  開啟拓撲建立器，然後選擇建立新的拓撲。

3.  輸入主要 SIP 網域。
    
    ![建立新拓撲、定義主要網域頁面](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "建立新的拓撲，定義主要網域頁面")

4.  繼續完成嚮導，直到您到達 [**定義新的前臺端池**] 嚮導。 按一下 [下一步]。

5.  輸入 [池 FQDN]。 當您定義您的試驗池時，您可以選擇部署企業版的前端池或標準版伺服器。 Lync Server 2013 不需要您的試點專案池功能與舊版池中部署的功能相符。
    
    <div>
    

    > [!WARNING]  
    > 您為試驗池定義的「池」或「伺服器」完整功能變數名稱（FQDN）必須是唯一的。 它無法與目前已部署的 Office 通訊伺服器 2007 R2 池或其他任何其他伺服器的名稱相符。

    
    </div>
    
    ![定義 [前端池 fqdn] 頁面]以(images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "定義 [前端池 fqdn] 頁面")

6.  定義將新增至池中的電腦。
    
    [![定義新的前端池] 對話方塊][(images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "定義新的前端池] 對話方塊")

7.  在 [**選取功能**] 頁面上，選取您要用於此前端池之功能的核取方塊。 例如，如果您只部署立即訊息（IM）和目前狀態功能，您可以選取 [會議] 核取方塊以允許多方 IM，但不會選取 [撥入（PSTN）會議]、[企業語音] 或 [通話許可控制] 核取方塊。因為它們代表語音、影片和共同作業會議功能。 如需有關選取功能的其他資訊，請參閱部署檔中的[Lync server 2013 中的定義及設定前端池或標準版伺服器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。
    
    ![前端池選取功能頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "正面端池選取 [功能] 頁面")

8.  在 [**選取 collocated 伺服器角色**] 頁面上，我們建議您 Collocate Lync server 2013 中的中繼伺服器。 當您將舊版拓撲與 Lync Server 2013 合併時，我們會要求您先 collocate Office 通訊伺服器 2007 R2 轉送伺服器。 在合併拓朴並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留 collocated 轉送伺服器，或在部署期間將轉送伺服器角色移至 Lync Server 2013 時，將它變更為獨立伺服器。程式.
    
    ![前端池選取 [collocated 伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池選取 [collocated 伺服器角色] 頁面")

9.  在 [**將伺服器角色與此前端池建立關聯**] 頁面上的 [試驗池] 部署期間，請不要選擇 [**啟用此前端池的媒體元件要使用 Edge 池**] 選項。 這是您將在稍後的遷移階段啟用並加入線上的功能。 暫時清除此設定。
    
    ![關聯伺服器角色與前端池頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "將伺服器角色與前端池頁面建立關聯")

10. 在 [**選取 Office Web Apps 伺服器**] 頁面上，按一下 [**新增**]，然後指定應用程式伺服器的 FQDN。
    
    ![定義新的 Office Web Apps 伺服器 fqdn 屬性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新的 Office WEB apps server fqdn 屬性")

11. 在 [**定義存檔 SQL Server store** ] 頁面上，選取舊版 Lync Server 2013 建立的 SQL Server 實例。
    
    ![定義 [封存 Sql server store]] （定義封存）(images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "[sql server Store") ] （存檔）頁面

12. 在 [**定義監視 SQL Server 存放區**] 頁面上，選取舊版 Lync server 2013 建立的 SQL Server 實例。 按一下 **[完成]**。

13. 從 [拓撲建立器] 的上方節點，以滑鼠右鍵按一下 [ **Lync Server** ]，然後按一下 [**編輯屬性]。** 按一下 [**簡易 url**]。

14. 更新**管理存取 URL**。
    
    ![編輯屬性、簡單 url 頁面](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "編輯屬性、簡單 url 頁面")
    
    如需簡單 Url 的其他資訊，請參閱部署檔中的 [[在 Lync Server 2013 編輯或設定簡單 url](lync-server-2013-edit-or-configure-simple-urls.md) ] 主題。

15. 從 [**編輯屬性**] 中，按一下 [**中央管理伺服器**]。

16. 從下拉式清單中，選取 [Lync Server 2013] 池。
    
    ![編輯屬性、集中式管理伺服器頁面](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "編輯屬性、中央管理伺服器頁面")

17. 按一下 [確定] 以關閉 **[編輯屬性**] 頁面。

18. 從 [**動作**] 功能表中，選取 [**發佈拓撲**]。

19. 發佈程式完成後，請按一下 **[完成]**。

20. 返回 [Lync Server 2013 部署嚮導]，然後按一下 [**安裝或更新 Lync Server 系統**]。
    
    ![Lync server 2013 部署嚮導](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 部署嚮導")

若要安裝 configuration store 的本機複本並啟動必要的服務，請參閱部署檔中的[Lync Server 2013 設定前端伺服器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。


</div>

<span> </span>

</div>

</div>

</div>

