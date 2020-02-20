---
title: Lync Server 2013： 在您的拓撲中定義選用的 Director 拓撲
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
ms.openlocfilehash: a07bf43552066260d55c8f5461a091d41732e46c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Lync Server 2013 的拓撲中定義選用的 Director 拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

Lync Server 2013 Director 可以為單一執行個體的伺服器，或將它們安裝為高可用性和容量的多個 Director 負載平衡集區。 支援的硬體負載平衡和網域名稱系統 (DNS) 負載平衡。 本主題說明如何設定 DNS 負載平衡的 Director 集區。

若要成功發佈、 啟用或停用拓樸，當您新增或移除伺服器角色，您應該是 [ **RTCUniversalServerAdmins** ] 和 [ **Domain Admins**群組成員的使用者身分登入。 您也可以委派適當的系統管理員權限和權限新增伺服器角色。 如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署文件中的[Lync Server 2013 中的委派設定權限](lync-server-2013-delegate-setup-permissions.md)。 變更其他設定，只能**以 RTCUniversalServerAdmins**群組的成員資格的必要。

本主題說明的步驟來定義並發行兩個 Director 拓撲的拓撲：

  - 若要定義 Director （單一執行個體）

  - 若要定義 Director （多個 Director 集區）

<div>

## <a name="to-define-the-director-single-instance"></a>若要定義 Director （單一執行個體）

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在 [歡迎] 頁面上，按一下 [**從現有部署下載拓撲**]。

3.  在 [**另存拓撲**] 對話方塊中，輸入的名稱和位置的現有拓撲中的本機複本，然後按一下 [**儲存**。

4.  展開您要新增 Director，以滑鼠右鍵按一下 [ **Director 集區**，然後按一下 [**新增 Director 集區**的網站。

5.  在 [**定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：
    
      - 在 [**集區 FQDN**] 中，輸入 Director 集區的 FQDN。
    
      - 按一下 **[單一電腦集區]**，然後按 **[下一步]**。

6.  在 [**定義檔案共用**] 對話方塊中，執行下列其中一項：
    
    1.  若要使用現有的檔案共用，請按一下 [**使用先前定義的檔案共用**，從清單中選取檔案共用，然後按一下 [**下一步**。
    
    2.  若要建立新的檔案共用，按一下 [**定義新的檔案共用**中**檔案伺服器 FQDN**] 中，輸入檔案共用之位置的 FQDN 中**檔案共用**，請輸入共用的名稱，然後按 [**下一步**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您指定，或在此步驟中建立的檔案共用必須存在於或建立之前發行的拓撲。<BR>指派給 Director 的檔案共用實際上不會使用，因此您可以指派組織中任何集區的檔案共用。

    
    </div>

7.  在 [**指定 Web 服務 URL** ] 對話方塊，在 [**外部基底 URL**] 中，指定 Director 的 FQDN，然後按一下 [**完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 名稱必須可以解析為反向 proxy 會接聽該 URL 和 proxy 的 HTTP/HTTPS 要求他們至 Director 上的外部 Web 服務虛擬目錄的公用 IP 位址從網際網路 DNS 伺服器和點。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有一個以上的前端集區或前端伺服器的外部 Web 服務 FQDN 必須是唯一的。 例如，如果您定義的外部 Web 服務的前端伺服器 FQDN 為<STRONG>pool01.contoso.com</STRONG>，您無法使用<STRONG>pool01.contoso.com</STRONG>另一個前端集區或前端伺服器。 如果您也要部署 Director、 外部 Web 服務 FQDN 定義任何 director 或 Director 集區必須是唯一的任何其他 Director 集區也為任何前端集區或前端伺服器。 如果決定要覆寫內部 web 服務以自我定義的 FQDN、 每個 FQDN 都必須是唯一因任何其他的前端集區、 Director 或 Director 集區。

    
    </div>

8.  發行拓撲。

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>若要定義 Director （多個 Director 集區）

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在 [歡迎] 頁面上，按一下 [**從現有部署下載拓撲**]。

3.  在 [**另存拓撲**] 對話方塊中，輸入的名稱和位置的現有拓撲中的本機複本，然後按一下 [**儲存**。

4.  展開您要新增 Director，以滑鼠右鍵按一下 [ **Director 集區**，然後按一下 [**新增 Director 集區**的網站。

5.  在 [**定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：
    
      - 在 [**集區 FQDN**] 中，輸入 Director 集區的 FQDN。
    
      - 按一下 [多部電腦集區]****，然後按 [下一步]****。

6.  在 [**定義此集區中的電腦**] 對話方塊中，執行下列動作：
    
      - 指定第一個集區成員的電腦 FQDN，然後按一下 [**新增]**。
    
      - 重複上述步驟，為每個您想要新增的電腦。 完成後，請按 **[下一步]**。

7.  在 [**定義檔案共用**] 對話方塊中，執行下列其中一項：
    
      - 若要使用現有的檔案共用，請按一下 [**使用先前定義的檔案共用**，從清單中選取檔案共用，然後按一下 [**下一步**。
    
      - 若要建立新的檔案共用，按一下 [**定義新的檔案共用**中**檔案伺服器 FQDN**] 中，輸入檔案共用之位置的 FQDN 中**檔案共用**，請輸入共用的名稱，然後按 [**下一步**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您指定，或在此步驟中建立的檔案共用必須存在於或建立之前發行的拓撲。<BR>指派給 Director 的檔案共用實際上不會使用，因此您可以指派組織中任何集區的檔案共用。

    
    </div>

8.  在 [**指定 Web 服務 URL** ] 對話方塊，在 [**外部基底 URL**] 中，指定 Director 的 FQDN，然後按一下 [**完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 名稱必須可以解析為反向 proxy 會接聽傳送至該 URL 及 proxy 它們以該 Director 集區上的外部 Web 服務虛擬目錄的 HTTP/HTTPS 要求的公用 IP 位址從網際網路 DNS 伺服器和點。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有一個以上的前端集區或前端伺服器的外部 Web 服務 FQDN 必須是唯一的。 例如，如果您定義的外部 Web 服務的前端伺服器 FQDN 為<STRONG>pool01.contoso.com</STRONG>，您無法使用<STRONG>pool01.contoso.com</STRONG>另一個前端集區或前端伺服器。 如果您也要部署 Director、 外部 Web 服務 FQDN 定義任何 director 或 Director 集區必須是唯一的任何其他 Director 集區也為任何前端集區或前端伺服器。 如果決定要覆寫內部 web 服務以自我定義的 FQDN、 每個 FQDN 都必須是唯一因任何其他的前端集區、 Director 或 Director 集區。

    
    </div>

9.  發行拓撲。

</div>

</div>

<span> </span>

</div>

</div>

</div>

