---
title: Lync Server 2013：在拓撲中定義選用的 Director 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53512d2d3c0bd99c4d5b23d20f21859ec974415
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504570"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>在您的拓撲中為 Lync Server 2013 定義選用的 Director 拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

Lync Server 2013 Director 可以是單一實例伺服器，也可以以多個 Director 的負載平衡集區形式進行安裝，以獲得較高的可用性和容量。 支援硬體負載平衡和網域名稱系統 (DNS) 負載平衡。 本主題說明如何設定 Director 集區的 DNS 負載平衡。

若要在您新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 **RTCUniversalServerAdmins** 和 **Domain Admins** 群組成員的使用者身分登入。 您也可以委派適當的系統管理員權力，以加入伺服器角色。 如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署檔中的 [Lync server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md) 。 針對其他設定變更，只需要 **RTCUniversalServerAdmins** 群組中的成員資格。

本主題說明為兩個 Director 拓撲定義及發行拓撲的步驟：

  - 若要定義 Director (單一實例) 

  - 若要定義 Director (多個 Director 集區) 

<div>

## <a name="to-define-the-director-single-instance"></a>若要定義 Director (單一實例) 

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [歡迎] 頁面上，按一下 [ **從現有的部署下載拓撲**]。

3.  在 [ **另存拓撲** ] 對話方塊中，輸入現有拓撲的本機複本名稱和位置，然後按一下 [ **儲存**]。

4.  展開您計畫加入 Director 的網站，以滑鼠右鍵按一下 [ **Director**集區]，然後按一下 [ **新增 director 集**區]。

5.  在 [ **定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：
    
      - 在 [ **集區 FQDN**] 中，輸入 Director 集區的 FQDN。
    
      - 按一下 **[單一電腦集區]**，然後按 **[下一步]**。

6.  在 [ **定義檔案共用** ] 對話方塊中，執行下列其中一項操作：
    
    1.  若要使用現有的檔案共用，請按一下 [ **使用先前定義的檔案共用**]，然後從清單中選取檔案共用，然後按 **[下一步]**。
    
    2.  若要建立新的檔案共用，請按一下 [ **定義新的檔案共用**]，並在 [ **檔案伺服器 FQDN**] 中輸入檔案共用位置的 FQDN，在 [檔案 **共用**] 中輸入共用的名稱，然後按 **[下一步]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在此步驟中所指定或建立的檔案共用，必須存在或在發佈拓撲之前建立。<BR>指派給 Director 的檔案共用實際上並未使用，因此您可以指派組織中任何集區的檔案共用。

    
    </div>

7.  在 [ **指定 Web 服務 URL** ] 對話方塊的 [ **外部基礎 URL**] 中，指定 director 的 FQDN，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 此名稱必須可從網際網路 DNS 伺服器解析，並指向反向 proxy 的公用 IP 位址，該位址會偵聽該 URL 的 HTTP/HTTPS 要求，並將其代理至該 Director 上的外部 Web 服務虛擬目錄。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。 如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。

    
    </div>

8.  發行拓撲。

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>若要定義 Director (多個 Director 集區) 

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [歡迎] 頁面上，按一下 [ **從現有的部署下載拓撲**]。

3.  在 [ **另存拓撲** ] 對話方塊中，輸入現有拓撲的本機複本名稱和位置，然後按一下 [ **儲存**]。

4.  展開您計畫加入 Director 的網站，以滑鼠右鍵按一下 [ **Director**集區]，然後按一下 [ **新增 director 集**區]。

5.  在 [ **定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：
    
      - 在 [ **集區 FQDN**] 中，輸入 Director 集區的 FQDN。
    
      - 按一下 [多部電腦集區]****，然後按 [下一步]****。

6.  在 [ **定義此集區中的電腦** ] 對話方塊中，執行下列動作：
    
      - 指定第一個集區成員的電腦 FQDN，然後按一下 [ **新增**]。
    
      - 針對您要新增的每一部電腦重複上述步驟。 完成後，請按 **[下一步]**。

7.  在 [ **定義檔案共用** ] 對話方塊中，執行下列其中一項操作：
    
      - 若要使用現有的檔案共用，請按一下 [ **使用先前定義的檔案共用**]，然後從清單中選取檔案共用，然後按 **[下一步]**。
    
      - 若要建立新的檔案共用，請按一下 [ **定義新的檔案共用**]，並在 [ **檔案伺服器 FQDN**] 中輸入檔案共用位置的 FQDN，在 [檔案 **共用**] 中輸入共用的名稱，然後按 **[下一步]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在此步驟中所指定或建立的檔案共用，必須存在或在發佈拓撲之前建立。<BR>指派給 Director 的檔案共用實際上並未使用，因此您可以指派組織中任何集區的檔案共用。

    
    </div>

8.  在 [ **指定 Web 服務 URL** ] 對話方塊的 [ **外部基礎 URL**] 中，指定 director 的 FQDN，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 此名稱必須可從網際網路 DNS 伺服器解析，並指向反向 proxy 的公用 IP 位址，該位址會偵聽傳送至該 URL 的 HTTP/HTTPS 要求，並將其代理至該 Director 集區上的外部 Web 服務虛擬目錄。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。 如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。

    
    </div>

9.  發行拓撲。

</div>

</div>

<span> </span>

</div>

</div>

</div>

