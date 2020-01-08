---
title: Lync Server 2013：在拓撲中定義選用的 Director 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>針對 Lync Server 2013 在拓撲中定義選用的 Director 拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

Lync Server 2013 控制器可以是單一實例伺服器，也可以安裝為多個控制器的負載平衡池，以獲得較高的可用性和容量。 支援硬體負載平衡和網域名稱系統（DNS）負載平衡。 本主題說明如何針對控制器池設定 DNS 負載平衡。

若要在您新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以**RTCUniversalServerAdmins**和**網域系統管理員**群組成員的使用者身分登入。 您也可以委派適當的管理員權力和許可權，以新增伺服器角色。 如需詳細資訊，請參閱在標準版 server 或 Enterprise Edition server 部署檔中的[Lync Server 2013 委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 針對其他設定變更，只需要**RTCUniversalServerAdmins**群組中的成員資格。

本主題描述定義及發佈兩個控制器拓朴拓撲的步驟：

  - 定義主管（單一實例）

  - 定義主管（多個控制器池）

<div>

## <a name="to-define-the-director-single-instance"></a>定義主管（單一實例）

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 [歡迎] 頁面上，按一下 [**從現有的部署下載拓撲**。

3.  在 [**另存拓朴為**] 對話方塊中，輸入現有拓朴之本機複本的名稱和位置，然後按一下 [**儲存**]。

4.  展開您要新增主管的網站，以滑鼠右鍵按一下 [**控制器池**]，然後按一下 [**新增控制器池**]。

5.  在 [**定義控制器池 FQDN** ] 對話方塊中，執行下列動作：
    
      - 在 [**池 FQDN**] 中，輸入控制器池的 FQDN。
    
      - 按一下 [**單一電腦池**]，然後按一下 **[下一步]**。

6.  在 [**定義檔案共用**] 對話方塊中，執行下列其中一項操作：
    
    1.  若要使用現有的檔案共用，請按一下 [**使用先前定義**的檔案共用]，從清單中選取檔案共用，然後按 **[下一步]**。
    
    2.  若要建立新的檔案共用，請按一下 [**定義新的檔案共用**]，在 [檔案**伺服器 FQDN**] 中輸入檔案共用位置的 FQDN，在 [檔案**共用**] 中輸入共用的名稱，然後按 **[下一步]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在此步驟中指定或建立的檔案共用，必須存在，或必須在發佈拓撲之前建立。<BR>指派給主管的檔案共用並未實際使用，所以您可以指派組織中任何文件庫的檔案共用。

    
    </div>

7.  在 [**指定 Web 服務 URL** ] 對話方塊的 [**外部基本 URL**] 中，指定控制器的 FQDN，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 此名稱必須可從網際網路 DNS 伺服器解析，並指向反向 proxy 的公用 IP 位址，這會偵聽該 URL 的 HTTP/HTTPS 要求，並將其代理到該導向中的外部 Web 服務虛擬目錄。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。 如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。

    
    </div>

8.  發佈拓撲。

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>定義主管（多個控制器池）

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 [歡迎] 頁面上，按一下 [**從現有的部署下載拓撲**。

3.  在 [**另存拓朴為**] 對話方塊中，輸入現有拓朴之本機複本的名稱和位置，然後按一下 [**儲存**]。

4.  展開您要新增主管的網站，以滑鼠右鍵按一下 [**控制器池**]，然後按一下 [**新增控制器池**]。

5.  在 [**定義控制器池 FQDN** ] 對話方塊中，執行下列動作：
    
      - 在 [**池 FQDN**] 中，輸入控制器池的 FQDN。
    
      - 按一下 [**多個電腦池**]，然後按一下 **[下一步]**。

6.  在 [**定義此池中的電腦**] 對話方塊中，執行下列動作：
    
      - 指定第一個池成員的電腦 FQDN，然後按一下 [**新增**]。
    
      - 針對您要新增的每個電腦，重複上一個步驟。 完成後，請按 **[下一步]**。

7.  在 [**定義檔案共用**] 對話方塊中，執行下列其中一項操作：
    
      - 若要使用現有的檔案共用，請按一下 [**使用先前定義**的檔案共用]，從清單中選取檔案共用，然後按 **[下一步]**。
    
      - 若要建立新的檔案共用，請按一下 [**定義新的檔案共用**]，在 [檔案**伺服器 FQDN**] 中輸入檔案共用位置的 FQDN，在 [檔案**共用**] 中輸入共用的名稱，然後按 **[下一步]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在此步驟中指定或建立的檔案共用，必須存在，或必須在發佈拓撲之前建立。<BR>指派給主管的檔案共用並未實際使用，所以您可以指派組織中任何文件庫的檔案共用。

    
    </div>

8.  在 [**指定 Web 服務 URL** ] 對話方塊的 [**外部基本 URL**] 中，指定控制器的 FQDN，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 該名稱必須可從網際網路 DNS 伺服器解析，並指向反向 proxy 的公用 IP 位址，這會偵聽傳送至該 URL 的 HTTP/HTTPS 要求，並將其代理到該導向池中的外部 Web 服務虛擬目錄。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。 如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。

    
    </div>

9.  發佈拓撲。

</div>

</div>

<span> </span>

</div>

</div>

</div>

