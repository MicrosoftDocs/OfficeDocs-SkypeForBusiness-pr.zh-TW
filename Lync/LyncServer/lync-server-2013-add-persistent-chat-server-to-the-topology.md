---
title: Lync Server 2013：將 Persistent Chat Server 新增至拓撲
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
ms.openlocfilehash: 4656c21d9d28d84259bfaa108c399f36bd2c3d72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521440"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中將 Persistent Chat Server 新增至拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

您必須在拓撲中納入 Lync Server 2013 和 Persistent Chat Server 支援，才能設定您的部署以支援 Persistent Chat Server。 本主題中的資訊說明如何使用拓撲產生器，將 Persistent Chat Server 支援新增至現有的拓撲。

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>將 Persistent Chat Server 新增至拓撲

請執行下列步驟來安裝單一持久聊天伺服器集區，而不需要災難修復設定。 若要設定高可用性和嚴重損壞修復的延伸持久聊天伺服器集區，請參閱部署檔中的在 [Lync server 2013 中設定 Persistent Chat server，以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 。

若要部署多個 Persistent Chat Server 集區，請對每個集區重複相同的程式。

1.  在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用本機使用者群組的成員帳戶來定義拓撲，但發行拓撲（安裝 Lync Server 2013 Server 所需）。您必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶，且具有在您要用於 Persistent Chat Server 檔案存放區之檔案存放區上的「完全控制」許可權 (（即讀取、寫入及修改) ），如此一來 (，拓撲產生器才能設定所需的 dacl) ，或具有對等權利的帳戶。

    
    </div>

2.  啟動拓撲產生器。

3.  在主控台樹中，流覽至 [ **Persistent chat** 集區] 節點，並展開以選取 [Persistent chat Server 集區]，或以滑鼠右鍵按一下該節點，然後選取 [ **新增持久聊天集**區]。 您必須定義集區的完整網域名稱 (FQDN)，並指出集區將是單一伺服器集區或多重伺服器集區部署。
    
    您可以選擇 [多重電腦集區]**** 或 [單一電腦集區]****。 如果您計畫在 Persistent Chat Server 集區中有一個以上的 Persistent Chat Server 前端伺服器，請選擇前者。 立即或稍後選擇，這是因為建立單一電腦集區後，稍後便無法新增其他伺服器。 如果您選擇 [多部電腦集區]，請輸入組成集區之個別 Persistent Chat Server 前端伺服器的名稱。
    
    <div>
    

    > [!IMPORTANT]  
    > 若要在 Lync Server 2013 Standard Edition server 上安裝 Persistent Chat Server role &nbsp; ，FQDN 必須符合 Standard edition server 的 fqdn。

    
    </div>

4.  定義 Persistent Chat Server 集區的簡易 **顯示名稱** 。 顯示名稱可供自訂用戶端使用，特別是在有多個 Persistent Chat Server 集區時，可以區別會議室。

5.  定義 Persistent Chat Server 使用的埠，以與 Lync Server 前端伺服器進行通訊。 預設的連接埠為 5041。

6.  如果您的組織需要規範支援，請選取 [用規範記錄]**** 核取方塊。 如有選取，Persistent Chat Server 規範服務會與 Persistent Chat Server 前端伺服器安裝在相同的電腦上。 稍後會提示您選取 SQL Server 後端伺服器以進行 Persistent Chat Server 相容性。

7.  為 Persistent Chat Server 集區指派網站相關性。 選取 [**使用此集區作為網站 \<SiteName\> 預設值**] 核取方塊，或**使用此集區作為所有網站的預設**值，將此 Persistent Chat Server 集區指定為目前網站或所有網站的預設集區。 當 Lync 2013 用戶端用來建立及管理聊天室時，會使用與使用者網站相關聯的預設集區建立和管理體驗，讓其可以將會議室建立及管理作業路由傳送至該集區。 這只有當您部署多個 Persistent Chat Server 集區，且想要使用 Persistent Chat Server 的聊天室建立及管理功能時，才適用。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以使用 Persistent Chat Server 軟體發展工具組 (SDK) ，自訂聊天室建立和管理功能。<BR>如需如何設定 SQL Server 備份資料庫以進行嚴重損壞修復的詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中設定 Persistent Chat Server 以取得高可用性和嚴重損壞修復</A> 。

    
    </div>

8.  透過執行下列其中一項操作，定義 **Persistent Chat Server 後端 (的 SQL 存放區。) 儲存聊天室內容 ** 的方式：
    
      - 若要使用現有的 SQL Server 資料庫，請在下拉式清單中，按一下您要使用之 SQL Server 資料庫的名稱。
    
      - 若要指定新的 SQL Server 資料庫，請按一下 [ **新增**]，然後在 **[定義新的 SQL 存放區**] 中執行下列作業：
    
    <!-- end list -->
    
      - 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 資料庫之 sql SERVER 的 FQDN。
    
      - 選取 [預設執行個體]**** 使用預設執行個體，或者，若要指定不同的執行個體，請選取 [具名執行個體]****，並指定要使用的執行個體。

9.  如果您已啟用規範，請定義 SQL Server 規範資料庫。
    
    <div>
    

    > [!IMPORTANT]  
    > 如需如何針對 Persistent Chat Server 資料庫和 Persistent Chat Server 合規性資料庫設定高可用性之 SQL Server 鏡像的詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中設定 Persistent Chat Server，以取得高可用性和嚴重損壞修復</A> 。

    
    </div>

10. 定義檔案存放區。 檔案存放區是儲存任何上傳至檔案儲存機制的檔案副本所用的資料夾 (例如，儲存張貼於聊天室的檔案附件)。 在多重伺服器持久聊天伺服器拓撲的情況下，這必須是通用命名慣例 (UNC) 路徑;而且，針對單一伺服器的持久聊天伺服器拓撲，它可以是本機檔路徑。
    
    若要使用現有的檔案存放區，請執行下列動作：
    
      - 在 [檔案伺服器 FQDN]**** 中，指定您要建立新檔案存放區的檔案存放區 FQDN。
    
      - 在 [檔案共用]**** 中，指定要使用的檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以在建立檔案存放區之前，先在拓撲產生器中定義檔案存放區，但是您必須先在您定義的位置中建立檔案存放區，然後才能發行拓撲。

    
    </div>

11. 選取此 Persistent Chat Server 集區的下一個躍點要使用的前端伺服器集區。 這是可以將 Persistent Chat Server 要求路由傳送至此集區的前端伺服器集區。

12. 若要儲存組態，請按一下 [完成]****。 Persistent Chat Server 集區會出現在拓撲產生器中，且附帶您的特定集區設定。
    
    若要立即發佈您已有持久聊天伺服器的更新拓撲，請參閱部署檔中的在 [Lync Server 2013 中發佈更新的拓撲](lync-server-2013-publish-the-updated-topology.md) 。
    
    <div>
    

    > [!NOTE]  
    > 在已開啟拓撲產生器的情況下，您可以繼續在 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中發佈更新的拓撲中的</A> 步驟3，以開始發行更新的拓撲。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

