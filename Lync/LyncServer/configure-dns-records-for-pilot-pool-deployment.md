---
title: 為試驗集區部署設定 DNS 記錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: ac28f32d6dc68cbfa23c3c1620a23b67fc182c43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499540"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>為試驗集區部署設定 DNS 記錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

在部署 Lync Server 2013 試驗集區之前，您必須更新 DNS 主機試驗集區的專案。 若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

**設定 DNS 主機 A 記錄**

1.  在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。

2.  在您網域的主控台樹中，展開 [ **正向對應區域**]，然後在將安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。

3.  按一下 **[新增主機 (A 或 AAAA)]**。

4.  依序按一下 [ **名稱**]、[Lync Server 2013 集區的主機名稱] (功能變數名稱會從記錄定義所在的區域來假設，而不需要在 A 記錄) 中輸入。

5.  按一下 [ **IP 位址**]，輸入前端集區的 IP 位址。

6.  按一下 **[新增主機]**，然後按一下 **[確定]**。

7.  完成時，按一下 **[完成]**。

</div>

<span> </span>

</div>

</div>

</div>

