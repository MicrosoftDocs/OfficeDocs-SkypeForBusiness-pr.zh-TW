---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a88712d68418b6c4144c67b6583f2451fb7e10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

舊版的 Lync Server 和 Office Communications Server 提供可延伸訊息和目前狀態通訊協定 (XMPP) 閘道，可以部署為不同的伺服器角色，以允許與 XMPP 部署同盟。 Lync Server 2013 中的 XMPP 功能可以部署為功能。 XMPP 功能安裝在兩個部分： 為 Lync Server 2013 Edge Server 執行 XMPP proxy 及 XMPP 閘道在 Lync Server 2013 前端伺服器上執行。

移轉的觀點而言，Lync Server 使用者帳戶可以移至 Lync Server 2013 集區，並繼續使用舊版 XMPP 閘道。 只有當 Lync Server 2013 中沒有設定 XMPP 同盟協力廠商時，這是可能。

在 [摘要] 中，如果已部署 Lync Server 2010 與 Office Communications Server 2007 R2 XMPP 閘道和舊版的 Lync Server 2010 使用者，將 XMPP 同盟移轉至 Lync Server 2013 已啟用 XMPP 同盟：

1.  部署 Lync Server 2013 集區。

2.  部署 Lync Server 2013 Edge server。

3.  將所有使用者都移至 Lync Server 2013 集區

4.  建立適用於 Edge Server 的 XMPP 存取原則及憑證。

5.  啟用 Lync Server 2013 中的 XMPP 同盟。 

6.  更新以指到 Lync Server 2013 XMPP 閘道的 DNS 項目。

</div>

<span> </span>

</div>

</div>

</div>

