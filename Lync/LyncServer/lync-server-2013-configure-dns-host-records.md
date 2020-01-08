---
title: Lync Server 2013：設定 DNS 主機記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>為 Lync Server 2013 設定 DNS 主機記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組的成員的身分登入伺服器或網域。

<div>

## <a name="to-configure-dns-host-a-records"></a>設定 DNS 主機 A 記錄

1.  在 [網域名稱系統（DNS）] 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。

2.  在您網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下將安裝 Lync Server 2013 的網域。

3.  按一下 **[新增主機（A 或 AAAA）**]。

4.  按一下 [**名稱**]，輸入該池的主機名稱（功能變數名稱是從定義該記錄的區域中假設，而且不需要輸入為 A 記錄的一部分）。

5.  按一下 [ **IP 位址**]，輸入前端池的負載平衡器虛擬 IP （VIP）。
    
    <div>
    

    > [!IMPORTANT]  
    > 在使用主管池的部署中，簡單 Url 的主機（A）記錄應該指向控制器負載平衡器的 VIP。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果您只部署一個不含負載平衡器即可連線至拓撲的 Enterprise Edition 伺服器或主管，或者如果您部署的是標準版 server，請輸入企業版 server、標準版伺服器或控制器的 IP 位址。 如果您在一個池中部署多個企業版伺服器或控制器，則需要負載平衡器。 負載平衡器不搭配標準版伺服器使用。

    
    </div>

6.  按一下 [**新增主機**]，然後按一下 **[確定]**。

7.  若要建立額外的 A 記錄，請重複步驟4和5。

8.  當您完成建立所需的所有記錄之後，按一下 [**完成**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

