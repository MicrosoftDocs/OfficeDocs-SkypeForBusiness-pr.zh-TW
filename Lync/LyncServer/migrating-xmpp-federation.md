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
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和目前狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署進行聯盟。 在 Lync Server 2013 中，您可以將 XMPP 功能部署為功能。 XMPP 功能已安裝于兩個部分：作為在 Lync Server 2013 Edge 伺服器上執行的 XMPP proxy，以及在 Lync Server 2013 前端伺服器上執行的 XMPP 閘道。

從遷移的角度來看，Lync Server 使用者帳戶可以移至 Lync Server 2013 池中，並繼續使用舊版 XMPP 閘道。 只有在 Lync Server 2013 沒有設定 XMPP 聯盟夥伴時，才能這麼做。

總之，如果已使用 Office 通訊伺服器 2007 R2 XMPP 閘道部署 Lync Server 2010，且已為舊版 Lync Server 2010 使用者啟用 XMPP 聯盟，請將 XMPP 同盟遷移至 Lync Server 2013：

1.  部署 Lync Server 2013 文件庫。

2.  部署 Lync Server 2013 Edge 伺服器。

3.  將所有使用者移至 Lync Server 2013 池

4.  建立邊緣伺服器的 XMPP 存取原則和憑證。

5.  在 Lync Server 2013 中啟用 XMPP 同盟。 

6.  更新 DNS 專案以指向 Lync Server 2013 XMPP 閘道。

</div>

<span> </span>

</div>

</div>

</div>

