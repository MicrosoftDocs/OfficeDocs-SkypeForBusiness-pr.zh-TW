---
title: Lync Server 2013：設定 DNS 以進行負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831968516ef155d6ad018f33bfa27226f58292dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537140"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>在 Lync Server 2013 中設定 DNS 以進行負載平衡

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

網域名稱系統 (DNS) 負載平衡會平衡 Lync Server 2013 特有的網路流量，例如 SIP 流量和媒體流量。 前端集區、Edge 集區、Director 集區和獨立中繼集區支援 DNS 負載平衡。 設定為使用 DNS 負載平衡的集區必須有兩個完全合格的功能變數名稱 (Fqdn) 定義： DNS 負載平衡所使用的一般集區 FQDN (例如，pool1.contoso.com) ，且解析為集區中伺服器的實體 Ip，以及集區 Web 服務的另一個 FQDN (例如，web1.contoso.net) ，可解析為集區的虛擬 IP 位址。 如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md) 。

<div>


> [!NOTE]  
> 用戶端到伺服器的 HTTPS 流量仍需要硬體負載平衡。



</div>

您必須先進行下列步驟，才能使用 DNS 負載平衡：

1.  覆寫內部 Web 服務集區 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。

    
    </div>

2.  建立 DNS A 主機記錄，以便將集區 FQDN 解析為集區中所有伺服器的 IP 位址。

3.  啟用 IP 位址隨機化，或針對 Windows Server DNS 啟用循環配置資源。
    
    <div>
    

    > [!NOTE]  
    > 預設應啟用循環配置資源。

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>覆寫內部 Web 服務 FQDN

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  從主控台樹狀目錄展開 Enterprise Edition 前端集區節點。

3.  以滑鼠右鍵按一下集區、按一下 **[編輯內容]**，然後按一下 **[Web 服務]**。

4.  在 **[內部 Web 服務]** 下方，選取 **[覆寫 FQDN]** 核取方塊。

5.  輸入用於解析為集區伺服器之實體 IP 位址的集區 FQDN。

6.  在 **[外部 Web 服務]** 下方，輸入用於解析為集區虛擬 IP 位址的外部集區 FQDN，然後按一下 **[確定]**。

7.  在主控台樹中，按一下 [ **Lync Server 2013**]，然後在 [ **動作** ] 窗格中，按一下 [ **發行拓撲**]。

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>建立所有內部集區伺服器的 DNS 主機 (A) 記錄

1.  依序按一下 **[開始]**、**[所有程式]**、**[系統管理工具]** 和 **[DNS]**。

2.  在 **[DNS 管理員]** 中，按一下管理記錄的 DNS 伺服器，將其展開。

3.  按一下 **[正向對應區域]** 將其展開。

4.  以滑鼠右鍵按一下您要新增記錄的 DNS 網域，然後按一下 **[新增主機 (A 或 AAAA)]**。

5.  在 [ **名稱** ] 方塊中，輸入主機記錄的名稱 (功能變數名稱將會自動附加) 中。

6.  在 [IP 位址] 方塊中，輸入個別前端伺服器的 IP 位址，然後選取 **[建立關聯的指標 (PTR) 記錄]** 或 **[允許已驗證的使用者更新相同擁有者名稱的 DNS 記錄]** (如果適用的話)。

7.  繼續為其他將參與 DNS 負載平衡的所有成員前端伺服器建立記錄。
    
    例如，如果您有個名為 pool1.contoso.com 的集區以及三個前端伺服器，您可以建立下列 DNS 項目：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>Type (類型)</th>
    <th>Data (資料)</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主機 (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主機 (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主機 (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    如需建立 DNS 主機 () 記錄的詳細資訊，請參閱 [設定 Lync Server 2013 的 Dns 主機記錄](lync-server-2013-configure-dns-host-records.md)。

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>啟用 Windows Server 的循環配置資源

1.  依序按一下 **[開始]**、**[所有程式]**、**[系統管理工具]** 和 **[DNS]**。

2.  展開 **[DNS]**，以滑鼠右鍵按一下您要設定的 DNS 伺服器，然後按一下 **[內容]**。

3.  按一下 **[進階]** 索引標籤，選取 **[啟用循環配置資源]** 和 **[啟用網路遮罩次序]**，然後按一下 **[確定]**。
    
    ![[DNS 迴圈複用] 對話方塊](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "[DNS 迴圈複用] 對話方塊")

<div>


> [!NOTE]  
> 預設應啟用此功能。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

