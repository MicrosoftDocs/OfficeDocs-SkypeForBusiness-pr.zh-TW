---
title: Lync Server 2013：將常設聊天室伺服器新增至拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中將常設聊天室伺服器新增至拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

您必須先在拓撲中加入 Lync Server 2013、持久聊天伺服器支援，然後才能設定您的部署支援永久聊天伺服器。 本主題中的資訊說明如何使用拓撲建立器，將持續聊天伺服器支援新增至現有的拓撲。

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>在拓撲中新增持續聊天伺服器

若要在沒有災害復原設定的情況下安裝單一持久聊天伺服器池，請執行下列步驟。 若要針對高可用性和災難復原來設定延伸持久聊天伺服器池，請參閱在部署檔中設定[持久聊天伺服器以取得 Lync Server 2013 的高可用性和災害復原](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

若要部署多個持續聊天伺服器池，請針對每個池重複執行相同的程式。

1.  在執行 Lync Server 2013 或已安裝 Lync Server 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權限的帳戶）。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須安裝 Lync Server 2013 server。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您要用於持續聊天伺服器檔案存放區的檔案存放區上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立器可以設定所需的 dacl。或具有同等權利的帳戶。

    
    </div>

2.  啟動拓撲建立器。

3.  在主控台樹中，流覽至 [**永久聊天池**] 節點，然後展開以選取持續聊天伺服器池，或以滑鼠右鍵按一下該節點，然後選取 [**新增持久聊天] 池**。 您必須定義池子的完整功能變數名稱（FQDN），並指出該池是單一伺服器池或多重伺服器池部署。
    
    您可以選擇**多個電腦池**或**單一電腦池**。 如果您打算在持久聊天伺服器池中安裝多個持續聊天伺服器前端伺服器，請選擇前者。 現在就進行這項選擇，或在稍後進行，因為在您建立單一電腦池之後，您稍後就不能再新增其他伺服器。 如果您選擇多個電腦池，請輸入組成該池的個別持久聊天伺服器前端伺服器的名稱。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果要在 Lync Server 2013&nbsp;標準版伺服器上安裝永久聊天伺服器角色，fqdn 必須與標準版伺服器的 fqdn 相符。

    
    </div>

4.  定義持續聊天伺服器池的簡單**顯示名稱**。 顯示名稱可以由自訂用戶端使用，特別是在有多個持續聊天伺服器池時，以區別會議室。

5.  定義持續聊天伺服器用來與 Lync Server 前端伺服器進行通訊的埠。 預設埠是5041。

6.  如果您的組織需要合規性支援，請選取 [**啟用合規性**] 核取方塊。 如果已選取，持久的聊天伺服器合規性服務會安裝在與永久聊天伺服器前端伺服器相同的電腦上。 接著系統會提示您選取一個 SQL Server 後端伺服器，以進行持續聊天伺服器的相容性。

7.  針對持續聊天伺服器池指派網站關聯性。 選取 [**使用此 pool 做為網站\<SiteName\>的預設值**] 核取方塊，或**將此 pool 作為 [所有網站**] 的預設值，將此永久性聊天伺服器池指定為目前網站或所有網站的預設池。 當 Lync 2013 用戶端用來建立及管理會議室時，聊天室的建立和管理體驗會使用與使用者網站相關聯的預設池，以便在該池中傳送聊天室的建立和管理作業。 這僅適用于已部署多個持久聊天伺服器池，且想要使用持續聊天伺服器的聊天室建立和管理功能。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以使用持續聊天伺服器軟體發展工具組（SDK）來自訂聊天室的建立與管理功能。<BR>如需如何設定 SQL Server 備份資料庫以進行災難復原的詳細資料，請參閱在部署檔中<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">針對 Lync server 2013 的高可用性和災難復原設定持久聊天伺服器</A>。

    
    </div>

8.  您可以執行下列其中一項動作，**以定義持續式聊天伺服器後端（儲存聊天室內容的位置）的 SQL store** ：
    
      - 若要使用現有的 SQL Server 資料庫，請在下拉式清單中，按一下您要使用的 SQL Server 資料庫的名稱。
    
      - 若要指定新的 SQL Server 資料庫，請按一下 [**新增**]，然後在 **[定義新的 sql Store**] 中，執行下列動作：
    
    <!-- end list -->
    
      - 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 資料庫之 sql SERVER 的 FQDN。
    
      - 您可以選取 [**預設實例**] 來使用預設實例，或者，若要指定不同的實例，請選取 [**命名實例**]，然後指定您要使用的實例。

9.  如果您已啟用合規性，請定義 SQL Server 合規性資料庫。
    
    <div>
    

    > [!IMPORTANT]  
    > 如需有關如何針對持久聊天伺服器資料庫和持續性聊天伺服器規範資料庫設定 SQL Server 鏡像的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">持久聊天伺服器以取得 Lync Server 2013 的高可用性和災害復原</A>。

    
    </div>

10. 定義檔案存放區。 檔案存放區是儲存上傳至檔案存放庫之任何檔案複本的資料夾（例如，儲存張貼到聊天室的檔案附件）。 如果是多重伺服器持續聊天伺服器拓撲，這必須是通用命名慣例（UNC）路徑;而且，對於單一伺服器持續聊天伺服器拓撲，它可以是本機檔案路徑。
    
    若要使用現有的檔案存放區，請執行下列步驟：
    
      - 在 [檔案**伺服器 FQDN**] 中，指定您要在其中建立新檔案存放區之檔案存放區的 FQDN。
    
      - 在 [檔案**共用**] 中，指定您要使用的檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以在建立檔案存放區前，在拓撲結構建立器中定義檔案存放區，但您必須先在您定義的定義位置中建立檔案存放區，然後才能發佈拓撲。

    
    </div>

11. 選取要做為此持續聊天伺服器池的下一個躍點的前端伺服器池。 這是可將持續聊天伺服器要求路由至此池中的前端伺服器池。

12. 若要儲存配置，請按一下 **[完成]**。 [持續聊天伺服器] 池會出現在拓撲建立器中，並隨附您的特定 [池] 設定。
    
    若要立即發佈您已永久聊天伺服器的更新拓撲，請參閱在部署檔中[發佈 Lync Server 2013 的更新拓撲](lync-server-2013-publish-the-updated-topology.md)。
    
    <div>
    

    > [!NOTE]  
    > 在已開啟 [拓撲結構建立器] 的情況下，您可以繼續在<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中發佈更新拓撲中的</A>步驟3，開始發佈您更新的拓撲。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

