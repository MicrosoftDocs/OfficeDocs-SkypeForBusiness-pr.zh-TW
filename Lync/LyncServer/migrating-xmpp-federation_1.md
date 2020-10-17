---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716e3c5eebf365118e795d584f7c9e73f949cf9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527320"
---
# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

舊版 Office 通訊伺服器提供可擴展的訊息和顯示狀態通訊協定 (XMPP) 閘道，可部署為個別的伺服器角色，以允許與 XMPP 部署的聯盟。 在 Lync Server 2013 中，可以將 XMPP 功能部署為功能。 XMPP 功能是以兩個部分安裝：作為在 Lync Server 2013 Edge Server 上執行的 XMPP proxy，以及在 Lync Server 2013 前端伺服器上執行的 XMPP 閘道。

從遷移的角度來看，Office 通訊伺服器 2007 R2 使用者帳戶可以移至 Lync Server 2013 集區，並繼續使用 Office 通訊伺服器 2007 R2 XMPP 閘道。 只有在 Lync Server 2013 中未設定 XMPP 同盟合作者時，才可以這麼做。

總而言之，如果 Office 通訊伺服器已與 Office 通訊伺服器 2007 R2 XMPP 閘道搭配使用，且已為舊版 Office 通訊伺服器 2007 R2 使用者啟用 XMPP 同盟，請將 XMPP 同盟遷移至 Lync Server 2013：

1.  部署 Lync Server 2013 集區。

2.  部署 Lync Server 2013 Edge server。

3.  將所有使用者移至 Lync Server 2013 集區。

4.  建立適用於 Edge Server 的 XMPP 存取原則及憑證。

5.  在 Lync Server 2013 中啟用 XMPP 同盟。 

6.  更新 DNS 專案以指向 Lync Server 2013 XMPP 閘道。

</div>

<span> </span>

</div>

</div>

</div>

