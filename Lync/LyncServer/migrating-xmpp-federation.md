---
title: 移轉 XMPP 同盟
description: 遷移 XMPP 同盟。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543209"
---
# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和顯示狀態通訊協定 (XMPP) 閘道，可部署為個別的伺服器角色，以允許與 XMPP 部署同盟。 在 Lync Server 2013 中，可以將 XMPP 功能部署為功能。 XMPP 功能是以兩個部分安裝：作為在 Lync Server 2013 Edge Server 上執行的 XMPP proxy，以及在 Lync Server 2013 前端伺服器上執行的 XMPP 閘道。

從遷移的角度來看，Lync Server 使用者帳戶可以移至 Lync Server 2013 集區，並繼續使用舊版的 XMPP 閘道。 只有在 Lync Server 2013 中未設定 XMPP 同盟合作者時，才可以這麼做。

總而言之，如果已使用 Office 通訊伺服器 2007 R2 XMPP 閘道部署 Lync Server 2010，且已為舊版 Lync Server 2010 使用者啟用 XMPP 同盟，請將 XMPP 同盟遷移至 Lync Server 2013：

1.  部署 Lync Server 2013 集區。

2.  部署 Lync Server 2013 Edge server。

3.  將所有使用者移至 Lync Server 2013 集區

4.  建立適用於 Edge Server 的 XMPP 存取原則及憑證。

5.  在 Lync Server 2013 中啟用 XMPP 同盟。 

6.  更新 DNS 專案以指向 Lync Server 2013 XMPP 閘道。

</div>

<span> </span>

</div>

</div>

</div>

