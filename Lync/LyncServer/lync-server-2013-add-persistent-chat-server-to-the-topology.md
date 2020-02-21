---
title: Lync Server 2013： 將 Persistent Chat Server 新增至拓撲
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
ms.openlocfilehash: 5ae7ca7e475fd106608dea09fedf250ef541a5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>將常設聊天室伺服器新增至 Lync Server 2013 中的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

您必須納入 Lync Server 2013，Persistent Chat Server 支援，您才能設定部署以支援 Persistent Chat Server 的拓撲中。 本主題中的資訊說明如何使用拓撲產生器將 Persistent Chat Server 支援新增至您現有的拓樸。

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>若要將 Persistent Chat Server 新增至拓撲

執行下列步驟安裝而不需要災害復原設定單一 Persistent Chat Server 集區。 設定高可用性和災害復原的延伸 Persistent Chat Server 集區，請參閱部署文件中的[Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

若要部署多個 Persistent Chat Server 集區，請針對每個集區重複相同的程序。

1.  在電腦上，執行 Lync Server 2013，或在 Lync Server 系統管理工具安裝上使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶） 登入。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要安裝 Lync Server 2013 伺服器，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且在您要使用 Persistent Chat Server 檔案存放區 （亦即，讓拓撲產生器可以設定必要的 Dacl） 的檔案存放區上具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶或具有相等的權限的帳戶。

    
    </div>

2.  啟動拓撲產生器]。

3.  在主控台樹狀目錄中，瀏覽至 [**常設聊天室集區**] 節點，並展開它選取 Persistent Chat Server 集區]，或在節點上按一下滑鼠右鍵，並選取 [**新增常設聊天室集區**。 您必須定義集區的完整網域名稱 (FQDN)，並指出集區將是單一伺服器集區或多重伺服器集區部署。
    
    您可以選擇 [多重電腦集區]**** 或 [單一電腦集區]****。 如果您計劃要 Persistent Chat Server 集區中有多個 Persistent Chat Server 前端伺服器，請選擇 [前者]。 立即或稍後選擇，這是因為建立單一電腦集區後，稍後便無法新增其他伺服器。 如果您選擇多部電腦集區]，輸入個別 Persistent Chat Server 前端伺服器組成之集區的名稱。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果 Persistent Chat Server role 安裝在 Lync Server 2013&nbsp;Standard Edition server FQDN 必須符合的 Standard Edition server 的 FQDN。

    
    </div>

4.  定義常設聊天室伺服器集區的簡易**顯示名稱**。 自訂用戶端，可以使用的顯示名稱，特別是當有多個 Persistent Chat Server 集區，來區分聊天室。

5.  定義常設聊天室伺服器用來與 Lync Server 前端伺服器進行通訊的連接埠。 預設的連接埠為 5041。

6.  如果您的組織需要規範支援，請選取 [用規範記錄]**** 核取方塊。 如果選擇，Persistent Chat Server 前端伺服器相同的電腦上安裝的常設聊天室伺服器規範服務。 系統會提示您稍後選取 SQL Server 後端伺服器的常設聊天室伺服器規範。

7.  指派 Persistent Chat Server 集區的站台相似性。 選取 [**使用此集區作為預設網站\<SiteName\> ** ] 核取方塊，或若要指定此 Persistent Chat Server 集區作為預設的集區的目前網站或所有網站的 [**使用此集區作為所有網站的預設值**。 Lync 2013 用戶端是用來建立及管理聊天室，與使用者網站相關聯的預設集區會使用會議室架設與管理經驗，讓它可將聊天室建立和管理作業路由傳送至該集區。 這僅適用於當您有多個 Persistent Chat Server 集區部署，而且想要使用 Persistent Chat Server 的會議室架設與管理功能。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以自訂使用常設聊天室伺服器軟體開發套件 (SDK) 的聊天室建立和管理功能。<BR>如需如何設定 SQL Server 備份資料庫進行災害復原的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原</A>。

    
    </div>

8.  定義**SQL 存放區的常設聊天室伺服器 Back End （其中儲存聊天室內容）** 執行下列其中一項：
    
      - 若要使用現有的 SQL Server 資料庫，在下拉式清單中，按一下您想要使用 SQL Server 資料庫的名稱。
    
      - 若要指定新的 SQL Server 資料庫，按一下 [**新增**]，並在 [**定義新 SQL 存放區**，執行下列：
    
    <!-- end list -->
    
      - 在 [ **SQL Server FQDN**] 中，指定您要建立新的 SQL Server 資料庫的 SQL server 的 FQDN。
    
      - 選取 [預設執行個體]**** 使用預設執行個體，或者，若要指定不同的執行個體，請選取 [具名執行個體]****，並指定要使用的執行個體。

9.  如果已啟用規範，請定義的 SQL Server 規範資料庫。
    
    <div>
    

    > [!IMPORTANT]  
    > 如需如何設定高可用性的 Persistent Chat Server 資料庫以及常設聊天室伺服器規範資料庫的 SQL Server 鏡像的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原</A>。

    
    </div>

10. 定義檔案存放區。 檔案存放區是儲存任何上傳至檔案儲存機制的檔案副本所用的資料夾 (例如，儲存張貼於聊天室的檔案附件)。 在多部伺服器 Persistent Chat Server 拓撲，這必須是通用命名慣例 (UNC) 路徑;與單一伺服器 Persistent Chat Server 拓撲，它可以是本機檔案路徑。
    
    若要使用現有的檔案存放區，請執行下列動作：
    
      - 在 [檔案伺服器 FQDN]**** 中，指定您要建立新檔案存放區的檔案存放區 FQDN。
    
      - 在 [檔案共用]**** 中，指定要使用的檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > 您建立的檔案存放區，但是您必須建立檔案存放區中定義的位置才能發行拓撲之前，您可以在拓撲產生器中定義的檔案存放區。

    
    </div>

11. 選取要用來作為下一個躍點此 Persistent Chat Server 集區的前端伺服器集區。 這是將能夠將 Persistent Chat Server 要求路由傳送到此集區的前端伺服器集區。

12. 若要儲存組態，請按一下 [完成]****。 Persistent Chat Server 集區會出現在拓撲產生器伴隨著您特定集區的設定。
    
    若要立即發佈更新過的拓撲後要 Persistent Chat Server，請參閱部署文件中的[發佈 Lync Server 2013 中更新的拓樸](lync-server-2013-publish-the-updated-topology.md)。
    
    <div>
    

    > [!NOTE]  
    > 使用拓撲產生器已經開啟，您可以繼續步驟 3 中<A href="lync-server-2013-publish-the-updated-topology.md">發佈 Lync Server 2013 中更新的拓樸</A>開始發佈更新過的拓撲。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

