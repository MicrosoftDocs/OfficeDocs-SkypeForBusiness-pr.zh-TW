---
title: Lync Server 2013：設定 DNS 負載平衡
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
ms.openlocfilehash: f5b68bf226c71d65835791577ab9a45f18b2a10e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>在 Lync Server 2013 中設定 DNS 負載平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

若要成功完成此程式，您必須以網域管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。

網域名稱系統（DNS）負載平衡會平衡 Lync Server 2013 （例如 SIP 流量及媒體流量）獨有的網路流量。 前端池、邊緣池、控制器池和獨立的轉送池都支援 DNS 負載平衡。 設定為使用 DNS 負載平衡的池必須有兩個完整的功能變數名稱（Fqdn）：由 DNS 負載平衡所使用的一般池 FQDN （例如 pool1.contoso.com），並解析為池中伺服器的實際 Ip以及池的 Web 服務（例如，web1.contoso.net）的另一個 FQDN，可解析為該池的虛擬 IP 位址。 如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。

<div>


> [!NOTE]  
> 用戶端到伺服器 HTTPS 流量仍需要硬體負載平衡。



</div>

在您可以使用 DNS 負載平衡之前，您必須執行下列動作：

1.  覆寫內部 Web 服務池 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。

    
    </div>

2.  建立 DNS 主機記錄，以將池 FQDN 解析成池中所有伺服器的 IP 位址。

3.  啟用 IP 位址隨機化，或針對 Windows Server DNS 啟用迴圈複用。
    
    <div>
    

    > [!NOTE]  
    > 預設會啟用迴圈複用。

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>覆寫內部 Web 服務 FQDN

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  從主控台樹中，展開 [企業版前端池] 節點。

3.  以滑鼠右鍵按一下該池，按一下 [**編輯屬性**]，然後按一下 [ **Web 服務**]。

4.  在 [**內部 web 服務**] 底下，選取 [覆**寫 FQDN** ] 核取方塊。

5.  輸入可解析為池中伺服器之物理 IP 位址的 [池 FQDN]。

6.  在 [**外部 web 服務**] 底下，輸入可解析為該池之虛擬 IP 位址的外部池 FQDN，然後按一下 **[確定]**。

7.  在主控台樹中，按一下 [ **Lync Server 2013**]，然後在 [**動作**] 窗格中，按一下 [**發佈拓撲**]。

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>若要建立所有內部池伺服器的 DNS 主機（A）記錄

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。

2.  在 [ **Dns 管理員**] 中，按一下記錄管理的 DNS 伺服器加以展開。

3.  按一下 [**轉寄查閱區域**] 將它展開。

4.  以滑鼠右鍵按一下您需要新增記錄的 DNS 網域，然後按一下 **[新增主機（A 或 AAAA）**]。

5.  在 [**名稱**] 方塊中，輸入主機記錄的名稱（將會自動附加功能變數名稱）。

6.  在 [IP 位址] 方塊中，輸入個別前端伺服器的 IP 位址，然後選取 [**建立相關的指標（PTR）記錄**] 或 **[允許任何經過驗證的使用者使用相同的擁有者名稱來更新 DNS 記錄**] （如果適用的話）。

7.  針對將參與 DNS 負載平衡的所有成員前端伺服器，繼續建立記錄。
    
    例如，如果您有一個名為 pool1.contoso.com 和三個前端伺服器的池，您會建立下列 DNS 專案：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>稱</th>
    <th>類型</th>
    <th>資料</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主機（A）</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主機（A）</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主機（A）</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    如需建立 DNS 主機（A）記錄的詳細資料，請參閱[設定 Lync Server 2013 的 DNS 主機記錄](lync-server-2013-configure-dns-host-records.md)。

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>若要啟用 Windows Server 的迴圈複用

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。

2.  展開 [ **DNS**]，以滑鼠右鍵按一下您要設定的 DNS 伺服器，然後按一下 [**屬性**]。

3.  按一下 [**高級**] 索引標籤，選取 [**啟用迴圈複用**並**啟用網路遮罩排序**]，然後按一下 **[確定]**。
    
    ![DNS 循環配置資源對話方塊](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS 循環配置資源對話方塊")

<div>


> [!NOTE]  
> 預設會啟用此功能。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

