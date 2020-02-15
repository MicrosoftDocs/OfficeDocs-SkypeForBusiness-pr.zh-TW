---
title: 設定試驗集區部署的 DNS 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3b1f4b507887bc046cefddae9c924f0de1916b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41999118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>設定試驗集區部署的 DNS 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-29_

之前部署 Lync Server 2013 試驗集區，您必須更新試驗集區的 DNS 主機的項目。 若要順利完成此程序，您應該伺服器或網域的 Domain Admins 群組成員或 DnsAdmins 群組成員登入。

**設定 DNS 主機 A 記錄**

1.  在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。

2.  在您網域的主控台樹狀目錄中，展開 [**正向對應區域**，，然後在要安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。

3.  按一下 **[新增主機 (A 或 AAAA)]**。

4.  按一下 [**名稱**]，輸入 （網域會假設該名稱的區域來記錄中所定義，而不需輸入為 A 記錄的一部分） 的 Lync Server 2013 集區的主機名稱。

5.  按一下 [ **IP 位址**] 中，輸入前端集區的 IP 位址。

6.  按一下 **[新增主機]**，然後按一下 **[確定]**。

7.  完成時，按一下 **[完成]**。

</div>

<span> </span>

</div>

</div>

</div>

