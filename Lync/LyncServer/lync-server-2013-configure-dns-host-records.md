---
title: Lync Server 2013： 設定 DNS 主機記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c688d09e1aababd384c28c5a79989fc5d93e69b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>設定 Lync Server 2013 的 DNS 主機記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

要成功完成此程序，必須至少以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

<div>

## <a name="to-configure-dns-host-a-records"></a>設定 DNS 主機 A 記錄

1.  在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。

2.  在您網域的主控台樹狀目錄中，展開 [**正向對應區域**，，然後在要安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。

3.  按一下 **[新增主機 (A 或 AAAA)]**。

4.  按一下 **[名稱]**，然後輸入集區的主機名稱 (網域名稱會從記錄定義所在的區域取得，而不需輸入為 A 記錄的一部分)。

5.  按一下 [ **IP 位址**] 中，輸入虛擬 IP (VIP) 負載平衡器的前端集區。
    
    <div>
    

    > [!IMPORTANT]  
    > 在使用 Director 集區的部署中，簡單 URL 的主機 (A) 記錄應指向 Director 負載平衡器的 VIP。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果您僅部署一個不使用負載平衡器就連線至拓撲的 Enterprise Edition Server 或 Director，或是您部署了一部 Standard Edition Server，請輸入 Enterprise Edition Server、Standard Edition Server 或 Director 的 IP 位址。如果您要在集區中部署多個 Enterprise Edition Server 或 Director，則需要負載平衡器。負載平衡器無法用於 Standard Edition Server。

    
    </div>

6.  按一下 **[新增主機]**，然後按一下 **[確定]**。

7.  如果要建立其他的 A 記錄，請重複步驟 4 和 5。

8.  完成建立所需的所有 A 記錄時，按一下 **[完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

