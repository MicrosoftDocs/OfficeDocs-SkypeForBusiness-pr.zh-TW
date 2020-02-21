---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c744b22941c47d94de0685074c65f6d95abea56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10-16_

舊版 Office Communications Server 提供可延伸訊息與顯示狀態通訊協定 (XMPP) 閘道，可以部署為不同的伺服器角色，以允許與 XMPP 部署同盟。 Lync Server 2013 中的 XMPP 功能可以部署為功能。 XMPP 功能安裝在兩個部分： 為 Lync Server 2013 Edge Server 執行 XMPP proxy 及 XMPP 閘道在 Lync Server 2013 前端伺服器上執行。

移轉的觀點而言，Office Communications Server 2007 R2 使用者帳戶可以移至 Lync Server 2013 集區，並繼續使用 Office Communications Server 2007 R2 XMPP 閘道。 只有當 Lync Server 2013 中沒有設定 XMPP 同盟協力廠商時，這是可能。

在 [摘要] 中，如果已部署 Office Communications Server 與 Office Communications Server 2007 R2 XMPP 閘道與舊版 Office Communications Server 2007 R2 使用者，將 XMPP 同盟移轉至 Lync Server 2013 已啟用 XMPP 同盟：

1.  部署 Lync Server 2013 集區。

2.  部署 Lync Server 2013 Edge server。

3.  將所有使用者都移至 Lync Server 2013 集區。

4.  建立適用於 Edge Server 的 XMPP 存取原則及憑證。

5.  啟用 Lync Server 2013 中的 XMPP 同盟。 

6.  更新以指到 Lync Server 2013 XMPP 閘道的 DNS 項目。

</div>

<span> </span>

</div>

</div>

</div>

