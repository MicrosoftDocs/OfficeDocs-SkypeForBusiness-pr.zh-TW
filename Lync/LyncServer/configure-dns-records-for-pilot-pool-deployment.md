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
ms.openlocfilehash: 9014581901a80507e088a6eb1804fdfccaea0215
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>設定試驗集區部署的 DNS 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

在部署 Lync Server 2013 試驗池之前，您必須更新 DNS 主機以取得試驗池的專案。 若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。

**設定 DNS 主機 A 記錄**

1.  在 [網域名稱系統（DNS）] 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。

2.  在您網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下將安裝 Lync Server 2013 的網域。

3.  按一下 **[新增主機（A 或 AAAA）**]。

4.  按一下 [**名稱**]，輸入 Lync Server 2013 池的主機名稱（功能變數名稱是來自訂該記錄的區域，而且不需要輸入為 A 記錄的一部分）。

5.  按一下 [ **IP 位址**]，輸入頂層端池的 IP 位址。

6.  按一下 [**新增主機**]，然後按一下 **[確定]**。

7.  完成後，請按一下 [**完成**]。

</div>

<span> </span>

</div>

</div>

</div>

